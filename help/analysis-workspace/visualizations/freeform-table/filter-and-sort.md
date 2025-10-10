---
description: 了解如何在Analysis Workspace中过滤和排序自由格式表。
title: 过滤和排序
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
role: User
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 97%

---

# 过滤和排序

Analysis Workspace 中的自由格式表是进行交互式数据分析的基础。因此，它们可以包含数千行信息。对数据进行过滤和排序是有效地呈现最重要信息的关键部分。

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## 过滤表格

Analysis Workspace 中的过滤器可帮助您显示最重要的信息。

>[!NOTE]
>
> 只有动态维度项才能按照本节所述进行过滤。静态维度项无法过滤。如需了解更多信息，请参阅[自由格式表中的动态与静态维度项](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)。

您可以使用多种方法来过滤自由格式表中的行。

- 排除表中的特定行
- 在表中应用过滤器
- 使用受众区段

请务必阅读每种方法对[自由格式表总计](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md)的影响。

### 排除表中的特定行

您可以快速从表中排除特定行，而无需使用 ![过滤器](/help/assets/icons/Filter.svg) **[!UICONTROL 过滤器]**。

>[!NOTE]
>
>当您按照本节所述排除行时，[!UICONTROL 高级]过滤器对话框中会自动添加一个[!UICONTROL 始终排除项目]规则。您可以通过选择 ![过滤器](/help/assets/icons/Filter.svg) 过滤器图标，然后选择[**[!UICONTROL 显示高级]**](#apply-a-simple-or-advanced-filter-to-a-table)来查看已应用的规则。

要从自由格式表中排除特定行：

1. 将鼠标悬停在要排除的行上，然后选择![关闭](/help/assets/icons/Close.svg)。

   按住 ***shift*** 键来选择一系列行，或者按住 ***cmd*** 键（在 Mac 上）或 ***ctrl*** 键（在 Windows 上）选择多行。

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->


### 对表格应用简单或高级过滤器

要过滤自由格式表中的数据：

1. 将鼠标悬停在包含要过滤的数据的列上。<!--only some types of columns show the filter... Which? Just Dimensions?-->

1. 在 ![过滤器](/help/assets/icons/Filter.svg) **过滤器** 出现时，选择它。

   ![突出显示过滤器图标的自由格式表。](assets/table-filter-icon.png)

   **[!UICONTROL 搜索]**&#x200B;对话框中提供了以下选项：

   ![简单过滤器](assets/filter-simple.png){width="500"}

   | 选项 | 功能 |
   |---------|----------|
   | [!UICONTROL **包括“无值”**] | 选择此选项可在表中显示&#x200B;**[!UICONTROL 无值]**&#x200B;行，其中包含选定维度中没有值的数据。取消选择此选项可以隐藏&#x200B;**[!UICONTROL 无值]**&#x200B;行。 |
   | [!UICONTROL **搜索单词或短语**] | 指定您想要过滤的单词或短语。仅显示包含指定单词或确切短语的行。 |


1. （可选）要按不同条件或多个条件筛选，请选择&#x200B;[!UICONTROL **显示高级选项**]。

   以下高级过滤选项可用：

   ![简单过滤器](assets/filter-advanced.png){width=500}

   | 选项 | 功能 |
   |---------|----------|
   | [!UICONTROL **包括“无值”**] | 选择此选项可在表中显示&#x200B;**[!UICONTROL 无值]**&#x200B;行，其中包含选定维度中没有值的数据。取消选择此选项可以隐藏&#x200B;**[!UICONTROL 无值]**&#x200B;行。 |
   | [!UICONTROL **匹配**] | 选择&#x200B;[!UICONTROL **如果满足所有条件**] 以仅显示满足您指定的所有条件的数据。此选项通常会产生更精确的数据。<br/><br/>选择&#x200B;[!UICONTROL **如果满足任何条件**]&#x200B;以仅显示满足您指定的任一过滤条件的数据。此选项通常会产生不太精确的数据。 |
   | [!UICONTROL **条件**] | 从以下过滤选项中选择：<br/><ul><li>[!UICONTROL **包含短语**]（默认）：只有包含您指定的确切短语的数据才会包含在过滤结果中。单词必须按照&#x200B;[!UICONTROL **搜索单词或短语字段**]&#x200B;中指定的顺序排列。</li><li>[!UICONTROL **包含任何词语**]：只有包含指定短语中的一个或多个单词的数据才会包含在筛选结果中。 </li><li>[!UICONTROL **包含所有词语**]：只有包含指定短语中所有单词的数据才会包含在筛选结果中。单词不需要按照&#x200B;[!UICONTROL **搜索词或短语字段**]&#x200B;中指定的顺序排列。</li><li>[!UICONTROL **不包含任何词语**]：只有不包含指定短语中任何单词的数据才会包含在筛选结果中。 </li><li>[!UICONTROL **不包含短语**]：只有不包含您指定的确切短语的数据才会包含在过滤结果中。单词必须按照&#x200B;[!UICONTROL **搜索词或短语字段**]&#x200B;中指定的顺序排列。</li><li>[!UICONTROL **对等**]：只有与您指定的短语完全匹配的数据才会包含在筛选结果中。 </li><li>[!UICONTROL **不对等**]：只有与您指定的短语不完全匹配的数据才会包含在筛选结果中。 </li><li>[!UICONTROL **开始于**]：只有以您指定的单词或确切短语开头的数据才会包含在筛选结果中。 </li><li>[!UICONTROL **结束于**]：只有以您指定的单词或确切短语结束的数据才会包含在筛选结果中。 </li></ul>（选择 ![添加](/help/assets/icons/Add.svg) [!UICONTROL **添加行**]&#x200B;以添加多个过滤器。您选择的&#x200B;[!UICONTROL **匹配**]&#x200B;选项将会决定&#x200B;**[!UICONTROL 是否满足所有条件]**&#x200B;或&#x200B;**[!UICONTROL 是否满足任何条件]**。 |
   | [!UICONTROL **始终排除项目**] | 指定要从过滤数据中排除的任何项目的名称。 |

1. 选择&#x200B;**[!UICONTROL 应用]**&#x200B;以筛选数据。选择&#x200B;**[!UICONTROL 清除]**&#x200B;来清除所有输入内容。选择&#x200B;**[!UICONTROL 取消]**&#x200B;来取消并关闭对话框。<br/>当表中应用有过滤器时，彩色的 ![过滤器](/help/assets/icons/FilterColored.svg) **过滤器**&#x200B;图标会指示并显示详细信息。

### 使用受众区段

有关详细信息，请参阅[分段概述](/help/components/segments/seg-overview.md)。

## 对表格进行排序

您可以按 Analysis Workspace 中的任何列（维度或量度）对自由格式表的数据进行排序。箭头表示数据的排序方式（**↓** 表示降序，或 **↑** 表示升序）。

![排序](assets/sorting.gif)
