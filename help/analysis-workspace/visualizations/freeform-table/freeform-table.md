---
title: 自由格式表概述
description: 自由格式表是在 Analysis Workspace 中进行数据分析的基础
feature: Visualizations
exl-id: e5ba9089-c575-47b3-af85-b8b2179396ac
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 26%

---

# 自由格式表概述 {#freeform-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_button"
>title="自由格式表"
>abstract="创建一个您可以使用维度、区段、量度和日期范围来构建的空的可视化自由格式表格。您可以使用自由格式表作为其他可视化的基础。"

<!-- markdownlint-enable MD034 -->


在Analysis Workspace中，![表](/help/assets/icons/Table.svg) **[!UICONTROL 自由格式表]**&#x200B;可视化是交互式数据分析的基础。 可以将[组件](/help/components/overview.md)组合拖放到行和列中，以创建自定义表格供您分析。拖动每个组件后，表格会立即更新，以便您能够快速分析和深入探索。

![自由格式表显示行和列中的组件，包括多个网页的访问和在线订单。](assets/opening-section.png)

创建和配置[!UICONTROL 自由格式表]：

* 添加![表](/help/assets/icons/Table.svg) **[!UICONTROL 自由格式表]**&#x200B;可视化图表。 请参阅[将可视化图表添加到面板](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。

## 自动化表

构建表最快捷的方法便是将组件直接拖到空白项目、面板或自由格式表中。系统会按照建议的格式为您构建自由格式表。 [观看教程](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace)。

![将带有访问组件的新面板拖放到工作空间。](assets/automated-table.png)

## 自由格式表生成器

如果您希望先向表中添加多个组件，然后再渲染数据，则可以选择&#x200B;**[!UICONTROL 启用表生成器]**。 启用该生成器后，您可以拖放维度、细分、量度和过滤器来构建可解答更复杂问题的表格。 选择&#x200B;**[!UICONTROL 生成]**&#x200B;后，数据将更新。

![显示](assets/table-builder.png)的自由格式表生成器

## 交互

您可以通过各种方式与自由格式表进行交互并进行自定义设置：

### 过滤和排序

* 您可以[过滤和排序](filter-and-sort.md)表中的数据。

### 行

* 您可以使用![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg)从一个或多个行快速[创建新的可视化图表](../freeform-analysis-visualizations.md#visualize)。
* 您可以通过调整项目的[视图密度](/help/analysis-workspace/build-workspace-project/view-density.md)，将更多行放入单个屏幕中。
* 在执行分页之前，每个维度行最多可显示 400 行。选择第一列标题中&#x200B;**[!UICONTROL 行]**&#x200B;旁边的数字，以在页面上显示更多行。 在第一列标题中使用![ChevronRight](/help/assets/icons/ChevronRight.svg)导航到其他页面。
* 您可以按其他组件划分行。 要同时划分多行，请选择多行，然后将下一个组件拖动到选定行上。 了解有关[划分](/help/components/dimensions/t-breakdown-fa.md)的更多信息。
* 可以[过滤](/help/components/filters/filters-overview.md)行，以显示缩减的项目集。在[行设置](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)下，提供了其他设置。

### 列

* 可以将组件堆放在列中，以创建过滤量度、跨标签分析等。
* 可以在[列设置](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)下调整每列的视图。
* 可通过[上下文菜单](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)执行多个操作。 根据您选择的是表标题、行还是列，菜单会提供不同的操作。


## 设置

选择![设置](/help/assets/icons/Setting.svg)以显示&#x200B;**[!UICONTROL 表设置]**。 以下特定可视化图表[设置](../freeform-analysis-visualizations.md#settings)可用：

### 数据源

| 选项 | 描述 |
|---|---|
| **[!UICONTROL 链接的可视化图表]**。 | 列出所有链接的可视化图表。 |
| **[!UICONTROL 显示数据源]** | 取消选中后，充当可视化图表数据源的自由格式表将在Workspace中隐藏。 |

### 设置

| 选项 | 描述 |
|---|---|
| **[!UICONTROL 将每列的日期调整为全部从同一行开始]** | 对齐或不对齐每列的日期与所有开始日期在同一行。 |


## 上下文菜单

可视化图表的标题中提供了以下[上下文菜单](../freeform-analysis-visualizations.md#context-menu)选项：

| 选项 | 描述 |
| --- | --- |
| **[!UICONTROL 插入复制的可视化图表]**n | 将复制的可视化图表粘贴（插入）到项目中的其他位置或完全不同的项目中。 |
| **[!UICONTROL 将数据复制到剪贴板]** | 将数据从可视化图表复制到剪贴板。 |
| **[!UICONTROL 将选定内容复制到剪贴板]** | 将可视化图表中的选定内容复制到剪贴板。 |
| **[!UICONTROL 以CSV格式下载项目（*维度名称*）]** | 立即将可视化的维度项目（最多50,000个）下载到您的本地设备。 所选维度的最大维度项为50,000个。 |
| **[!UICONTROL 复制可视化图表]** | 复制可视化图表，以便您可以将该可视化图表插入到项目中的其他位置或完全不同的项目中。 |
| **[!UICONTROL 下载数据CSV]** | 立即将可视化图表的显示数据下载到您的本地设备。 |
| **[!UICONTROL 导出完整表……]** | 将整个表导出到指定的云位置。 请参阅[将Customer Journey Analytics报告导出到云](../../export/export-cloud.md) |
| **[!UICONTROL 重复的可视化图表]** | 生成一个与可视化图表完全相同的副本。 |
| **[!UICONTROL 编辑描述]** | 添加（或编辑）可视化图表的文本描述。 查看[文本](../text.md)。 |
| **[!UICONTROL 获取可视化图表链接]** | 直接复制并共享可视化图表的链接。 共享链接对话框会显示该链接。 选择复制以将链接复制到剪贴板。 |
| **[!UICONTROL 从头开始]** | 删除当前可视化图表的配置，以便您可以从头开始重新配置。 |


>[!MORELIKETHIS]
>
>[将可视化图表添加到面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[可视化设置](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[可视化上下文菜单](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
