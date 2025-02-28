---
description: 了解流量功能，该功能可显示客户浏览您的网站和应用程序的路径。
title: 流量概述
feature: Visualizations
exl-id: 2ef325d9-1d82-46c9-86e3-6b2332548823
role: User
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 25%

---

# 流量 {#flow}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_flow_button"
>title="流量"
>abstract="创建可视化效果来查看从一个检查点到下一个检查点的人员流动。"

>[!CONTEXTUALHELP]
>id="workspace_flow_panel"
>title="流量"
>abstract="分析从一个接触点到下一个接触点的访问或访客流量。 指定要以开始和结束的组件（量度、维度或项目）。 或者，您可以定义高级设置以进一步配置可视化图表。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文记录了_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;中的流量可视化图表。_<br/>_查看本文的_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;版本的[流程](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/flow/flow)。_

>[!ENDSHADEBOX]


![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL 流量]**&#x200B;可视化图表显示客户浏览您的网站和应用程序的路径。

通过可视化，您可以：

* 可视化客户浏览您的网站或应用程序的历程。
* 分析客户在所指定检查点（例如登入、特定维度或退出）之前和之后的位置。
* 通过在选定路径中指定一个特定点来创建过滤器。


>[!BEGINSHADEBOX]

查看![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [为演示视频创建流量可视化图表](https://video.tv.adobe.com/v/346063/?quality=12&learn=on){target="_blank"}。

{{videoaa}}

>[!ENDSHADEBOX]


## 维度间流量

您可以显示[维度间的流量](/help/analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)。例如，您可以在一个图表中合并多个页面和部门。在这种情况下，您的流量可能从主页转到“男士”页面，然后转到“鞋类”部门。

每一列可显示一个不同的维度。在拖放区域中对维度进行拖放，以将该维度添加到图表。

>[!MORELIKETHIS]
>
>[配置流量可视化图表](/help/analysis-workspace/visualizations/c-flow/create-flow.md)。
>

## 在“流量”、“流失”或“历程画布”可视化之间选择

流量可视化图表与[流失可视化图表](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)和[历程画布可视化图表](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)相似，但存在重要差异。

### 了解差异

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### 何时使用流量

流量可视化图表最适合：

* 探索性的Ad Hoc Analysis，了解路径上的下一个即时接触点。 (对于具有预定义历程序列的旅程，或者使用最终路径的旅程，请使用页面画布。)

* 具有多个入口点和路径的非线性历程。 (对于具有预定义历程序列的旅程，使用页面画布。)

使用[上表](#understand-the-differences)了解“流量”、“流失”和“历程”画布之间的区别。
