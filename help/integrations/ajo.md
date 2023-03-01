---
title: 将 Adobe Journey Optimizer (AJO) 与 Customer Journey Analytics (CJA) 集成
description: 引入 AJO 生成的数据，并在 CJA 中使用 Analysis Workspace 分析这些数据。
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
source-git-commit: 9aed4e724c564272071b96c037f4eb0e82572e6f
workflow-type: ht
source-wordcount: '647'
ht-degree: 100%

---

# 将 Adobe Journey Optimizer 与 Customer Journey Analytics 集成

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html) 帮助您营造紧密联系、与上下文相关且个性化的体验。它还有助于让客户了解其客户历程的下一步。

可通过执行以下步骤而导入 Journey Optimizer 生成的数据以在 Customer Journey Analytics 中执行高级分析：

## 将数据从 Journey Optimizer 发送到 Adobe Experience Platform

Adobe Experience Platform 作为中心数据源，联系 Journey Optimizer 与 Customer Journey Analytics。有关如何将 Journey Optimizer 数据发送到 Platform as a Dataset 的步骤，请参阅 Journey Optimizer 用户指南中的[开始使用数据集](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html)。

## 在 Customer Journey Analytics 中创建连接

一旦 Journey Optimizer 数据进入 Adobe Experience Platform，即可根据 Journey Optimizer 数据集[创建连接](/help/connections/create-connection.md)。选择已发送到 Platform 的数据集。

## 配置数据视图以容纳 Journey Optimizer 维度和度量

创建连接之后，可创建一个或多个[数据视图](/help/data-views/create-dataview.md)配置可在 Customer Journey Analytics 中找到的所需的维度和度量。

>!![NOTE]
>AJO 和 CJA 之间的数据差异通常小于 1-2%。过去两小时内收集到的数据可能存在较大差异。请使用排除今天的日期范围以缓解涉及处理时间的差异。

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

{style="table-layout:auto"}

### 在数据视图中配置度量

可在数据视图中创建以下度量，以实现与 Journey Optimizer 中类似的度量大致对等。有关度量自定义选项的详细信息，请参阅数据视图管理器中的[组件设置](/help/data-views/component-settings/overview.md)。

| 度量 | 描述 | 模式元素 | 组件设置 |
| --- | --- | --- | --- |
| 退信数 | 退回的邮件数，包括立即退回和投放后退回。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 组件类型：度量<br>包括排除值：如果满足任意条件<br>等于：`bounce`，等于：`denylist` |
| 投放后退回 | 一些电子邮件服务会报告电子邮件已投放，稍后再将其退回。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | 组件类型：度量<br>包括排除值：等于 `async` |
| 电子邮件点击数 | 邮件中的点击数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 组件类型：度量<br>包括排除值：等于 `click` |
| 电子邮件打开次数 | 打开的邮件数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 组件类型：度量<br>包括排除值：等于 `open` |
| 错误数 | 出错的邮件数。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 组件类型：度量<br>包括排除值：等于 `error` |
| 排除数 | 排除的邮件数。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 组件类型：度量<br>包括排除值：等于 `exclude` |
| 发送次数 | 电子邮件提供商接受的邮件数。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 组件类型：度量<br>包括排除值：等于 `sent` |
| 垃圾邮件投诉次数 | 垃圾邮件投诉的次数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 组件类型：度量<br>包括排除值：等于 `spam_complaint` |
| 取消订阅次数 | 取消订阅的次数。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 组件类型：度量<br>包括排除值：等于 `unsubscribe` |

{style="table-layout:auto"}

### 在 Analysis Workspace 中配置计算度量

配置要用于 Journey Optimizer 数据集的维度和度量后，还可为关于这些数据的其他见解配置[计算度量](/help/components/calc-metrics/calc-metr-overview.md)。这些计算度量基于上述在数据视图管理器中创建的度量。

| 计算度量 | 描述 | 公式 |
| --- | --- | --- |
| 已发送邮件数 | 已发送邮件的总数。包括发送成功或失败的邮件。 | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| 已投放邮件数 | 已投放给客户的电子邮件数。 | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
