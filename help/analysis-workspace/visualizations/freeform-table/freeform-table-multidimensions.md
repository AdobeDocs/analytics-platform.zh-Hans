---
title: 在自由格式表中包含多个维度
description: 了解如何在自由格式表中包含多个维度
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: bff352181392c19b6c4fe70893a016179fb77f06
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 2%

---

# 在自由格式表中包含多个维度

{{release-limited-testing}}

在自由格式表中最多可包含5个维度列，这样您可以并排查看多个维度项目。 维度项目的每一行都作为单个连接项目。

您可以对维度列（以及量度列）进行排序，以实现更完整且自定义的分析。

## 多个维度列和划分

Analysis Workspace提供了以下方式在自由格式表中添加多个维度：

* 包括多个维度列（如本文所述）

* [添加划分](/help/components/dimensions/t-breakdown-fa.md)

这两种方法都允许您根据其他维度分析维度。 但是，两者之间有着重要差异，可以在同一表中使用这两种方法进行更深入的分析。

利用多个维度列，您可以：

* 跨多个维度和量度关联数据行。

* 仅当数据适用于表中的每个维度列时才显示数据。 要完成此操作，请使用列筛选器取消选择每个维度列上的&#x200B;**[!UICONTROL 包括“没有值”]**&#x200B;设置。

  有关详细信息，请参阅[筛选和排序表](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。

* 按多个维度和量度列对数据进行排序。

  有关详细信息，请参阅[筛选和排序表](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。

划分允许您：

* 仅显示针对一个的维度项

* 显示单个的排名最前的维度项目

## 添加维度列

可一次添加一个维列或批量添加维列。

1. 在Analysis Workspace中，创建一个自由格式表。

   有关详细信息，请参阅[可视化概述](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)中的[将可视化添加到面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)。

1. 向自由格式表添加维度。 可一次添加一个维度，也可以一次添加多个维度。

   * 将维度逐个拖动到自由格式表中。 将其他维度列放置在表中现有维度列的左侧或右侧。 将在其中创建新列的位置显示一条蓝色垂直&#x200B;**[!UICONTROL 添加]**&#x200B;行。

     ![拖动单个维度](assets/dimensions-add-individually.png)

   * 在组件菜单中选择最多5个维度，然后将它们拖动到自由格式表中。 维度会按您选择的顺序从左到右添加到表中。

     要选择多个维度，请按住&#x200B;***命令***&#x200B;键(在Mac上)或&#x200B;***Ctrl***&#x200B;键（在Windows上）。

     ![拖动多个维度](assets/dimensions-add-multiple.png)

## 过滤表格

有关筛选表的信息，请参阅[筛选和排序表](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#filter-tables)中的[筛选表](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。

## 对表格进行排序 {#sort-tables}

<!--At GA, move this section into the "Filter and sort tables" article and replace the current "Sort tables" section. Change the "Filter tables" section above to "Filter and sort tables" and link to the other article. Also add row to Guardrails article. -->

您可以按Analysis Workspace中作为维度或量度的任何列对自由格式表的数据进行排序。

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

当您为多个列排序数据时，将根据您分配给每个列的优先级对数据排序。 优先级编号显示在排序图标![排序优先级图标](assets/sort-priority-icon.png)旁边。

具有主优先级的列决定主顺序，具有次优先级的列决定主列中行的相同值的顺序，具有第三优先级的列决定主列和次列中行的相同值的顺序，依此类推。

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

## 将划分添加到具有多个维度列的表中

向具有多个维度列的表添加划分时，该划分会跨越添加该划分的行上的所有维度项。

您可以按照[划分维度](/help/components/dimensions/t-breakdown-fa.md)中的说明添加划分。

## 不支持的维度 {#unsupported}

不支持以下维度组合，Analysis Workspace会禁止添加这些维度组合，或在添加这些维度组合后显示错误消息：

* 多个维度来自引用在同一自由格式表中一起使用的不同[对象数组](/help/use-cases/object-arrays.md)的字段。

  同一自由格式表中允许同时使用多个维度（如果它们引用相同的对象数组）。