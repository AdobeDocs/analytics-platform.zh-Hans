---
title: 将 Adobe Journey Optimizer 与 Customer Journey Analytics 集成
description: 引入 AJO 生成的数据，并在 CJA 中使用 Analysis Workspace 分析这些数据。
source-git-commit: b24ad572ca36bbafffcd242fe257a2113977392d
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 100%

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

可在数据视图中配置以下量度以实现与 Journey Optimizer 中类似的量度大致对等。有关如何自定义维度和量度的详细信息，请参阅数据视图管理器中的[组件设置](/help/data-views/component-settings/overview.md)。

| 指标 | 描述 | 数据视图设置 |
| --- | --- | --- |
| 退信数 | 退回的邮件数 | 使用具有以下各项设置的架构字符串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus`：<br>组件类型：量度<br>包括排除值：如果符合任何条件<br>等于：`bounce`<br>等于：`denylist` |
| 错误数 | 出错的邮件数 | 使用具有以下设置的架构字符串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus`：<br>组件类型：量度<br>包括排除值：等于`error` |
| 排除数 | 排除的邮件数 | 使用具有以下设置的架构字符串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus`：<br>组件类型：量度<br>包括排除值：等于`exclude` |
| 取消订阅次数 | 取消订阅的次数 | 使用具有以下设置的架构字符串元素 `_experience.customerJourneyManagement.messageInteraction.interactionType`：<br>组件类型：量度<br>包括排除值：等于`unsubscribe` |
| 点击量 | 邮件中点击的数量 | 使用具有以下设置的架构字符串元素 `_experience.customerJourneyManagement.messageInteraction.interactionType`：<br>组件类型：量度<br>包括排除值：等于`click` |
| 打开次数 | 打开的邮件数 | 使用具有以下设置的架构字符串元素 `_experience.customerJourneyManagement.messageInteraction.interactionType`：<br>组件类型：量度<br>包括排除值：等于`open` |
| 垃圾邮件投诉次数 | 垃圾邮件投诉的次数 | 使用具有以下设置的架构字符串元素 `_experience.customerJourneyManagement.messageInteraction.interactionType`：<br>组件类型：量度<br>包括排除值：等于`spam_complaint` |
| 成功发送的邮件数 | 成功发送的邮件数 | 使用具有以下设置的架构字符串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus`：<br>组件类型：量度<br>包括排除值：等于`sent` |
| 同步失败次数 | 同步失败的邮件的总数 | 使用具有以下设置的架构字符串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category`：<br>组件类型：量度<br>包括排除值：等于`sync` |

{style=&quot;table-layout:auto&quot;}

## 使用 Journey Optimizer 量度配置计算量度

配置要用于 Journey Optimizer 数据集的维度和量度后，还可为关于这些数据的其他见解配置[计算量度](/help/components/calc-metrics/calc-metr-overview.md)。这些计算量度基于上述在数据视图管理器中创建的量度。

| 计算量度 | 描述 | 公式 |
| --- | --- | --- |
| 发送的邮件总数 | 发送成功或失败的邮件总数 | `[Messages successfully sent]` + `[Bounces]` + `[Sync failures]` |

{style=&quot;table-layout:auto&quot;}

## Journey Optimizer 与 Customer Journey Analytics 之间在报表方面的区别

产品之间的数据差异一般为百分之 1 至 2。以下各项可能导致产品之间的差异更大：

* 处理传入数据的时间在产品之间可能稍有不同，尤其对于过去两小时内收集的数据。请使用排除今天的日期范围以缓解涉及处理时间的差异。
* “发送的邮件总数”计算量度不包括“重试次数”量度。数据集中不包括“重述次数”量度的数据，而这表示 CJA 报表中的数字可能低于 AJO 报表。但是，重试数据转换为“成功发送的邮件数”或“退信数”量度。请使用一周或更久以前的日期范围以缓解产品之间在“发送的邮件总数”量度上的差异。
