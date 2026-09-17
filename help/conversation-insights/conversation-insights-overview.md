---
title: 对话分析概述
description: 了解“对话见解”的价值及术语，并了解“对话见解”的工作方式。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: 39d6847296cc385d501defda292b5b3cae98b46a
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 1%
---
# 对话分析

对话分析允许您从提供给客户的座席体验分析对话。 这些代理体验可以基于大型语言模型(LLM)或基于人类对话。 “对话见解”可以大规模分析对话，并在整个客户历程中为这些对话提供上下文。 通过对话分析，您可以了解座席对实际用户结果的影响。

对话分析可解决您可能会遇到的问题。 例如：

* 对于客户在历程上下文中与代理（LLM或人）交互时所发生的情况，您没有insight。
* 您没有能力理解：
  * 代理商对客户大规模的告知。
  * 客户如何与代理进行大规模互动。
  * 这些交互对KPI产生的总体影响是什么？
* 可创建代理式体验以适应不断变化的用户偏好。

通过对话分析，您可以了解：

* 代理告诉用户的内容。
* 用户向代理询问什么。
* 对话对您的KPI有何影响。

您可以确定代理执行指令的方式、代理遵守品牌准则的程度以及运行代理的成本是否合理。


## 概念

在Conversation Insights的高层级中，[对话](#conversation)是相互关联的[轮次](#turn)的序列。 每个轮次都可以独立传递[提示](#prompt)、[响应](#response)和[反馈](#feedback)事件。 [信号](#signal)是从对话派生的结构化观察结果，而混合数据集将源事件和信号汇集在一起以便报告。

“对话见解”分析座席在两个级别上的交互：

* [对话](#conversation)级别：用户与代理之间的完整交互，包含多个轮次。
* [翻转](#turn)级别：该对话中的一个交互循环，包含用户提示和代理响应。

代理应用程序或服务会将与对话相关的体验事件发送到Experience Platform中。 提示、响应和反馈事件数据可以独立到达。 Platform服务将这些事件关联并混合到级别记录中，可以选择使用提取的信号扩充数据，并将生成的数据用于Customer Journey Analytics报表。

### 对话

对话是用户与座席之间的完整交互。 它可以包含一个或多个车轮。

对话是容器级别或分组级别。 该容器可用于提出以下问题：

* 发生了多少次对话？
* 谈话的总体主题是什么？
* 在对话中，情绪发生了什么变化？
* 哪些对话最终导致转化？

有关实现详细信息，请参阅[实现对话见解](./conversation-insights-implement.md)文档中的[对话](./conversation-insights-implement.md#conversation)对象。

### 翻转

轮次是对话中的一个交互周期。

典型转弯包括

* 用户提示
* 代理响应
* （可选）用户反馈

转弯是报告用途的主要分析对象。 所述对话混合器服务将可用的提示、响应、反馈和信号信息组合成转级记录。

有关实施详细信息，请参阅[实施对话分析](./conversation-insights-implement.md)文档中的[turn](./conversation-insights-implement.md#turn)对象。

### 提示

提示是提交给代理的输入。 在大多数客户情景中，此输入是用户的问题、请求、说明或消息。

一个提示可以包含多个原始区段。 例如，用户输入文本并包含一个URL。

* `Prompt`
  * `"What is the capital of France"`
  * `"https://example.com/france"`

提示是对话分析可从中获取分析信息的主要输入内容，例如：

* 用户的意图
* 主题或主题
* 用户的音调
* 用户的情绪
* 其他支持的信号

有关实施详细信息，请参阅[实施对话分析](./conversation-insights-implement.md)文档中的[prompt](./conversation-insights-implement.md#prompt)对象。

### 响应

响应是指代理或其他响应方返回的内容。

响应通常包含不同类型的内容。 例如：

* 主要答案
* 引用或引用
* 链接
* 图像
* 促销内容

这种区分非常有用，因为分析需要将主要答案与支持链接、引文、广告或其他响应组件分开。

有关实现详细信息，请参阅[实现对话分析](./conversation-insights-implement.md)文档中的[响应](./conversation-insights-implement.md#response)对象。

### 反馈

反馈是用户对交互的明确评估或反应。

反馈可包含：

* 自由格式反馈文本
* 数值评级
* 评级分类
* 评级的一个或多个原因

反馈不一定与提示或响应同时提供。 用户评估完答案后，您可以稍后从代理应用程序或服务发送反馈。

有关实施详细信息，请参阅[实施对话见解](./conversation-insights-implement.md)文档中的[反馈](./conversation-insights-implement.md#feedback)对象。

### 信号

信号是对会话内容的结构化分析观察。 信号提取服务提取信号。

有关实施详细信息，请参阅[实施对话分析](./conversation-insights-implement.md)文档中的[信号](./conversation-insights-implement.md#signal)对象。


### 代理

要确定代理应用程序或服务，需要每个“对话分析”事件（提示、响应、反馈、信号）的代理信息。

#### 技能调用

如果您的座席体验应用程序支持对表示在处理期间调用的功能的技能的调用，则可以将这些技能调用添加为座席信息字段组的一部分。

有关实施详细信息，请参阅[实施对话见解](./conversation-insights-implement.md)文档中的[代理信息](./conversation-insights-implement.md#agentic-information-field-group)字段组。

## 工作原理

对话分析基于三个核心功能而构建：

* **数据收集**：使用户能够了解LLM和代理执行任务的效果。 需要收集数据才能收集所有必需的数据点。
* **信号提取和对话混合**：将非结构化提示和响应（也称为turns）转换为可报告的数据点，如意图和情绪。 这样用户就可以大规模地报告这些数据点。
* **报告**：要确定代理的有效性和ROI，请在客户历程的上下文中大规模分析对话。

下面显示了数据收集、信号提取和会话混合的总体过程。

![会话工作原理分析插图](assets/conversation-insights.png){zoomable="yes"}

| | 描述 |
|---|---|
| 1 | 您可以检测代理应用程序或服务，以创建包含提示![CommentText](/help/assets/icons2/CommentText.svg)、响应![CommentReply](/help/assets/icons2/CommentReply.svg)和反馈![反馈](/help/assets/icons2/Feedback.svg)数据集的事件。<br/>有关如何检测代理应用程序或服务的详细信息，请参阅[实施文档](./conversation-insights-implement.md)。 |
| 2 | 信号提取服务从提示![CommentText](/help/assets/icons2/CommentText.svg)、响应![CommentReply](/help/assets/icons2/CommentReply.svg)和反馈数据集![Feedback](/help/assets/icons2/Feedback.svg)中提取信号作为信号事件![OnAir](/help/assets/icons/OnAir.svg)，并将这些信号事件存储在新的数据集中。<br>此步骤作为定义[对话分析配置](./conversation-insights-configure.md)的一部分实施。 |
| 3 | 对话混合器服务将来自提示![CommentText](/help/assets/icons2/CommentText.svg)、响应![CommentReply](/help/assets/icons2/CommentReply.svg)、反馈![Feedback](/help/assets/icons2/Feedback.svg)和信号![OnAir](/help/assets/icons/OnAir.svg)事件数据集的事件混合，并将混合的![Merge](/help/assets/icons/Merge.svg)事件输出到新数据集中。<br>此步骤作为定义[对话分析配置](./conversation-insights-configure.md)的一部分实施。 |
| 4 | 混合![Merge](/help/assets/icons/Merge.svg)数据集成为连接的一部分，并且在用于混合数据集的架构中定义的组件成为数据视图的一部分。<br>此步骤作为定义[对话分析配置](./conversation-insights-configure.md)的一部分实施。 |

