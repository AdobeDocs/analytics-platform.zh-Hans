---
description: 配置历程画布可视化图表时的示例
title: 历程画布示例
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: 2fc2bd660b017140b8dfa660cf71054af9efb87e
workflow-type: tm+mt
source-wordcount: '1271'
ht-degree: 0%

---

# 历程画布疑难解答

{{release-limited-testing}}

历程画布可视化图表允许您分析提供给用户和客户的旅程，并获取有关这些旅程的深入见解。

要了解有关历程画布的更多信息，请参阅[历程画布概述](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)和[配置历程画布可视化图表](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

以下信息可帮助您排除可能看到的意外结果，例如历程稍后出现的节点，其显示的百分比或数量高于历程中较早出现的节点。

## 具有比以前的节点更高的百分比或值的节点

在历程画布中，对于旅程中较晚进入的节点，可能会显示比旅程中较早进入的节点更高的百分比或数量计数。

换句话说，与始终为漏斗形状的流失可视化图表不同（参与率随每一步骤减少），历程画布可视化图表在历程的后一步中的参与率可能高于之前的步骤。

在以下情况下可能会发生这种情况：

* 使用人员或会话以外的主指标时

* 当多个路径收敛到单个节点时

### 历程使用除人员或会话之外的主要指标

由于历程画布允许您将任何量度用作主要量度，这可能会导致旅程中较晚的节点显示比旅程中较早的节点更高的百分比或数量计数。

![历程的百分比高于前一个节点](assets/journey-canvas-higher-percentage.png)

以下方案中使用的历程使用以下设置进行配置：

* 将&#x200B;**[!UICONTROL 人员]**&#x200B;设置为容器

* **[!UICONTROL Event]**&#x200B;设置为主要量度

#### 场景1 — 用户A遵循第一个会话中的历程路径，然后仅遵循后续会话中的后续节点

假设用户A访问网站并完成历程（节点1：“访问网站”>节点2：“查看产品A”>节点3：“结账”）。 由于用户A已完成历程，因此事件将计入历程的每个节点。

现在，假设用户A在以后的会话中再次访问网站。 由于用户A已通过遵循历程路径在上一会话中完成了历程，这意味着只要用户A具有的事件与历程中的任何节点匹配 — 即使用户A未在其当前会话中遵循历程路径 — 事件就会计入历程的相关节点中。 例如，如果用户A签出，则在“签出”节点中会计入一个事件。 这会导致“检出”节点上的百分比和数量高于前一个节点“查看产品A”上的百分比和数量。

在本例中，历程的“人员”容器设置在确定将第三个节点上的事件（“签出”）计入后续会话中时，将发挥关键作用。

或者，如果将容器设置设为“会话”，则仅在后续访问中发生在第三个节点上的事件将不会计入旅程，因为旅程中显示的统计信息将被限制为给定人员的单个已定义会话。 要了解有关容器设置的更多信息，请参阅[配置历程画布可视化](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)一文中的[开始构建历程画布可视化](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#begin-building-a-journey-canvas-visualization)

<!-- The time allotted for users to move along the path is determined by the container setting. Because "Person" is selected as the container setting in this example, people who followed the journey's path in one session (moving from Node 1 to Node 2 and to Node 3) met the criteria of the journey. On any subsequent visits to the site, any event they have that matches any node on the journey is counted on that node. -->

#### 场景2 — 用户B退出历程

假设用户B访问网站但未完成历程（访问网站，查看产品B，然后签出）。 在这种情况下，事件计入历程的开始节点“访问站点”，但事件不计入其余节点，并且用户B退出历程。 即使用户B已签出，事件也不会计入第三个节点（“签出”）中，因为用户B在签出之前未通过查看产品A完成历程。

这是因为仅当人员遵循历程的“最终路径”时，才会计算每个节点的事件，这意味着仅当人员最终从一个节点移动到另一个节点时，才会计算事件，而不考虑在这两个节点之间发生的任何事件。

### 历程具有收敛到单个节点的多个路径

历程画布允许您在单个旅程中包含多个开始节点，从而生成多个路径。 这些路径可以收敛到公共节点中，从而导致旅程中稍后访问的节点显示的百分比或数量高于旅程中较早访问的节点。

![包含多个路径的历程收敛到单个节点](assets/journey-canvas-percentage-converge.png)

<!--

The journey used in the following scenarios is configured with the following settings:

* **[!UICONTROL Person]** is set as the container

* **[!UICONTROL Event]** is set as the primary metric

#### Scenario 

When a journey contains multiple paths that converge into a single node, the two paths are combined into the single node using the OR operator. This can result in the

-->

### 历程百分比

尽管在历程的每个节点上显示的数字保持不变，而不管在&#x200B;**[!UICONTROL 百分比值]**&#x200B;字段中选择了什么内容，但百分比本身可以更改。

以下部分显示同一历程的百分比如何变化，具体取决于在&#x200B;**[!UICONTROL 百分比值]**&#x200B;字段中选择的以下选项：

+++开始节点的百分比

当&#x200B;**[!UICONTROL 百分比值]**&#x200B;字段设置为起始节点&#x200B;]**的**[!UICONTROL &#x200B;百分比时，此历程中的节点包含以下统计信息：

![历程的百分比高于前一个节点](assets/journey-canvas-higher-percentage.png)

| 节点 | 统计资料 |
|---------|----------|
| 节点1 — “访问站点” | 在此历程中，在报告日期范围内有354,147个事件在网站上，如历程的开始节点“访问站点”中所示。 |
| 节点2 — “查看产品A” | 在开始节点中显示的总事件数中，14%(48,394)与历程的第二个节点“查看产品A”的条件匹配。 |
| 节点3 — “签出” | 在开始节点中显示的总事件数中，32%(113,782)符合历程的第三个节点“签出”的标准。 |

+++

+++上一节点的百分比

当&#x200B;**[!UICONTROL 百分比值]**&#x200B;字段设置为前一个节点的&#x200B;**[!UICONTROL 百分比]**&#x200B;时，此历程中的节点包含以下统计信息：

![历程的百分比高于前一个节点](assets/journey-canvas-percentage-previous.png)

| 节点 | 统计资料 |
|---------|----------|
| 节点1 — “访问站点” | 在此历程中，在报告日期范围内有354,147个事件在网站上，如历程的开始节点“访问站点”中所示。 |
| 节点2 — “查看产品A” | 在上一个节点中显示的总事件数中，14%(48,394)符合历程的第二个节点“查看产品A”的标准。 |
| 节点3 — “签出” | 在上一个节点中显示的总事件数中，超过100% (113,782)的事件符合历程的第三个节点“签出”的标准。 |

+++

总数的+++百分比

当&#x200B;**[!UICONTROL 百分比值]**&#x200B;字段设置为总数的百分比&#x200B;]**的**[!UICONTROL &#x200B;时，此历程中的节点包含以下统计信息：

![历程的百分比高于前一个节点](assets/journey-canvas-percentage-total.png)

| 节点 | 统计资料 |
|---------|----------|
| 节点1 — “访问站点” | 在此历程中，在报告日期范围内有354,147个事件在网站上，如历程的开始节点“访问站点”中所示。 |
| 节点2 — “查看产品A” | 在事件总数中，不到1% (48,394)的事件与历程的第二个节点“查看产品A”的条件匹配。 |
| 节点3 — “签出” | 在事件总数中，1%(113,782)的匹配历程的第三个节点“签出”的标准。 |

+++

## 容器量度和主要量度之间的兼容性

您可以将“历程画布”容器配置为“人员”（使用“人员”指标）或“会话”（使用“会话”指标）。

确保选择与当前所选容器量度兼容的主要量度。 大多数量度都与可用的容器量度兼容。 但是，应避免使用某些容器量度和主要量度的组合。

例如，使用人员作为容器，会话作为主要量度可能会导致意外结果。

<!--

## Percentages that exceed 100%

The following configurations can result in nodes that show percentages that exceed 100%:

* When the **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of total]** or **[!UICONTROL Percent of start node]**, and a primary metric is selected that results in less data for the start node than on subsequent nodes.

  For example, if Revenue is selected as the primary metric, and no revenue is being realized on the primary metric, then on any node where revenue is being realized will show as exceeding 100%. 

-->
