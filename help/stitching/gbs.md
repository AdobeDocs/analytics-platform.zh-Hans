---
title: 基于图形的拼接
description: 解释基于图表的拼接的概念和工作方式。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: ea5c9114-1fc3-4686-b184-2850acb42b5c
source-git-commit: 4c5376171afe7ee830c52cc1066d0645a1adbc5d
workflow-type: tm+mt
source-wordcount: '1741'
ht-degree: 69%

---

# 基于图形的拼接

在基于图形的拼接中，您可以从身份图中指定一个事件数据集、该数据集的永久ID (Cookie)以及所需的人员ID命名空间。 基于图形的拼接会尝试将人员ID信息用于任何事件上的Customer Journey Analytics数据分析。 持久ID用于从Experience Platform Identity Service查询身份图，以从指定的命名空间获取人员ID。

如果无法检索某个事件的人员ID信息，则将改用永久ID用于该&#x200B;*未拼合*&#x200B;事件。 因此，在与包含启用拼合的数据集的[连接](/help/data-views/data-views.md)关联的[数据视图](/help/connections/overview.md)中，人员ID数据视图组件包含事件级别的人员ID值或永久ID值。


![基于图形的拼接](/help/stitching/assets/gbs.svg)

## IdentityMap

基于图形的拼接支持在以下场景中使用[`identityMap`字段组](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/schema/composition#identity)：

- 在 `identityMap` 命名空间中使用主要身份标识来定义永久 ID：
   - 如果在不同的命名空间中找到多个主身份，则按词典方式对命名空间中的身份进行排序，并选择第一个身份。
   - 如果在一个命名空间中找到多个主要身份标识，就会选择按字典序排序的第一个可用的主要身份标识。

  在以下示例中，命名空间和身份将生成一个排序的主要身份标识列表，最后生成选定的身份标识。

  <table style="table-layout:auto">
     <tr>
       <th>命名空间</th>
       <th>身份标识列表</th>
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
      <th>已排序的身份标识列表</th>
      <th>选定的身份标识</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>PrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-2", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-1", "namespace": "ECID"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "namespace": "ECID"}<br/>]<br/>NonPrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-1", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-3", "namespace": "ECID"}<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ccid-2",<br/>"namespace": "CCID"</code></pre></td>
    </tr>
  </table>

- 使用 `identityMap` 命名空间定义永久 ID：
   - 如果在 `identityMap` 命名空间中找到永久 ID 的多个值，就使用按字典序排序的第一个可用的身份标识。

  在以下示例中，您选择了 ECID 作为要使用的命名空间。这个选择会生成一个排序的身份标识列表，最终生成选定的身份标识。

  <table style="table-layout:auto">
     <tr>
       <th>命名空间</th>
       <th>身份标识列表</th>
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
      <th>已排序的身份标识列表</th>
      <th>选定的身份标识</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;"id": "ecid-1",<br/>&nbsp;&nbsp;"id": "ecid-2",<br/>&nbsp;&nbsp;"id": "ecid-3"<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ecid-1",<br/>"namespace": "ECID"</code></pre></td>
    </tr>
  </table>


## 基于图形的拼接如何工作

拼接时至少会对一个给定数据集中的数据进行两次处理。

- **实时拼接**：尝试在每个点击（事件）进入时进行拼接，使用永久 ID 通过查询身份标识图查找选定命名空间的人员 ID。如果人员 ID 在查找中可用，就会立即拼接这个人员 ID。

- **重播拼接**：根据身份标识图中更新过的身份标识&#x200B;*重播*&#x200B;数据。在这个阶段，来自先前未知设备（永久 ID）的点击会在身份标识图为一个命名空间解析了此身份标识后进行拼接。两个参数决定重播： **频率**&#x200B;和&#x200B;**回顾时间范围**。 Adobe 提供这些参数的以下组合：
   - **以每日频率进行每日回顾**：数据每天重播，采用 24 小时回顾窗口。此选项的优势在于重播更频繁，但未经身份验证的轮廓必须在访问您网站的当天进行身份验证。
   - **以每周频率进行每周回顾**：数据每周重播一次，采用每周回顾窗口（请参阅[选项](#options)）。此选项的优势在于允许未经身份验证的会话在更加宽松充裕的时间范围内进行身份验证。但是，未拼接且时间不足一周的数据要等到下一次每周重播时才会重新处理。
   - **以每周频率进行每两周回顾**：数据每周重播一次，采用两周回顾窗口（请参阅[选项](#options)）。此选项的优势在于允许未经身份验证的会话在更加宽松充裕的时间范围内进行身份验证。但是，未拼接且时间不足两周的数据要等到下一次每周重播时才会重新处理。
   - **以每周频率进行每月回顾**：数据每周重播一次，采用每月回顾窗口（请参阅[选项](#options)）。此选项的优势在于允许未经身份验证的会话在更加宽松充裕的时间范围内进行身份验证。但是，未拼接且时间不足一个月的数据要等到下一次每周重播时才会重新处理。

- **隐私**：收到与隐私相关的请求时，除了从来源数据集移除所请求的身份标识外，还必须将该身份标识在未经身份验证的事件中的任何拼接解除。此外，身份标识还必须从身份标识图中移除，以防止未来对这个特定的身份标识进行基于图形的拼接。

  >[!IMPORTANT]
  >
  >作为隐私请求的一部分，解除拼接过程在 2025 年初发生变化。当前的解除拼接过程是使用最新版本的已知身份标识来重新拼接事件。将事件重新分配给另一个身份标识可能会产生不良的法律后果。为了消除这些疑虑，从 2025 年开始，新的解除拼接过程是通过永久 ID 更新隐私请求涉及的事件。
  > 

不会重播回顾窗口以外的数据。用户档案必须在给定的回看窗口内进行身份验证，才能同时识别未经身份验证的访问和经过身份验证的访问。 识别出某个设备后，就会从此时开始对该设备进行实时拼接。

请考虑以下两个关于访客 A（具有永久 ID `246`）和访客 B（具有永久 ID `3579`）在一段时间内的身份标识图更新，以及这些更新对基于图形的拼接的步骤有何影响。

![身份标识图 3579](assets/identity-graphs.svg)

您可以使用[身份标识图查看器](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/features/identity-graph-viewer)查看某个特定轮廓在一段时间内的身份标识图形。另请参阅[身份标识服务链接逻辑](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/features/identity-linking-logic)，更好地了解链接身份标识时使用的逻辑。

### 步骤 1：实时拼接

实时拼接会尝试在收集时将每个事件与当时从身份标识图中已知的信息进行拼接。

+++ 详细信息

| | 时间 | 永久 ID<br/>`ECID` | 命名空间<br/>`Email` ![数据映射](/help/assets/icons/DataMapping.svg) | 结果ID（实时拼接后） |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) *未定义* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 17:00 | `3579` | `3579` ![分支 1](/help/assets/icons/Branch1.svg) *未定义* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![分支 1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

您可以看到如何解析每个事件的结果ID。 基于时间、永久ID和查找指定人员ID命名空间的身份图。
当查找解析为多个结果ID（如事件7）时，将选择标识图返回的词典说明第一个ID（示例中为`a.b@yahoo.co.uk`）。

+++

### 步骤 2：重播拼接

重播拼接会定期（取决于所选的回顾窗口）根据身份标识图的最新版本在间隔时间重新计算历史数据。

+++ 详细信息

如果某次重播拼接发生在 2023-05-13 16:30，回顾窗口配置为 24 小时，示例中的有些事件就会重新拼接（通过![重播](/help/assets/icons/Replay.svg)表示出来）。

| | 时间 | 永久 ID<br/>`ECID` | 命名空间<br/>`Email` ![数据映射](/help/assets/icons/DataMapping.svg) | 生成的ID<br/>（实时拼接后） | 生成的ID<br/>（重放24小时之后） |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![重播](/help/assets/icons/Replay.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![重播](/help/assets/icons/Replay.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![重播](/help/assets/icons/Replay.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![重播](/help/assets/icons/Replay.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg)`a.b@yahoo.co.uk`<br/>`246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


如果重播拼接发生在 2023-05-13 16:30，回顾窗口配置为 7 天，示例中的所有事件都会重新拼接。


| | 时间 | 永久 ID<br/>`ECID` | 命名空间<br/>`Email` ![数据映射](/help/assets/icons/DataMapping.svg) | 生成的ID<br/>（实时拼接后） | 生成的ID<br/>（重播7天后） |
|---|---|---|---|---|---|
| ![重播](/help/assets/icons/Replay.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) *未定义* | `246` | `a.b@yahoo.co.uk` |
| ![重播](/help/assets/icons/Replay.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![重播](/help/assets/icons/Replay.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![重播](/help/assets/icons/Replay.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![分支 1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![重播](/help/assets/icons/Replay.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![分支 1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![重播](/help/assets/icons/Replay.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![重播](/help/assets/icons/Replay.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### 步骤 3：隐私请求

当您收到隐私请求时，生成的ID将会在隐私请求的用户主体的所有记录中删除。

+++ 详细信息

下表的数据与上面相同，但展示了隐私请求（例如在 2023-05-13 18:00）对示例事件产生的影响。

| | 时间 | 永久 ID<br/>`ECID` | 命名空间<br/>`Email` ![数据映射](/help/assets/icons/DataMapping.svg) | 结果ID（隐私请求后） |
|--:|---|---|---|---|
| ![移除圆圈](/help/assets/icons/RemoveCircle.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![移除圆圈](/help/assets/icons/RemoveCircle.svg) 2 | 2023-05-12 14:00 | `246` | `246`![分支 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![移除圆圈](/help/assets/icons/RemoveCircle.svg) 3 | 2023-05-12 15:00 | `246` | `246`  ![分支 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![移除圆圈](/help/assets/icons/RemoveCircle.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![分支 1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![移除圆圈](/help/assets/icons/RemoveCircle.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![分支 1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![移除圆圈](/help/assets/icons/RemoveCircle.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![移除圆圈](/help/assets/icons/RemoveCircle.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![分支 1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![分支 1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## 先决条件

以下先决条件专门应用于基于图形的拼接：

- 您想为其应用拼接的 Adobe Experience Platform 中的事件数据集必须有一列是在每一行上标识一个轮廓，就是&#x200B;**永久 ID**。例如，Adobe Analytics AppMeasurement 库生成的访客 ID 或者身份标识服务生成的 ECID。
- 在启用基于图形的拼合之前，必须在沙盒级别设置Experience Platform Identity Service中的身份图形。
   - 身份图形必须具有要在拼接期间用于解析人员ID的命名空间（例如`Email`或`Phone`）。
   - 必须使用来自任何相关数据集（类型为&#x200B;*event*&#x200B;或&#x200B;*profile*&#x200B;且至少包含两个具有ID值的有用命名空间）的标识信息填充标识图。
   - 所有包含此类相关标识的数据集都必须为标识图数据摄取[启用](faq.md#enable-a-dataset-for-the-identity-service)。 此支持可确保随着时间的推移，将来自所有所需来源的传入身份添加到图表中。
   - 如果一段时间内已在使用实时客户数据配置文件或Adobe Journey Optimizer，则应已在一定程度上设置此图表。<br/>如果启用基于图形的拼合的数据集也需要历史拼合回填，则图形应已包含整个时段的历史标识，以获取所需的拼合结果。
- 如果要使用基于图形的拼合，并且预期事件数据集将参与身份图形，则应[为身份服务启用该数据集](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service)。
- 永久性ID和人员ID可以与[identityMap](#identitymap)一起使用。 或者，持久ID和人员ID可以是XDM架构中的字段，在这种情况下，这些字段必须是[在架构中定义为标识](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/ui/fields/identity?lang=en)。

>[!NOTE]
>
>进行基于图形的拼接，您&#x200B;**不**&#x200B;需要 Real-time Customer Data Platform 许可证。Customer Journey Analytics 的 **Prime** 包或更高级版本包括了所需的身份标识服务授权。


## 限制

以下限制专门应用于基于图形的拼接：

- 使用指定的命名空间查询人员 ID 时不考虑时间戳。因此，永久 ID 可能会与具有更早时间戳的记录中的人员 ID 拼接。
- 在共享设备的场景中，如果图形中的命名空间包含多个身份标识，就会使用按字典序排序的第一个身份标识。如果命名空间限制和优先级是在发布图形链接规则时配置的，就会使用最后一个经过身份验证的用户的身份标识。更多信息请参阅[共享设备](/help/use-cases/stitching/shared-devices.md)。
- 有一个将身份标识回填到身份标识图中的时间最长不超过三个月的硬性限制。如果您没有使用 Experience Platform 应用程序（如 Real-time Customer Data Platform）填充身份标识图，就可以使用回填身份标识的功能。
- [身份标识服务护栏](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/guardrails)适用。例如，查看以下[静态限制](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/guardrails#static-limits)：
   - 图中的最大身份标识数量：50。
   - 一个批次摄取中指向某个身份标识的最大链接数量：50。
   - 用于图形摄取的一条 XDM 记录中的最大身份标识数量： 20。
   - 用于图形摄取的一条 XDM 记录中的最少身份标识数量： 2。
