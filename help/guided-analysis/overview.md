---
title: 引导式分析概述
description: 一种分析Customer Journey Analytics中的数据的方法，使产品团队能够快速获得高质量的见解。
keywords: 产品分析
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: a7545c5a197bd318212328ef6344245b2026d401
workflow-type: tm+mt
source-wordcount: '1393'
ht-degree: 79%

---

# 引导式分析概述

引导式分析使用户能够通过基于Customer Journey Analytics的跨渠道数据构建的引导式工作流，从营销到产品再到分析人员，自助提供高质量数据和关于客户历程的见解。 与 Analysis Workspace 和移动记分卡类似，引导式分析使用来自[数据视图](/help/data-views/data-views.md)中的数据，该视图通过[连接](../connections/overview.md)引用 Adobe Experience Platform 中的数据。在引导式分析中创建的许多报告均可以无缝传输到 Analysis Workspace 以进行其他研究。

可以使用以下引导式分析：

| 图标 | 分析 | 描述 |
| :----:|--- | --- |
| ![人员组](/help/assets/icons/PeopleGroup.svg) | [活动增长](types/active-growth.md) | 确定新的、保留的、返回的或非活跃的用户。 |
| ![转化趋势](/help/assets/icons/ConversionTrends.svg) | [转化趋势](types/conversion-trends.md) | 跟踪转化率随时间发生的变化。 |
| ![参与图形](/help/assets/icons/EngagementGraph.svg) | [参与度](types/engagement.md) | 了解功能参与的广度和深度。 |
| ![FirstUse](/help/assets/icons/FirstUse.svg) | [首次使用影响](types/first-use-impact.md) | 衡量功能首次使用对关键量度的影响。 |
| ![Histogram](/help/assets/icons/Histogram.svg) | [频率](types/frequency.md) | 按使用频率衡量参与度。 |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [漏斗](types/funnel.md) | 比较步骤之间的转化率。 |
| ![网络增长](/help/assets/icons/NetGrowth.svg) | [净增长](types/net-growth.md) | 您是在获得用户还是在失去用户？ |
| ![发布](/help/assets/icons/Release.svg) | [版本影响](types/release-impact.md) | 比较发布前和发布后相同时期的性能。 |
| ![保留](/help/assets/icons/Retention.svg) | [保留](types/retention.md) | 衡量用户持续的返回习惯。 |
| ![时间表](/help/assets/icons/Timeline.svg) | [时间表](types/timeline.md) | 探索会话活动中的模式。 |
| ![GraphTrend](/help/assets/icons/GraphTrend.svg) | [趋势](types/trends.md) | 随着时间的推移衡量用户参与度。 |



## 访问

您可以从 Customer Journey Analytics 主页访问引导式分析。

1. 通过选择主页上的&#x200B;**[!UICONTROL 引导式分析]**，您可以直接进入[使用趋势视图](types/trends.md)。

   ![Landing page tile](assets/landing-page-tile.png){style="border:1px solid gray"}

1. 选择&#x200B;**[!UICONTROL 新建]**，查看不同的视图选项，并选择不同的分析起点。

   ![Create a new modal](assets/create-new-modal.png){style="border:1px solid gray"}

您还可以从 Analysis Workspace 项目中访问引导式分析。

1. 从主页中选择&#x200B;**[!UICONTROL 空白项目]**&#x200B;来创建一个空的 Workspace 项目。

   ![Create blank project](assets/blank-project.png){style="border:1px solid gray"}

1. 选择左侧边栏中的![Guided analysis](/help/assets/icons/GuidedAnalysis.svg) **[!UICONTROL 引导式分析]**。

   ![Workspace left rail](assets/workspace-left-rail.png){style="border:1px solid gray"}

1. 将任何新分析拖到Workspace画布上，然后选择&#x200B;**[!UICONTROL 创建]**&#x200B;以生成所需的分析（例如： **[!UICONTROL 创建趋势]**）。 您还可以将现有分析从&#x200B;**[!UICONTROL 已保存]**&#x200B;部分拖动到 Workspace 画布上。

   ![Create panel](assets/create-guided-analysis-panel.gif)

## 界面

引导式分析的界面遵循问答格式。在查询边栏中生成您的问题，然后通过书面洞察、图表和表格获得答案。然后，在下一个问题中您可以提出有关视图类型和可视化设置的问题。

引导式分析使用以下 UI 元素：

| 界面预览 | UI 元素 | 描述 |
| --- | --- | --- |
| ![查询边栏](assets/query-rail.png){style="border:1px solid gray"} | 查询边栏 | 通过选择构成分析的所需组件（事件、属性和区段）来配置您的“问题”。以下选项适用于所有视图类型，并且每个视图都可以使用其他设置。 <ul><li>**分析选择器**：可以切换到新的分析类型的下拉菜单。您的查询选择将会保持在新分析类型允许的限制内。</li><li>**活动**：您要测量的事件。每种视图类型对您可以配置的事件数量实施不同的限制。</li><li>**筛选器**：使用“事件”或“区段”部分中的![筛选器](assets/filter.png)图标按特定维度缩小。 选择维度时，标准筛选条件（如[!UICONTROL Equals]、[!UICONTROL Contains]或[!UICONTROL Ends with]）和前1000个维度值均可用。</li><li>**计为**：要应用于所选事件的计数方法。</li><li>**区段**：您要测量的区段。每种视图类型对您可以配置的区段数量实施不同的限制。</li></ul> |
| ![图表](assets/chart.png){style="border:1px solid gray"} | 图表 | 根据查询边栏和设置的输入返回的数据生成的可视化内容。您看到的可视化效果取决于图表上方的视图和设置。该图表还包括： <ul><li>**工具提示**：将鼠标悬停在任何图表数据点上可显示包含更多信息的工具提示。</li><li>**图例**：将鼠标悬停在图表图例系列上可查看可用的定义、关注该系列并暂时隐藏其他系列。单击图例中的系列可隐藏它。</li><li>**注释**：适用的[注释](../components/annotations/overview.md)在可视化和图例之间可见。它以注释的配置颜色显示为![注释图标](assets/annotation.png)图标。随时间显示数据的视图类型将![注释图标](assets/annotation.png)图标置于配置的日期或日期范围下。不随时间显示数据的视图类型在图表的右下角显示![注释图标](assets/annotation.png)图标。</li><li>**选择操作**：通过选择任何数据点来公开可用的后续操作。 选项包括&#x200B;**保存区段**。</li></ul> |
| ![表格](assets/table.png){style="border:1px solid gray"} | 表格 | 根据查询边栏和设置的输入内容返回的数据的表格表示形式。表中的列取决于图表上方的视图类型。该表还包括： <ul><li>**选择操作**：通过切换每行中的![显示隐藏图标](assets/hide-in-chart.png)图标来隐藏或公开图表系列。 通过选择&#x200B;**[!UICONTROL 更多]**&#x200B;菜单，可以使用其他操作。 选项包括&#x200B;**保存区段**。</li></ul> |
| ![可视化设置](assets/visualization-settings.png){style="border:1px solid gray"} | 可视化设置 | 图表上方的选项允许您提出下一个问题，并自定义图表和表格返回数据的方式。以下选项适用于所有视图类型，并且每个视图都可以使用其他设置。 <ul><li>**图表设置**：微调图表和表格的显示内容。可用选项取决于所选视图。</li><li>**日期范围**：用于确定分析的日期范围的日程表选择器。您还可以选择趋势视图的时间间隔，例如每日、每周或每月。</li><li>**洞察**：上下文的洞察取决于您查看的分析。这些洞察为当前的分析提供了洞察结果。如果有多个洞察，您可以使用右侧的箭头查看它们。您可以使用右上角的灯泡图标切换此框的可见性。</li></ul> |
| ![菜单](assets/menu.png){style="border:1px solid gray"} |  菜单 | 引导式分析右上角的命令为您的分析提供总体操作。<ul><li>**数据视图选择器**：更改分析使用的数据视图。当您更改数据视图时，查询边栏中的可用组件也会更改。</li><li>**复制链接**：将分析链接复制到剪贴板。系统会提示您在共享之前进行保存。</li><li>**共享**：打开共享模式，其中包含用于共享给个人用户或群组的更多选项。您可以与其他用户分享分析，或生成链接与任何人分享。</li><li>**保存**：保存分析。如果您要保存新的分析，则会出现一个模式窗口，要求输入名称和描述。</li><li>**另存为**：将分析与当前分析分开保存，创建副本。将会出现一个模式窗口，要求输入新名称和描述。</li><li>**导出到Workspace**：在Analysis Workspace中重新创建当前的引导式分析查询。 Workspace 项目会在新选项卡中创建，以防止在引导式分析中出现中断。它是分析的副本，打开后不会与原始引导式分析保持同步。当您想要将任务移交给分析师团队，或者想要比引导式分析更近一步分析数据时，请使用此命令。</li><li>**复制到剪贴板**：将图表图形复制到剪贴板，以便粘贴到其他应用程序中。图形中不包含查询边栏和表格。</li><li>**下载 PNG**：将图表图形下载为  `.png`。图形中不包含查询边栏和表格。</li><li>**下载 CSV**：将表数据下载为  `.csv`。查询边栏和图表不包含在文件中。</li></ul> |

{style="table-layout:auto"}

## 设置

引导式分析通过以下方式包含在Customer Journey Analytics包中：

| 包 | 可用分析 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics加载项] | 主动增长，转化趋势，频率，漏斗，净增长，保留，趋势 |
| [!UICONTROL Customer Journey Analytics基础] | 趋势 |
| [!UICONTROL Customer Journey Analytics选择] | Foundation视图+主动增长，转化趋势，频率，漏斗，净增长，保留 |
| [!UICONTROL Customer Journey AnalyticsPrime] | 选择视图+参与、首次使用影响、发布影响、时间线 |
| [!UICONTROL Customer Journey AnalyticsUltimate] | 最佳视图 |

{style="table-layout:auto"}

产品配置文件管理员可以在 Adobe Admin Console 中添加或删除对引导式分析的访问权限。

1. 登录到 [Adobe Admin Console](https://adminconsole.adobe.com)。
1. 在产品列表中选择 **[!UICONTROL Customer Journey Analytics]**。
1. 为您要编辑的权限选择所需的产品配置文件。
1. 选择&#x200B;**[!UICONTROL 权限]**&#x200B;选项卡，然后单击[!UICONTROL 报告工具]下的&#x200B;**[!UICONTROL 编辑]**。
1. 在[!UICONTROL 可用权限项]的列表中选择&#x200B;**[!UICONTROL 引导式分析访问]**&#x200B;旁边的![AddCircle](/help/assets/icons/AddCircle.svg)，以将其添加到[!UICONTROL 包含的权限项]的列表。
1. 选择&#x200B;**[!UICONTROL 保存]**。

有关详细信息，请参阅[用户级访问权限](/help/technotes/access-control.md#user-level-access)。

>[!TIP]
>
>一些管理员更喜欢为 Customer Journey Analytics 的新用户启用引导式分析并禁用 Analysis Workspace。当这些用户熟悉了产品和您的组织数据后，您就可以启用对 Analysis Workspace 的访问权限。
