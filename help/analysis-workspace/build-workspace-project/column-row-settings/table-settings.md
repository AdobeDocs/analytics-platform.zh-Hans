---
description: 行设置因您拖入到表格中的组件而异。
title: 行设置
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 89%

---


# 行设置

>[!NOTE]
>
>您正在查看Customer Journey Analytics中的Analysis Workspace文档。 其功能集与传统Adobe [Analytics的Analysis Workspace略有不同](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html)。 [了解更多...](/help/getting-started/cja-aa.md)

行设置因您拖入到表格中的组件而异。

您还可以[在表格中使用右键单击操作](/help/analysis-workspace/visualizations/freeform-table.md)来管理选定行。

要访问表格行设置，请单击每个行内的维度、区段、量度、时间段或划分旁边的“设置”图标：

![](assets/row-settings.png)

| 行设置 | 描述 |
|--- |--- |
| 日期比较 | 将每列的日期调整为全部从同一行开始。如果选择调整日期，例如在 2016 年 10 月和 9 月间的月同比比较中，左列将从 10 月 1 日开始，右列将从 9 月 1 日开始。<br>默认情况下处于禁用状态。 |
| 百分数 | 按行计算百分比 强制自由格式表计算整行中的单元格百分比，而不是沿列向下计算。这对显示百分比趋势特别有用。<br>默认情况下，在使用“可视化”图标时启用。 |
| 列总计 | 这些设置只显示 [static rows](/help/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) (when you have selected a finite set of items), not with dynamic rows (i.e., when you drop in a dimension that shows all items).<ul><li>**[!UICONTROL 将当前行的总和显示为总计]** - 此设置将显示表中行的客户端总和，这意味着总计将&#x200B;**不会**&#x200B;消除重复的量度，如访问次数或访客。</li><li>**[!UICONTROL 显示总计]** - 此设置将显示服务器端总和，这意味着总计将消除重复的量度，如访问次数或访客。</li></ul> |
| 划分 | **[!UICONTROL 按位置划分]** - 您可以基于自由格式表中的固定位置执行划分。例如，您可以指定始终对表的头七行进行划分。<br>（以前，划分中的值列表会被“锁定”。这会导致这样一种情况，例如，如果您按页面划分日期，则会得到您选定日期范围内的前 50 页的列表。如果您保存了该报表然后在一个月后运行它，则头 50 页很可能已发生更改。然而，Analysis Workspace 将使用来自原始划分的结果并返回相同页面，但将当前月份作为日期范围。）<br>要执行基于固定位置的划分，请执行以下操作：1. 划分表格中的一些行。2. 单击希望处于固定位置的表格行旁边的“设置”（齿轮）图标。3. 选中按位置划分旁边的复选框。4. 更改排序顺序或日期范围，并注意划分现在已绑定到行位置，而不是硬编码的行。<br>默认情况下处于禁用状态。 |