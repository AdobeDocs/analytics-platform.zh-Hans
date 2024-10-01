---
title: 日期范围概述
description: 了解日期范围是什么，以及如何在报告中使用它们。
feature: Calendar
exl-id: 99b31bd9-32f1-4da1-9e47-6d90c66282c5
role: User
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 21%

---

# 日期范围概述

在Workspace项目中，通常使用面板](/help/analysis-workspace/c-panels/panels.md#calendar)中的[日历指定该面板中可视化的日期范围。

日期范围组件允许您定义和覆盖面板的日历设置。

<!-- Very old video, should we show it?

+++ View a video illustrating use of calendar and date ranges

>[!VIDEO](https://video.tv.adobe.com/v/24136?format=jpeg)

{{videoaa}}
+++

-->

## 使用日期范围

您可以使用日期范围组件重新定义面板的日历。

或者，您可以在自由格式表中将日期范围用作量度或维度。

![日期范围使用情况](/help/components/date-ranges/assets/date-ranges-usage.png)

- **指标**。 例如，比较特定量度两个不同月份的维度。
- **Dimension**。 比较日期范围维度的不同维度项目上的量度。

>[!NOTE]
>
>在自由格式表中使用日期范围时，日期范围会覆盖为自由格式表所属的面板指定的日历。
>

您可以使用日期范围，就像[使用任何组件](/help/components/overview.md#analysis-workspace-components)一样。 您从![日历](/help/assets/icons/Calendar.svg) **[!UICONTROL 日期范围]**&#x200B;组件面板拖动日期范围，并将组件放置在：

- **[!UICONTROL 日历]**：您![切换](/help/assets/icons/Switch.svg)**[!UICONTROL 将]**&#x200B;当前日历配置替换为日期范围。
- **量度列标题**：您![切换](/help/assets/icons/Switch.svg) **[!UICONTROL 替换]**&#x200B;量度，![添加](/help/assets/icons/Add.svg)**[!UICONTROL 添加&#x200B;]**日期范围作为量度，或者![筛选](/help/assets/icons/Filter.svg)**[!UICONTROL &#x200B;筛选&#x200B;]**使用日期范围组件的量度。
- **列标题** Dimension：您![切换](/help/assets/icons/Switch.svg) **[!UICONTROL 替换]**&#x200B;当前维度。 新维度现在为&#x200B;**[!UICONTROL 日期范围]**。 一旦维度为日期范围，您可以![添加](/help/assets/icons/Add.svg)**[!UICONTROL 添加&#x200B;]**其他日期范围作为维度项。
- **Dimension项**：您![按日期范围](/help/assets/icons/Breakdown.svg)划分&#x200B;**[!UICONTROL 划分]**&#x200B;特定维度项。

您还可以直接在自由格式表可视化图表中添加日期范围列：

1. 在量度列中，从上下文菜单中选择：

   - **[!UICONTROL 添加时间段列]**。 您可以在基于当前日历的建议选项之间进行选择，也可以创建[自定义日期范围](#custom-date-ranges)。
   - **[!UICONTROL 比较时间段]**。 您可以在基于当前日历的建议选项之间进行选择，也可以创建[自定义日期范围](#custom-date-ranges)。

1. 根据您的选择，会将其他日期范围列添加到自由格式表中。

## 默认日期范围

Analysis Workspace提供了大量默认日期范围。


| 日 | 周 | 月 | 季度 | 年 |
|---|---|---|---|---|
| 今天 | 本周 | 本月 | 本季度 | 今年 |
| 昨天 | 本周（不包括今天） | 本月（不包括今天） | 本季度（不包括今天） | 今年（不包括今天） |
| 2天前 | 2 周前 | 2个月前 |   |  |
| 3天前 | 3 周前 | 3个月前 |  | |
| 最近 7 天 | 上周 | 上个月 | 上个季度 | 去年 |
| 最近 14 天 | 最近的 2 个整周 | 过去2个月 | 最近 4 个整季度 | |
| 最近 30 天 | 最近的 3 个整周 | 过去3个月 | | |
| 最近 60 天 | 最近的 4 个整周 | 过去6个月 | | |
| 最近 90 天 | 最近的 12 个整周 | 过去12个月 | | |
| 最近 7 整天 | 最近的 52 个整周 | 过去13个月 | | |
| 最近 14 整天 | | | | |
| 最近 30 整天 | | | | |
| 最近 90 整天 | | | | |

<table style="table-layout:fixed">

## 自定义日期范围

您可以创建自己的自定义日期范围。 有关创建日期范围的各种可用选项，请参阅[创建日期范围](/help/components/date-ranges/create.md)。 然后在[日期范围生成器](create.md#date-range-builder)中生成、修改和保存日期范围。

您使用[日期范围管理器](manage.md)管理日期范围。
