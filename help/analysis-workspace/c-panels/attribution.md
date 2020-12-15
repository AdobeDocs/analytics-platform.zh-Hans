---
title: 归因面板
description: 在 Analysis Workspace 中如何使用和解读归因面板。
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 94%

---


# 归因面板

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html) 略有不同。[了解更多...](/help/getting-started/cja-aa.md)

归因面板是一种用于构建各种归因模型的比较分析的简便方法。它是[归因 IQ](../attribution/overview.md) 的一项功能，为您提供专用工作区来使用和比较归因模型。

## 创建归因面板

1. 单击左侧的面板图标。
1. 将归因面板拖动到您的 Analysis Workspace 项目中。

   ![新建归因面板](assets/Attribution_Panel_1.png)

1. 添加要归因的量度，并添加要归因的对比维度。例如“营销渠道”或自定义维度，如内部促销。

   ![选择维度和量度](assets/attribution_panel2.png)

1. 选择要比较的[归因模型和回顾时间范围](../attribution/models.md)。

1. “归因”面板会返回一组丰富的数据和可视化图表，其中对选定维度和度量进行了归因比较。

   ![归因可视化图表](assets/attr_panel_vizs.png)

## 归因可视化图表

* **总数量度**：报表时间范围内发生的转化总数。这些是在您所选维度中归因的转化。
* **量度归因比较条形图**：以可视方式比较选定维度中每个维度项目的归因转换。每种条形颜色代表一个不同的归因模型。
* **量度归因自由格式表**：显示与条形图相同的数据，以表格形式展现。选择此表中的不同列或行，会过滤条形图以及面板中的其他一些可视化图表。此表的作用与工作区中任何其他自由形式表的作用相似，允许您添加度量、细分或细分等组件。
* **维度重叠图**：一个维恩图，显示排名前三的维度项目以及它们共同参与转化的频率。例如，气泡重叠的大小表示当访客出现在两个维度项目中时发生转化的频率。选择相邻自由格式表中的其他行，会更新可视化图表以反映所选内容。
* **每个历程的营销接触点**：直方图，显示访客在回顾时间范围内的接触点数量。这有助于了解多接触点归因对数据集的影响程度。如果几乎所有访客只有一个接触点，则不同的归因模型可能会显示相似的数据。
* **营销渠道表现详细信息**：让您可以使用散点图直观地对最多三个归因模型进行比较。
* **营销渠道流量**：让您可以了解哪些是最常交互的渠道，以及这些渠道在访客历程中的顺序。
