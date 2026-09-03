---
description: 了解如何使用Analysis Workspace中的流量可视化图表。
title: 流量概述
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
autotag-review: '2026-05-19T08:39:33.544Z'
TQID: 'https://experienceleague.adobe.com/X0VLZhluDR9Q-ax7TcTOHEcn4r0V5yu64spZlfc4fwU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 349
ht-degree: 74%

---

# 流量概述 {#flow}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_flow_button"
>title="流量"
>abstract="创建可视化图表来查看从一个检查点到下一个检查点的人员流动。"

>[!CONTEXTUALHELP]
>id="workspace_flow_panel"
>title="流量"
>abstract="分析从一个接触点到下一个接触点的访问次数或访客流量。 指定开始和结束的组件（量度、维度或项目）。 您也可以定义高级设置来进一步配置可视化图表。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文在_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;中记录了流量可视化图表。_<br/>_请参阅本文的_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**&#x200B;版本的[流量](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow)。_

>[!ENDSHADEBOX]


![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL 流量]**&#x200B;可视化图表会显示客户浏览您的网站或应用程序的路径。

使用该可视化图表可以：

* 可视化客户浏览您的网站或应用程序的历程。
* 分析客户在指定检查点（例如入口、特定维度或退出）之前和之后的去向。
* 在选定路径中指定一个特定点来创建区段。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [创建流量可视化图表](https://experienceleague.adobe.com/zh-hans/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/flow-visualization){target="_blank"}以观看演示视频。

{{videoaa}}

>[!ENDSHADEBOX]


## 维度间流量

您可以显示[维度间的流量](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)。 例如，您可以在一个图表中合并页面和部门。 在这种情况下，您的流量可能会从主页转到男士页面，然后转到鞋类部门。

每列可显示不同的维度。 将一个维度拖放到拖放区域中，以将该维度添加到图中。

>[!MORELIKETHIS]
>
>[配置流量可视化图表](/help/analysis-workspace/visualizations/c-flow/create-flow.md)。
>

## 在“流量”、“流失”或“历程”画布可视化图表之间进行选择

流量可视化图表与[流失可视化图表](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)和[历程画布可视化图表](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)有相似之处，但也存在重要区别。

### 了解这些差异

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### 何时使用流量

流程可视化图表最适合于：

* 对路径上的下一个接触点进行探索性、临时性分析。 （对于具有预定义页面顺序的历程，或使用最终路径的历程，请使用历程画布。）

* 具有多个入口点和路径的非线性历程。 （对于具有预定义页面顺序的历程，请使用历程画布。）

使用[上述表格](#understand-the-differences)来了解流量、流失和历程画布之间的区别。
