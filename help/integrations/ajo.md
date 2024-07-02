---
title: 将 Adobe Journey Optimizer 与 Customer Journey Analytics 集成
description: 引入 Adobe Journey Optimizer 生成的数据，并使用 Customer Journey Analytics 中的 Analysis Workspace 对其进行分析。
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 13c3f99dba7725553c775df4492803f759ebead5
workflow-type: tm+mt
source-wordcount: '1541'
ht-degree: 94%

---

# 将 Journey Optimizer 与 Customer Journey Analytics 集成

[Adobe Journey Optimizer](https://experienceleague.adobe.com/zh-hans/docs//journey-optimizer/using/get-started/get-started) 帮助您营造紧密联系、与上下文相关且个性化的体验。它还有助于让客户了解其客户历程的下一步。

您可以配置 Journey Optimizer 生成的数据，在 Customer Journey Analytics 中执行高级分析。您可以自动配置此集成。如果需要，您可以对连接或数据视图中可用的数据集、维度或量度进行额外的手动自定义。

## 自动配置 Journey Optimizer 集成

{{release-limited-testing-section}}

Journey Optimizer 支持使用 Customer Journey Analytics 作为报告引擎。请参阅 Journey Optimizer 文档中的[开始使用新的报告界面。](https://experienceleague.adobe.com/zh-hans/docs//journey-optimizer/using/channel-report/report-gs-cja)

当您为 Journey Optimizer 启用 Customer Journey Analytics 报告后，系统会自动为特定沙盒创建[连接](/help/connections/overview.md)和[数据视图。](/help/data-views/data-views.md)

### 连接

该连接的名称为 **[!UICONTROL AJO Enabled Connection（*沙盒名称*）]**，并具有以下用于配置和数据集的开箱即用值：

| **连接设置** | 值 |
|---|---| 
| [!UICONTROL 连接名称] | `AJO Enabled Connection (`_`sandbox name`_`)` |
| [!UICONTROL 连接说明] | [!UICONTROL *在此处描述您的连接*] |
| [!UICONTROL 标记] | [!UICONTROL *选择标记*] |


| **数据设置** | 值 |
|---|---| 
| [!UICONTROL 启用滚动数据窗口] | 已启用。[!UICONTROL 选定的月数。]`13` |
| [!UICONTROL 沙盒] | [!UICONTROL *沙盒名称*]（已禁用；您无法修改此设置）。 |
| [!UICONTROL 平均每日事件数] | 少于 100 万（已禁用；您无法修改此设置）。 |


| 数据集名称 | 架构 | 数据集类型 | 数据源类型 | 人员 ID | 键 | 匹配键 | 导入新数据 | 回填数据 |
|---|---|---|---|---|---|---|---|---|
| [!UICONTROL AJO 实体数据集] | [!UICONTROL AJO 实体记录模式] | [!UICONTROL 查询] | [!UICONTROL 其他] | - | ` _id` | `_experience. decisioning. propositions. scopeDetails. correlationID` | ![状态绿色](assets/../../connections/assets/status-green.svg) 开启 | ![状态灰色](assets/../../connections/assets/status-gray.svg) 关闭 |
| [!UICONTROL 历程步骤事件] | [!UICONTROL Journey Orchestration 的历程步骤事件模式] | [!UICONTROL 事件] | [!UICONTROL 其他] | [!UICONTROL  IdentityMap(\&lt;primary\>)] | - | - | ![状态绿色](assets/../../connections/assets/status-green.svg) 开启 | ![状态灰色](assets/../../connections/assets/status-gray.svg) 关闭 |
| [!UICONTROL AJO 电子邮件跟踪体验事件数据集] | [!UICONTROL AJO 电子邮件跟踪体验事件模式] | [!UICONTROL 事件] | [!UICONTROL 其他] | [!UICONTROL  IdentityMap(\&lt;primary\>)] | - | - | ![状态绿色](assets/../../connections/assets/status-green.svg) 开启 | ![状态灰色](assets/../../connections/assets/status-gray.svg) 关闭 |
| [!UICONTROL AJO 电子邮件跟踪体验事件数据集] | [!UICONTROL AJO 电子邮件跟踪体验事件模式] | [!UICONTROL 事件] | [!UICONTROL 其他] | [!UICONTROL  IdentityMap(\&lt;primary\>)] | - | - | ![状态绿色](assets/../../connections/assets/status-green.svg) 开启 | ![状态灰色](assets/../../connections/assets/status-gray.svg) 关闭 |
| [!UICONTROL AJO 消息反馈事件数据集] | [!UICONTROL AJO 消息反馈事件模式] | [!UICONTROL 事件] | [!UICONTROL 其他] | [!UICONTROL  IdentityMap(\&lt;primary\>)] | - | - | ![状态绿色](assets/../../connections/assets/status-green.svg) 开启 | ![状态灰色](assets/../../connections/assets/status-gray.svg) 关闭 |
| [!UICONTROL AJO 推送跟踪体验事件数据集] | [!UICONTROL AJO 推送跟踪体验事件模式] | [!UICONTROL 事件] | [!UICONTROL 其他] | [!UICONTROL  IdentityMap(\&lt;primary\>)] | - | - | ![状态绿色](assets/../../connections/assets/status-green.svg) 开启 | ![状态灰色](assets/../../connections/assets/status-gray.svg) 关闭 |


### 数据视图

数据视图的名称为 **AJO Enable Data View（*沙盒名称*）。**

- 在&#x200B;**[!UICONTROL 配置]**&#x200B;选项卡中，以下是现成的配置。

  | 设置 | 值 |
  |---|---|
  | [!UICONTROL 连接] | AJO Enabled Connection（*沙盒名称*） |
  | [!UICONTROL 名称] | `AJO Enabled Data View (`_`sandbox name`_`)` |
  | [!UICONTROL 外部 ID] | `AJO_Enabled_Data_View__`_`sandbox_name`_`_`（源自名称） |
  | [!UICONTROL 描述] | `undefined` |

  {style="table-layout:fixed"}

  | 兼容性 | 值 |
  |---|---|
  | [!UICONTROL 在 Adobe Journey Optimizer 中设置为默认数据视图] | 已启用（默认）。<br/><br/>此配置选项允许您指定与 Journey Optimizer 一起使用的数据视图，而无需手动配置。有关如何启用此配置选项的更多信息（如果默认没有启用），请参阅[创建或编辑数据视图](/help/data-views/create-dataview.md)中的[兼容性](/help/data-views/create-dataview.md#compatibility)部分。<br/><br/>当您禁用该选项时，会出现一个对话框提示您是否要继续更改默认数据视图。当您选择&#x200B;**[!UICONTROL 继续]**&#x200B;时，您需要选择另一个数据视图作为默认数据视图。选择&#x200B;**[!UICONTROL 确认]**&#x200B;以确认您的选择。选择&#x200B;**[!UICONTROL 取消]**&#x200B;以取消更改默认数据视图。 |

  | 容器 | 值 |
  |---|---|
  | [!UICONTROL 人员容器名称] | `Person` |
  | [!UICONTROL 会话容器名称] | `Session` |
  | [!UICONTROL 事件容器名称] | `Event` |

  | 日历 | 值 |
  |---|---|
  | [!UICONTROL 时区] | 符合您所在位置的时区 |
  | [!UICONTROL 日历类型] | 公历 |
  | [!UICONTROL 每年第一个月] | 1 月 |
  | [!UICONTROL 每周的第一天] | 星期日 |


- 在&#x200B;**组件**&#x200B;选项卡中：
   - 所有名称中附加有 [!UICONTROL (AJO)] 的量度和维度均会作为此自动配置的一部分自动添加。
   - 一些自动添加的量度或维度基于派生字段。 这些派生字段是专门为此集成创建的。例如，量度 [!UICONTROL 登陆页面点击量(AJO)] 基于 [!UICONTROL 登陆页面点击次数] 派生字段。
   - 某些量度或维度具有其他配置。 例如， [!UICONTROL 垃圾邮件投诉(AJO)] 有 [!UICONTROL 格式] 和 [!UICONTROL 包括/排除值] 设置已应用。
   - 所有自动添加的量度和维度都有一个名为的上下文标签 `:`*`name_of_metric_or_dimension`*. 例如， [!UICONTROL 登陆页面点击量(AJO)] 量度具有上下文标签 `:Landing page clicks (AJO)`.

- 在&#x200B;**[!UICONTROL 设置]**&#x200B;选项卡中，未应用任何特定配置值

>[!IMPORTANT]
>
>修改连接和数据视图的任何自动配置的值都会对依赖和使用自动配置的 Customer Journey Analytics 集成的 Journey Optimizer 报告产生影响。


## 手动配置与 Journey Optimizer 一起使用的数据视图

以下部分介绍如何手动使用 Journey Optimizer 生成的数据，以便在 Customer Journey Analytics 中执行高级分析。仅在[自动配置选项](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer)无法满足您的需求时才需要进行此操作。

### 将数据从 Journey Optimizer 发送到 Experience Platform

Adobe Experience Platform 作为中心数据源，联系 Journey Optimizer 与 Customer Journey Analytics。有关如何将 Journey Optimizer 数据以数据集的形式发送到 Platform as a Dataset 的步骤，请参阅 Journey Optimizer 用户指南中的[开始使用数据集](https://experienceleague.adobe.com/zh-hans/docs//journey-optimizer/using/data-management/datasets/get-started-datasets)。

### 在 Customer Journey Analytics 中创建连接

一旦 Journey Optimizer 数据进入 Adobe Experience Platform，即可根据 Journey Optimizer 数据集[创建连接](/help/connections/create-connection.md)。或者，您可以将 Journey Optimizer 数据集添加到现有连接。

选择并配置以下数据集：

| 数据集 | 数据集类型 | 连接设置 | 描述 |
| --- | --- | --- | --- |
| AJO 消息反馈事件数据集 | 事件 | 人员 ID：`IdentityMap` | 包含消息传递事件，例如“[!UICONTROL 发送]”和“[!UICONTROL 退回]”。 |
| AJO 电子邮件跟踪体验事件数据集 | 事件 | 人员 ID：`IdentityMap` | 包含电子邮件跟踪事件，例如“[!UICONTROL 打开]”、“[!UICONTROL 点击]”和“[!UICONTROL 取消订阅]”。 |
| AJO 推送跟踪体验事件数据集 | 事件 | 人员 ID：`IdentityMap` | 包含推送跟踪事件，例如“[!UICONTROL 应用程序启动]”。 |
| 历程步骤事件 | 事件 | 人员 ID：`_experience.journeyOrchestration.`<br>`stepEvents.profileID` | 包含显示哪些配置文件参与了历程的每个节点的事件。 |
| AJO 实体数据集 | 查询 | 键：`_id`<br>匹配键：`_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | 包含将历程和营销活动元数据与所有 Journey Optimizer 事件数据相关联的分类。 |

{style="table-layout:auto"}


### 配置数据视图以容纳 Journey Optimizer 维度和量度

创建连接之后，可创建一个或多个[数据视图](/help/data-views/create-dataview.md)配置可在 Customer Journey Analytics 中找到的所需的维度和量度。

>[!NOTE]
>
>Journey Optimizer 和 Customer Journey Analytics 之间的数据差异通常小于 1-2%。过去两小时内收集到的数据可能存在较大差异。请使用排除今天的日期范围以缓解涉及处理时间的差异。


#### 在数据视图中配置维度

可在数据视图中创建以下维度，以实现与 Journey Optimizer 中类似的维度大致对等。有关维度自定义选项的详细信息，请参阅数据视图管理器中的[组件设置](/help/data-views/component-settings/overview.md)。

| 维度 | 模式元素 | 组件设置 |
| --- | --- | --- |
| 历程名称 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | 组件类型：维度 |
| 历程名称和版本 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | 组件类型：维度 |
| 历程节点名称 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeName` | 组件类型：维度 |
| 历程节点类型 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | 组件类型：维度 |
| 营销活动名称 | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | 组件类型：维度 |
| 渠道 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | 组件类型：维度 |
| 推送标题 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | 组件类型：维度 |
| 电子邮件主题 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | 组件类型：维度 |
| 链接标签 | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | 组件类型：维度 |
| 试验名称 | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | 组件类型：维度<br>上下文标签：试验尝试 |
| 处理名称 | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | 组件类型：维度<br>上下文标签：试验变体 |
| 电子邮件投放失败原因 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | 组件类型：维度 |
| 电子邮件投放排除原因 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | 组件类型：维度 |
| 元素标签 | `_experience.decisioning.propositionAction.label` | 组件类型：维度 |

{style="table-layout:auto"}

#### 在数据视图中配置量度

可在数据视图中创建以下量度，以实现与 Journey Optimizer 中类似的量度大致对等。有关量度自定义选项的详细信息，请参阅数据视图管理器中的[组件设置](/help/data-views/component-settings/overview.md)。

| 量度 | 描述 | 模式元素 | 组件设置 |
| --- | --- | --- | --- |
| 退信数 | 退回消息的数量，包括立即退回的消息和发送后退回的消息。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 组件类型：量度<br>包括排除值：如果满足任意条件<br>等于：`bounce`，等于：`denylist` |
| 投放后退回 | 一些电子邮件服务会报告电子邮件已投放，稍后再将其退回。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | 组件类型：量度<br>包括排除值：等于 `async` |
| 电子邮件点击数 | 邮件中的点击数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 组件类型：量度<br>包括排除值：等于 `click` |
| 电子邮件打开次数 | 打开的邮件数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 组件类型：量度<br>包括排除值：等于 `open` |
| 错误数 | 出错的消息数。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 组件类型：量度<br>包括排除值：等于 `error` |
| 排除数 | 排除的消息数。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 组件类型：量度<br>包括排除值：等于 `exclude` |
| 发送次数 | 电子邮件提供商接受的邮件数。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 组件类型：量度<br>包括排除值：等于 `sent` |
| 垃圾邮件投诉次数 | 垃圾邮件投诉的次数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 组件类型：量度<br>包括排除值：等于 `spam_complaint` |
| 取消订阅次数 | 取消订阅的次数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 组件类型：量度<br>包括排除值：等于 `unsubscribe` |
| Edge 发送次数 | Edge 网络向 Web 或移动 SDK 发送消息的次数 | 使用架构字符串元素 `_experience.decisioning.propositionEventType.send` | |
| 入站显示次数 | 向用户显示 Web 或应用程序内消息的次数 | 使用架构字符串元素 `_experience.decisioning.propositionEventType.display` | |
| 入站点击次数 | Web 或应用程序内消息点击次数 | 使用架构字符串元素 `_experience.decisioning.propositionEventType.interact` | |
| 应用程序内触发器 | 决策引擎建议应显示消息的次数。移动 SDK 可以推翻减少实际显示次数的决定。 | 使用架构字符串元素 `_experience.decisioning.propositionEventType.trigger` | |
| 应用程序内解除 | SDK 从 UI 中删除应用程序内消息的次数 | 使用架构字符串元素 `_experience.decisioning.propositionEventType.dismiss` | |

{style="table-layout:auto"}

#### 在 Analysis Workspace 中配置计算量度

配置要用于 Journey Optimizer 数据集的维度和量度后，还可为关于这些数据的其他见解配置[计算量度](/help/components/calc-metrics/calc-metr-overview.md)。这些计算量度基于上述在数据视图管理器中创建的量度。

| 计算量度 | 描述 | 公式 |
| --- | --- | --- |
| 已发送邮件数 | 已发送邮件的总数。包括发送成功或失败的邮件。 | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| 已投放邮件数 | 已投放给客户的电子邮件数。 | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
