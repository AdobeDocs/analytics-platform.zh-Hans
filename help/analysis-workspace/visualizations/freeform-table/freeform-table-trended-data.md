---
description: 了解如何在Analysis Workspace中查看自由格式表的趋势数据。
title: 查看自由格式表的趋势数据
feature: Freeform Tables
role: User, Admin
source-git-commit: 6ffc02c537a5e0b24edab34c87866d5c8413ae6f
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# 查看自由格式表的趋势数据

您可以查看自由格式表中包含的数据的趋势。 此趋势数据显示在Analysis Workspace的以下区域：

* [迷你图](#use-sparklines-to-view-trended-data)

* [折线图可视化图表](#use-line-visualizations-to-view-trended-data)

## 使用迷你图查看趋势数据

迷你图显示在自由格式表的量度列标题中。

自由格式表中的![迷你图](assets/table-sparkline.png)

迷你图始终包括：

* 列中所有数据的趋势数据

* 应用于表维度的任何搜索筛选条件

  有关详细信息，请参阅[筛选和排序](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。

## 使用折线图可视化图表查看趋势数据

[行](/help/analysis-workspace/visualizations/line.md)可视化显示它们所连接的自由格式表的数据。

### 将折线图可视化图表连接到自由格式表

根据折线图可视化图表添加到项目的方法和时间，它可能已连接到所需的自由格式表。 使用以下步骤检查或手动连接它：

1. 向Analysis Workspace项目添加折线图可视化图表。

1. 选择可视化图表名称旁边的圆点，选择&#x200B;**[!UICONTROL 数据源]**&#x200B;选项卡，然后选择要连接到折线图可视化图表的自由格式表的名称。

   ![连接到自由格式表的折线图可视化图表](assets/table-line-viz.png)

### 选择折线图可视化图表中包含的数据

根据在自由格式表中选择的单元格，连接的折线图可视化图表中包含的数据会有所不同。

要查看自由格式表中所有数据的趋势，请选择自由格式表中的迷你图单元格。

选择迷你图单元格时，单元格显示为深灰色。

已选择![迷你图](assets/table-sparkline-selected.png)

选择所连接表的迷你图单元格时，行可视化包括：

* 列中所有数据的趋势数据

* 应用于表维度的任何搜索筛选条件

  有关详细信息，请参阅[筛选和排序](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。

未选择所连接表的迷你图时，行可视化包括：

* 在连接的表中选择的行的数据。 如果未选择任何行，则只显示所连接表的第一个维的数据。

* 将忽略应用于表维的任何搜索筛选条件

  有关详细信息，请参阅[筛选和排序](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。


## 在连接的行可视化图表中包括筛选条件

有关何时将筛选条件包含在连接的行可视化中的信息，请参阅[在迷你图和行可视化中的趋势数据中包括筛选条件](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#include-filter-criteria-in-trended-data-in-sparklines-and-line-visualizations)

