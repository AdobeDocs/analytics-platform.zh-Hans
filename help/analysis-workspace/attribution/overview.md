---
title: 归因概述
description: 将成功事件的点数归因到多个维度项目的概念。
exl-id: 845b4310-e1b2-4690-b267-6f6d211845fb
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 93%

---

# 归因概述

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 略有不同。[了解更多...](/help/getting-started/cja-aa.md)

通过归因，分析师能够自定义维度项目获取成功事件点数的方式。例如：

1. 网站访客单击指向您的某个产品页面的付费搜索链接。他们将产品添加到购物车，但不购买。
2. 第二天，他们查看自己朋友的社交媒体帖子，单击链接，然后完成购买。

在某些报表中，您可能希望将订单归因到“付费”搜索。在其他报表中，您可能希望将订单归因到社交。通过归因，您能够控制报表对的各个方面。它适用于 Adobe Analytics Ultimate、Prime、Select 和 Foundation 上的所有组织。如果您不确定您与 Adobe 签订的合同类型，请联系贵组织的客户经理。

## 归因 IQ 的价值

给定的客户历程不是线性的，而且往往难以预测。每位客户按各自的进度进行；通常，它们会再次返回、延迟、重新启动或参与其他非线性行为。这些免费操作使得我们很难了解营销工作在整个客户历程中所产生的影响。它还会妨碍将多个数据渠道绑定在一起的工作。

![归因 IQ 问题](assets/attribution_iq_problem.png)

Adobe Analytics 通过让您能够执行以下操作来增强归因：

* 定义付费媒体之外的归因：可将任何维度、量度、渠道或事件应用于模型（例如内部搜索），而不仅仅是营销活动。
* 使用无限制的归因模型比较：动态比较任意所需数量的模型。
* 避免实施更改：使用报表时间处理和上下文感知会话，可在运行时构建并应用客户历程上下文。
* 构建与您的归因方案最匹配的会话。
* 按过滤器划分归因：轻松比较营销渠道在任何重要过滤器（例如，新客户与回访客户、产品X与产品Y、忠诚度级别或CLV）中的表现。
* 检查渠道交叉和多接触点分析：使用维恩图和直方图，以及趋势归因结果。
* 直观地分析关键营销序列：通过多节点流量和流失可视化图表，以可视方式探索导致转化的路径。
* 构建计算量度：使用任意数量的归因分配方法。

## 功能

归因 IQ 包括以下功能：

* [归因面板](../c-panels/attribution.md)：获取任何维度和量度，并快速将其与不同的归因模型进行比较。
* [将归因应用于度量](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)：对项目中的任何量度使用非默认归因。
* [将归因应用于细分](/help/components/dimensions/t-breakdown-fa.md)：对细分使用非默认归因。
* [比较归因模型](/help/components/apply-create-metrics.md)：快速了解任何量度的不同归因模型的异同。
