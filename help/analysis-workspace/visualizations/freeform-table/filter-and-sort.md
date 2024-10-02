---
description: 描述如何在 Analysis Workspace 中筛选和排序表格的文档。
title: 排序和过滤表格
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
role: User
source-git-commit: 590a3ddbe988d27341fe96a3fa866960d1641e24
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 42%

---

# 自由格式表筛选和排序

Analysis Workspace 中的自由格式表是进行交互式数据分析的基础。因此，它们可以包含数千行信息。对数据进行过滤和排序是有效地呈现最重要信息的关键部分。

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## 过滤表格

Analysis Workspace 中的过滤器可帮助您显示最重要的信息。

>[!NOTE]
>
> 仅可以过滤动态维度项，如本节所述。 无法筛选静态维度项目。 有关详细信息，请参阅自由格式表中的[动态与静态维度项](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)。

您可以使用多种方法来过滤自由格式表中的行。

- 从表中排除特定行
- 将过滤器应用到表
- 使用受众过滤器

请务必阅读每种方法如何影响[自由格式表总计](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md)。

### 从表中排除特定行

您可以快速从表中排除特定行，而无需使用![筛选器](/help/assets/icons/Filter.svg) **[!UICONTROL 筛选器]**。

>[!NOTE]
>
>如本节所述，排除行时，会在[!UICONTROL 高级]筛选器对话框中自动添加[!UICONTROL 始终排除项]规则。 您可以通过选择![筛选器](/help/assets/icons/Filter.svg)筛选器图标，然后选择[**[!UICONTROL 显示高级选项]**](#apply-a-simple-or-advanced-filter-to-a-table)来查看应用的规则。

要从自由格式表中排除特定行，请执行以下操作：

1. 将鼠标悬停在要排除的行上，然后选择![关闭](/help/assets/icons/Close.svg)。

   按住&#x200B;***shift***&#x200B;以选择一定范围的行，或按住&#x200B;***cmd***&#x200B;键(在Mac上)或&#x200B;***ctrl***&#x200B;键（在Windows上）以选择多行。

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->


### 对表应用简单或高级过滤器

过滤自由格式表中的数据：

1. 将鼠标悬停在包含要过滤的数据的列上。<!--only some types of columns show the filter... Which? Just Dimensions?-->

1. 选择![筛选器](/help/assets/icons/Filter.svg) **筛选器**（出现时）。

   ![自由格式表突出显示“筛选器”图标。](assets/table-filter-icon.png)

   **[!UICONTROL 搜索]**&#x200B;对话框中提供了以下选项：

   ![简单筛选](assets/filter-simple.png){width="500"}

   | 选项 | 功能 |
   |---------|----------|
   | [!UICONTROL **包括“无值”**] | 选择此选项可在表中针对选定维度没有值的数据显示&#x200B;**[!UICONTROL 没有值]**&#x200B;行。 取消选择此选项可隐藏&#x200B;**[!UICONTROL 无值]**&#x200B;行。 |
   | [!UICONTROL **搜索单词或短语**] | 指定要作为过滤依据的单词或短语。 仅显示包含指定单词或确切短语的行。 |


1. （可选）要按不同条件或多个条件筛选，请选择&#x200B;[!UICONTROL **显示高级选项**]。

   可以使用以下高级筛选器选项：

   ![简单筛选](assets/filter-advanced.png){width=500}

   | 选项 | 功能 |
   |---------|----------|
   | [!UICONTROL **包括“无值”**] | 选择此选项可在表中针对选定维度没有值的数据显示&#x200B;**[!UICONTROL 没有值]**&#x200B;行。 取消选择此选项可隐藏&#x200B;**[!UICONTROL 无值]**&#x200B;行。 |
   | [!UICONTROL **匹配**] | 选择&#x200B;[!UICONTROL **如果满足所有条件**] 以仅显示满足您指定的所有条件的数据。此选项通常会产生更精确的数据。<br/><br/>选择&#x200B;[!UICONTROL **如果满足任意标准**]，则显示满足您指定的任意筛选条件的数据。 此选项通常会产生不太精确的数据。 |
   | [!UICONTROL **条件**] | 从以下筛选器选项中选择：<br/><ul><li>[!UICONTROL **包含短语**]（默认）：过滤的结果中只包含包含您指定的精确短语的数据。 单词必须按照&#x200B;[!UICONTROL **搜索词或短语字段**]&#x200B;中指定的顺序排列。</li><li>[!UICONTROL **包含任何词语**]：只有包含指定短语中的一个或多个单词的数据才会包含在筛选结果中。 </li><li>[!UICONTROL **包含所有词语**]：只有包含指定短语中所有单词的数据才会包含在筛选结果中。单词不需要按照&#x200B;[!UICONTROL **搜索词或短语字段**]&#x200B;中指定的顺序排列。</li><li>[!UICONTROL **不包含任何词语**]：只有不包含指定短语中任何单词的数据才会包含在筛选结果中。 </li><li>[!UICONTROL **不包含短语**]：只有不包含您指定的确切短语的数据才会包含在过滤结果中。单词必须按照&#x200B;[!UICONTROL **搜索词或短语字段**]&#x200B;中指定的顺序排列。</li><li>[!UICONTROL **等于**]：过滤的结果中只包括与指定的短语完全匹配的数据。 </li><li>[!UICONTROL **不对等**]：只有与您指定的短语不完全匹配的数据才会包含在筛选结果中。 </li><li>[!UICONTROL **开始于**]：只有以您指定的单词或确切短语开头的数据才会包含在筛选结果中。 </li><li>[!UICONTROL **结束于**]：只有以您指定的单词或确切短语结束的数据才会包含在筛选结果中。 </li></ul>选择![添加](/help/assets/icons/Add.svg) [!UICONTROL **添加行**]&#x200B;以添加多个筛选条件。 您为&#x200B;[!UICONTROL **匹配**]&#x200B;选择的选项将决定&#x200B;**[!UICONTROL 如果满足所有条件]**&#x200B;或&#x200B;**[!UICONTROL 如果满足任意条件]**。 |
   | [!UICONTROL **始终排除项目**] | 指定要从过滤数据中排除的任何项目的名称。 |

1. 选择&#x200B;**[!UICONTROL 应用]**&#x200B;以筛选数据。 选择&#x200B;**[!UICONTROL 清除]**&#x200B;以清除所有输入。 选择&#x200B;**[!UICONTROL 取消]**&#x200B;以取消并关闭对话框。 <br/>将过滤器应用于表时，彩色![过滤器](/help/assets/icons/FilterColored.svg) **过滤器**&#x200B;图标指示并显示详细信息。

### 使用受众过滤器

有关详细信息，请参阅[筛选器概述](/help/components/filters/filters-overview.md)。

## 对表格进行排序

您可以按Analysis Workspace中作为维度或量度的任何列对自由格式表的数据进行排序。 箭头指示数据的排序方式(**↓**&#x200B;表示降序，**↑**&#x200B;表示升序)。

![排序](assets/sorting.gif)
