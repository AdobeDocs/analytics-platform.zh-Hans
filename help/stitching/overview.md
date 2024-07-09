---
title: 拼接概述
description: 拼接概述。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: ca2387c2dd4c6c0ccdf6cec245c5d66ecea93bd5
workflow-type: tm+mt
source-wordcount: '3817'
ht-degree: 12%

---

# 拼合

>[!NOTE]
>
>您必须拥有 **选择** 包或更高版本（用于基于字段的拼接）或 **Prime** 软件包或更高版本（用于基于图形的拼接），以使用本节中描述的功能。 如果您不确定您拥有的是哪个 Customer Journey Analytics 包，请联系您的管理员。


身份拼接（或简单地说，拼接）是一项强大的功能，可以提高事件数据集进行跨渠道分析的适用性。 跨渠道分析是Customer Journey Analytics可以处理的主要用例，允许您基于通用标识符（人员ID）对不同渠道的多个数据集无缝组合和运行报告。

当您合并具有相似人员 ID 的数据集时，将跨设备和渠道进行归因。例如，用户首先通过台式计算机上的广告访问了您的网站。该用户在下单时遇到了问题，随后致电客服团队以请求其帮助解决此问题。通过跨渠道分析，您可以将呼叫中心事件归因于最初点击的广告。

很遗憾，作为Customer Journey Analytics中连接一部分的所有基于事件的数据集并非都填充了足够的数据，开箱即用地支持此归因。 特别是，基于Web或基于移动设备的体验数据集通常没有可用于所有事件的实际人员ID信息。

拼接允许为一个数据集行中的身份重新生成键，确保人员ID（拼接ID）在每个事件上可用。 拼接查看来自经过身份验证和未经身份验证的会话的用户数据，以确定可用作拼接ID的通用临时ID（人员ID）值。 通过重新生成键值，可将不同的记录解析为单个拼合ID，以供在人员级别，而不是设备或Cookie级别进行分析。

Customer Journey Analytics支持两种类型的拼合：基于字段的拼合和基于图形的拼合。

## 先决条件

>[!IMPORTANT]
>
>如果不满足所有先决条件，则可能会导致无法正确进行跨渠道分析。

在使用拼合之前，请确保贵组织已做好以下准备：

- 拼接包括合并的经过身份验证的用户数据和未经身份验证的用户数据。 在激活事件数据集的拼合之前，请确保遵守适用的法律和法规，包括获取必要的最终用户权限。 请参阅 [在 UI 中定义标识字段](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/ui/fields/identity) 以了解更多信息。

- 将所需数据导入Adobe Experience Platform：

   - 有关Adobe Analytics数据，请参阅 [在Customer Journey Analytics中使用Adobe Analytics报表包数据](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - 有关其他类型的数据，请参阅 Adobe Experience Platform 文档中的[创建模式](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui)和[摄取数据](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home)。

如果在定义Customer Journey Analytics连接时将一个或多个拼合数据集与其他数据集（例如呼叫中心数据）相结合，您将受益于跨渠道分析。 此连接配置假定其他那些数据集在每行上均已包含一个人员ID，与拼接ID类似。


## 限制

>[!IMPORTANT]
>
>- 不支持使用 `identityMap` 作为永久ID。 您必须在数据集中定义特定的标识符(例如， `ECID`)作为永久ID。
>
>- 将您对源事件数据集架构所做的任何更改也应用于新拼接的数据集架构，否则这会断开拼接的数据集。
>
>- 如果删除源数据集，则拼接的数据集将停止处理并被系统删除。
>
>- 数据使用标签不会自动传播到拼接的数据集架构。 如果您已将数据使用标签应用于源数据集架构，则需要手动将这些数据使用标签应用于拼接的数据集架构。 请参阅 [管理Experience Platform中的数据使用标签](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) 以了解更多信息。

拼接是一项具有突破性的强大功能，但其使用方式存在限制。

- 仅支持事件数据集。不支持其他数据集，例如查找数据集。
- 拼接不会以任何方式转换用于拼接的字段。 拼接使用指定字段中的值，因为该值存在于数据湖内的未拼接数据集中。
- 拼接过程区分大小写。例如，如果字段中有时出现“Bob”一词，有时出现“BOB”一词，则这些id将被视为两个不同的人。

请确保不要将拼合与以下内容混淆：

- 两个或更多数据集的合并。 拼接仅适用于一个数据集。 数据集合并是设置Customer Journey Analytics连接并在该连接的所选数据集中选择相同的人员ID的结果。

- 两个数据集的连接。 在Customer Journey Analytics中，连接通常用于Analysis Workspace中的查找或分类。 尽管拼接使用连接功能，但过程本身涉及的连接还不止于。


## 基于字段的拼合

您可以指定一个事件数据集，以及该数据集的永久ID (Cookie)和临时ID （人员ID）。 基于字段的拼接会在新拼接的数据集中创建一个新的拼接ID列，并根据具有该特定永久ID的临时ID的行更新此拼接ID列。 <br/>将Customer Journey Analytics用作独立解决方案(无权访问Experience Platform身份服务和关联的身份图)时，可以使用基于字段的拼合。 或者，如果您不想使用可用的身份图。

![基于字段的拼合](/help/stitching/assets/fbs.png)

### 基于字段的拼合的工作原理

拼合至少会对给定数据集中的数据执行两次传递。

- **实时拼合**：尝试在每次点击（事件）进入时拼合点击。 来自对数据集“最新”的设备（从未经过身份验证）的点击通常不会在此级别拼合。 来自已识别设备的点击将立即拼合。

- **重播拼合**：根据已学到的唯一标识符（临时ID）“重播”数据。 在此阶段，来自先前未知设备（永久ID）的点击将被拼合（到临时ID）。 Adobe 提供以下两个重播时间间隔：
   - **每日**：数据每天重播，回顾时间范围为24小时。 此选项的优势在于重播更频繁，但未经身份验证的访客必须在访问您网站的同一天进行身份验证。
   - **每周**：使用您选择的回看窗口每周重播一次数据(请参阅 [options](#options))。 此选项的优势在于允许未经身份验证的会话在更加宽松充裕的时间范围内进行身份验证。但是，只有到下一次每周重放时，才会重新处理不到一周的未拼合数据。

- **隐私**：在收到与隐私相关的请求时，除了删除所请求的身份之外，还必须撤消该身份在未验证事件之间的任何拼合。

不会重放回看窗口以外的数据。访客必须在给定的回看窗口内进行身份验证，才能同时识别未经身份验证的访问和经过身份验证的访问。 一旦识别出设备，就会从该时间点开始对其进行实时拼合。

#### 步骤1：实时拼合

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
| | | **3台设备** | | **4人**：<br/>`246`， `Bob`， `3579`， `81911` |

新设备上未经身份验证和经过身份验证的事件都将计为单独的人员（临时）。已识别设备上的未经身份验证的事件将进行实时拼合。

当标识自定义变量与设备绑定时，归因可发挥作用。 在以上示例中，除事件1、8、9和10之外的所有其他事件都将进行实时拼合(它们都使用 `Bob` 标识符)。 实时拼接“解析”事件4、6和12的拼接ID。

延迟的数据（时间戳超过24小时之前的数据）会尽最大努力处理，同时会为当前数据的拼合设置优先顺序以实现最高质量。

+++

#### 步骤 2：重播拼接

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
| | | **3台设备** | | **4人**：<br/>`246`， `Bob`， `3579`， `81911` | **2人**：<br/>`Bob`， `3579` |

{style="table-layout:auto"}

当标识自定义变量与设备绑定时，归因可发挥作用。 在以上示例中，事件1和10是在重放之后拼接的，仅留下事件8和9未拼接。 并将“人员”量度（累积）减少到2。

+++

#### 步骤3：隐私请求

当您收到隐私请求时，拼合的ID将会在隐私请求的用户主体的所有记录中删除。

+++ 详细信息

下表显示与上表相同的数据，但显示了Bob隐私请求在处理该数据后对数据的影响。 删除了对Bob进行身份验证的行（2、3、5、7和11），同时还删除了Bob作为其他行的临时ID。

*向Bob发出隐私请求后的相同数据：*

| 事件 | 时间戳 | 永久性ID(Cookie ID) | 临时ID（登录ID） | 拼合ID（实时拼合后） | 拼合ID（重播后） | 临时ID（登录ID） | 拼合ID（隐私请求后） |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![向上箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 3 | 2023-05-12 12:03 | `246` | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![向上箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3台设备** | | **4人**：<br/>246， `Bob`， `3579`， `81911` | **2人**：<br/>鲍勃， `3579` |  | **3人**：<br/>`246`， `3579`， `81911` |

+++

### 先决条件

以下先决条件专门适用于基于字段的拼合：

- Adobe Experience Platform中的事件数据集（您要对其应用拼接）必须具有两个帮助识别访客的列：

   - A **永久ID**，每行都可用的标识符。 例如，由Adobe AnalyticsAppMeasurement库生成的访客ID或由Adobe Experience Platform Identity服务生成的ECID。
   - A **临时ID**，该标识符仅在部分行可用。 例如，经过身份验证的访客的经过哈希处理的用户名或电子邮件地址。您实际上可以使用任何喜欢的标识符。 拼接会将此字段视为保存实际人员ID信息。 为获得最佳的拼接结果，应在数据集的事件中为每个永久ID至少发送一次临时ID。 如果计划在Customer Journey Analytics连接中包含此数据集，则最好其他数据集也具有类似的公共标识符。

- 对于要拼合的数据集，必须将两列（永久ID和临时ID）定义为架构中具有标识命名空间的标识字段。 在Real-time Customer Data Platform中使用身份拼接时，使用 [`identityMap` 字段组](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity)，您仍需要添加具有身份命名空间的身份字段。 由于Customer Journey Analytics拼接不支持 `identityMap` 字段组。 在架构中添加标识字段时，同时使用 `identityMap` 字段组，不要将附加标识字段设置为主标识。 将附加标识字段设置为主标识会干扰 `identityMap` Real-time Customer Data Platform使用的字段组。

### 限制

以下限制特别适用于基于字段的拼合：

- 当前，重新生成键值功能只能执行一步（即将永久 ID 转换为临时 ID）。而不支持多步重新生成键值功能（例如，将永久 ID 转换为临时 ID，然后再转换为另一个临时 ID）。
- 如果一台设备由多人共享，并且用户之间的转换总数超过50,000，则Customer Journey Analytics将停止为该设备拼合数据。
- 不支持在组织中使用的自定义 ID 映射。
- 拼接区分大小写。 对于通过Analytics Source Connector生成的数据集，Adobe建议审查任何适用于临时ID字段的VISTA规则或处理规则。 此审查可确保所有这些规则都不会引入同一ID的新形式。 例如，对于部分事件，您应确保没有任何 VISTA 或处理规则将小写字母引入到临时 ID 字段。
- 拼接不会组合或连接字段。
- 临时ID字段应包含单一类型的ID（来自单个命名空间的ID）。 例如，临时 ID 字段不应包含登录 ID 和电子邮件 ID 的组合。
- 如果对于同一持久ID发生了多个具有同一时间戳的事件，但临时ID字段中的值不同，则拼接操作会根据字母顺序选择该ID。 因此，如果持久ID A具有时间戳相同的两个事件，其中一个事件指定Bob，而另一个事件指定Ann，则拼接操作将选择Ann。
- 对于临时ID包含占位符值的情况（例如），请务必谨慎 `Undefined`. 请参阅 [常见问题解答](faq.md) 以了解更多信息。


## 基于图形的拼接

您可以为该数据集指定事件数据集、永久ID (Cookie)和临时ID （人员ID）的命名空间。 基于图形的拼合会在新拼合的数据集中为拼合的ID创建新列。 然后，使用持久ID使用指定的命名空间从Experience Platform身份服务查询身份图以更新拼合的ID。

![基于图形的拼合](/help/stitching/assets/gbs.png)

### 基于图形的拼合的工作原理

拼合至少会对给定数据集中的数据执行两次传递。

- **实时拼合**：尝试在每次点击（事件）传入时对其进行拼合，使用永久ID通过查询身份图查找所选命名空间的临时ID。 如果临时id在查找中可用，则会立即拼合此临时id。

- **重播拼合**：根据身份图中的更新身份“重播”数据。 在这个阶段，来自先前未知设备（永久ID）的点击会在身份图解析命名空间身份后拼合。 Adobe 提供以下两个重播时间间隔：
   - **每日**：数据每天重播，回顾时间范围为24小时。 此选项的优势在于重播更频繁，但未经身份验证的访客必须在访问您网站的同一天进行身份验证。
   - **每周**：数据在回看时段内每周重播一次(请参阅 [options](#options))。 此选项的优势在于允许未经身份验证的会话在更加宽松充裕的时间范围内进行身份验证。但是，只有到下一次每周重放时，才会重新处理不到一周的未拼合数据。

- **隐私**：在收到与隐私相关的请求时，除了从源数据集中删除所请求的身份之外，还必须撤消该身份在未经身份验证的事件之间的任何拼合。 此外，必须从身份图中删除身份，以防止将来对该特定身份进行基于图形的拼合。

不会重放回看窗口以外的数据。访客必须在给定的回看窗口内进行身份验证，才能同时识别未经身份验证的访问和经过身份验证的访问。 一旦识别出设备，就会从该时间点开始对其进行实时拼合。

考虑以下两个持久id的标识图 `246` 和 `3579`、这些身份图形如何随时间进行更新，以及这些更新如何影响基于图形的拼合中的步骤。

![身份图246](assets/identity-graph-246.svg)
![身份图3579](assets/identity-graph-3579.svg)

您可以使用查看特定配置文件的标识图 [身份图查看器](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer). 另请参阅 [标识服务链接逻辑](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic) 以更好地了解关联身份时使用的逻辑。

#### 步骤1：实时拼合

实时拼接会在收集时尝试将每个事件与当时来自身份图的已知信息拼合。

+++ 详细信息

| | 时间 | 永久ID<br/>`ECID` | 命名空间<br/>`Email` ![图表](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | 拼合ID（实时拼合后） |
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
当查找解析为一个以上的拼合ID（如事件7）时，将选择身份图返回的词典说明第一个ID(`a.b@yahoo.co.uk` 在示例中)。

+++

#### 步骤 2：重播拼接

重放拼合会定期（取决于选择的回顾时间范围）根据身份图的最新版本在时间间隔重新计算历史数据。

+++ 详细信息

重放拼合时间为2023-05-13 16:30，回顾时间范围配置为24小时，在这种情况下，将重新拼合示例中的某些事件(由 ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg))。

| | 时间 | 永久ID<br/>`ECID` | 命名空间<br/>`Email` ![图表](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | 拼接ID<br/>（实时拼接后） | 拼接ID<br/>（重播24小时后） |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![重播](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


重放拼合时间为2023-05-13 16:30，具有7天回看窗口配置，在这种情况下，将重新拼合示例中的所有事件。


| | 时间 | 永久ID<br/>`ECID` | 命名空间<br/>`Email` ![图表](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | 拼接ID<br/>（实时拼接后） | 拼接ID<br/>（重播7天后） |
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

#### 步骤3：隐私请求

当您收到隐私请求时，拼合的ID将会在隐私请求的用户主体的所有记录中删除。

+++ 详细信息

下表显示与上述相同的数据，但显示隐私请求（例如，在2023-05-13 18:00）对示例事件具有的影响。

| | 时间 | 永久ID<br/>`ECID` | 命名空间<br/>`Email` ![图表](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | 拼合ID（隐私请求后） |
|--:|---|---|---|---|
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 1 | 2023-05-12 11:00 | `246` | `246`  ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 2 | 2023-05-12 14:00 | `246` | `246`  ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 3 | 2023-05-12 15:00 | `246` | `246`  ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 4 | 2023-05-12 17:00 | `3579` | `3579` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 5 | 2023-05-12 19:00 | `3579` | `3579` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 6 | 2023-05-13 15:00 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 7 | 2023-05-13 16:30 | `246` | `246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![链接](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

### 先决条件

以下先决条件专门适用于基于图形的拼接：

- Adobe Experience Platform中的事件数据集（您要对其应用拼接）必须有一列用于在每行上标识访客，即 **永久ID**. 例如，由Adobe AnalyticsAppMeasurement库生成的访客ID或由Adobe Experience Platform Identity服务生成的ECID。
- 来自Experience Platform身份服务的身份图必须具有命名空间(例如 `Email`，或 `Phone`)，您希望在拼合期间使用来解析 **临时ID**. 请参阅 [Experience Platform标识服务](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/home) 以了解更多信息。

>[!NOTE]
>
>您需要 **非** 需要Real-time Customer Data Platform许可证才能进行基于图形的拼合。 此 **Prime** Customer Journey Analytics包或更高版本包括所需的Experience PlatformIdentity Service权限。


### 限制

以下限制专门适用于基于图形的拼接：

- 使用指定的命名空间查询临时ID时，不考虑时间戳。 因此，持久ID可能与具有更早时间戳的记录的临时ID拼合。
- 不支持共享设备。 当返回多个身份时，通过使用命名空间查询身份图，使用第一个词典图身份。
- 在身份图中，存在三个月回填身份信息的硬性限制。 如果您没有使用Experience Platform应用程序(如Real-time Customer Data Platform)填充身份图，则可以使用回填身份。
- 此 [Identity服务护栏](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails) 应用。 例如，请参阅以下内容 [静态限制](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits)：
   - 图形中的最大标识数：50。
   - 一次批次摄取中指向某个身份的最大链接数：50。
   - 用于图形提取的XDM记录中的最大身份数： 20。
   - 用于图形提取的XDM记录中的最小身份数： 2。


## 使用拼合

您的组织满足所有条件后 [先决条件](#prerequisites) 并了解常见的 [限制](#limitations) 和拼接方法特定的([基于字段](#limitations-1) 和 [基于图](#limitations-2))限制，您可以按照以下步骤开始在Customer Journey Analytics中使用拼合。

### 选择选项

您有权使用的Customer Journey Analytics包将决定可用的拼接方法、初始回填持续时间的选项、回顾时间范围、重放频率和允许拼接的最大数据集数。 请参阅 [Customer Journey Analytics产品描述](https://helpx.adobe.com/cn/legal/product-descriptions/customer-journey-analytics.html) 以了解更多详细信息。 在请求支持之前决定可用的选项。

| | Customer Journey Analytics<br/>选择 | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| 可用的拼接方法 | <li>基于字段的拼合</li> | <li>基于字段的拼合</li><li>基于图形的拼接</li> | <li>基于字段的拼合</li><li>基于图形的拼接</li> |
| 一次性拼接回填持续时间 | 13 个月 | 13 个月 | 25 个月 |
| 回顾窗口和重放频率 | <li>1天，每天</li><li>长达7天，每周</li> | <li>1天，每天</li><li>长达14天，每周</li> | <li>1天，每天</li><li>长达30天，每周</li> |
| 允许拼合的最大数据集数 | 5 | 10 | 50 |

### 请求支持

1. 请联系 Adobe 客户支持并提供以下信息：

   - 启用拼合的请求。
   - 要重新生成键值的数据集的数据集ID。
   - 所需数据集（每行都显示的标识符）的永久ID的列名称（身份路径和命名空间）。
   - 对于基于字段的拼合，所需数据集的“临时ID”列名称（人员标识符，也用作连接上下文中数据集之间的链接）。 对于基于图的拼接，为用于查询身份图的身份命名空间。
   - 您的回顾窗口和重播频率首选项。 请参阅您的Customer Journey Analytics包，了解 [options](#options) 可用。
   - 沙盒名称。


2. Adobe客户支持与Adobe工程部门合作，以便在收到您的请求时启用拼合。 启用后，Adobe Experience Platform中会显示一个包含新拼接ID列的已重新生成键值的新数据集。 Adobe客户支持可以提供新数据集的ID。

3. 首次打开时，Adobe提供拼合数据的回填。 请参阅您的Customer Journey Analytics包，了解 [option](#options) 可用。

4. 如果要在跨渠道分析中使用新拼接的数据集，则需要将新拼接的数据集添加到 [连接](../connections/overview.md) Customer Journey Analytics中。 然后，添加跨渠道分析所需的任何其他数据集，并为每个数据集选择正确的人员ID。

5. 根据连接[创建数据视图](/help/data-views/create-dataview.md)。

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

数据视图设置完成后，您可以跨渠道和设备运行Customer Journey Analytics报表分析。

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->

