---
title: 自由格式表
description: 自由格式表是在 Analysis Workspace 中进行数据分析的基础
feature: Visualizations
exl-id: e5ba9089-c575-47b3-af85-b8b2179396ac
source-git-commit: 43c8af6f9010354258a702fb702a330873d9cb8e
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 98%

---

# 自由格式表

在 Analysis Workspace 中，自由格式表是进行交互式数据分析的基础。可以将[组件](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=zh-Hans)组合拖放到行和列中，以创建自定义表格供您分析。在拖放每个组件后，表都将立即更新，以便您能够快速分析和深入探索。

![](assets/opening-section.png)

## 自动化表

构建表最快捷的方法便是将组件直接拖到空白项目、面板或自由格式表中。随后将自动以建议的格式为您构建自由格式表。[观看教程](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace.html?lang=zh-Hans)。

![](assets/automated-table.png)

## 自由格式表生成器

如果您希望先向表中添加多个组件，然后再渲染数据，则可以启用自由格式表生成器。启用该生成器后，您可以通过拖放多个维度、划分、量度和过滤器来构建可解答更复杂业务问题的表格。数据不会即时更新，单击&#x200B;**[!UICONTROL 构建]**&#x200B;后，数据将会更新。

![](assets/table-builder.png)

## 表交互

您可以通过各种方式与自由格式表进行交互并进行自定义设置：

* **行**
   * 您可以通过调整项目的[视图密度](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=zh-Hans)，将更多行放入单个屏幕中。
   * 在执行分页之前，每个维度行最多可显示 400 行。单击“行”旁边的数字可在单个页面上显示更多行。使用页眉中的页面箭头可导航到其他页面。
   * 可以按其他组件划分行。要同时划分多行，只需选择多行，然后将下一个组件拖动到选定行上即可。了解有关[划分](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html?lang=zh-Hans)的更多信息。
   * 可以[过滤](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html)行，以显示缩减的项目集。在[行设置](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.html?lang=zh-Hans)下，提供了其他设置。

* **列**
   * 可以将组件堆放在列中，以创建过滤量度、跨标签分析等。
   * 可以在[列设置](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html?lang=zh-Hans)下调整每列的视图。
   * 可通过[右键单击菜单](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html?lang=zh-Hans)执行多个操作。根据您单击表标题、行或列的情况，菜单可提供不同的操作。

## 导出自由格式表数据

了解有关用于 Analysis Workspace 的所有数据[导出选项](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=zh-Hans)的更多信息。

* 右键单击并选择&#x200B;**[!UICONTROL 将数据复制到剪贴板]**&#x200B;可导出显示的表数据。如果已选择表，则此选项将显示为&#x200B;**[!UICONTROL 将选定内容复制到剪贴板]**。也可以使用 **Ctrl+C** 热键复制所选数据。
* 右键单击并选择&#x200B;**[!UICONTROL 将数据下载为 CSV]** 可将显示的表数据下载为 CSV。如果已选择表，则此选项将显示为&#x200B;**[!UICONTROL 将选定内容下载为 CSV]**。
* 右键单击并依次选择&#x200B;**[!UICONTROL 项目 > 以 CSV 格式下载项目]**&#x200B;将最多导出选定维度的 50,000 个项目。

了解有关用于 Analysis Workspace 的所有数据[导出选项](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=zh-Hans)的更多信息。

![](assets/export-options.png)
