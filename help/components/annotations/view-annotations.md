---
title: 查看注释
description: 如何在工作区中查看注释。
role: User, Admin
feature: Components
exl-id: 52b179fd-d9a4-4119-a3c6-f6a36f24f8ea
source-git-commit: 998cc9e5f8d2ffd3964078dc389f55bb573063b9
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 79%

---

# 查看注释

>[!NOTE]
>
>此功能当前正在进行小范围测试。

注释的显示方式略有不同，具体取决于它们是跨越一天还是跨越一个日期范围。

## 在折线图或表中查看注释

| 日期 | 外观 |
| --- | --- |
| **一天** | ![](assets/single-day.png)<p>将鼠标悬停在注释上时，可以查看其详细信息，通过选择钢笔图标进行编辑，或者删除注释：<p> ![](assets/hover.png) |
| **日期范围** | 图标会发生变化，当您将鼠标悬停在它上面时，会显示日期范围。<p>![](assets/multi-day.png)<p>在折线图中选择注释时，将显示注释元数据，您可以进行编辑或删除：![](assets/multi-hover.png)<p>在表中，会在日期范围内的每个日期上显示一个图标。<p>![](assets/multi-day-table.png) |
| **重叠注释** | 在有多个注释与其关联的日期上，图标将为灰色。<p>![](assets/grey.png)<p>将鼠标悬停在灰色图标上时，将显示所有重叠的注释：<p>![](assets/overlap.png) |

## 在 .pdf 文件中查看注释

由于您无法将鼠标悬停在 .pdf 文件中的图标上，因此该文件（导出后）在面板底部提供了注释或说明。示例如下：

![](assets/ann-pdf.png)

## 查看包含非趋势数据的注释

有时，注释会以非趋势数据显示，但会与特定维度绑定。 在这种情况下，此类注释仅显示在右下角的摘要注释中。示例如下：

![](assets/non-date.png)

概要图表显示在角落的所有可视化图表类型中，而不只是显示在非趋势自由格式表和概要数字中。 它还会显示在 [!UICONTROL 圆环], [!UICONTROL 流量],[!UICONTROL 流失],[!UICONTROL 同类群组]，等等。

![](assets/ann-summary.png)