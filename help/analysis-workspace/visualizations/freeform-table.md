---
title: 自由格式表
description: 了解自由格式表和自由格式表生成器
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 100%

---


# 自由格式表

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html) 略有不同。[了解更多...](/help/getting-started/cja-aa.md)

在 Analysis Workspace 中，自由格式表不仅可以作为数据表，而且还是一个交互式的可视化图表。可以将[组件](/help/components/overview.md)组合拖放到行和列中，以创建自定义表格供您分析。拖动每个组件后，表格会立即更新，这样您便可以进行快速分析。

可以采取多种方式来自定义表格：

* **行**
   * 在执行分页之前，每个维度行最多可显示 400 行。您可以通过调整项目的[视图密度](/help/analysis-workspace/build-workspace-project/view-density.md)，将更多行放入单个屏幕中。
   * 可以按其他组件划分行。要同时划分多行，只需选择多行，然后将下一个组件拖动到选定行上即可。了解有关[划分](/help/components/dimensions/t-breakdown-fa.md)的更多信息。
   * 可以[过滤](/help/analysis-workspace/build-workspace-project/pagination-filtering-sorting.md)行，以显示缩减的项目集。在[行设置](/help/analysis-workspace/build-workspace-project/column-row-settings/table-settings.md)下，提供了其他设置。

* **列**
   * 可以将组件堆放在列中，以创建分段量度、跨标签分析等。
   * 可以在[列设置](/help/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md)下调整每列的视图。
   * 可通过[右键单击菜单](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html)执行多个操作。根据您单击表标题、行或列的情况，菜单可提供不同的操作。

## 自由格式表生成器

如果您希望先向表中添加多个组件，然后再渲染数据，则可以启用自由格式表生成器。启用该生成器后，您可以通过拖放多个维度、划分、量度和区段来构建可解答更复杂业务问题的表格。数据不会即时更新，单击&#x200B;**[!UICONTROL 构建]**&#x200B;后，数据将会更新。

如果您遇到复杂的数据问题，并且您想要构建表格来回答您的问题，则表生成器是一个省时的选项。表生成器的其他优势包括：

* 以所需的确切格式排列表，无需渲染每个操作。
* 可快速划分多达 4 个级别的数据。
* 为每个表行和维度列定义行和划分设置。
* 默认情况下，将针对表的每个级别&#x200B;**[!UICONTROL 按位置划分]**（在传统的自由格式表中，默认为&#x200B;**[!UICONTROL 按项目划分]**）。
* 手动对表中的静态行排序。例如，希望量度行按特定顺序显示。
* 在渲染真实数据之前预览表格式。

请在[此处](https://youtu.be/GUMWiJAmMGI)观看正在运行的自由格式表生成器。

## 导出自由格式表数据

可以通过以下几种方式，从 Analysis Workspace 中复制自由格式表中的数据：

* 右键单击表标题，然后选择&#x200B;**[!UICONTROL 复制到剪贴板]**。这将可以导出完整的（可见）表格。
* 突出显示表中的特定单元格，右键单击并选择&#x200B;**[!UICONTROL 复制到剪贴板]**，或使用 Ctrl + C 热键。
* **[!UICONTROL 项目 > 下载 CSV]**。此操作可将项目中的所有可见表格导出为 CSV。
