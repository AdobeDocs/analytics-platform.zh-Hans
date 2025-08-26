---
title: 基于字段的拼合
description: 基于字段的拼接说明
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: e5cb55e7-aed0-4598-a727-72e6488f5aa8
source-git-commit: 1ee282d0bf91c1a2f27073d0755cf404148d4d5b
workflow-type: tm+mt
source-wordcount: '1784'
ht-degree: 15%

---

# 基于字段的拼合

在基于字段的拼合中，您可以指定事件数据集，以及该数据集的永久ID (Cookie)和临时ID （人员ID）。 基于字段的拼接会在新拼接的数据集中创建一个新的拼接ID列，并根据具有该特定永久ID的临时ID的行更新此拼接ID列。 <br/>将Customer Journey Analytics用作独立解决方案(无权访问Experience Platform Identity Service和关联的身份图)时，可以使用基于字段的拼合。 或者，如果您不想使用可用的身份图。

![基于字段的拼合](/help/stitching/assets/fbs.png)


## Identitymap

基于字段的拼接支持在以下情况下使用[`identityMap`字段组](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/schema/composition#identity)：

- 使用`identityMap`命名空间中的主标识来定义persistentID：
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


- 使用`identityMap`命名空间定义persistentID或transientID，或同时定义两者：
   - 如果在`identityMap`命名空间中找到persententID或transientID的多个值，则使用第一个词典学可用值。
   - persistentID和transientID的命名空间必须互斥。

  在以下示例中，您已选择ECID作为用于基于字段的拼合的命名空间。 该选择导致排序的标识列表，以及最终选择的标识。

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

## 基于字段的拼合的工作原理

拼合至少会对给定数据集中的数据执行两次传递。

- **实时拼合**：尝试在每次点击（事件）进入时拼合点击。 来自对数据集“最新”的设备（从未经过身份验证）的点击通常不会在此级别拼合。 来自已识别设备的点击将立即拼合。

- **重播拼接**：根据它所获知的唯一标识符（临时ID）“重播”数据。 在此阶段，来自先前未知设备（永久ID）的点击将被拼合（到临时ID）。 重放由两个参数决定：**频率**&#x200B;和&#x200B;**回看时段**。 Adobe提供以下这些参数的组合：
   - **每日回顾频率**：数据每天重播，回顾时间范围为24小时。 此选项的优势在于重播更频繁，但未经身份验证的访客必须在访问您网站的同一天进行身份验证。
   - **每周回顾频率**：数据每周重播一次，回顾时间为每周一次（请参阅[选项](#options)）。 此选项的优势在于允许未经身份验证的会话在更加宽松充裕的时间范围内进行身份验证。但是，只有到下一次每周重放时，才会重新处理不到一周的未拼合数据。
   - **按每周频率进行两次回顾**：数据每周重播一次，回顾时间为双周（请参阅[选项](#options)）。 此选项的优势在于允许未经身份验证的会话在更加宽松充裕的时间范围内进行身份验证。但是，只有到下一次每周重放时，才会重新处理两周之内的未拼合数据。
   - **按每周频率每月回顾**：数据每周重播一次，回顾时间为每月一次（请参阅[选项](#options)）。 此选项的优势在于允许未经身份验证的会话在更加宽松充裕的时间范围内进行身份验证。但是，只有到下一次每周重播时，才会重新处理不到一个月未拼合的数据。

- **Privacy**：在收到与隐私相关的请求时，除了删除请求的身份外，还必须撤消该身份在未经身份验证的事件之间的任何拼合。

  >[!IMPORTANT]
  >
  >作为隐私请求的一部分，取消拼合过程在2025年初发生变化。 当前的取消拼接过程使用最新版本的已知身份重置事件。 将事件重新分配给另一个身份可能会产生不良的法律后果。 为了消除这些疑虑，从2025年开始，新的解拼接流程将使用永久ID更新隐私请求中的事件。
  > 


不会重放回看窗口以外的数据。访客必须在给定的回看窗口内进行身份验证，才能同时识别未经身份验证的访问和经过身份验证的访问。 一旦识别出设备，就会从该时间点开始对其进行实时拼合。

### 步骤1：实时拼合

实时拼接会尝试在收集时将每个事件拼接到已知设备和渠道。

+++ 详细信息

请考虑以下示例，其中Bob将不同的事件记录为事件数据集的一部分。

*收集数据当天显示的数据：*

| 事件 | 时间戳 | 永久性ID(Cookie ID) | 临时ID（登录ID） | 拼合ID（实时拼合后） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **3个设备** | | **4人**：<br/>`246`，`Bob`，`3579`，`81911` |

新设备上未经身份验证和经过身份验证的事件都将计为单独的人员（临时）。已识别设备上的未经身份验证的事件将进行实时拼合。

当标识自定义变量与设备绑定时，归因可发挥作用。 在以上示例中，除事件1、8、9和10之外的所有其他事件都将进行实时拼合（它们都使用`Bob`标识符）。 实时拼接“解析”事件4、6和12的拼接ID。

延迟的数据（时间戳超过24小时之前的数据）会尽最大努力处理，同时会为当前数据的拼合设置优先顺序以实现最高质量。

+++ 

### 步骤 2：重播拼接

重播拼合会定期（每周一次或每天一次，具体取决于选择的回顾时间范围）根据其当前识别的设备重新计算历史数据。 如果设备最初在未经身份验证的情况下发送数据，然后登录，则重播拼接会将那些未经身份验证的事件与正确的人员关联起来。

+++ 详细信息

下表与上表所示的数据相同，但根据重播数据显示了不同的数字。

*重播后的相同数据：*

| 事件 | 时间戳 | 永久性ID(Cookie ID) | 临时ID（登录ID） | 拼合ID（实时拼合后） | 拼合ID（重播后） |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![向上箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![向上箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3个设备** | | **4人**：<br/>`246`，`Bob`，`3579`，`81911` | **2人**：<br/>`Bob`，`3579` |

{style="table-layout:auto"}

当标识自定义变量与设备绑定时，归因可发挥作用。 在以上示例中，事件1和10是在重放之后拼接的，仅留下事件8和9未拼接。 并将“人员”量度（累积）减少到2。

+++ 

### 步骤3：隐私请求

当您收到隐私请求时，拼合的ID将会在隐私请求的用户主体的所有记录中删除。

+++ 详细信息

下表显示与上表相同的数据，但显示了Bob隐私请求在处理该数据后对数据的影响。 删除了对Bob进行身份验证的行（2、3、5、7和11），同时还删除了Bob作为其他行的临时ID。

*对Bob的隐私请求后的相同数据：*

| 事件 | 时间戳 | 永久性ID(Cookie ID) | 临时ID（登录ID） | 拼合ID（实时拼合后） | 拼合ID（重播后） | 临时ID（登录ID） | 拼合ID（隐私请求后） |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | Bob ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![向上箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 3 | 2023-05-12 12:03 | `246` | Bob ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | Bob ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![向上箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3个设备** | | **4人**：<br/>246，`Bob`，`3579`，`81911` | **2人**：<br/>Bob，`3579` |  | **3人**：<br/>`246`，`3579`，`81911` |

+++ 

## 先决条件

以下先决条件专门适用于基于字段的拼合：

- Adobe Experience Platform中的事件数据集（您要对其应用拼接）必须具有两个帮助识别访客的列：

   - **永久ID**，每行都有一个可用的标识符。 例如，由Adobe Analytics AppMeasurement库生成的访客ID或由Adobe Experience Platform Identity服务生成的ECID。
   - **临时ID**，该标识符仅在部分行可用。 例如，经过身份验证的访客的经过哈希处理的用户名或电子邮件地址。您实际上可以使用任何喜欢的标识符。 拼接会将此字段视为保存实际人员ID信息。 为获得最佳的拼接结果，应在数据集的事件中为每个永久ID至少发送一次临时ID。 如果计划在Customer Journey Analytics连接中包含此数据集，则最好其他数据集也具有类似的通用标识符。

<!--
- Both columns (persistent ID and transient ID) must be defined as an identity field with an identity namespace in the schema for the dataset you want to stitch. When using identity stitching in Real-time Customer Data Platform, using the [`identityMap` field group](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/schema/composition#identity), you still need to add identity fields with an identity namespace. This identification of identity fields is required as Customer Journey Analytics stitching does not support the `identityMap` field group. When adding an identity field in the schema, while also using the `identityMap` field group, do not set the additional identity field as a primary identity. Setting an additional identity field as primary identity interferes with the `identityMap` field group used for Real-time Customer Data Platform.

-->

## 限制

以下限制特别适用于基于字段的拼合：

- 当前，重新生成键值功能只能执行一步（即将永久 ID 转换为临时 ID）。而不支持多步重新生成键值功能（例如，将永久 ID 转换为临时 ID，然后再转换为另一个临时 ID）。
- 如果一台设备由多人共享，并且用户之间的转换总数超过50,000，Customer Journey Analytics将停止为该设备拼合数据。
- 不支持在组织中使用的自定义 ID 映射。
- 拼接区分大小写。 对于通过Analytics Source Connector生成的数据集，Adobe建议审查任何适用于临时ID字段的VISTA规则或处理规则。 此审查可确保所有这些规则都不会引入同一ID的新形式。 例如，对于部分事件，您应确保没有任何 VISTA 或处理规则将小写字母引入到临时 ID 字段。
- 拼接不会组合或连接字段。
- 临时ID字段应包含单一类型的ID（来自单个命名空间的ID）。 例如，临时 ID 字段不应包含登录 ID 和电子邮件 ID 的组合。
- 如果对于同一持久ID发生了多个具有同一时间戳的事件，但临时ID字段中的值不同，则拼接操作会根据字母顺序选择该ID。 因此，如果持久ID A具有时间戳相同的两个事件，其中一个事件指定Bob，而另一个事件指定Ann，则拼接操作将选择Ann。
- 对于临时ID包含占位符值（例如`Undefined`）的情况，请务必小心。 有关详细信息，请参阅[常见问题解答](faq.md)。
- 不能同时使用相同的命名空间persistentID和transientID，命名空间需要互斥。
