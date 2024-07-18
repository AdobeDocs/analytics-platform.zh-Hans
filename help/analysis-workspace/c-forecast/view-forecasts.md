---
description: 了解如何在表或折线图中查看预测。
title: 如何在Analysis Workspace中查看预测
feature: Visualizations
role: User
exl-id: 4a8b602c-e6aa-4a46-bba9-642387e6af88
source-git-commit: fea1b12a594a820ab2e55f850ca95c5a373184f0
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 2%

---

# 在 Analysis Workspace 中查看预测

您可以在自由格式表或折线图中查看预测。

## 在表中查看预测

您可以在时间序列自由格式表中查看预测。 在[用户首选项](../user-preferences.md)中为自由格式表启用[!UICONTROL 显示预测]时，将自动显示添加到该表的第一个量度列的预测。 对于任何其他列：

1. 在列标题中选择列设置图标![列设置](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg)，然后确保在选项列表中选择&#x200B;**[!UICONTROL 显示预测]**。 有关更多信息，请参阅[列设置](../visualizations/freeform-table/column-row-settings/column-settings.md)。

1. 单击&#x200B;**[!UICONTROL 列设置]**&#x200B;菜单外部以保存设置并查看更新的表。

预测如下表所示：

![在表](assets/show-forecast-table.png)中显示预测

* 每个单元格的预测值和百分比以&#x200B;**深灰色**&#x200B;显示。
* 要指明预测值，请使用预测符号 <img src="./assets/forecast.svg" alt="预测符号" width="20" />显示在单元格的右上角。


## 在折线图中查看预测

折线图是唯一允许您查看预测的可视化图表。

1. 在可视化图表标题中选择设置图标![列设置](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg)，然后确保在选项列表中选择&#x200B;**[!UICONTROL 显示预测]**。

1. （可选）要允许预测正确缩放图表，请选择&#x200B;**[!UICONTROL 允许预测缩放Y轴]**。 默认情况下不选中此选项，因为它有时可能会呈现较不清晰的图表。

1. 单击&#x200B;**[!UICONTROL 设置]**&#x200B;菜单外部以查看更新的折线图。

预测在折线图中显示如下：

![在折线图中显示预测](assets/show-forecast-linechart.png)

* 折线图中量度的当前值由垂直条形图指示。 如果将鼠标悬停在该垂直线上，则会显示一个弹出窗口，其中包含最后一个当前日期。
* 一个或多个量度的预测值使用虚线直接从垂直栏显示。 您可以将鼠标悬停在量度的任何数据点上。 此时将显示一个弹出窗口，其中包含：
   * 预测日期
   * 量度的预测值
   * 量度的预测值上限
   * 量度的预测值下限
* 阴影区域显示预测的置信带。
