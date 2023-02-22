---
title: 将Adobe Journey Optimizer(AJO)与Customer Journey Analytics(CJA)集成
description: 引入 AJO 生成的数据，并在 CJA 中使用 Analysis Workspace 分析这些数据。
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
source-git-commit: 3a4dbe9a87f8e195a4daf78423d29d73f2be0f83
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 53%

---

# 将 Adobe Journey Optimizer 与 Customer Journey Analytics 集成

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html) 帮助您营造紧密联系、与上下文相关且个性化的体验。它还有助于让客户了解其客户历程的下一步。

可通过执行以下步骤而导入 Journey Optimizer 生成的数据以在 Customer Journey Analytics 中执行高级分析：

## 将数据从 Journey Optimizer 发送到 Adobe Experience Platform

Adobe Experience Platform 作为中心数据源，联系 Journey Optimizer 与 Customer Journey Analytics。有关如何将 Journey Optimizer 数据发送到 Platform as a Dataset 的步骤，请参阅 Journey Optimizer 用户指南中的[开始使用数据集](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html)。

## 在 Customer Journey Analytics 中创建连接

一旦 Journey Optimizer 数据进入 Adobe Experience Platform，即可根据 Journey Optimizer 数据集[创建连接](/help/connections/create-connection.md)。选择已发送到 Platform 的数据集。

## 配置数据视图以容纳 Journey Optimizer 维度和量度

创建连接之后，可创建一个或多个[数据视图](/help/data-views/create-dataview.md)配置可在 Customer Journey Analytics 中找到的所需的维度和量度。

>!![NOTE]
AJO和CJA之间的数据差异通常不到1%到2%。 对于过去两小时内收集的数据，可能会出现较大的差异。 请使用排除今天的日期范围以缓解涉及处理时间的差异。

### 在数据视图中配置维度

您可以在数据视图中创建以下维度，以便与Journey Optimizer中的类似维度实现近似对等。 请参阅 [组件设置](/help/data-views/component-settings/overview.md) （在数据视图管理器中），以了解有关维度自定义选项的详细信息。

| 维度 | 架构元素 | 组件设置 |
| --- | --- | --- |
| 历程名称 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | 组件类型：Dimension |
| 历程名称和版本 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | 组件类型：Dimension |
| 历程节点名称 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | 组件类型：Dimension |
| 历程节点类型 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | 组件类型：Dimension |
| 营销活动名称 | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | 组件类型：Dimension |
| 渠道 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | 组件类型：Dimension |
| 推送标题 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | 组件类型：Dimension |
| 邮件主题 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | 组件类型：Dimension |
| 链接标签 | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | 组件类型：Dimension |
| 实验名称 | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | 组件类型：Dimension<br>上下文标签：实验实验 |
| 处理名称 | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | 组件类型：Dimension<br>上下文标签：实验变体 |
| 电子邮件投放失败的原因 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | 组件类型：Dimension |
| 电子邮件投放排除原因 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | 组件类型：Dimension |

{style=&quot;table-layout:auto&quot;}

### 在数据视图中配置量度

可在数据视图中配置以下量度以实现与 Journey Optimizer 中类似的量度大致对等。请参阅 [组件设置](/help/data-views/component-settings/overview.md) ，以了解有关量度自定义选项的详细信息。

| 指标 | 描述 | 架构元素 | 组件设置 |
| --- | --- | --- | --- |
| 退信数 | 退回的邮件数，包括立即退回和投放后退回。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 组件类型：量度<br>包括排除值：如果满足任何标准<br>等于： `bounce`，等于： `denylist` |
| 投放后退回 | 某些电子邮件服务会报告已发送的电子邮件，然后稍后将其退回。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | 组件类型：量度<br>包括排除值：等于 `async` |
| 电子邮件点击量 | 邮件中点击的数量. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 组件类型：量度<br>包括排除值：等于 `click` |
| 电子邮件打开次数 | 打开的邮件数. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 组件类型：量度<br>包括排除值：等于 `open` |
| 错误数 | 出错的邮件数。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 组件类型：量度<br>包括排除值：等于 `error` |
| 排除数 | 排除的邮件数。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 组件类型：量度<br>包括排除值：等于 `exclude` |
| 发送 | 电子邮件提供商接受的邮件数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 组件类型：量度<br>包括排除值：等于 `sent` |
| 垃圾邮件投诉 | 垃圾邮件投诉的次数. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 组件类型：量度<br>包括排除值：等于 `spam_complaint` |
| 取消订阅次数 | 取消订阅的次数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 组件类型：量度<br>包括排除值：等于 `unsubscribe` |

{style=&quot;table-layout:auto&quot;}

### 在Analysis Workspace中配置计算量度

配置要用于 Journey Optimizer 数据集的维度和量度后，还可为关于这些数据的其他见解配置[计算量度](/help/components/calc-metrics/calc-metr-overview.md)。这些计算量度基于上述在数据视图管理器中创建的量度。

| 计算量度 | 描述 | 公式 |
| --- | --- | --- |
| 已发送的消息 | 已发送的消息总数。 包括成功或失败的消息。 | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| 投放的消息 | 发送给客户的电子邮件数量。 | `[Sends] - [Bounces After Delivery]` |

{style=&quot;table-layout:auto&quot;}
