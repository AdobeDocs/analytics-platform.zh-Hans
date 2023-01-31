---
description: 您可以在表格或折线图中查看异常。
title: 在 Analysis Workspace 中查看异常
feature: Anomaly Detection
exl-id: a76fd967-e4ae-4616-83ce-19de67300f0c
source-git-commit: e62261d1d440c0a85e4cab95611c6e6272de6724
workflow-type: ht
source-wordcount: '460'
ht-degree: 100%

---

# 在 Analysis Workspace 中查看异常

您可以在表格或折线图中查看异常。

## 在表中查看异常 {#section_869A87B92B574A38B017A980ED8A29C5}

您可以在时间序列自由形式表中查看异常。

1. 选择列标题中的列设置图标，然后确保在选项列表中选择了&#x200B;[!UICONTROL **异常情况**]&#x200B;选项。有关更多信息，请参阅[列设置](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)。

1. 在设置菜单之外单击以查看更新的表格。

   ![](assets/anomaly_detected.png)

1. 异常情况如下表所示：

   **深灰色三角形**&#x200B;出现在检测到数据异常的每一行的右上角。

   每行中的彩色&#x200B;**竖线**&#x200B;表示预期值。每行中的&#x200B;**着色区域**&#x200B;表示实际值。线条（预期值）与阴影区域（实际值）的比较方式决定是否存在异常。（根据[异常检测中使用的统计技术](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)中描述的高级统计技术，观察被认为是异常的。）

1. 选择行右上角的灰色三角形以查看有关异常的详细信息。这显示了实际值偏离预期值以上或以下的程度（以百分比表示）。

## 在折线图中查看异常 {#section_7C1192AFDB4345A8A2CCFB3AE0C47D82}

折线图是唯一允许您查看异常情况的可视化。

要在折线图中查看异常：

1. 选择可视化标题中的设置图标，然后确保在选项列表中选择&#x200B;[!UICONTROL **显示异常**]&#x200B;选项。有关详细信息，请参阅[折线图](/help/analysis-workspace/visualizations/line.md)。

1. （可选）要允许置信区间缩放图表，请选择可视化标题中的设置图标，然后选择选项&#x200B;**[!UICONTROL 允许异常缩放 Y 轴]**。

   默认情况下不选择此选项，因为它有时会使图表不那么清晰。

1. 在设置菜单之外单击以查看更新的折线图。

   ![](assets/anomaly_linechart.png)

   异常情况如下折线图所示：

   当检测到数据异常时，**白点**&#x200B;出现在线路上。（根据[异常检测中使用的统计技术](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)中描述的高级统计技术，观察被认为是异常的。）

   **浅色阴影区域**&#x200B;是值应该出现的置信带或预期范围。超出此预期范围的任何值都是异常。

   如果折线图中包含多个量度，仅显示异常，您必须将鼠标悬停在每个异常上，才能查看该量度的置信带。

   **虚线**&#x200B;是确切的预期值。

1. 单击异常（白点）可查看以下信息：

   * 异常发生的日期

   * 异常的原始值

   * 与预期值相差（高出或低于）的百分比，该值由绿色实线表示。

