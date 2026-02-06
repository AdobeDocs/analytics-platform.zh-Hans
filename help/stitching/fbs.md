---
title: 基于字段的拼合
description: 解释基于字段的拼合的概念和工作方式。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: e5cb55e7-aed0-4598-a727-72e6488f5aa8
source-git-commit: b5afcfe2cac8aa12d7f4d0cf98658149707123e3
workflow-type: tm+mt
source-wordcount: '1797'
ht-degree: 81%

---

# 基于字段的拼接

在基于字段的拼合中，您可以指定事件数据集以及该数据集的永久ID (Cookie)和人员ID。 基于字段的拼合会尝试对任何具有特定永久ID的匿名事件提供人员ID信息，以供Customer Journey Analytics数据分析。  该信息将从具有特定永久ID的人员ID的行中检索。

如果无法检索某个事件的人员ID信息，则将改用永久ID用于该&#x200B;*未拼合*&#x200B;事件。 因此，在与包含启用拼合的数据集的[连接](/help/data-views/data-views.md)关联的[数据视图](/help/connections/overview.md)中，人员ID组件在事件级别包含人员ID值或永久ID值。

将Customer Journey Analytics用作独立解决方案(无权访问Experience Platform Identity服务和关联的身份图)时，您可以使用基于字段的拼合。 或者，如果您不想使用可用的身份标识图。

![基于字段的拼接](/help/stitching/assets/fbs.png)


## IdentityMap

基于字段的拼接支持在以下场景中使用[`identityMap`字段组](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/schema/composition#identity)：

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


- 使用 `identityMap` 命名空间定义永久 ID 或人员 ID 或同时定义两者：
   - 如果在一个 `identityMap` 命名空间中找到多个永久 ID 或人员 ID 的值，就会使用按字典序排序的第一个可用的值。
   - 永久 ID 和人员 ID 的命名空间必须互斥。

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

## 基于字段的拼接如何进行

拼接时至少会对一个给定数据集中的数据进行两次处理。

- **实时拼接**：尝试在每个点击（事件）发生时对其进行拼接。来自数据集中的&#x200B;*新*&#x200B;设备的点击（从未经过身份验证）通常不会在这个层面上拼接。来自已识别的设备的点击会立即拼接。

- **重播拼接**：根据唯一标识符（人员 ID）*重播*&#x200B;数据。在这个阶段，来自先前未知设备（永久 ID）的点击会拼接（到人员 ID）。两个参数决定重播： **频率**&#x200B;和&#x200B;**回顾时间范围**。 Adobe 提供这些参数的以下组合：
   - **以每日频率进行每日回顾**：数据每天重播，采用 24 小时回顾窗口。此选项的优势在于重播更频繁，但未经身份验证的轮廓必须在访问您网站的当天进行身份验证。
   - **以每周频率进行每周回顾**：数据每周重播一次，采用每周回顾窗口（请参阅[选项](#options)）。此选项的优势在于允许未经身份验证的会话在更加宽松充裕的时间范围内进行身份验证。但是，未拼接且时间不足一周的数据要等到下一次每周重播时才会重新处理。
   - **以每周频率进行每两周回顾**：数据每周重播一次，采用两周回顾窗口（请参阅[选项](#options)）。此选项的优势在于允许未经身份验证的会话在更加宽松充裕的时间范围内进行身份验证。但是，未拼接且时间不足两周的数据要等到下一次每周重播时才会重新处理。
   - **以每周频率进行每月回顾**：数据每周重播一次，采用每月回顾窗口（请参阅[选项](#options)）。此选项的优势在于允许未经身份验证的会话在更加宽松充裕的时间范围内进行身份验证。但是，未拼接且时间不足一个月的数据要等到下一次每周重播时才会重新处理。

- **隐私**：收到与隐私相关的请求时，除了移除所请求的身份标识外，还必须将该身份标识在未经身份验证的事件中的任何拼接解除。

  >[!IMPORTANT]
  >
  >作为隐私请求的一部分，解除拼接过程在 2025 年初发生变化。当前的解除拼接过程是使用最新版本的已知身份标识来重新拼接事件。将事件重新分配给另一个身份标识可能会产生不良的法律后果。为了消除这些疑虑，从 2025 年开始，新的解除拼接过程是通过永久 ID 更新隐私请求涉及的事件。
  > 


不会重播回顾窗口以外的数据。用户档案必须在给定的回看窗口内进行身份验证，才能同时识别未经身份验证的访问和经过身份验证的访问。 识别出某个设备后，就会从此时开始对该设备进行实时拼接。

### 步骤 1：实时拼接

实时拼接会尝试在收集时将每个事件与已知设备和渠道进行拼接。

+++ 详细信息

请考虑以下示例：Bob 将不同的事件记录为事件数据集的一部分。

*收集数据当天显示的数据：*

| 事件 | 时间戳 | 永久 ID（Cookie ID） | 人员 ID | 结果ID（实时拼接后） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![右箭头](/help/assets/icons/ArrowRight.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![右箭头](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![右箭头](/help/assets/icons/ArrowRight.svg) | `Bob` ![下箭头](/help/assets/icons/ArrowDown.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![右箭头](/help/assets/icons/ArrowRight.svg) | `Bob` ![下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![右箭头](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![右箭头](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![右箭头](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![右箭头](/help/assets/icons/ArrowRight.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![右箭头](/help/assets/icons/ArrowRight.svg) | `Bob` ![下箭头](/help/assets/icons/ArrowDown.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **3 个设备** | | **4 个人**：<br/>`246`，`Bob`，`3579`，`81911` |

新设备上未经身份验证和经过身份验证的事件都将计为单独的人员（临时）。已识别设备上的未经身份验证的事件进行实时拼接。

自定义变量识别与设备关联后，就会开始归因。在上例中，除事件 1、8、9 和 10 之外的所有其他事件都进行实时拼接（它们都使用 `Bob` 标识符）。实时拼合“解析”事件4、6和12的结果ID。

延迟的数据（时间戳超过 24 小时的数据）会“以最大努力”处理，并会为当前数据的拼接设置优先顺序，以达到最高质量。

+++ 

### 步骤 2：重播拼接

重播拼接会定期（每周一次或每天一次，具体取决于选择的回顾窗口）根据其当前识别的设备重新计算历史数据。如果设备最初在未经身份验证的情况下发送数据，然后登录，重播拼接就会将那些未经身份验证的事件与正确的人员关联起来。

+++ 详细信息

下表与上表所示的数据相同，但根据重播数据显示了不同的数字。

*重播后的相同数据：*

| 事件 | 时间戳 | 永久 ID（Cookie ID） | 人员 ID | 结果ID（实时拼接后） | 生成的ID（重播后） |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![右箭头](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![上箭头](/help/assets/icons/ArrowUp.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![右箭头](/help/assets/icons/ArrowRight.svg) | `Bob` | Bob |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![右箭头](/help/assets/icons/ArrowRight.svg) | `Bob` ![下箭头](/help/assets/icons/ArrowDown.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![右箭头](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![右箭头](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![右箭头](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![右箭头](/help/assets/icons/ArrowRight.svg) | `Bob` ![下箭头](/help/assets/icons/ArrowDown.svg) | `Bob` ![上箭头](/help/assets/icons/ArrowUp.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3 个设备** | | **4 个人**：<br/>`246`，`Bob`，`3579`，`81911` | **2 个人**：<br/>`Bob`，`3579` |

{style="table-layout:auto"}

自定义变量识别与设备关联后，就会开始归因。在上例中，事件 1 和 10 是从重播拼接的，现在只有事件 8 和 9 未拼接。并且“人员”量度（累积）减少到 2。

+++ 

### 步骤 3：隐私请求

当您收到隐私请求时，拼接过程设置的任何与人员ID值的标识符信息将在所有记录中更新为隐私请求用户主体的永久ID值。

+++ 详细信息

下表的数据与上面相同，但展示了对 Bob 的隐私请求在处理数据后对数据的影响。Bob 经过身份验证的行（2、3、5、7 和 11）被移除，同时还移除了其他行中 Bob 这个人员 ID。

*发出对 Bob 的隐私请求之后的相同数据：*

| 事件 | 时间戳 | 永久 ID（Cookie ID） | 人员 ID | 结果ID（实时拼接后） | 生成的ID（重播后） | 人员 ID | 结果ID（隐私请求后） |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | Bob ![右箭头](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![上箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | ![移除圆圈](/help/assets/icons/RemoveCircle.svg) | `246` |
| 3 | 2023-05-12 12:03 | `246` | Bob ![右箭头](/help/assets/icons/ArrowRight.svg) | `Bob` ![下箭头](/help/assets/icons/ArrowDown.svg) | `Bob` | ![移除圆圈](/help/assets/icons/RemoveCircle.svg) | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | Bob ![右箭头](/help/assets/icons/ArrowRight.svg) | `Bob` ![下箭头](/help/assets/icons/ArrowDown.svg) | `Bob` | ![移除圆圈](/help/assets/icons/RemoveCircle.svg) | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![右箭头](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` | ![移除圆圈](/help/assets/icons/RemoveCircle.svg) | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![右箭头](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![右箭头](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![右箭头](/help/assets/icons/ArrowRight.svg) | `Bob` ![下箭头](/help/assets/icons/ArrowDown.svg) | `Bob` ![上箭头](/help/assets/icons/ArrowUp.svg) | ![移除圆圈](/help/assets/icons/RemoveCircle.svg) | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 个设备** | | **4 个人**：<br/>246，`Bob`，`3579`，`81911` | **2 个人**：<br/>Bob，`3579` |  | **3 个人**：<br/>`246`，`3579`，`81911` |

+++ 

## 先决条件

以下先决条件专门应用于基于字段的拼接：

- Adobe Experience Platform 中您想对其应用拼接的事件数据集必须有两列用于帮助识别轮廓：

   - **永久 ID**，这是每行都可用的标识符。例如，由 Adobe Analytics AppMeasurement 库生成的访客 ID 或由身份标识服务生成的 ECID。
   - **人员 ID**，这是仅在某些行中可用的标识符。例如，轮廓经过身份验证后，经过哈希处理的用户名或电子邮件地址。实际上您可以使用任何标识符。拼接时会将此字段用于保存实际人员 ID 信息。为获得最佳拼接结果，应在数据集的事件中为每个永久 ID 至少发送一次人员 ID。如果您计划在 Customer Journey Analytics 连接中包含此数据集，那么其他数据集最好也有一个类似的常见标识符。

<!--
- Both columns (persistent ID and person ID) must be defined as an identity field with an identity namespace in the schema for the dataset you want to stitch. When using identity stitching in Real-time Customer Data Platform, using the [`identityMap` field group](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/schema/composition#identity), you still need to add identity fields with an identity namespace. This identification of identity fields is required as Customer Journey Analytics stitching does not support the `identityMap` field group. When adding an identity field in the schema, while also using the `identityMap` field group, do not set the additional identity field as a primary identity. Setting an additional identity field as primary identity interferes with the `identityMap` field group used for Real-time Customer Data Platform.

-->

## 限制

以下限制专门应用于基于字段的拼接：

- 当前，重新生成键值功能只能执行一步（将永久 ID 过渡到人员 ID）。而不支持多步骤重新生成键值功能（例如将永久 ID 过渡到人员 ID，然后再过渡到另一个人员 ID）。
- 如果多个用户共享一台设备，并且用户之间的转换总数超过50,000，则Customer Journey Analytics将停止为该设备拼合数据。
- 不支持在组织中使用的自定义 ID 映射。
- 拼接区分大小写。对于通过 Analytics 源连接器生成的数据集，Adobe 建议检查任何应用于人员 ID 字段的 VISTA 规则或处理规则。这个检查可以确保任何这些规则都不会引入同一 ID 的新形式。例如，对于部分事件，您应确保没有任何 VISTA 或处理规则将小写字母引入到人员 ID 字段。
- 拼接时不会组合或连接字段。
- 人员 ID 字段应仅包含一种类型的 ID（即 ID 仅来自一个命名空间）。例如，人员 ID 字段不应包含登录 ID 和电子邮件 ID 的组合。
- 如果同一个永久 ID 发生了多个有同一个时间戳的事件，但人员 ID 字段中有多个不同的值，拼接时就会根据字母顺序选择 ID。因此，如果永久 ID A 有时间戳相同的两个事件，其中一个事件指定 Bob，而另一个指定 Ann，拼接时就会选择 Ann。
- 务必小心人员 ID 包含占位符值的这类场景，例如 `Undefined`。更多信息请参阅 [常见问题](faq.md)。
- 不能对永久ID和人员ID使用相同的命名空间，命名空间需要互斥。
