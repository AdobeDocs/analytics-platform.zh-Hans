---
description: 了解如何在Analysis Workspace中查看和分析数据异常。
title: 查看异常
feature: Anomaly Detection
exl-id: a76fd967-e4ae-4616-83ce-19de67300f0c
role: User
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 50%

---


# 查看异常

您可以在Analysis Workspace中的表或折线图中查看异常。

## 在表中查看异常 {#section_869A87B92B574A38B017A980ED8A29C5}

您可以在时间序列自由格式表中查看异常。

1. 在列标题中选择![设置](/help/assets/icons/Setting.svg)，然后确保在选项列表中选择&#x200B;**[!UICONTROL 显示异常]**&#x200B;选项。 有关更多信息，请参阅[列设置](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)。

1. 异常情况如下表所示：

   检测到![异常](assets/anomaly-detected.png)

   ◥显示在检测到数据异常的每一行的右上角。

   每行&#x200B;**中的**&#x200B;彩色垂直线➋表示预期值。 每行&#x200B;**中的**&#x200B;彩色阴影区域➊表示实际值。 线条（预期值）与阴影区域（实际值）的比较方式决定是否存在异常。（根据[异常检测中使用的统计技术](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)中描述的高级统计技术，将观测视为异常。）

1. 选择行右上角的◥查看有关异常的详细信息。 这显示了实际值偏离预期值以上或以下的程度（以百分比表示）。

## 在折线图中查看异常

折线图是唯一允许您查看异常情况的可视化图表。

要在折线图中查看异常，请执行以下操作：

1. 在可视化图表标题中选择![设置](/help/assets/icons/Setting.svg)，然后确保在选项列表中选择&#x200B;[!UICONTROL **显示异常**]&#x200B;选项。 有关更多信息，请参阅[折线图](/help/analysis-workspace/visualizations/line.md)。

1. （可选）要允许置信度间隔缩放图表，请在可视化图表标题中选择![设置](/help/assets/icons/Setting.svg)，然后选择选项&#x200B;**[!UICONTROL 允许异常缩放Y轴]**。

   默认情况下不选择此选项，因为它有时会使图表不那么清晰。

   异常情况如下折线图所示：

   ![异常检测到的折线图可视化图表](assets/anomaly-detected-line.png)

   当检测到数据异常时，**白点**&#x200B;出现在折线上。（根据[异常检测中使用的统计技术](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)中描述的高级统计技术，将观测视为异常。）

   **浅色阴影区域**&#x200B;是值应该出现的置信带或预期范围。超出此预期范围的任何值都是异常。

   如果折线图中包含多个量度，仅显示异常，您必须将鼠标悬停在每个异常上，才能查看该量度的置信带。

   **虚线**&#x200B;是确切的预期值。

1. 选择异常（白点）以查看以下信息：

   * 异常发生的日期。

   * 异常的原始值。

   * 与预期值相差（高出或低于）的百分比，该值由绿色实线表示。








<!--
# View anomalies in Analysis Workspace

You can view anomalies in a table or in a line chart.

## View anomalies in a table {#table}

You can view anomalies in a time-series Freeform Table.

1. Select the column settings icon in the column header, then ensure that the [!UICONTROL **Anomalies**] option is selected in the list of options. For more information, see [Column settings](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. Click away from the settings menu to view the updated table.

   ![An anomaly detection notification indicating 15% below expected.](assets/anomaly_detected.png)

1. Anomalies are shown in the table as follows:

   A **dark gray triangle** appears in the upper-right corner of each row where a data anomaly is detected.

   The colored **vertical line** in each row indicates the expected value. The colored **shaded area** in each row indicates the actual value. How the line (expected value) compares with the shaded area (actual value) determines whether there is an anomaly. (An observation is considered anomolous based on the advanced statistical techniques described in [Statistical techniques used in anomaly detection](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).)

1. Select the gray triangle in the upper-right corner of a row to view details about the anomaly. This shows the extent (as a percentage) to which the actual value diverges either above or below the expected value.

## View anomalies in a line chart {#line-chart}

A Line chart is the only visualization that allows you to view anomalies.

To view anomalies in a line chart:

1. Select the settings icon in the visualization header, then ensure that the [!UICONTROL **Show anomalies**] option is selected in the list of options. For more information, see [Line](/help/analysis-workspace/visualizations/line.md).

1. (Optional) To allow the confidence interval to scale the chart, select the settings icon in the visualization header, then select the option, **[!UICONTROL Allow anomalies to Scale Y-axis]**. 

   This option is not selected by default because it can sometimes make the chart less legible.
   
1. Click away from the settings menu to view the updated line chart.

      ![A line chart with an anomaly detected message indicating 15% above expected.](assets/anomaly_linechart.png)

   Anomalies are shown in the line chart as follows:
   
   A **white dot** appears on the line wherever a data anomaly is detected. (An observation is considered anomolous based on the advanced statistical techniques described in [Statistical techniques used in anomaly detection](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).)

   The **light shaded area** is the confidence band, or expected range, where values should occur. Any value that falls outside of this expected range is an anomaly. 

   If you have multiple metrics in the line chart, only the anomalies are shown and you have to hover over each anomaly to see the confidence band for that metric. 

   The **dotted line** is the exact expected value.

1. Click an anomaly (white dot) to view the following information:

   * The date the anomaly occurred 
   
   * The raw value of the anomaly 
   
   * The percentage value above or below the expected value, which is represented by the solid green line.
   
-->
