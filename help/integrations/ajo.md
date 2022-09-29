---
title: 将Adobe Journey Optimizer与Customer Journey Analytics集成
description: 在CJA中使用Analysis Workspace导入AJO生成的数据并对其进行分析。
source-git-commit: 28bc99a7f5ec7b280fd26a7a45dc076e67f652dc
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 2%

---


# 将Adobe Journey Optimizer与Customer Journey Analytics集成

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=zh-Hans) 帮助您提供连接、情境和个性化的体验。 它有助于让您的客户进入其客户历程的下一步。

您可以通过执行以下步骤，导入Journey Optimizer生成的数据，以在Customer Journey Analytics中执行高级分析：

## 将数据从Journey Optimizer发送到Adobe Experience Platform

Adobe Experience Platform用作Journey Optimizer和Customer Journey Analytics之间的中央数据源和链接。 请参阅 [数据集入门](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html) 有关如何将Journey Optimizer数据作为数据集发送到Platform的步骤，请参阅Journey Optimizer用户指南。

## 在Customer Journey Analytics中创建连接

将Journey Optimizer数据放入Adobe Experience Platform后，您可以 [创建连接](/help/connections/create-connection.md) 基于您的Journey Optimizer数据集。 选择您发送到Platform的数据集。

## 配置数据视图以适应Journey Optimizer维度和量度

创建连接后，可以创建一个或多个 [数据视图](/help/data-views/create-dataview.md) ，以配置所需的Customer Journey Analytics和量度。

您可以在数据视图中创建以下量度，以便与Journey Optimizer中的类似量度实现大致对等。 请参阅 [组件设置](/help/data-views/component-settings/overview.md) 中，以了解有关如何自定义维度和量度的详细信息。

| 指标 | 描述 | 数据视图设置 |
| --- | --- | --- |
| 跳出次数 | 退回的邮件数 | 使用架构字符串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` 设置：<br>组件类型：量度<br>包括排除值：如果满足任何标准<br>等于： `bounce`<br>等于： `denylist` |
| 错误 | 出错的消息数 | 使用架构字符串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` 设置：<br>组件类型：量度<br>包括排除值：等于 `error` |
| 不包含 | 排除的消息数 | 使用架构字符串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` 设置：<br>组件类型：量度<br>包括排除值：等于 `exclude` |
| 取消订阅 | 取消订阅的计数 | 使用架构字符串元素 `_experience.customerJourneyManagement.messageInteraction.interactionType` 设置：<br>组件类型：量度<br>包括排除值：等于 `unsubscribe` |
| 点击 | 消息内的点击次数计数 | 使用架构字符串元素 `_experience.customerJourneyManagement.messageInteraction.interactionType` 设置：<br>组件类型：量度<br>包括排除值：等于 `click` |
| 打开 | 已打开的消息数 | 使用架构字符串元素 `_experience.customerJourneyManagement.messageInteraction.interactionType` 设置：<br>组件类型：量度<br>包括排除值：等于 `open` |
| 垃圾邮件投诉 | 垃圾邮件投诉计数 | 使用架构字符串元素 `_experience.customerJourneyManagement.messageInteraction.interactionType` 设置：<br>组件类型：量度<br>包括排除值：等于 `spam_complaint` |
| 消息已成功发送 | 成功发送的消息数 | 使用架构字符串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` 设置：<br>组件类型：量度<br>包括排除值：等于 `sent` |
| 同步失败 | 无法同步的消息总数 | 使用架构字符串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category` 设置：<br>组件类型：量度<br>包括排除值：等于 `sync` |

## 使用Journey Optimizer量度配置计算量度

为Journey Optimizer数据集配置所需的维度和量度后，您还可以配置 [计算量度](/help/components/calc-metrics/calc-metr-overview.md) 以了解有关该数据的其他分析。 这些计算量度基于在数据视图管理器中创建的上述量度。

| 计算量度 | 描述 | 公式 |
| --- | --- | --- |
| 已发送邮件总数 | 已发送、成功或失败的消息总数 | `[Messages successfully sent]` + `[Bounces]` + `[Sync failures]` |

## Journey Optimizer和Customer Journey Analytics之间的报表差异

产品之间的数据差异通常介于1%到2%之间。 产品之间差异较大，可能归因于以下原因：

* 不同产品对传入数据的处理时间可能略有不同，尤其是对于过去两小时内收集的数据。 使用不包括今天的日期范围来缓解涉及处理时间的差异。
* 计算量度“发送的消息总数”不包含“重试”量度。 “重试”量度的数据未包含在数据集中，因此与AJO报表相比，CJA报表中显示的数字可能会较低。 但是，重试数据会聚合到“消息已成功发送”或“跳出次数”量度中。 使用一周或更早的日期范围来缓解产品之间“已发送邮件总数”量度存在的差异。
