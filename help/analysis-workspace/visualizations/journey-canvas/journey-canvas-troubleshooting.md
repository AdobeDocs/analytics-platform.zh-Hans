---
description: 了解如何在配置历程画布可视化图表时排除故障。
title: 历程画布故障排除
feature: Visualizations
role: User
exl-id: f0ac3752-9244-4d9e-807b-e6471e6aa55b
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: ht
source-wordcount: '1290'
ht-degree: 100%

---

# 历程画布故障排除

历程画布可视化图表可帮助您进行分析，获得关于您为用户和客户提供的历程的深入洞察。

要了解有关历程画布的更多信息，请参阅[历程画布概述](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)和[配置历程画布可视化图表](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

以下信息可帮助您排查可能遇到的意外结果，例如历程中较晚出现的节点显示的百分比或数量高于历程中较早出现的节点。

## 节点的百分比或值高于之前的节点

在历程画布中，较晚进入历程的节点可能会显示比较早进入历程的节点更高的百分比或数量。

换句话说，与始终是漏斗形状的流失图不同（参与率随每一步减少），历程画布可视化图表在历程的较晚步骤中的参与率可能高于之前的步骤。

这可能发生在以下场景中：

* 使用不是“人员”和“会话”的主要量度

* 多个路径汇聚到一个节点

### 历程使用不是“人员”和“会话”的主要量度

由于历程画布允许您将任何量度用作主要量度，这可能会导致历程中较晚的节点显示比历程中较早的节点更高的百分比或数量。

![历程中节点的百分比高于之前的节点](assets/journey-canvas-higher-percentage.png)

以下场景中使用的历程配置了这些设置：

* **[!UICONTROL 人员]**&#x200B;设置为容器

* **[!UICONTROL 事件]**&#x200B;设置为主要量度

#### 场景 1：用户 A 遵循第一个会话中的历程路径。在接下来的会话中，用户有一个事件仅与一个较晚的节点匹配。

假设用户 A 访问网站并完成了历程（节点 1：“访问网站” > 节点 2：“查看产品 A” > 节点 3：“结账”）。由于用户 A 有一个按顺序匹配历程中每个节点的事件，因此历程的每个节点上都会计入一个事件。

现在，假设用户 A 在一个较晚的会话中再次访问网站。由于用户 A 已在之前的会话中遵循了历程路径完成了历程，这意味着只要用户 A 有一个与历程中任何节点匹配的事件，即使用户 A 在当前会话中未遵循历程路径，历程的相关节点上仍会计入一个事件。例如，如果用户 A 结账，“结账”节点上就会计入一个事件。这会导致“结账”节点上的百分比和数量高于前一个节点“查看产品 A”上的百分比和数量。

在本例中，确定将第三个节点（“结账”）上的事件计入接下来的会话中，历程的“人员”容器设置对此起到关键作用。

或者，如果将容器设置设为“会话”，那么在接下来的访问中只发生在第三个节点上的事件就不会计入历程，因为历程中显示的统计数据仅限于某个给定人员的一个已定义会话。要了解有关容器设置的更多信息，请参阅[配置历程画布可视化图表](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)一文中的[开始构建历程画布可视化图表](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#begin-building-a-journey-canvas-visualization)

<!-- The time allotted for users to move along the path is determined by the container setting. Because "Person" is selected as the container setting in this example, people who followed the journey's path in one session (moving from Node 1 to Node 2 and to Node 3) met the criteria of the journey. On any subsequent visits to the site, any event they have that matches any node on the journey is counted on that node. -->

#### 场景 2：用户 B 退出历程

假设用户 B 访问网站，但未完成历程（访问网站，查看产品 B，然后结账）。在这种情况下，历程的起始节点“访问网站”计入一个事件，但其余节点不计入，用户 B 退出了历程。虽然用户 B 结账，第三个节点（“结账”）也不会计入事件，因为用户 B 在结账之前未通过查看产品 A 完成历程。

这是因为只有当用户遵循历程的“最终路径”时，每个节点才会计入事件。这意味着只有当人员最终从一个节点移动到另一个节点时，才会计入事件，无论这两个节点之间发生任何事件。

### 历程中有多个路径汇聚到一个节点

历程画布允许您在一个历程中包含多个起始节点，这会导致有多个路径。这些路径可能汇聚到一个共用节点，从而导致历程中较晚的节点显示的百分比或数量高于历程中较早的节点。

![历程中有多个路径汇聚到一个节点](assets/journey-canvas-percentage-converge.png)

<!--

The journey used in the following scenarios is configured with the following settings:

* **[!UICONTROL Person]** is set as the container

* **[!UICONTROL Event]** is set as the primary metric

#### Scenario 

When a journey contains multiple paths that converge into a single node, the two paths are combined into the single node using the OR operator. This can result in the

-->

### 历程百分比

无论在&#x200B;**[!UICONTROL 百分比值]**&#x200B;字段中选择了什么，历程的每个节点上显示的数量都保持不变，但百分比本身可以变化。

以下几个部分介绍了同一历程的百分比如何变化，具体取决于在&#x200B;**[!UICONTROL 百分比值]**&#x200B;字段中选择了以下哪个选项：

+++起始节点百分比

如果&#x200B;**[!UICONTROL 百分比值]**&#x200B;字段设置为&#x200B;]**起始节点的百分比**[!UICONTROL ，此历程中的节点会包含以下统计数据：

![历程中节点的百分比高于之前的节点](assets/journey-canvas-higher-percentage.png)

| 节点 | 统计数据 |
|---------|----------|
| 节点 1 - “访问网站” | 在这个历程中，在报告日期范围内网站上共发生了 354,147 个事件，正如历程的起始节点“访问网站”中所示。 |
| 节点 2 - “查看产品 A” | 在起始节点上显示的总事件数中，有 14%（48,394）符合历程的第二个节点“查看产品 A”的标准。 |
| 节点 3 - “结账” | 在起始节点上显示的总事件数中，有 32%（113,782）符合历程的第三个节点“结账”的标准。 |

+++

+++以前的节点百分比

如果&#x200B;**[!UICONTROL 百分比值]**&#x200B;字段设置为&#x200B;]**前一个节点的百分比**[!UICONTROL ，此历程中的节点会包含以下统计数据：

![历程中节点的百分比高于之前的节点](assets/journey-canvas-percentage-previous.png)

| 节点 | 统计数据 |
|---------|----------|
| 节点 1 - “访问网站” | 在这个历程中，在报告日期范围内网站上共发生了 354,147 个事件，正如历程的起始节点“访问网站”中所示。 |
| 节点 2 - “查看产品 A” | 在前一个节点上显示的总事件数中，有 14%（48,394）符合历程的第二个节点“查看产品 A”的标准。 |
| 节点 3 - “结账” | 在前一个节点上显示的总事件数中，超过 100%（113,782）符合历程的第三个节点“结账”的标准。 |

+++

+++总数的百分比

如果&#x200B;**[!UICONTROL 百分比值]**&#x200B;字段设置为&#x200B;]**总数的百分比**[!UICONTROL ，此历程中的节点会包含以下统计数据：

![历程中节点的百分比高于之前的节点](assets/journey-canvas-percentage-total.png)

| 节点 | 统计数据 |
|---------|----------|
| 节点 1 - “访问网站” | 在这个历程中，在报告日期范围内网站上共发生了 354,147 个事件，正如历程的起始节点“访问网站”中所示。 |
| 节点 2 - “查看产品 A” | 在总事件数中，不到 1%（48,394）符合历程的第二个节点“查看产品 A”的标准。 |
| 节点 3 - “结账” | 在总事件数中，有 1%（113,782）符合历程的第三个节点“结账”的标准。 |

+++

## 容器量度和主要量度之间的兼容性

您可以将历程画布容器配置为“人员”（使用“人员”量度）或“会话”（使用“会话”量度）。

确保选择与当前所选容器量度兼容的主要量度。大多数量度都与可用的容器量度兼容。但是，应避免使用容器量度和主要量度的某些组合。

例如，使用人员作为容器，会话作为主要量度，可能会导致意外结果。

<!--

## Percentages that exceed 100%

The following configurations can result in nodes that show percentages that exceed 100%:

* When the **[!UICONTROL Percentage value]** field is set to **[!UICONTROL Percent of total]** or **[!UICONTROL Percent of start node]**, and a primary metric is selected that results in less data for the start node than on subsequent nodes.

  For example, if Revenue is selected as the primary metric, and no revenue is being realized on the primary metric, then on any node where revenue is being realized will show as exceeding 100%. 

-->
