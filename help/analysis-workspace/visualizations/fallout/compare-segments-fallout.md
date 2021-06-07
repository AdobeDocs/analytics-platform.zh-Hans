---
description: 您可以在Analysis Workspace中从接触点创建过滤器、添加过滤器作为接触点，以及比较各种过滤器之间的关键工作流程。
keywords: 流失和过滤器；流失分析中的过滤器；比较流失中的过滤器
title: 在流失分析中应用过滤器
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 15%

---

# 在流失分析中应用过滤器

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 略有不同。[了解更多...](/help/getting-started/cja-aa.md)

您可以在Analysis Workspace中从接触点创建过滤器、添加过滤器作为接触点，以及比较各种过滤器之间的关键工作流程。

>[!IMPORTANT]
>
>用作流失中检查点的过滤器必须使用级别低于流失可视化图表整体上下文的容器。 对于访客上下文流失，用作检查点的过滤器必须是基于访问的过滤器或基于点击的过滤器。 对于访问上下文流失，用作检查点的过滤器必须是基于点击的过滤器。 如果您使用的组合无效，则流失率将为 100%。我们为流失可视化图表添加了警告，当您添加不兼容的过滤器作为接触点时，将显示该警告。 某些无效的过滤器容器组合将导致无效的流失图表，例如：

* 在访客上下文流失可视化图表中使用基于访客的过滤器作为接触点
* 在访问上下文流失可视化图表中使用基于访客的过滤器作为接触点
* 在访问上下文流失可视化图表中使用基于访问的过滤器作为接触点

## 从接触点创建过滤器 {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. 从您特别感兴趣的特定接触点创建一个过滤器，该过滤器可能会应用到其他报表。 为此，请右键单击接触点并选择&#x200B;**[!UICONTROL 从接触点创建过滤器]**。

   ![](assets/segment-from-touchpoint.png)

   此时会打开过滤器生成器，其中预填充了与您选择的接触点匹配的预建顺序过滤器：

   ![](assets/segment-builder.png)

1. 为过滤器提供标题和描述并保存。

   现在，您可以在所需的任何项目中使用此过滤器。

## 添加过滤器作为接触点 {#section_17611C1A07444BE891DC21EE8FC03EFC}

例如，如果您想要了解美国用户的趋势和对流失的影响，只需将美国用户过滤器拖到流失中：

![](assets/segment-touchpoint.png)

或者，也可以通过将美国用户过滤器拖到另一个检查点来创建“与”接触点。

## 在流失中比较过滤器 {#section_E0B761A69B1545908B52E05379277B56}

您可以在流失可视化图表中比较无限数量的过滤器。

1. 从左侧的[!UICONTROL Filter]边栏中选择要比较的过滤器。 在本例中，我们选择了2个过滤器：美国用户和非美国用户。
1. 将它们拖到顶部的过滤器拖放区域。

   ![](assets/segment-drop.png)

1. 可选：您可以保留“所有访问”作为默认容器，或者删除它。

   ![](assets/seg-compare.png)

1. 您现在可以比较两个过滤器的流失情况，例如一个过滤器的性能优于另一个过滤器的情况，或者其他分析。
