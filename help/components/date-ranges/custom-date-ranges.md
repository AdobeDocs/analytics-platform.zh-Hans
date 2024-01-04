---
description: 在 Analysis Workspace 中创建自定义日期范围，并将它们另存为“时间”组件。
keywords: Analysis Workspace
title: 创建自定义日期范围
feature: Calendar
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 85%

---

# 创建自定义日期范围

在 Analysis Workspace 中创建自定义日期范围，并将它们另存为“时间”组件。

**[!UICONTROL 组件]** > **[!UICONTROL 新建日期范围]**

日期范围应用于面板级别。要在项目中添加日期范围，请单击&#x200B;**面板** > *`<select panel>`*，然后指定一个新的日期范围。

## “两个月之前”的日期范围

下面的自定义日期范围显示了“两个月之前”的日期范围，其中，“概要更改”可视化图表显示了方向上的变化。

![日期范围生成器显示两个月前的使用滚动日期](assets/date-range-two-months-ago.png)

自定义日期范围显示在项目中“日期范围”组件面板的最上方：

![日期范围组件面板，带有指向两个月前的箭头。](assets/date-range-panel-two-months-ago.png)

您可以将这个自定义日期范围拖至使用“上个月”预设的自定义月连续日期范围旁边的列中，以便进行比较。添加一个“概要更改”可视化图表并从每个列中选择总量，可显示方向上的变化：

![总变化显示和增加14.45%。](assets/date-range-two-months-table.png)

## 使用 7 天滚动日期范围

日期范围应用于面板级别。若要在项目中添加日期范围，请单击&#x200B;**操作** > **添加面板**，然后指定一个新的日期范围。

在“日期范围生成器”中，您可以创建一个与其他日期范围一同显示在“组件”面板中的自定义日期范围。

例如，您可以创建一个日期范围，指定一个于一周前结束的连续 7 天的时段。

![日期范围生成器，其中显示一个指定7天滚动窗口的日期范围。](assets/create_date_range.png)

使用 *`rolling daily`*。

* “开始”设置是 *`current day minus 14 days`*。

* “结束”设置是 *`current day minus 7 days`*。

这个日期范围可作为一个组件拖至任何自由格式表中。
