---
description: 历程画布概述
title: 历程画布
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 820251833eae9fed1574a0010f726b0ba6e12cd1
workflow-type: tm+mt
source-wordcount: '1654'
ht-degree: 1%

---

# 历程画布概述

历程画布可视化图表允许您分析提供给用户和客户的旅程，并获取有关这些旅程的深入见解。 它允许您从头开始定义旅程或从Journey Optimizer查看旅程，然后查看人员如何离开（流失）或继续通过（流过）旅程。

您可以[通过使用事件、维度项、过滤器和日期范围的任意组合来创建用户旅程](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)的分析以创建旅程节点。 连接节点以创建历程流，并包含多个路径和决策点。 拖动画布上的节点以重新排列历程的事件和条件。 在进行更改时实时更新数据。

[节点已连接](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes)作为“最终路径”，这意味着只要访客最终从一个节点移动到另一个节点，就会计入访客，而不考虑在这两个节点之间发生的任何事件。 为用户沿路径移动所分配的时间由容器设置确定。

![历程画布](assets/journey-canvas.png)

## 主要功能

历程画布可视化图表的主要功能包括：

* 深入分析适合最复杂用户历程的流失和流过。

* 用于映射和可视化用户历程的各种入口点、节点和路径的画布。

* 拖放交互以将组件添加到画布和重新定位现有节点。

* 用于在历程画布中构建用户旅程的分析或根据Journey Optimizer旅程自动创建这些分析的选项。

## 潜在见解

历程画布为最复杂的旅程提供可操作的见解。

### 转换率最高的路径 {#conversion-rate-caption}

历程画布中最突出的洞察内容以标题的形式显示在画布本身的顶部。

此标题总结了历程中的所有路径中哪些路径的转化率最高。

当历程包含多个开始节点时，描述如下所示：

![历程画布分析标题](assets/journey-canvas-caption.png)

当历程包含单个开始节点时，描述如下所示：

![历程画布分析标题单个开始节点](assets/journey-canvas-caption-singlestart.png)

在解释此标题时，请考虑以下事项：

* _path_&#x200B;被定义为通过箭头连接到结束节点的起始节点，其间连接任意数量的节点。

* 转化率计算取决于历程类型（历程中包含的开始节点和结束节点的数量，以及路径是否在它们之间相交）。

  下表介绍了如何根据历程类型计算转化率：

  | 历程类型 | 转化率计算 | 示例 |
  |---------|----------|---------|
  | **单个起始节点和单个结束节点** | 转化率是通过将结束节点的数量除以开始节点的数量来计算的。 | ![有多个开始点的历程会聚到一个公共节点](assets/journey-canvas-single-path.png) |
  | **单个开始节点和多个结束节点** | 转化率的计算方式为：找到编号最高的结束节点，然后将该编号除以开始节点的编号。 | ![有多个开始点的历程会聚到一个公共节点](assets/journey-canvas-singlestart-multiend.png) |
  | **多个独立路径，每个路径包含一个开始节点和一个结束节点** | 转化率是通过将结束节点的数量除以开始节点的数量来计算的。 转换率最高的路径在标题中描述。 | ![有多个开始点的历程会聚到一个公共节点](assets/journey-canvas-multi-start-separate.png) |
  | **旅程中任何时刻的多个开始节点会聚合为一个公共节点** | 转化率的计算方法是找到编号最高的结束节点，然后将该编号除以编号最低的开始节点的编号。 | ![有多个开始点的历程会聚到一个公共节点](assets/journey-canvas-multi-start-converge.png) |

### 流过、流失等

以下是其他见解历程画布可帮助提供的几个示例。 您可以选择这些见解是基于数据视图中的所有人员、所有开始历程的人员还是历程之前节点的所有人员。

#### 途经

* 已完成历程（到达结束节点）的人员数量和百分比

* 到达历程的给定节点的人数和百分比

* 在历程的给定节点之后或之前执行的最常见步骤

#### 流失

* 人最常退出旅程的旅程节点（从未到达任何紧接的后续节点）

#### 每个节点的附加数据

* 在历程的任何节点上添加划分维度，以查看该特定节点的其他数据

## 在历程画布、流失或流量可视化图表之间进行选择

历程画布可视化图表与[流失可视化图表](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)和[流量可视化图表](/help/analysis-workspace/visualizations/c-flow/flow.md)相似，但存在重要差异。

### 了解差异

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### 何时使用历程画布

历程画布对于以下各项至关重要：

* 涉及具有多个入口点和路径的历程的流失分析。

* 具有多个入口点和路径的非线性历程，并具有预定义的页面序列。

* 基于预定义历程的探索性Ad Hoc Analysis。

* 需要会话、人员或发生次数以外的主要指标的分析。

* 对源自Adobe Journey Optimizer的历程的更深入分析。

使用[上表](#understand-the-differences)了解历程画布、流失和流量可视化图表之间的差异。

## 分析Journey Optimizer历程

>[!NOTE]
>
>如果您的组织无权访问Journey Optimizer，您仍可以[在历程画布中构建分析](#build-analyses-in-customer-journey-analytics)。

在历程画布中分析Journey Optimizer旅程，可提供有关人员如何与旅程进行交互的深入可操作洞察。

在历程画布中分析Journey Optimizer历程时，该历程的显示顺序、顺序和结构与在Journey Optimizer中相同。 如果您可以对历程画布中的历程进行更改，则不再从Journey Optimizer](#synchronization-between-journey-optimizer-and-journey-canvas)同步[更改。

### 使用历程画布分析Journey Optimizer旅程的好处

历程画布提供了在Journey Optimizer中无法提供的深入、全面的分析。

使用历程画布分析在Journey Optimizer中创建的历程具有多种好处：

* 使用任何Customer Journey Analytics维度、量度、过滤器或日期范围创建事件。

  在Journey Optimizer中，技术用户必须先创建事件，然后才能将其添加到旅程。

* 基于您创建的自定义节点创建受众(启动Customer Journey Analytics受众生成器)。

  在Journey Optimizer中，您只能为预定义的活动创建受众。

* 分析流过和流失

* 使用任何维度划分事件

* 合并事件

* 连接事件

* 重命名和删除事件

* 更多内容

### Journey Optimizer和历程画布之间的同步

在历程画布中创建Journey Optimizer旅程的分析后，数据仅在一个方向上同步，从Journey Optimizer到历程画布。 这意味着对历程画布中的旅程所做的更改绝不会反映在Journey Optimizer中。

此外，仅当Journey Optimizer中的旅程在历程画布中保持未修改状态时，对旅程所做的更改才会同步到历程画布。 在历程画布中修改旅程后，您对Journey Optimizer中的旅程所做的任何更改都不会反映在历程画布中。 若要查看在历程画布中反映的更改，您可以在历程画布](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)中删除并重新创建历程[。

### 在历程画布中修改旅程后的差异 {#differences-after-modifying}

在历程画布中修改Journey Optimizer历程后，数据处理、可用功能和同步行为可能会发生更改。

如果您在历程画布中对Journey Optimizer历程进行了重大修改，则可能会更改数据处理、可用功能和同步行为。 重大修改包括以下任何一项：

* 添加或删除节点

* 在节点之间添加或删除箭头

* 更改节点上的组件

如果您对历程画布中的Journey Optimizer历程进行了其他更改，例如拖动节点或添加划分，则以下部分中描述的差异不适用。

>[!NOTE]
>
>要将历程恢复到其原始状态，可以在历程画布中进行首次更改后按Ctrl+z。 或者，您可以在历程画布中删除并[重新创建历程](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

#### 数据处理差异

在历程画布中修改Journey Optimizer历程后，如果您的历程包含具有非默认归因模型的量度，您可能会注意到数据发生了更改。

这是因为，与Journey Optimizer不同，历程画布允许您在单个历程中应用多个维度。 此功能意味着不支持[量度归因](/help/data-views/component-settings/attribution.md)。

#### 功能差异

在历程画布中修改Journey Optimizer历程后，[!UICONTROL **箭头设置**]&#x200B;下拉字段中可用的选项会根据您的修改进行更改。 有关详细信息，请参阅[配置设置](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

[!UICONTROL **节点类型**]&#x200B;字段仅在Journey Optimizer中可用。 在历程画布中查看Journey Optimizer旅程时，无论是否在历程画布中修改旅程，该变量均不可用。

#### 同步差异

仅当历程在Journey Optimizer画布中保持未修改状态时，对历程所做的更改才同步到历程历程。

在历程画布中修改Journey Optimizer历程后，您对Journey Optimizer中的历程所做的任何更改都不会反映在历程画布中。 若要查看在历程画布中反映的更改，您可以在历程画布](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)中删除并重新创建历程[。

### Journey Optimizer和Customer Journey Analytics之间的术语差异

在Journey Optimizer中，某些术语表示一件事，而在Customer Journey Analytics中，这些术语则表示其他事情。 使用历程画布时，会使用Customer Journey Analytics词。

| 术语 | 历程画布 | Journey Optimizer |
|---------|----------|---------|
| **Event** | Customer Journey Analytics中可用的几个标准指标之一。 此量度会计入收入、订阅或生成的商机等。 | 触发个性化历程（如在线购买）的活动类别。 |

### 在历程画布中分析Journey Optimizer历程

有关在历程画布中分析Journey Optimizer历程的信息，请参阅[配置历程画布可视化图表](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

## 在历程画布中构建分析

您可以在历程画布中基于Analysis Workspace中可用的任何维度或指标构建分析。 或者，您可以分析在Journey Optimizer中创建的历程。 有关详细信息，请参阅[配置历程画布可视化](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。
