---
title: 指导分析概述
description: 一种分析Customer Journey Analytics中的数据的方法，使产品团队能够轻松生成报告和见解。
source-git-commit: 03f6b0cef6fa4259041a82173acda852d91e06b5
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 1%

---

# 指导分析概述

{{release-limited-testing}}

引导式分析是一种报告格式，它允许产品团队快速自助满足其数据需求，以便他们可以做出更多由数据驱动的产品决策。 跨职能团队可以实时连接以使用和了解这些报告。

与Analysis Workspace和移动记分卡类似，引导式分析报表使用来自 [数据视图](../data-views/data-views.md)，通过Adobe Experience Platform中的引用数据 [连接](../connections/overview.md). 在引导式分析中创建的所有报告都可以无缝地传输到Analysis Workspace以供进一步研究。

引导式分析报告目前具有三种分析类型： [漏斗](analysis-types/funnel.md)， [趋势](analysis-types/trends.md)、和 [用户增长](analysis-types/user-growth.md). 其中每种分析类型都有多种视图类型，可为每个报表提供附加见解。

## 配置

引导式分析是Customer Journey Analytics的付费附加功能。 如果您的组织希望开始使用此功能，请联系您的Adobe客户团队。

## 界面

无论分析类型如何，引导式分析的界面都包含以下主要UI元素：

1. **查询边栏**：使用左侧的此边栏构建分析。
1. **图表**：选择所需的事件、人员或步骤后，右侧会显示一个图表，用于可视化数据。
1. **表**：图表下方的表格，其中显示可视化图表中使用的数字。
1. **设置和分析**：图表上方的几个UI元素，它们允许您自定义返回的数据。

[UI屏幕快照]

引导式分析包含以下界面部分：

| 界面预览 | UI 元素 | 描述 |
| --- | --- | --- |
| [查询边栏屏幕截图] | 查询边栏 | 配置构成报表的所需组件。 不同的分析类型共享多个查询选项；如果两个分析类型共享查询选项，则它们在切换分析类型时延续。 参见 [分析类型](analysis-types/overview.md) 有关每种分析类型的查询选项的更多信息。 |
| [图表屏幕快照] | 图表 | 根据从查询边栏和设置输入的内容，显示返回的数据。 您看到的可视化图表取决于图表上方的视图类型。 可用的视图类型取决于 [分析类型](analysis-types/overview.md) 查询边栏的上方。 |
| [表格的屏幕快照] | 表格 | 基于从查询边栏和设置输入的返回数据的表表示形式。 表中的列取决于图表上方的视图类型。 可用的视图类型取决于 [分析类型](analysis-types/overview.md) 查询边栏的上方。 |
| [设置的屏幕快照] | 设置 | 图表上方的多个选项允许您自定义图表和表返回数据的方式。<ul><li>**视图类型**：一个下拉选择器，允许您显示给定数据 [分析类型](analysis-types/overview.md) 换种方式。 每个分析类型至少具有两种视图类型。</li><li>**图表设置**：微调图表的外观以及您希望图表使用的事件。 可用选项取决于所选的视图类型。</li><li>**日期范围**：日历选择器，用于确定报表的日期范围。 某些分析类型还允许设置间隔，例如每日、每周或每月。</li><li>**分析**：根据您查看的报表提供上下文分析。 您可以使用右上角的灯泡图标来显示或隐藏这些见解。</li></ul> |
| [分析菜单屏幕快照] | “分析”菜单 | 引导式分析右上角的命令提供了总体操作。<ul><li>**数据视图选择器**：更改此分析使用的数据视图。 当您更改数据视图时，查询边栏中的可用组件也会更改。</li><li>**保存**：保存分析。 如果要保存新分析，则会显示一个请求名称和说明的模式窗口。</li><li>**另存为**：将分析与当前分析分开保存，并创建一个副本。 此时将显示一个模式窗口，请求提供新的名称和说明。</li><li>**在工作区中打开**：在Analysis Workspace中重新创建当前的引导式分析。 Workspace项目是在新选项卡中创建的，可防止在引导式分析中工作时发生中断。 当引导式分析不能为您提供所需的灵活性或特定洞察时，请使用此命令。 例如，您希望 [趋势](analysis-types/trends.md) 一个区段使用会话，另一个区段使用人员的报表。</li><li>**下载PNG**：将图表图形下载为 `.png`. 查询边栏和表未包含在图形中。</li><li>**下载SVG**：将图表图形下载为 `.svg`. 查询边栏和表未包含在图形中。</li></ul> |

{style="table-layout:auto"}

## 权限

Adobe计划在未来提供特定于引导式分析的权限。

<!-- Once your organization is provisioned to use Guided analysis, product profile administrators can grant access to it in the Adobe Admin Console.

1. Log in to the [Adobe admin console](https://adminconsole.adobe.com).
1. Select **[!UICONTROL Customer Journey Analytics]** in the list of products.
1. Select the desired product profile to edit permissions.
1. Click the **[!UICONTROL Permissions]** tab, then click **[!UICONTROL Edit]** under [!UICONTROL Reporting Tools].
1. Drag **[!UICONTROL Guided analysis]** from the list of [!UICONTROL Available Permission Items] to the list of [!UICONTROL Included Permission Items].
1. Click **[!UICONTROL Save]**. -->
