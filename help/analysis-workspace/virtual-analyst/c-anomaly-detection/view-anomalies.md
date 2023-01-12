---
description: 您可以在表格或折线图中查看异常。
title: 在 Analysis Workspace 中查看异常
feature: Anomaly Detection
exl-id: a76fd967-e4ae-4616-83ce-19de67300f0c
source-git-commit: e62261d1d440c0a85e4cab95611c6e6272de6724
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 14%

---

# 在 Analysis Workspace 中查看异常

您可以在表格或折线图中查看异常。

## 在表中查看异常 {#section_869A87B92B574A38B017A980ED8A29C5}

您可以在自由格式表中查看时间系列中的异常。

1. 选择列标题中的列设置图标，然后确保 [!UICONTROL **异常**] 选项。 有关更多信息，请参阅 [列设置](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. 单击“设置”菜单以查看更新的表。

   ![](assets/anomaly_detected.png)

1. 表中显示了异常情况，如下所示：

   A **深灰色三角形** 显示在检测到数据异常的每行的右上角。

   颜色 **垂直线** 在每行中均指示预期值。 颜色 **阴影区域** 在每行中都表示实际值。 线条（预期值）与阴影区域（实际值）的比较方式确定是否存在异常。 (根据 [异常检测中使用的统计技术](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md).)

1. 选择行右上角的灰色三角形以查看有关异常的详细信息。 这显示实际值偏高于或低于预期值的程度（以百分比表示）。

## 在折线图中查看异常 {#section_7C1192AFDB4345A8A2CCFB3AE0C47D82}

折线图是唯一允许您查看异常的可视化图表。

要在折线图中查看异常，请执行以下操作：

1. 选择可视化标题中的设置图标，然后确保 [!UICONTROL **显示异常**] 选项。 有关更多信息，请参阅 [折线图](/help/analysis-workspace/visualizations/line.md).

1. （可选）要允许置信度间隔缩放图表，请选择可视化标题中的设置图标，然后选择选项， **[!UICONTROL 允许异常缩放Y轴]**.

   默认情况下未选择此选项，因为它有时会使图表变得不太清晰。

1. 单击离开设置菜单可查看更新的折线图。

   ![](assets/anomaly_linechart.png)

   折线图中显示的异常如下所示：

   A **白点** 出现在检测到数据异常的位置。 (根据 [异常检测中使用的统计技术](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md).)

   的 **阴影区域** 是应出现值的置信范围或预期范围。 超出此预期范围的任何值都是异常。

   如果折线图中有多个量度，则只会显示异常，您必须将鼠标悬停在每个异常上才能看到该量度的置信区。

   的 **虚线** 是确切的预期值。

1. 单击异常（白色圆点）可查看以下信息：

   * 异常发生的日期

   * 异常的原始值

   * 与预期值相差（高出或低于）的百分比，该值由绿色实线表示。

