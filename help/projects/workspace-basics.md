---
title: 工作区基础知识
description: 介绍如何在Workspace中提取基本报表
translation-type: tm+mt
source-git-commit: eba2b60496976eb6027d58e0ce231ee046c8fc02

---


# 工作区基础知识

如果您还不熟悉工作区工具，下面是一些入门提示。

Workspace是Adobe的首要工具，可为您的组织制定基于数据的可操作决策。 通过自由格式表（最常见的可视化图表），您可以使用维度、量度、区段和日期范围轻松创建自定义报表。

## 在工作区中提取基本的排名报表

排名报表会显示每个维度值的聚合总视图，其中最先显示最大值。这些类型的报表有助于查看网站中的哪些组件最有效，例如，哪些页面的流量最大，或者哪些产品销量最高。

1. 确保您已登录 [analytics.adobe.com](https://analytics.adobe.com)。
1. In the top navigation bar, click **[!UICONTROL Workspace]**.
1. 单击 **[!UICONTROL Create New Project]**.
1. In the modal popup, make sure &#39;Blank Project&#39; is selected, then click **[!UICONTROL Create]**.
1. 在左侧，您应该会看到维度、量度、区段和日期范围的列表。找到“页面”维度（橙色），并将其拖动到画布上，其中显示“将维度放置在此处”。
1. 可查看显示本月最热门页面的报告。 Analysis Workspace 会自动使用[发生次数](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html)量度填充报表。
1. 找到“访问次数”量度（绿色），将其拖动到“发生次数”量度标头的&#x200B;**上面**&#x200B;或&#x200B;**旁边**（避免将“访问次数”量度置于“发生次数”的上方）。如果将“访问次数”量度拖动到“发生次数”的上方，则报表中的“发生次数”量度会被替换。如果将“访问次数”量度拖动到“发生次数”旁边，则这两个量度会并排显示。
1. If you&#39;d like to save your project, click **[!UICONTROL Project]>[!UICONTROL Save]**in the upper left menu.

## 在工作区中提取基本的趋势报表

趋势报表使用选定日期范围显示一段时间的量度视图。这些类型的报表有助于确定一段时间内的趋势，并且可用于衡量业务决策的成败。例如，您可以查看一段时间的页面查看次数趋势报表，以便了解网站重新设计是否有助于增加流量或减少流量。

1. 确保您已登录 [analytics.adobe.com](https://analytics.adobe.com)。
1. In the top navigation bar, click **[!UICONTROL Workspace]**.
1. 单击 **[!UICONTROL Create New Project]**.
1. In the modal popup, make sure &#39;Blank Project&#39; is selected, then click **[!UICONTROL Create]**.
1. 在左侧，您应该会看到维度、量度、区段和日期范围的列表。Locate the Page Views dimension, and drag it to the small space on the canvas labeled **[!UICONTROL Drop a Metric Here]**. 请勿将其放置在为维度保留的空间中（至少对于本次练习）。
1. 请注意，如果报表包包含数据，您应该会看到一个当月页面查看次数趋势报表。Analysis Workspace 会自动引入“日”日期范围，以便您可以查看当月页面查看次数趋势。
1. 在左侧的日期范围组件列表中找到“周”日期范围（紫色）。单击日期范围标题可展开并查看所有日期范围组件，或使用搜索栏。
1. 将“周”日期范围拖动到画布上的“日”日期范围标题上方可将其替换。
1. 请注意，现在按“周”而不是按“日”来汇总您的趋势报表。
1. If you&#39;d like to save your project, click **[!UICONTROL Project]>[!UICONTROL Save]**in the upper left menu.

## 试用该工具

由于 Workspace 是一款报表工具，因此不会对数据收集产生任何影响。您可以不加选择地将组件拖到项目中来查看具体效果，这不会产生任何影响。将不同的维度和量度组合拖动到工作区项目中，可查看相应的效果。

如果意外地将无效组件拖动到工作区项目，或者希望返回到上一个步骤，请按 Ctrl + Z (Windows) 或 cmd + Z (Mac) 以撤消上一个操作。You can also start with a clean slate by clicking **[!UICONTROL Project]>[!UICONTROL New]**in the upper left menu.

## 故障诊断

### 当我将量度拖动到上面时，显示“数据无效”。

无效数据意味着 Adobe 无法通过报表中使用的维度和量度组合返回数据。例如，两个彼此堆叠的量度不能作为数据返回，因为无法以这种堆叠方式显示这两个量度。相反，会并排显示这两个量度。

### 当我将量度拖动到上面时，看不到任何实际数据 - 只有零。

如果您成功创建了工作区报表，但报表中没有数据，则可以检查以下几项内容：

* 仔细检查报表包，并确保报表包中已填充数据。
* 如果在报表中使用了区段，区段标准可能与所有数据不匹配。请尝试移除区段或调整区段定义。
* 检查右上角的日期范围，并确保它已设置为预期的值。
* 导航到您的网站，然后使用调试器验证正在收集的数据。

## 其他资源

请注意，以下资源可能指在传统的Adobe Analytics产品中使用Workspace，而不是在客户旅程分析中。

* 博客文章：
   * [使组织拥有更智能的分析功能](https://theblog.adobe.com/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [Analysis Workspace:秘密酱越来越美味](https://theblog.adobe.com/analysis-workspace-secret-sauce-getting-tastier/)
   * [为何要使用 Analysis Workspace](https://theblog.adobe.com/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)
   * [使用 Analysis Workspace 最大程度提高工作效率的 5 个提示](https://theblog.adobe.com/5-tips-maximize-productivity-analysis-workspace/)

## 后续步骤

您可以从多个不同角度来加深对 Workspace 的了解。以下是 Adobe 推荐掌握的一些基本知识：

### 对于希望拓展有关如何使用 Workspace 相关知识的最终用户

* [关于工作区 UI 的详细信息](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/t-freeform-project.html)：既然您已创建了基础报表，那么应该更加熟悉用户界面的其余部分。
* [工作区中的可视化图表](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)：自由格式表只是 Analysis Workspace 中可视化图表的一种类型。了解如何使用其他可视化图标，例如折线图、条形图和地理地图。
* [工作区中的维度](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html)：了解有关什么是维度及如何在排名报表等表格中使用维度的更多信息。
* [工作区中的量度](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html)：了解有关什么是量度及如何在自由形式表的其他部分中使用量度的更多信息。
* [区段简介](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html)：了解什么是区段，并使用区段提取基本报告。
* [工作区中的日期范围](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html)：了解相对日期和滚动日期，并在工作区项目中加以运用。
* [在工作区中共享项目：向您的同事展示您创建的精彩工作区项目。](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)

### 对于希望提高组织中工作区质量的分析师和管理员

* [Analysis Workspace 权限](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)：通过 Adobe Admin Console 向用户分配工作区权限。
* [工作区中的模板](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html)：创建模板，让您的同事可以开始根据自己的需求定制项目空间。
* [工作区管理操作](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)：创建一个限制可用组件的项目，让不太熟悉这款工具的用户也能访问这些项目
