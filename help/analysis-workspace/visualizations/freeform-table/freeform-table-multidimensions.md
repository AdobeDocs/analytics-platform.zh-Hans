---
title: 在自由格式表中包含多个维度
description: 了解如何在自由格式表中包含多个维度
feature: Visualizations
role: User
source-git-commit: e51dced9ac7886ae8d087ca3b2fc6ac2755c3ac6
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 1%

---

# 在自由格式表中包含多个维度列

{{release-limited-testing}}

在自由格式表中最多可包含5个维度列，这样您可以并排查看多个维度项目。 每一行维度项目的行为类似于单个连接的维度项目。

您可以将过滤器、排序、划分等应用于具有多个维度列的自由格式表，从而创建更深入、更自定义的分析。

## 连接的维度项目

当您[将多个维度列添加到自由格式表](#add-multiple-dimension-columns)时，维度项的每一行都将像单个串联维度项那样运行。 此功能允许您查看特定维度组合的量度数据。

例如，考虑一个自由格式表，其中的维度列为&#x200B;_城市_、_设备类型_&#x200B;和&#x200B;_日期_，量度为&#x200B;_事件_。 本表第一行的3个维度项成为单个拼接维度项，表明每个月30日孟买通过手机发生了2,056个事件。

| Dimension：城市 | Dimension：设备类型 | Dimension：日期 | 量度：事件 |
|---------|----------|---------|---------|
| 孟买 | 手机 | 30 | 2,056 |
| 纽约 | 平板电脑 | 31 | 1,761 |
| 班加罗尔 | 桌面 | 1 | 1,666 |
| 德里 | 手机 | 14 | 1,396 |

下表显示于Analysis Workspace中：

![多维度示例](assets/multi-dim-example.png)

## 添加多个维度列

可一次添加多个维列或批量添加多个维列。

1. 在Analysis Workspace中，创建一个自由格式表。

   有关详细信息，请参阅[可视化概述](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)中的[将可视化添加到面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)。

1. 向自由格式表添加维度。 可一次添加一个维度，也可以一次添加多个维度。

   * 将维度逐个拖动到自由格式表中。 将其他维度列放置在表中现有维度列的左侧或右侧。 将在其中创建新列的位置显示一条蓝色垂直&#x200B;**[!UICONTROL 添加]**&#x200B;行。

     ![拖动单个维度](assets/dimensions-add-individually.png)

   * 在组件菜单中选择最多5个维度，然后将它们拖动到自由格式表中。 维度按您选择它们的顺序从左到右添加到表中。

     要选择多个维度，请按住&#x200B;***命令***&#x200B;键(在Mac上)或&#x200B;***Ctrl***&#x200B;键（在Windows上）。

     ![拖动多个维度](assets/dimensions-add-multiple.png)

1. 将表的每一行作为单个维度项查看。 有关详细信息，请参阅[串联的维度项](#concatenated-dimension-items)。

## 排序和过滤表格

您可以对自由格式表中的列应用筛选和排序。 您可以按任何列对自由格式表的数据进行排序，无论这些列是维度还是量度。 您甚至可以同时按多个列排序。

有关信息，请参阅[筛选和排序自由格式表](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。

## 多个维度列和划分

Analysis Workspace提供了以下方式在自由格式表中添加多个维度：

* 包括多个维度列（如本文所述）

* [添加划分](/help/components/dimensions/t-breakdown-fa.md)

这两种方法都允许您根据其他维度分析维度。 但是，两者之间有着重要差异，可以在同一表中使用这两种方法进行更深入的分析。

### 维度列和划分之间的差异

利用多个维度列，您可以：

* 将维度项目连接到多个维度上的不同数据行。

* 仅当维度项应用于表中的每个维度列时，才将维度项包含在连接行中。 要完成此操作，请使用列筛选器取消选择每个维度列上的&#x200B;**[!UICONTROL 包括“没有值”]**&#x200B;设置。

  有关详细信息，请参阅[按多列对表进行排序（高级排序）](#sort-tables-by-multiple-columns-advanced-sorting)。

* 按多个维度和量度列排序数据，以查看更多自定义数据。

  有关详细信息，请参阅[按多列对表进行排序（高级排序）](#sort-tables-by-multiple-columns-advanced-sorting)

划分允许您：

* 在自由格式表中按次要维度划分维度项。 对于次要维度，最多可显示400个维度项目。

### 将划分添加到具有多个维度列的表中

向具有多个维度列的表添加划分时，该划分会应用于添加该划分的行上的拼接维度项（在所有维度列中）。

![多排序划分示例](assets/dimensions-multiple-sort-breakdown.png)

此外，您还可以在划分中添加多个维度列。 划分中的每一行维度项目的行为也类似于单个串联维度项目。

<!-- Add a screenshot of a breakdown with multiple cllumns, then add this sentence: "For example, you can break down the first dimension item in this table by a new concatenated dimension item that shows..." -->

有关如何添加划分的更多信息，请参阅[划分维度](/help/components/dimensions/t-breakdown-fa.md)。

## 基于跨多个维度列的维度项创建区段

当您基于跨越多个维度列的维度项创建区段时，每个维度项都包含在区段定义中，并且使用And运算符连接它们。

有关创建区段的信息，请参阅[创建区段](/help/components/segments/seg-create.md)。

## 不支持的维度 {#unsupported}

不支持以下维度组合，Analysis Workspace会禁止添加这些维度组合，或在添加这些维度组合后显示错误消息：

* 多个维度来自引用在同一自由格式表中一起使用的不同[对象数组](/help/use-cases/object-arrays.md)的字段。

  同一自由格式表中允许同时使用多个维度（如果它们引用相同的对象数组）。