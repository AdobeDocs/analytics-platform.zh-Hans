---
description: 了解如何在Analysis Workspace中使用旅程画布。
title: 历程画布概述
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '1996'
ht-degree: 99%

---

# 历程画布概述 {#journey-canvas-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_button"
>title="历程画布"
>abstract="显示人们如何完成或退出一系列接触点。用于具有多个入口点和路径的历程，或分析在 Journey Optimizer 中创建的历程。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_panel"
>title="历程画布"
>abstract="分析人们如何完成或退出既定的历程。创建由节点和箭头构成的灵活图表来代表事件、维度项和区段之间的任意组合，从而生成用户历程分析。拖动画布上的节点来重新排列历程的事件和条件。当您进行该操作时，数据会相应更新。<br/><br/>有权访问 Adobe Journey Optimizer 的客户可以分析现有的 Journey Optimizer 历程。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_button"
>title="历程画布"
>abstract="显示人们如何完成或退出一系列接触点。用于具有多个入口点和路径的历程，或分析在 Journey Optimizer 中创建的历程。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_panel"
>title="历程画布"
>abstract="分析人们如何完成或退出既定的历程。创建由节点和箭头构成的灵活图表来代表事件、维度项和区段之间的任意组合，从而生成用户历程分析。拖动画布上的节点来重新排列历程的事件和条件。当您进行该操作时，数据会相应更新。<br/><br/>有权访问 Adobe Journey Optimizer 的客户可以分析现有的 Journey Optimizer 历程。"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_本文记录了_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;中的历程画布可视化图表。<br/>**Adobe Analytics** 中没有等效的可视化图表。_

>[!ENDSHADEBOX]

历程画布可视化图表可帮助您进行分析，并深入了解您为用户和客户提供的历程。它允许您从头开始定义历程，或从 Journey Optimizer 中查看历程，然后查看人们是如何离开（流失）或继续完成（流过）这个历程的。

您可以通过任意组合事件、维度项、区段和日期范围来创建历程节点，从而[构建用户历程分析](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。通过连接各个节点来创建历程的流量，并包含多条路径和决策点。拖动画布上的节点来重新排列历程的事件和条件。当您进行更改时，数据会实时更新。

[节点会](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes)以“最终路径”的形式连接，这意味着只要访问者最终从一个节点移动到另一个节点，无论这两个节点之间发生任何事件，都会被计算在内。用户沿路径移动的时间由容器设置决定。

![历程画布](assets/journey-canvas.png)

## 主要功能

历程画布可视化图表的主要功能包括：

* 深入分析流失和流过情况，以适应最复杂的用户历程。

* 用于映射以及对用户历程的各个入口点、节点和路径进行可视化的画布。

* 通过拖放操作，将组件添加到画布上，并重新定位现有节点。

* 可以选择在历程画布中构建用户历程分析，或根据 Journey Optimizer 历程自动创建用户历程分析。

## 潜在洞察

历程画布可为最复杂的历程提供可操作洞察。

### 转化率最高的路径 {#conversion-rate-caption}

历程画布中最突出的洞察会以标题的形式在画布顶端显示。

此标题总结了历程中的哪些路径的转化率最高。

当历程中包含多个起始节点时，标题如下所示：

![历程画布洞察标题](assets/journey-canvas-caption.png)

当历程包含单个起始节点时，标题如下所示：

![历程画布洞察标题（单一起始节点）](assets/journey-canvas-caption-singlestart.png)

解释此标题时请考虑以下几点：

* _路径_&#x200B;被定义为由箭头连接的一个起始节点和一个终止节点，其间可连接任意数量的节点。

* 转化率的计算取决于历程的类型（历程中包含的起始节点和终止节点的数量，以及它们之间的路径是否相交）。

  下表描述了如何根据历程类型计算转换率：

  | 历程类型 | 转化率计算 | 示例 |
  |---------|----------|---------|
  | **单个起始节点和单个终止节点** | 转化率是通过将终止节点的数量除以起始节点的数量来计算的。 | ![有多个起点并汇聚到一个共同节点的历程](assets/journey-canvas-single-path.png) |
  | **单个起始节点和多个终止节点** | 转化率的计算方法是找到数值最高的终止节点，然后将该数字除以起始节点的数值。 | ![有多个起点并汇聚到一个共同节点的历程](assets/journey-canvas-singlestart-multiend.png) |
  | **多个独立路径，其中每个路径均包含一个起始节点和一个终止节点** | 转化率是通过将终止节点的数量除以起始节点的数量来计算的。标题中描述了转化率最高的路径。 | ![有多个起点并汇聚到一个共同节点的历程](assets/journey-canvas-multi-start-separate.png) |
  | **在历程中的任何一点，汇聚到一个共同的节点的多个起始节点** | 转化率的计算方法是找到数值最高的终止节点，并将该数字除以具有最低数值的开始节点的数值来计算的。 | ![有多个起点并汇聚到一个共同节点的历程](assets/journey-canvas-multi-start-converge.png) |

### 流过、流失等

以下是历程画布可帮助提供的其他洞察的几个示例。您可以选择这些洞察是基于数据视图中的所有人员、开始历程的所有人员，还是历程前一个节点的所有人员。

#### 流过

* 完成历程（到达终止节点）的人数和百分比

* 到达历程中某一节点的人数和百分比

* 在历程的某个给定节点之前或之后最常见的步骤

#### 流失

* 在历程中，人们最常流失（即从未到达任何紧邻的下一个节点）的节点

#### 每个节点的附加数据

* 在历程的任何节点上添加一个细分维度，以查看该特定节点的其他数据

## 在“历程画布”、“流失”或“流量”可视化图表之间进行选择

历程画布可视化图表与[流失可视化图表](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)和[流量可视化图表](/help/analysis-workspace/visualizations/c-flow/flow.md)有相似之处，但也存在重要区别。

### 了解这些差异

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### 何时使用历程画布

历程画布对于以下方面至关重要：

* 涉及具有多个入口点和路径的历程的流失分析。

* 具有多个入口点和路径的非线性历程，其中带有预定义的页面序列。

* 基于预定义历程的探索性、临时性分析。

* 需要除会话、人员或发生次数之外的主要量度的分析。

* 对源自 Adobe Journey Optimizer 的历程进行更深入的分析。

使用[上述表格](#understand-the-differences)来了解历程画布、流失和流量可视化图表之间的区别。

## 分析 Journey Optimizer 历程

>[!NOTE]
>
>如果您的组织无法访问 Journey Optimizer，您仍然可以[在历程画布中构建分析](#build-analyses-in-customer-journey-analytics)。

分析历程画布中的 Journey Optimizer 历程可以提供有关人们如何与历程互动的深入、可操作洞察。

当您在历程画布中分析 Journey Optimizer 历程时，历程将会以与 Journey Optimizer 中相同的顺序、序列和结构显示。如果您对历程画布中的历程进行了重大更改，则[&#x200B; Journey Optimizer 中的更改将不再同步](#synchronization-between-journey-optimizer-and-journey-canvas)。

### 使用历程画布分析 Journey Optimizer 历程的好处

历程画布可提供 Journey Optimizer 无法实现的深入、彻底的分析。

使用历程画布分析在 Journey Optimizer 中创建的历程可带来多种好处：

* 可使用任何 Customer Journey Analytics 维度、量度、区段或日期范围创建事件。

  在 Journey Optimizer 中，技术用户必须先创建一个事件，然后才能将其添加到历程中。

* 可根据您创建的自定义节点创建受众（启动 Customer Journey Analytics 受众生成器）。

  在 Journey Optimizer 中，您只能为预定义的活动创建受众。

* 分析流过和流失情况

* 以任意维度细分事件

* 合并事件

* 连接事件

* 重命名和删除事件

* 更多

### Journey Optimizer 与历程画布之间的同步

考虑以下行为，了解 Journey Optimizer 和 Journey 画布之间的同步：

* **数据同步仅为单向**

  在历程画布中创建对 Journey Optimizer 历程的分析后，数据仅在一个方向进行同步，即从 Journey Optimizer 到历程画布进行同步。这意味着在历程画布中对历程所做的更改不会反映在 Journey Optimizer 中。

* **在历程画布中更改历程会停止同步**

  [仅当历程画布中的历程没有发生重大修改时，对 Journey Optimizer 中的历程所做的更改才会同步到历程画布](#differences-after-modifying-a-journey-in-journey-canvas)。在历程画布中修改历程后，您在 Journey Optimizer 中对历程所做的任何更改都不会反映在历程画布中。要查看历程画布中所反映的更改，您可以删除并[重新创建历程画布中的历程](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

* **使用“与任何人共享”链接需要在 Journey Optimizer 中进行更改后将项目保存在 Customer Journey Analytics 中**

  使用“与任何人共享”链接时，Journey Optimizer 中所做的更改不会反映在历程画布中，直到项目被保存在 Customer Journey Analytics 中。

  有关“与任何人共享”链接的更多信息，请参阅[共享项目](/help/analysis-workspace/curate-share/share-projects.md)中的[与任何人共享项目（无需登录）](/help/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required)。

### 在历程画布中修改历程后的差异 {#differences-after-modifying}

在历程画布中修改 Journey Optimizer 历程后，数据处理、可用功能和同步行为可能会发生变化。

如果您对历程画布中的 Journey Optimizer 历程进行了重大的修改，则数据处理、可用功能和同步行为可能会发生变化。重大修改包括以下任何一项：

* 添加或移除节点

* 在节点之间添加或删除箭头

* 更改节点上的组件

如果您对历程画布中的 Journey Optimizer 历程进行了其他更改，例如拖动节点或添加细分，则以下部分中描述的差异不适用。

>[!NOTE]
>
>要将历程恢复到原始状态，您可以在历程画布中进行第一次更改后按 Ctrl+z。或者，您可以删除并[在历程画布中重新创建历程](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

#### 数据处理差异

在历程画布中修改 Journey Optimizer 历程后，如果您的历程包含具有非默认归因模型的量度，那么您可能会注意到数据发生变化。

这是因为，与 Journey Optimizer 不同，历程画布允许您在一次历程中应用多个维度。此功能意味着[量度归因](/help/data-views/component-settings/attribution.md)功能不受支持。

#### 功能差异

在历程画布中更改 Journey Optimizer 历程后，[!UICONTROL **箭头设置**]&#x200B;下拉字段中可用的选项会根据您的更改内容而发生变化。有关更多信息，请参阅[配置设置](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

[!UICONTROL **节点类型**]&#x200B;字段仅在 Journey Optimizer 中可用。在历程画布中查看 Journey Optimizer 历程时，无论您是否在历程画布中对历程进行了修改，此功能均不可用。

#### 同步差异

仅当历程在历程画布中保持不变时，对 Journey Optimizer 中的历程所做的更改才会同步到历程画布。

在历程画布中修改 Journey Optimizer 历程后，您在 Journey Optimizer 中对历程所做的任何更改都不会反映在历程画布中。要查看历程画布中所反映的更改，您可以删除并[重新创建历程画布中的历程](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

### Journey Optimizer 与 Customer Journey Analytics 之间的术语差异

在 Journey Optimizer 中，某些术语会表示一种含义，而在 Customer Journey Analytics 中，它们则会表示另一种含义。在使用历程画布时，会使用 Customer Journey Analytics 术语。

| 术语 | 历程画布 | Journey Optimizer |
|---------|----------|---------|
| **事件** |  Customer Journey Analytics 中提供的几种标准量度之一。该量度会计入收入、订阅或产生的商机等。 | 触发个性化历程的活动类别，例如在线购买。 |

### 在历程画布中分析 Journey Optimizer 历程

有关在历程画布中分析 Journey Optimizer 历程的信息，请参阅[配置历程画布可视化图表](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

## 在历程画布中构建分析

您可以在历程画布中构建基于 Analysis Workspace 中可用的任何维度或量度的分析。或者，您可以分析在 Journey Optimizer 中创建的历程。有关详细信息，请参阅[配置历程画布可视化图表](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。


>[!MORELIKETHIS]
>
> * [Adobe Customer Journey Analytics 中的历程画布可视化图表指南](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-guide-to-journey-canvas-visualization-in-adobe-customer/ba-p/737857?profile.language=zh-Hans)

