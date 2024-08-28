---
title: 将 Adobe Journey Optimizer 与 Customer Journey Analytics 集成
description: 引入 Adobe Journey Optimizer 生成的数据，并使用 Customer Journey Analytics 中的 Analysis Workspace 对其进行分析。
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 5434b8432608ba5ee49f7062070fa1624af1b46a
workflow-type: ht
source-wordcount: '3028'
ht-degree: 100%

---

# 将 Journey Optimizer 与 Customer Journey Analytics 集成

[Adobe Journey Optimizer](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/get-started/get-started) 帮助您营造紧密联系、与上下文相关且个性化的体验。它还有助于让客户了解其客户历程的下一步。

您可以配置 Journey Optimizer 生成的数据，在 Customer Journey Analytics 中执行高级分析。您可以自动配置此集成。如果需要，您可以对连接或数据视图中可用的数据集、维度或量度进行额外的手动自定义。

## 自动配置 Journey Optimizer 集成

{{release-limited-testing-section}}

Journey Optimizer 支持使用 Customer Journey Analytics 作为报告引擎。请参阅 Journey Optimizer 文档中的[开始使用新的报告界面。](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/channel-report/report-gs-cja)

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
   - 一些自动添加的量度或维度是基于派生字段的。这些派生字段是专门为此集成创建的。例如，量度“[!UICONTROL 登陆页面点击次数”（AJO）]基于“[!UICONTROL 登陆页面点击次数]”派生字段。
   - 某些量度或维度有额外的配置。例如，[!UICONTROL 垃圾邮件投诉 (AJO) ]的确应用了“[!UICONTROL 格式]”和“[!UICONTROL 包含排除值]”设置。
   - 所有自动添加的量度和维度都有一个名为 `:`*`name_of_metric_or_dimension`*的上下文标签。例如，[!UICONTROL 登陆页点击次数（AJO）] 量度具有上下文标签 `:Landing page clicks (AJO)`。

- 在&#x200B;**[!UICONTROL 设置]**&#x200B;选项卡中，未应用任何特定配置值

>[!IMPORTANT]
>
>修改连接和数据视图的任何自动配置的值都会对依赖和使用自动配置的 Customer Journey Analytics 集成的 Journey Optimizer 报告产生影响。


## 手动配置与 Journey Optimizer 一起使用的数据视图

以下部分介绍如何手动使用 Journey Optimizer 生成的数据，以便在 Customer Journey Analytics 中执行高级分析。仅在[自动配置选项](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer)无法满足您的需求时才需要进行此手动配置。

### 将数据从 Journey Optimizer 发送到 Experience Platform

Adobe Experience Platform 作为中心数据源，联系 Journey Optimizer 与 Customer Journey Analytics。有关如何将 Journey Optimizer 数据以数据集的形式发送到 Platform as a Dataset 的步骤，请参阅 Journey Optimizer 用户指南中的[开始使用数据集](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/data-management/datasets/get-started-datasets)。

### 创建连接

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


### 配置数据视图

创建连接之后，可创建一个或多个[数据视图](/help/data-views/create-dataview.md)，以配置在 Customer Journey Analytics 中可用的所需维度和量度。

>[!NOTE]
>
>Journey Optimizer 和 Customer Journey Analytics 之间的数据差异通常小于 1-2%。过去两小时内收集到的数据可能存在较大差异。请使用排除今天的日期范围以缓解涉及处理时间的差异。


#### 配置维度

可在数据视图中创建以下维度，以实现与 Journey Optimizer 中类似的维度大致对等。有关维度自定义选项的详细信息，请参阅数据视图管理器中的[组件设置](/help/data-views/component-settings/overview.md)。

| 维度 | 描述 | 数据集 | 模式元素 | 组件设置 |
| --- | --- | --- | --- | --- |
| 操作执行错误（AJO） | 阻止 Journey Runtime 执行操作的错误条件。 | 历程步骤事件 | `_experience.journeyOrchestration.`<br/>`stepEvents.actionExecutionError ` | 组件类型：维度 |
| 操作标签（AJO） | 客户生成的与最终用户交互的元素的显示名称。 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | `_experience.decisioning.`<br/>`propositionAction.label` | 组件类型：维度 |
| 批次 ID (AJO) | 在为预定的历程或营销活动操作调用每个新批处理实例时创建的 GUID。例如，如果预定的历程或营销活动操作在上午 8 点和上午 10 点运行，则有两个不同的 batchInstanceID。 | AJO 推送跟踪体验事件数据集、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | ` _experience.customerJourneyManagement.`<br/>`messageExecution.batchInstanceID` | 组件类型：维度 |
| 批处理实例时间戳 (AJO) | 批处理实例的时间戳。 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | 派生字段 | 组件类型：维度（派生字段） |
| 活动 ID (AJO) | 活动的 ID。 | AJO 实体数据集 | `_experience.customerJourneyManagement.entities.`<br/>`campaign.campaignID` | 组件类型：维度 |
| 活动名称（AJO） | 活动的名称。 | AJO 实体数据集 | `_experience.customerJourneyManagement.entities.`<br/>`campaign.name` | 组件类型：维度 |
| 营销活动版本 ID（AJO） | 营销活动的版本 ID。 | AJO 实体数据集 | `_experience.customerJourneyManagement.`<br/>`entities.campaign.campaignVersionID` | 组件类型：维度 |
| 渠道（AJO） | 该数据应关联到的渠道。 | AJO 实体数据集 | `_experience.customerJourneyManagement.`<br/>`entities.channelDetails.channel._id` | 组件类型：维度 |
| 关联 ID (AJO) | 关联 ID。 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | `_experience.decisioning.propositions.`<br/>`scopeDetails.correlationID` | 组件类型：维度 |
| 决策策略 Id (AJO) | 在决定将哪些项目包含在此命题中时使用的决策策略的 ID。 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | 派生字段 | 组件类型：维度（派生字段） |
| 电子邮件收件人域（AJO） | 电子邮件地址的域。 | AJO 推送跟踪体验事件数据集、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | `_experience.customerJourneyManagement.`<br/>`emailChannelContext.address` | 组件类型：维度 |
| 电子邮件主题（AJO） | 电子邮件主题，非个性化 | AJO 实体数据集 | `_experience.customerJourneyManagement.entities.`<br/>`channelDetails.email.subject` | 组件类型：维度 |
| 事件 ID (AJO) | 时间序列事件的唯一标识符。 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | `_id` | 组件类型：维度（派生字段） |
| 退出条件 ID (AJO) | 用于确定历程是否应该退出的退出标准的 ID。 | 历程步骤事件 | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaID` | 组件类型：维度 |
| 退出条件名称（AJO） | 退出标准的名称。 | 历程步骤事件 | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaName` | 组件类型：维度 |
| 试验 Id (AJO) | 试验的 ID。 | AJO 实体数据集 | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | 组件类型：维度 |
| 试验名称（AJO） | 试验的名称。 | AJO 实体数据集 | `_experience.customerJourneyManagement.entities.`<br/>`experiment.experimentName` | 组件类型：维度上下文标签：试验尝试 |
| 提取错误（AJO） | 阻止 Journey Runtime 执行提取的错误条件 | 历程步骤事件 | `_experience.journeyOrchestration.`<br/>`stepEvents.fetchError` | 组件类型：维度 |
| 发送时间是否优化（AJO） | 消息执行是否已实现 SendTimeOptimized | AJO 推送跟踪体验事件数据集、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | `_experience.customerJourneyManagement.`<br/>`messageProfile.isSendTimeOptimized` | 组件类型：维度 |
| 是测试历程（AJO） | 该事件是测试历程执行的一部分 | 历程步骤事件 | `_experience.journeyOrchestration.`<br/>`stepEvents.inTest` | 组件类型：维度 |
| 测试消息是（AJO） | 消息是否作为测试执行发送 | AJO 推送跟踪体验事件数据集、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | `_experience.customerJourneyManagement.`<br/>`messageProfile.isTestExecution` | 组件类型：维度 |
| 项目 Id (AJO) | 项目的 ID。 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | `_experience.decisioning.`<br/>`propositions.items.id` | 组件类型：维度 |
| 项目名称 (AJO) | 项目名称。 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | `_experience.decisioning.`<br/>`propositions.items.name` | 组件类型：维度 |
| 历程操作 ID | 触发 MessageExecution 的历程操作 ID。 | AJO 推送跟踪体验事件数据集、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | `_experience.customerJourneyManagement.`<br/>`messageExecution.journeyActionID` | 组件类型：维度 |
| 历程操作节点名称 (AJO) | 历程操作的节点名称。 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集，AJO 实体数据集 | 派生字段 | 组件类型：维度（派生字段） |
| 历程事件节点名称 (AJO) | 每当历程中发生区段或外部事件时，都会设置此值。 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集，AJO 实体数据集 | 派生字段 | 组件类型：维度（派生字段） |
| 历程 ID（AJO） | 历程的 ID。 | AJO 实体数据集 | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyID` | 组件类型：维度 |
| 历程名称（AJO） | 历程名称。 | AJO 实体数据集 | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyName` | 组件类型：维度 |
| 历程名称和版本（AJO） | 历程的名称和版本。 | AJO 实体数据集 | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyNameAndVersion` | 组件类型：维度 |
| 历程版本 ID（AJO） | 历程的版本 ID。 | AJO 实体数据集 | `_experience.customerJourneyManagement.entities.`<br/>`journey.journeyVersionID` | 组件类型：维度 |
| 登陆页 Id（AJO） | 登陆页面的唯一标识符。 | AJO 电子邮件跟踪体验事件数据集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.landingpage.landingPageID` | 组件类型：维度 |
| 登陆页面来源（AJO） | 登陆页面的来源。 | AJO 电子邮件跟踪体验事件数据集 | 派生字段 | 组件类型：维度（派生字段） |
| 链接 URL（AJO） | 用户点击的 URL。 | AJO 电子邮件跟踪体验事件数据集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.urlID` | 组件类型：维度 |

{style="table-layout:auto"}

#### 配置量度

可在数据视图中创建以下量度，以实现与 Journey Optimizer 中类似的量度大致对等。有关量度自定义选项的详细信息，请参阅数据视图管理器中的[组件设置](/help/data-views/component-settings/overview.md)。

| 量度 | 描述 | 数据集 | 模式元素 | 组件设置 |
| --- | --- | --- | --- | --- |
| 应用程序安装（AJO） | 应用程序安装数量 | AJO 推送跟踪体验事件数据集 | `application.installs.value` | 组件类型：量度 |
| 应用程序启动次数（AJO） | 移动设备应用程序启动次数 | AJO 推送跟踪体验事件数据集 | `application.launches.value` | 组件类型：量度 |
| 出站频道的退回率（AJO） | 出站频道退回消息总数 | AJO 消息反馈事件数据集 | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | 组件类型：量度 |
| 点击次数（AJO） | 所有渠道的点击总数 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 邮件跟踪体验事件数据集、AJO 消息反馈事件数据集 | 派生字段 | 组件类型：量度（派生字段） |
| 后备优惠数量（AJO） | 后备优惠数量。 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | `_experience.decisioning.propositions.items.`<br/>`itemSelection.selectionDetail.selectionType` | 组件类型：量度 |
| 优惠数量（AJO） | 优惠数量。 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | ` _experience.decisioning.`<br/>`propositions.items.id` | 组件类型：量度 |
| 删除量度（AJO） | 删除量度 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | `_id` | 组件类型：量度 |
| 投放日期（AJO） | 已投放的消息总数。 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | 派生字段 | 组件类型：量度（派生字段） |
| 消除（AJO） | 每次 Adobe SDK 关闭应用程序内消息时均进行计数，无论最终用户选择哪种操作来关闭它。 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | 组件类型：量度 |
| 显示次数（AJO） | 这是计算 AJO 消息的显示次数。这包括电子邮件打开次数、网页显示次数和应用程序内消息显示次数。Mobile Platform 不报告 SMS 和推送消息显示次数，因此不计算在内。 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 邮件跟踪体验事件数据集、AJO 消息反馈事件数据集 | 派生字段 | 组件类型：量度（派生字段） |
| 电子邮件打开次数（AJO） | 打开电子邮件总次数 | AJO 电子邮件跟踪体验事件数据集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | 组件类型：量度 |
| 入站点击次数（AJO） | 所有入站频道的点击总数 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | `_experience.decisioning.`<br/>`propositionEventType.interact` | 组件类型：量度 |
| 入站驳回次数（AJO） | 所有入站频道的驳回总数 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | 组件类型：量度 |
| 入站印象（AJO） | 入站频道的印象总数 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | `_experience.decisioning.`<br/>`propositionEventType.display` | 组件类型：量度 |
| 历程结束（AJO） | 如果当前步骤导致历程的一个实例结束，则为 true。给定轮廓的历程的最后一步已成功执行。 | 历程步骤事件 | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | 组件类型：量度 |
| 历程入口（AJO） | 如果步骤事件是配置文件的历程进入事件，为 True。 | 历程步骤事件 | 派生字段 | 组件类型：量度（派生字段） |
| 历程出口（AJO） | 如果当前步骤导致历程的一个实例结束，则为 true。给定轮廓的历程的最后一步已成功执行。 | 历程步骤事件 | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | 组件类型：量度 |
| 历程失败（AJO） | 给出已完成执行的步骤的当前状态。可能的值：`Transitions`（下一步将在事件过渡时发生），`EndStep`（此历程实例中的最后一步已执行），`Error`（此步骤遇到错误条件，导致当前的历程实例结束），`TimedOut`（由于获取或操作超时，当前步骤已结束）。 | 历程步骤事件 | `_experience.journeyOrchestration.`<br/>`stepEvents.stepStatus` | 组件类型：量度 |
| 登陆页面点击次数 (AJO) | 登陆页上点击总次数。 | AJO 电子邮件跟踪体验事件数据集 | 派生字段 | 组件类型：量度（派生字段） |
| 登陆页面转化（AJO） | 登陆页上的转化总数。 | AJO 电子邮件跟踪体验事件数据集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | 组件类型：量度 |
| 登陆页面查看次数（AJO） | 登陆页上浏览总次数。 | AJO 电子邮件跟踪体验事件数据集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | 组件类型：量度 |
| 节点进入 (AJO) | 如果步骤事件是配置文件的节点进入事件，为 True。 | 历程步骤事件 | 派生字段 | 组件类型：量度（派生字段） |
| 出站点击次数（AJO） | 所有出站频道的点击总数 | AJO 电子邮件跟踪体验事件数据集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | 组件类型：量度 |
| 出站错误（AJO） | 出站频道出现错误的消息总数 | AJO 消息反馈事件数据集 | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | 组件类型：量度 |
| 出站排除（AJO） | 出站频道排除事件的总数 | AJO 消息反馈事件数据集 | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | 组件类型：量度 |
| 出站发送次数（AJO） | 出站频道发送的消息总数 | AJO 消息反馈事件数据集 | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | 组件类型：量度 |
| 推送自定义操作（AJO） | 推送交互中自定义操作的总数。 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | `eventType` | 组件类型：量度 |
| 推送交互次数（AJO） | 由于直接推送消息交互而启动移动设备应用程序的次数 | AJO 推送跟踪体验事件数据集 | `application.launches.value` | 组件类型：量度 |
| 发送（AJO） | 所有渠道发送的消息总数 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | 派生字段 | 组件类型：量度（派生字段） |
| SMS 入站消息（AJO） | SMS 入站回复。例如停止、开始、订阅等等。 | AJO 推送跟踪体验事件数据集、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | `_experience.customerJourneyManagement.`<br/>`smsChannelContext.inboundMessage` | 组件类型：量度 |
| 垃圾邮件投诉（AJO） | 垃圾邮件投诉总数 | AJO 电子邮件跟踪体验事件数据集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | 组件类型：量度 |
| 订阅列表添加（AJO） | 添加至订阅列表的总数。 | AJO 电子邮件跟踪体验事件数据集 | 派生字段 | 组件类型：量度（派生字段） |
| 订阅列表删除（AJO） | 从订阅列表中删除的总数量。 | AJO 电子邮件跟踪体验事件数据集 | 派生字段 | 组件类型：量度（派生字段） |
| 已定向（AJO） | 这是计算定向到个人的建议次数。这是被视为显示给某人的建议次数。 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | 派生字段 | 组件类型：量度（派生字段） |
| 已触发 (AJO) | Adobe SDK 选择显示提案。其他因素可能会阻止其实际显示。 | AJO 推送跟踪体验事件数据集、历程步骤事件、AJO 消息反馈事件数据集、AJO 邮件跟踪体验事件数据集 | `_experience.decisioning.`<br/>`propositionEventType.trigger` | 组件类型：量度 |
| 试验中的独特访客 (AJO) | 实验中的独立访客 | AJO 实体数据集 | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | 组件类型：量度 |
| 取消订阅（AJO） | 取消订阅的总次数 | AJO 电子邮件跟踪体验事件数据集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | 组件类型：量度 |

{style="table-layout:auto"}
