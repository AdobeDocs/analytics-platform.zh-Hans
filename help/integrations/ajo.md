---
title: 将 Adobe Journey Optimizer 与 Customer Journey Analytics 集成
description: 引入 Adobe Journey Optimizer 生成的数据，并使用 Customer Journey Analytics 中的 Analysis Workspace 对其进行分析。
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '862'
ht-degree: 100%

---

# 将 Adobe Journey Optimizer 与 Adobe Customer Journey Analytics 集成

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html) 帮助您营造紧密联系、与上下文相关且个性化的体验。它还有助于让客户了解其客户历程的下一步。

可通过执行以下步骤而导入 Journey Optimizer 生成的数据以在 Customer Journey Analytics 中执行高级分析：

## 将数据从 Journey Optimizer 发送到 Adobe Experience Platform

Adobe Experience Platform 作为中心数据源，联系 Journey Optimizer 与 Customer Journey Analytics。有关如何将 Journey Optimizer 数据发送到 Platform as a Dataset 的步骤，请参阅 Journey Optimizer 用户指南中的[开始使用数据集](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html)。

## 在 Customer Journey Analytics 中创建连接

一旦 Journey Optimizer 数据进入 Adobe Experience Platform，即可根据 Journey Optimizer 数据集[创建连接](/help/connections/create-connection.md)。或者，您可以将 Journey Optimizer 数据集添加到现有连接。

选择并配置以下数据集：

| 数据集 | 数据集类型 | 连接设置 | 描述 |
| --- | --- | --- | --- |
| AJO 消息反馈事件数据集 | 事件 | 人员 ID：`IdentityMap` | 包含消息传递事件，例如“[!UICONTROL 发送]”和“[!UICONTROL 退回]”。 |
| AJO 电子邮件跟踪体验事件数据集 | 事件 | 人员 ID：`IdentityMap` | 包含电子邮件跟踪事件，例如“[!UICONTROL 打开]”、“[!UICONTROL 点击]”和“[!UICONTROL 取消订阅]”。 |
| AJO 推送跟踪体验事件数据集 | 事件 | 人员 ID：`IdentityMap` | 包含推送跟踪事件，例如“[!UICONTROL 应用程序启动]”。 |
| 历程步骤事件 | 事件 | 人员 ID：`_experience.journeyOrchestration.`<br>`stepEvents.profileID` | 包含显示哪些配置文件参与了历程的每个节点的事件。 |
| AJO 实体数据集 | 查询 | 键：`_id`<br>匹配键：`_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | 包含将历程和营销活动元数据与所有 Adobe Journey Optimizer 事件数据相关联的分类。 |

{style="table-layout:auto"}


## 配置数据视图以容纳 Journey Optimizer 维度和量度

创建连接之后，可创建一个或多个[数据视图](/help/data-views/create-dataview.md)配置可在 Customer Journey Analytics 中找到的所需的维度和量度。

>[!NOTE]
>
>Adobe Journey Optimizer 和 Customer Journey Analytics 之间的数据差异通常小于 1-2%。过去两小时内收集到的数据可能存在较大差异。请使用排除今天的日期范围以缓解涉及处理时间的差异。


### 在数据视图中配置维度

可在数据视图中创建以下维度，以实现与 Journey Optimizer 中类似的维度大致对等。有关维度自定义选项的详细信息，请参阅数据视图管理器中的[组件设置](/help/data-views/component-settings/overview.md)。

| 维度 | 模式元素 | 组件设置 |
| --- | --- | --- |
| 历程名称 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | 组件类型：维度 |
| 历程名称和版本 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | 组件类型：维度 |
| 历程节点名称 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | 组件类型：维度 |
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

### 在数据视图中配置量度

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
| Edge 发送次数 | Edge 网络向 Web 或移动 SDK 发送消息的次数 | 使用架构字符串元素 `_experience.decisioning.propositionEventType.send` |
| 入站显示次数 | 向用户显示 Web 或应用程序内消息的次数 | 使用架构字符串元素 `_experience.decisioning.propositionEventType.display` |
| 入站点击次数 | Web 或应用程序内消息点击次数 | 使用架构字符串元素 `_experience.decisioning.propositionEventType.interact` |
| 应用程序内触发器 | 决策引擎建议应显示消息的次数。移动 SDK 可以推翻减少实际显示次数的决定。 | 使用架构字符串元素 `_experience.decisioning.propositionEventType.trigger` |
| 应用程序内解除 | SDK 从 UI 中删除应用程序内消息的次数 | 使用架构字符串元素 `_experience.decisioning.propositionEventType.dismiss` |

{style="table-layout:auto"}

### 在 Analysis Workspace 中配置计算量度

配置要用于 Journey Optimizer 数据集的维度和量度后，还可为关于这些数据的其他见解配置[计算量度](/help/components/calc-metrics/calc-metr-overview.md)。这些计算量度基于上述在数据视图管理器中创建的量度。

| 计算量度 | 描述 | 公式 |
| --- | --- | --- |
| 已发送邮件数 | 已发送邮件的总数。包括发送成功或失败的邮件。 | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| 已投放邮件数 | 已投放给客户的电子邮件数。 | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
