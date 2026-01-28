---
description: 了解如何在Analysis Workspace中过滤和排序自由格式表。
title: 过滤和排序
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
role: User
source-git-commit: 696bd0db44949162307d8ce7d2debed351a76cd6
workflow-type: tm+mt
source-wordcount: '1575'
ht-degree: 46%

---

# 筛选和排序自由格式表

Analysis Workspace 中的自由格式表是进行交互式数据分析的基础。因此，它们可以包含数千行信息。对数据进行过滤和排序是有效地呈现最重要信息的关键部分。

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## 过滤表格

Analysis Workspace 中的过滤器可帮助您显示最重要的信息。

>[!NOTE]
>
> 只有动态维度项才能按照本节所述进行过滤。静态维度项无法过滤。如需了解更多信息，请参阅[自由格式表中的动态与静态维度项](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)。

您可以使用多种方法来过滤自由格式表中的行。

* 排除表中的特定行
* 在表中应用过滤器
* 使用受众区段

请务必阅读每种方法如何影响[自由格式表总计](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md)。

### 排除表中的特定行

您可以快速从表中排除特定行，而无需使用 ![过滤器](/help/assets/icons/Filter.svg) **[!UICONTROL 过滤器]**。

>[!NOTE]
>
>当您按照本节所述排除行时，[!UICONTROL 高级]过滤器对话框中会自动添加一个[!UICONTROL 始终排除项目]规则。您可以通过选择 ![过滤器](/help/assets/icons/Filter.svg) 过滤器图标，然后选择[**[!UICONTROL 显示高级]**](#apply-a-simple-or-advanced-filter-to-a-table)来查看已应用的规则。

要从自由格式表中排除特定行，请执行以下操作：

1. 将鼠标悬停在要排除的行上，然后选择![关闭](/help/assets/icons/Close.svg)。

   按住&#x200B;***Shift***&#x200B;键以选择一定范围的行，或按住&#x200B;***Command***&#x200B;键(在Mac上)或&#x200B;***Ctrl***&#x200B;键（在Windows上）以选择多行。

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->


### 对表应用简单或高级筛选

要筛选自由格式表中的数据，请执行以下操作：

1. 将鼠标悬停在包含要过滤的数据的列上。<!--only some types of columns show the filter... Which? Just Dimensions?-->

1. 在 ![过滤器](/help/assets/icons/Filter.svg) **过滤器** 出现时，选择它。

   ![突出显示过滤器图标的自由格式表。](assets/table-filter-icon.png)

   **[!UICONTROL 搜索]**&#x200B;对话框中提供了以下选项：

   ![简单过滤器](assets/filter-simple.png){width="500"}

   | 选项 | 功能 |
   |---------|----------|
   | [!UICONTROL **包括“无值”**] | 选择此选项可在表中显示&#x200B;**[!UICONTROL 无值]**&#x200B;行，其中包含选定维度中没有值的数据。取消选择此选项可隐藏&#x200B;**[!UICONTROL 无值]**&#x200B;行。<!-- Add at multi dim GA: When tables include multiple dimension columns, you can deselect this option to show data only when it applies to each dimension column in the table.--> |
   | [!UICONTROL **搜索单词或短语**] | 指定您想要过滤的单词或短语。仅显示包含指定单词或确切短语的行。 |


1. （可选）要按不同条件或多个条件筛选，请选择&#x200B;[!UICONTROL **显示高级选项**]。

   以下高级过滤选项可用：

   ![简单过滤器](assets/filter-advanced.png){width=500}

   | 选项 | 功能 |
   |---------|----------|
   | [!UICONTROL **包括“无值”**] | 选择此选项可在表中显示&#x200B;**[!UICONTROL 无值]**&#x200B;行，其中包含选定维度中没有值的数据。取消选择此选项可隐藏&#x200B;**[!UICONTROL 无值]**&#x200B;行。 |
   | [!UICONTROL **匹配**] | 选择&#x200B;[!UICONTROL **如果满足所有条件**] 以仅显示满足您指定的所有条件的数据。此选项通常会产生更精确的数据。<br/><br/>选择&#x200B;[!UICONTROL **如果满足任何条件**]&#x200B;以仅显示满足您指定的任一过滤条件的数据。此选项通常会产生不太精确的数据。 |
   | [!UICONTROL **条件**] | 从以下过滤选项中选择：<br/><ul><li>[!UICONTROL **包含短语**]（默认）：只有包含您指定的确切短语的数据才会包含在过滤结果中。单词必须按照&#x200B;[!UICONTROL **搜索单词或短语字段**]&#x200B;中指定的顺序排列。</li><li>[!UICONTROL **包含任何词语**]：只有包含指定短语中的一个或多个单词的数据才会包含在筛选结果中。 </li><li>[!UICONTROL **包含所有词语**]：只有包含指定短语中所有单词的数据才会包含在筛选结果中。单词不需要按照&#x200B;[!UICONTROL **搜索词或短语字段**]&#x200B;中指定的顺序排列。</li><li>[!UICONTROL **不包含任何词语**]：只有不包含指定短语中任何单词的数据才会包含在筛选结果中。 </li><li>[!UICONTROL **不包含短语**]：只有不包含您指定的确切短语的数据才会包含在过滤结果中。单词必须按照&#x200B;[!UICONTROL **搜索词或短语字段**]&#x200B;中指定的顺序排列。</li><li>[!UICONTROL **对等**]：只有与您指定的短语完全匹配的数据才会包含在筛选结果中。 </li><li>[!UICONTROL **不对等**]：只有与您指定的短语不完全匹配的数据才会包含在筛选结果中。 </li><li>[!UICONTROL **开始于**]：只有以您指定的单词或确切短语开头的数据才会包含在筛选结果中。 </li><li>[!UICONTROL **结束于**]：只有以您指定的单词或确切短语结束的数据才会包含在筛选结果中。 </li></ul>（选择 ![添加](/help/assets/icons/Add.svg) [!UICONTROL **添加行**]&#x200B;以添加多个过滤器。您选择的&#x200B;[!UICONTROL **匹配**]&#x200B;选项将会决定&#x200B;**[!UICONTROL 是否满足所有条件]**&#x200B;或&#x200B;**[!UICONTROL 是否满足任何条件]**。 |
   | [!UICONTROL **始终排除项目**] | 指定要从过滤数据中排除的任何项目的名称。 |

1. 选择&#x200B;**[!UICONTROL 应用]**&#x200B;以筛选数据。选择&#x200B;**[!UICONTROL 清除]**&#x200B;来清除所有输入内容。选择&#x200B;**[!UICONTROL 取消]**&#x200B;来取消并关闭对话框。<br/>当表中应用有过滤器时，彩色的 ![过滤器](/help/assets/icons/FilterColored.svg) **过滤器**&#x200B;图标会指示并显示详细信息。

### 在迷你图和折线图可视化图表的趋势数据中包括筛选条件 {#include-filter-criteria}

应用于自由格式表的表维度的任何搜索筛选条件始终包含在迷你图中。

除了迷你图之外，您还可以配置要包含在连接的行可视化中的筛选条件。 (默认情况下，筛选条件不包含在行可视化中。 折线图可视化图表显示所连接表中选定行的数据。 如果未选择任何行，则只显示所连接表的第一个维的数据。)

有关迷你图和折线图可视化的详细信息，请参阅[查看自由格式表的趋势数据](/help/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md)。

#### 配置包含筛选条件的行可视化

1. 在量度列标题中选择迷你图。

   选择迷你图单元格时，它显示为深灰色。 这表示所连接的折线图可视化图表中包含筛选条件。 筛选条件将作为列的区段应用。<!--show how to see it? Show what the segment looks like when it's applied? -->

   已选择![迷你图](assets/table-sparkline-selected.png)

#### 了解列总数何时可能不准确

在以下场景中，列总数可能并不精确：

* 当在左列中使用静态组件时，[列总数计算为行的总和](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)

  如果此方案中的行项目包含重叠数据，则列总数将不正确。

  例如，如果您在左列添加静态区段，然后在右列添加用户作为量度，则其中某些用户可能属于多个静态区段。 在这种情况下，Workspace不会为每个静态区段删除重复用户。 这可能会导致用户总数增加，因为某些用户可能会被多次计数。

* 使用多值维度时

>[!NOTE]
>
>折线图和折线图仍可反映这些场景中的准确总计。

### 使用受众区段

有关详细信息，请参阅[分段概述](/help/components/segments/seg-overview.md)。

## 对表格进行排序

在Analysis Workspace中，您可以按任何列对自由格式表的数据进行排序，无论这些列是维度还是量度。 您甚至可以同时按多个列排序。

默认情况下，维度按升序排序，量度按降序排序。

### 按单列对表进行排序

按本节所述对单列的数据进行排序时，将删除应用于表的所有[高级排序](#sort-tables-by-multiple-columns-advanced-sorting)。

要按单列对表中的数据进行排序，请执行以下操作：

1. 将鼠标悬停在要排序的列的标题上，然后选择&#x200B;**排序**&#x200B;图标![排序](/help/assets/icons/SortOrderDown.svg)（当它出现时）。

   ![排序下拉菜单](assets/sort-dropdown-menu.png)

1. 选择&#x200B;**[!UICONTROL 升序]**&#x200B;或&#x200B;**[!UICONTROL 降序]**。

   对列应用排序时，排序图标保持可见。 箭头指示数据的排序方式（升序为![排序](/help/assets/icons/SortOrderUp.svg)或降序为![排序](/help/assets/icons/SortOrderDown.svg)）。

### 按多列对表进行排序（高级排序）

{{release-limited-testing-section}}

#### 将排序应用于多个列

要按多列对表中的数据进行排序，请执行以下操作：

1. 将鼠标悬停在要排序的任何列的标题上，然后选择&#x200B;**排序**&#x200B;图标![排序](/help/assets/icons/SortOrderDown.svg)（当它出现时）。

   ![排序下拉菜单](assets/sort-dropdown-menu.png)

1. 选择&#x200B;**[!UICONTROL 高级排序]**。

   ![高级排序对话框](assets/sort-advanced-dialog.png)

1. 在高级排序对话框中，执行以下任一操作：

   * 通过选择&#x200B;**[!UICONTROL 添加排序列]**&#x200B;按钮，添加尚未排序的列。

   * 通过选择&#x200B;**删除**&#x200B;图标![删除](/help/assets/icons/Close.svg)来删除您不再想要排序的列。

   * 在列表中上下拖动列可调整排序优先级。

     有关详细信息，请参阅[排序优先级](#sort-priority)。

   * 在下拉菜单中选择&#x200B;**[!UICONTROL 升序]**&#x200B;或&#x200B;**[!UICONTROL 降序]**&#x200B;以更改排序值。

   * 通过选择列名称下拉菜单选择其他列。

1. 选择&#x200B;**[!UICONTROL 应用]**。

对列应用排序时，排序图标保持可见。 箭头指示数据的排序方式（升序为![排序](/help/assets/icons/SortOrderUp.svg)或降序为![排序](/help/assets/icons/SortOrderDown.svg)）。

![多排序示例](assets/dimensions-multiple-sort.png)

#### 排序优先级

当您为多个列排序数据时，将根据您分配给每个列的优先级对数据排序。 优先级编号显示在排序图标![SortOrderDown](/help/assets/icons/SortOrderDown.svg)<sup>➊</sup>旁边。

具有主优先级的列决定主顺序；具有次优先级的列决定主列中行的相同值的顺序；具有第三优先级的列决定主列和次列中行的相同值的顺序；依此类推。

例如，考虑一个包含以下列的表：

* 日期（维度）

* 小时（维度）

* 事件（量度）

您可以为每个列分配排序优先级，如下所示：

| 列（组件）名称 | 组件类型 | 排序优先级 |
|---------|----------|---------|
| 月中几号 | 维度 | 1 |
| 小时 | 维度 | 2 |
| 事件 | 量度 | 3 |

通过为每个列指定排序优先级，您可以确切控制数据在表中的显示方式。 在本例中，信息首先按日期、小时，最后按事件排序。

![多排序示例](assets/dimensions-multiple-sort.png)
