---
description: 行设置因您拖入到表格中的组件而异。
title: 行设置
feature: Visualizations
exl-id: a9438d83-498d-4b22-9e5e-c357bd3a2680
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 88%

---

# 行设置

在此处查看有关行和列设置的视频：

>[!VIDEO](https://video.tv.adobe.com/v/40382/?quality=12)

行设置因您拖入到表格中的组件而异。要访问表格行设置，请单击每个行内的维度、筛选器、量度、时间段或划分旁边的[!UICONTROL 设置]图标：

![自由格式表突出显示指标的“设置”图标](assets/row-settings.png)

| 设置 | 描述 |
| --- | --- |
| 调整日期 | 这是一个表级设置，它会将每列的日期调整为全部从同一行开始。默认情况下，当在表行中使用时间维度且在列中应用不同的日期范围时，会启用日期调整。例如，在每日表中将“10 月”和“9 月”应用于列，则左列从 10 月 1 日开始，右列从 9 月 1 日开始。 |
| 按位置划分 | 默认情况下，此设置处于禁用状态，并且划分固定在静态行项目。例如，假设您按营销渠道划分排名前 3 的“页面”维度项（主页、搜索结果、结账）。然后，您离开项目，两周后返回。再次打开项目时，排名前 3 的页面已更改，此时“主页”、“搜索结果”和“结账”页面成为排名第 4-6 的页面。默认情况下，营销渠道划分仍将显示在“主页”、“搜索结果”和“结账”下方，即使三者现在分别位于第 4-6 行中。<br>相反，**按位置划分**&#x200B;始终划分排名前 3 的项目，而不管它们具体是什么。回顾我们的示例，当您重新打开项目时，营销渠道划分将会绑定到表中排名前 3 的页面，而不是“主页”、“搜索结果”和“结账”（三者现在分别位于第 4-6 行中）。 |
| 百分比 | **按列计算百分比**&#x200B;是默认设置；列中显示的百分比是根据列总数计算的。<br>**按行计算百分比**&#x200B;强制自由格式表计算整行中的单元格百分比，而不是沿列向下计算，该计算方式以总计作为分母。这对显示百分比趋势特别有用。默认情况下，使用“可视化图表”图标时会启用此设置。 |
| 列总计 | 这些设置仅可用于[静态行](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)。<br> **显示为当前行的总和**&#x200B;显示表中行的客户端总和，这意味着总计将&#x200B;*不*&#x200B;去除重复的量度，如访问次数或人员。<br> **显示总计**&#x200B;将显示服务器端总和，这意味着总计将去除重复量度。 |

## 更改行计数

要更改显示的行数，请执行以下步骤：

1. 单击表顶部的[!UICONTROL 行数]旁边的数字。

   ![自由格式表，显示所显示行数的下拉列表。 已选择400行。](assets/row-number.png)

1. 从下拉列表中，选择您希望表显示的行数。