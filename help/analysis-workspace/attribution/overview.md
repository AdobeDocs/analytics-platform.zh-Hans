---
title: 归因概述
description: 将成功事件的信用归因到多维值的概念。
translation-type: tm+mt
source-git-commit: 05bc0b378c962f4513ab292d518e32f5f70f7dfd
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 50%

---


# 归因概述

>[!NOTE] 您正在查看Customer Journey Analytics中的Analysis Workspace文档。 其功能集与传统Adobe [Analytics的Analysis Workspace略有不同](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html)。 [了解更多...](/help/getting-started/cja-aa.md)

Attribution使分析师能够自定义维度值如何为成功事件赢得赞誉。 例如：

1. 网站访客单击指向您的某个产品页面的付费搜索链接。 将产品添加到购物车，但不购买。
2. 第二天，查看其朋友的社交媒体帖子，单击链接，然后完成购买。

在某些报表中，您可能希望订单归属于“付费”搜索。 在其他报表中，您可能希望订单归属于社交。 Attribution允许您控制报告的这一方面。 它适用于AdobeAnalytics旗舰店、Prime、Select和Foundation的所有组织。 如果您不确定您与Adobe的合同类型，请与贵组织的客户经理联系。

## 归因IQ的价值

给定的客户历程不是线性的，而且往往难以预测。每位客户按各自的进度进行；通常，它们会再次返回、延迟、重新启动或参与其他非线性行为。这些免费操作使得我们很难了解营销工作在整个客户历程中所产生的影响。它还会妨碍将多个数据渠道绑定在一起的工作。

![归因 IQ 问题](assets/attribution_iq_problem.png)

Adobe Analytics 通过让您能够执行以下操作来增强归因：

* 定义付费媒体之外的归因：可将任何维度、量度、渠道或事件应用于模型（例如内部搜索），而不仅仅是营销活动。
* 使用无限制的归因模型比较：动态比较任意所需数量的模型。
* 避免实施更改：使用报表时间处理和上下文感知会话，可在运行时构建并应用客户历程上下文。
* 构建与您的归因方案最匹配的会话。
* 按区段划分归因：轻松对所有重要区段中的营销渠道效果进行比较（例如新客户与老客户、产品 X 与产品 Y、忠诚度级别或 CLV）。
* 检查渠道交叉和多接触点分析：使用维恩图和直方图，以及趋势归因结果。
* 直观地分析关键营销序列：通过多节点流量和流失可视化图表，以可视方式探索导致转化的路径。
* 构建计算量度：使用任意数量的归因分配方法。

## 功能

归因 IQ 包括以下功能：

* [归因面板](../c-panels/attribution.md): 获取任何维度和指标，并快速将其与不同的归因模型进行比较。
* [将归因应用于度量](../build-workspace-project/column-row-settings/column-settings.md): 对项目中的任何度量使用非默认属性。
* [将归因应用于细分](/help/components/dimensions/t-breakdown-fa.md): 对细分使用非默认属性。
* [比较归因模型](/help/components/apply-create-metrics.md): 快速了解不同归因模型对任何指标的比较情况。
