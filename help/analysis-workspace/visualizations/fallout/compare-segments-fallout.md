---
description: 您可以从接触点创建过滤器，将过滤器添加为接触点，并在Analysis Workspace中比较不同过滤器的关键工作流。
keywords: 流失和过滤器；流失分析中的过滤器；流失中的过滤器比较
title: 在流失分析中应用过滤器
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 15%

---

# 在流失分析中应用过滤器

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html) 略有不同。[了解更多...](/help/getting-started/cja-aa.md)

您可以从接触点创建过滤器，将过滤器添加为接触点，并在Analysis Workspace中比较不同过滤器的关键工作流。

>[!IMPORTANT]
>
>在流失中用作检查点的过滤器必须使用低于流失可视化整体上下文的容器。 使用访客上下文流失时，用作检查点的过滤器必须是访问或基于点击的过滤器。 使用访问上下文流失，用作检查点的过滤器必须是基于点击的过滤器。 如果您使用的组合无效，则流失率将为 100%。我们已向流失可视化添加了警告，当您将不兼容的过滤器添加为接触点时，将显示该警告。 某些无效的过滤器容器组合将导致无效的流失图，例如：

* 将基于访客的过滤器用作访客上下文流失可视化中的接触点
* 使用基于访客的过滤器作为访问上下文流失可视化中的接触点
* 使用基于访问的过滤器作为访问上下文流失可视化中的接触点

## 从触点{#section_915E8FBF35CD4F34828F860C1CCC2272}创建过滤器

1. 从您特别感兴趣的特定接触点创建过滤器，该过滤器可能对应用于其他报表非常有用。 要执行此操作，请右键单击触点，然后选择&#x200B;**[!UICONTROL 从触点]**&#x200B;创建过滤器。

   ![](assets/segment-from-touchpoint.png)

   此时会打开Filter Builder，并预填充与所选接触点匹配的预建顺序过滤器：

   ![](assets/segment-builder.png)

1. 为过滤器提供标题和说明并保存它。

   您现在可以在您希望的任何项目中使用此过滤器。

## 添加滤镜作为触点{#section_17611C1A07444BE891DC21EE8FC03EFC}

例如，如果您想了解您的美国用户如何趋势化和影响流失，只需将美国用户拖入流失中：

![](assets/segment-touchpoint.png)

或者，也可以通过将美国用户筛选器拖到另一个检查点来创建AND触点。

## 比较流失{#section_E0B761A69B1545908B52E05379277B56}中的过滤器

您可以在流失可视化中比较不限数量的过滤器。

1. 从左侧的[!UICONTROL 滤镜]边栏中选择要比较的过滤器。 在示例中，我们选择了2个过滤器:美国用户和非美国用户。
1. 将它们拖入顶部的“滤镜”放置区。

   ![](assets/segment-drop.png)

1. 可选：您可以保留“所有访问”作为默认容器，或者删除它。

   ![](assets/seg-compare.png)

1. 您现在可以比较两个过滤器的流失情况，如一个过滤器的性能优于另一个过滤器的位置，或其他洞察。
