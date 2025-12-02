---
description: 在 Analysis Workspace 中，可使用日历和数据范围功能来指定日期区间。
title: 日期范围概述
feature: Calendar
exl-id: 99b31bd9-32f1-4da1-9e47-6d90c66282c5
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 100%

---

# 日期范围概述

在工作区项目中，您通常会使用[面板中的日程表](/help/analysis-workspace/c-panels/panels.md#calendar)来指定该面板中可视化图表的日期范围。

使用日期范围组件可以定义和覆盖面板的日程表设置。

<!-- Very old video, should we show it?

+++ View a video illustrating use of calendar and date ranges

>[!VIDEO](https://video.tv.adobe.com/v/24136?format=jpeg)

{{videoaa}}
+++

-->

## 使用日期范围

您可以使用日期范围组件重新定义面板的日程表。

或者，您可以使用自由格式表中的日期范围作为量度或维度。

![日期范围使用情况](/help/components/date-ranges/assets/date-ranges-usage.png)

- **量度**。例如，比较两个不同月份的特定量度的维度。
- **维度**。比较日期范围维度上不同维度项的量度。

>[!NOTE]
>
>当您在自由格式表中使用日期范围时，这些日期范围会覆盖为自由表格所属面板指定的日程表。
>

您可以像[使用任何组件](/help/components/overview.md#analysis-workspace-components)一样使用日期范围。从 ![日程表](/help/assets/icons/Calendar.svg) **[!UICONTROL 日期范围]**&#x200B;组件面板中拖动日期范围，并将该组件放置在：

- **[!UICONTROL 日程表]**：用日期范围 ![切换](/help/assets/icons/Switch.svg) **[!UICONTROL 替换]**&#x200B;当前的日程表配置。
- **量度列标题**：![切换](/help/assets/icons/Switch.svg) **[!UICONTROL 替换]**&#x200B;量度、将日期范围 ![添加](/help/assets/icons/Add.svg)**[!UICONTROL  添加&#x200B;]**为量度，或者使用日期范围组件 ![过滤](/help/assets/icons/Filter.svg)**[!UICONTROL &#x200B;过滤&#x200B;]**该量度。
- **维度列标题**：![切换](/help/assets/icons/Switch.svg) **[!UICONTROL 替换]**&#x200B;当前的维度。现在的新维度是&#x200B;**[!UICONTROL 日期范围]**。当维度是日期范围时，您就可以将其他日期范围 ![添加](/help/assets/icons/Add.svg)**[!UICONTROL  添加&#x200B;]**为维度项。
- **维度项**：按日期范围 ![细分](/help/assets/icons/Breakdown.svg) **[!UICONTROL 细分]**&#x200B;特定维度项。

您还可以通过直接在自由格式表格可视化中添加日期范围列：

1. 在量度列中，从上下文菜单中选择：

   - **[!UICONTROL 添加时间段列]**。您可以选择基于当前日程表的建议选项，或创建一个[自定义日期范围](#custom-date-ranges)。
   - **[!UICONTROL 比较时间段]**。您可以选择基于当前日程表的建议选项，或创建一个[自定义日期范围](#custom-date-ranges)。

1. 根据您的选择，额外的日期范围列将会添加到自由格式表中。

## 默认日期范围

Analysis Workspace 提供了许多默认日期范围。


| 日 | 周 | 月 | 季度 | 年 |
|---|---|---|---|---|
| 今天 | 本周 | 本月 | 本季度 | 本年 |
| 昨天 | 本周（不包括今天） | 本月（不包括今天） | 本季度（不包括今天） | 今年（不包括今天） |
| 2 天前 | 2 周前 | 2 个月前 |   |  |
| 3 天前 | 3 周前 | 3 个月前 |  | |
| 最近 7 天 | 上周 | 上个月 | 上个季度 | 去年 |
| 最近 14 天 | 最近的 2 个整周 | 最近 2 个月整 | 最近 4 个整季度 | |
| 最近 30 天 | 最近的 3 个整周 | 最近 3 个月整 | | |
| 最近 60 天 | 最近的 4 个整周 | 最近 6 个月整 | | |
| 最近 90 天 | 最近的 12 个整周 | 最近 12 个月整 | | |
| 最近 7 整天 | 最近的 52 个整周 | 最近 13 个月整 | | |
| 最近 14 整天 | | | | |
| 最近 30 整天 | | | | |
| 最近 90 整天 | | | | |

<table style="table-layout:fixed">

## 自定义日期范围

您可以创建自定义日期范围。请参阅[创建日期范围](/help/components/date-ranges/create.md)，了解可用于创建日期范围的各种选项。然后，您可以在[日期范围构建器](create.md#date-range-builder)中构建、修改和保存日期范围。

您可以使用[日期范围管理器](manage.md)来管理日期范围。
