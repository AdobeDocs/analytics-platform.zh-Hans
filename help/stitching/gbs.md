---
title: 基于图形的拼合
description: 基于图形的拼合说明
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: ea5c9114-1fc3-4686-b184-2850acb42b5c
source-git-commit: c4aea74807be15af56413522d9e6fbf5f18a37a0
workflow-type: tm+mt
source-wordcount: '1553'
ht-degree: 7%

---

# 基于图形的拼合


在基于图形的拼合中，您可以指定事件数据集，以及该数据集的永久ID (Cookie)和临时ID（人员ID）的命名空间。 基于图形的拼合会在新拼合的数据集中为拼合的ID创建新列。 然后，使用持久ID使用指定的命名空间从Experience Platform Identity Service查询身份图以更新拼合的ID。

>[!NOTE]
>
>您必须确保为Identity Service[启用数据集](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service)。
>


![基于图形的拼合](/help/stitching/assets/gbs.png)

## Identitymap

基于图形的拼接支持在以下情况下使用[`identityMap`字段组](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/schema/composition#identity)：

- 在`identityMap`命名空间中使用主标识来定义persistentID：
   - 如果在不同的命名空间中找到多个主身份，则命名空间中的身份按词法排序并选择第一个身份。
   - 如果在单个命名空间中找到多个主身份，则选择第一个词典学上可用的主身份。

  在以下示例中，命名空间和身份将生成排序的主身份列表，最后生成选定的身份。

  <table style="table-layout:auto">
     <tr>
       <th>命名空间</th>
       <th>身份列表</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>&nbsp;]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>已排序的标识列表</th>
      <th>选定的身份</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>PrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-2", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-1", "namespace": "ECID"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "namespace": "ECID"}<br/>]<br/>NonPrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-1", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-3", "namespace": "ECID"}<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ccid-2",<br/>"namespace": "CCID"</code></pre></td>
    </tr>
  </table>

- 使用`identityMap`命名空间定义persistentID：
   - 如果在`identityMap`命名空间中找到persistentID的多个值，则使用第一个词典学上的可用标识。

  在以下示例中，您已选择ECID作为要使用的命名空间。 该选择导致排序的标识列表，以及最终选择的标识。

  <table style="table-layout:auto">
     <tr>
       <th>命名空间</th>
       <th>身份列表</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>已排序的标识列表</th>
      <th>选定的身份</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;"id": "ecid-1",<br/>&nbsp;&nbsp;"id": "ecid-2",<br/>&nbsp;&nbsp;"id": "ecid-3"<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ecid-1",<br/>"namespace": "ECID"</code></pre></td>
    </tr>
  </table>


## 基于图形的拼合的工作原理

拼合至少会对给定数据集中的数据执行两次传递。

- **实时拼接**：尝试在每次点击（事件）进入时拼合点击（事件），使用永久ID通过查询标识图查找所选命名空间的临时ID。 如果临时id在查找中可用，则会立即拼合此临时id。

- **重播拼接**： *根据身份图形中更新的身份重播*&#x200B;数据。 在这个阶段，来自先前未知设备（永久ID）的点击会在身份图解析命名空间身份后拼合。 重放由两个参数决定：**频率**&#x200B;和&#x200B;**回看时段**。 Adobe提供以下这些参数的组合：
   - **每日回顾频率**：数据每天重播，回顾时间范围为24小时。 此选项的优势在于重播更频繁，但未经身份验证的访客必须在访问您网站的同一天进行身份验证。
   - **每周回顾频率**：数据每周重播一次，回顾时间为每周一次（请参阅[选项](#options)）。 此选项的优势在于允许未经身份验证的会话在更加宽松充裕的时间范围内进行身份验证。但是，只有到下一次每周重放时，才会重新处理不到一周的未拼合数据。
   - **按每周频率进行两次回顾**：数据每周重播一次，回顾时间为双周（请参阅[选项](#options)）。 此选项的优势在于允许未经身份验证的会话在更加宽松充裕的时间范围内进行身份验证。但是，只有到下一次每周重放时，才会重新处理两周之内的未拼合数据。
   - **按每周频率每月回顾**：数据每周重播一次，回顾时间为每月一次（请参阅[选项](#options)）。 此选项的优势在于允许未经身份验证的会话在更加宽松充裕的时间范围内进行身份验证。但是，只有到下一次每周重播时，才会重新处理不到一个月未拼合的数据。

- **Privacy**：在收到与隐私相关的请求时，除了从源数据集中删除所请求的身份外，还必须撤消该身份在未经身份验证的事件之间的任何拼合。 此外，必须从身份图中删除身份，以防止将来对该特定身份进行基于图形的拼合。

  >[!IMPORTANT]
  >
  >作为隐私请求的一部分，取消拼合过程在2025年初发生变化。 当前的取消拼接过程使用最新版本的已知身份重置事件。 将事件重新分配给另一个身份可能会产生不良的法律后果。 为了消除这些疑虑，从2025年开始，新的解拼接流程将使用永久ID更新隐私请求中的事件。
  > 

不会重放回看窗口以外的数据。访客必须在给定的回看窗口内进行身份验证，才能同时识别未经身份验证的访问和经过身份验证的访问。 一旦识别出设备，就会从该时间点开始对其进行实时拼合。

请考虑以下两个持久id `246`和`3579`的标识图，这些标识图如何随时间更新，以及这些更新如何影响基于图形的拼接中的步骤。

![身份图246](assets/identity-graph-246.svg)
![身份图3579](assets/identity-graph-3579.svg)

您可以使用[身份图形查看器](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/features/identity-graph-viewer)查看特定配置文件的随时间变化的身份图形。 另请参阅[标识服务链接逻辑](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/features/identity-linking-logic)，以更好地了解链接标识时使用的逻辑。

### 步骤1：实时拼合

实时拼接会在收集时尝试将每个事件与当时来自身份图的已知信息拼合。

+++ 详细信息

| | 时间 | 永久ID<br/>`ECID` | 命名空间<br/>`Email` ![图形](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | 拼合ID（实时拼合后） |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *未定义* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 17:00 | `3579` | `3579` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *未定义* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

您可以查看如何针对每个事件解析拼合的ID。 基于时间、持久ID和查找指定命名空间的身份图（同时）。
当查找解析为多个拼接ID（如事件7）时，选择标识图返回的词典说明第一个ID（示例中为`a.b@yahoo.co.uk`）。

+++

### 步骤 2：重播拼接

重放拼合会定期（取决于选择的回顾时间范围）根据身份图的最新版本在时间间隔重新计算历史数据。

+++ 详细信息

重播拼接发生在2023-05-13 16:30，回顾时间范围配置为24小时，在这种情况下，将重新拼接示例中的某些事件（由![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)指示）。

| | 时间 | 永久ID<br/>`ECID` | 命名空间<br/>`Email` ![图形](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | 已拼合ID<br/>（实时拼合后） | 拼合ID<br/>（重播24小时后） |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


重播拼接发生在2023-05-13 16:30，回顾窗口配置为7天，在这种情况下，将重新拼接示例中的所有事件。


| | 时间 | 永久ID<br/>`ECID` | 命名空间<br/>`Email` ![图形](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | 已拼合ID<br/>（实时拼合后） | 拼合ID<br/>（重播7天后） |
|---|---|---|---|---|---|
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *未定义* | `246` | `a.b@yahoo.co.uk` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### 步骤3：隐私请求

当您收到隐私请求时，拼合的ID将会在隐私请求的用户主体的所有记录中删除。

+++ 详细信息

下表显示与上述相同的数据，但显示了隐私请求（例如，在2023-05-13 18:00）对示例事件产生的影响。

| | 时间 | 永久ID<br/>`ECID` | 命名空间<br/>`Email` ![图形](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | 拼合ID（隐私请求后） |
|--:|---|---|---|---|
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 1 | 2023-05-12 11:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 2 | 2023-05-12 14:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 3 | 2023-05-12 15:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 4 | 2023-05-12 17:00 | `3579` | `3579` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 5 | 2023-05-12 19:00 | `3579` | `3579` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 6 | 2023-05-13 15:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 7 | 2023-05-13 16:30 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## 先决条件

以下先决条件专门适用于基于图形的拼接：

- Adobe Experience Platform中的事件数据集（您要对其应用拼接）必须有一列用于在每行上标识访客，即&#x200B;**永久ID**。 例如，由Adobe Analytics AppMeasurement库生成的访客ID或由Experience Platform Identity服务生成的ECID。
- 永久性ID还必须在架构中定义为[标识](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/ui/fields/identity)。
- 来自Experience Platform Identity Service的标识图必须具有要在拼接期间用于解析`Email`临时ID`Phone`的命名空间（例如&#x200B;**或**）。 有关详细信息，请参阅[Experience Platform Identity Service](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/home)。

>[!NOTE]
>
>您不&#x200B;**需要** Real-time Customer Data Platform许可证才能进行基于图形的拼合。 Customer Journey Analytics的&#x200B;**Prime**&#x200B;程序包或更高版本包含所需的Experience Platform Identity Service授权。


## 限制

以下限制专门适用于基于图形的拼接：

- 使用指定的命名空间查询临时ID时，不考虑时间戳。 因此，持久ID可能与具有更早时间戳的记录的临时ID拼合。
- 在共享设备方案中，如果图形中的命名空间包含多个标识，则使用第一个词典标识。 如果命名空间限制和优先级是在发布图形链接规则时配置的，则使用上次经过身份验证的用户身份。 有关详细信息，请参阅[共享设备](/help/use-cases/stitching/shared-devices.md)。
- 在身份图中，存在三个月回填身份信息的硬性限制。 如果您没有使用Experience Platform应用程序（如Real-time Customer Data Platform）来填充身份图，则可以使用回填身份。
- 应用[Identity Service护栏](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/guardrails)。 例如，查看以下[静态限制](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/guardrails#static-limits)：
   - 图形中的最大标识数：50。
   - 一次批次摄取中指向某个身份的最大链接数：50。
   - 用于图形提取的XDM记录中的最大身份数： 20。
   - 用于图形提取的XDM记录中的最小身份数： 2。
