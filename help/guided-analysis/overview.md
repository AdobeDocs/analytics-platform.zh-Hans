---
title: 指导分析概述
description: 一种分析Customer Journey Analytics中的数据的方法，使产品团队能够快速获得高质量的见解。 也称为Product Analytics。
exl-id: 6a8a92db-f030-424e-af9b-f8f6502084f6
feature: Guided Analysis
source-git-commit: 4ed5acc2c9bb1a530d16d9c3ce8f5e9243bfa1f2
workflow-type: tm+mt
source-wordcount: '1054'
ht-degree: 8%

---

# 指导分析概述

引导式分析是一种报告格式，它允许产品团队快速满足其数据需求，以便他们能够快速获得高质量见解并做出更多由数据驱动的产品决策。 跨职能团队可以实时连接以使用和了解这些报告。

与Analysis Workspace和移动记分卡类似，引导式分析报表使用来自 [数据视图](../data-views/data-views.md)，通过Adobe Experience Platform中的引用数据 [连接](../connections/overview.md). 在引导式分析中创建的所有报告都可以无缝地传输到Analysis Workspace以供进一步研究。

引导式分析提供了多种分析和查看数据的方法。 视图类型可以以不同的方式显示相同的数据，从而导致使用相同的事件和区段获得不同的见解。 根据您选择的视图，您会获得不同的查询边栏和可视化图表设置。 您可以在视图之间自由切换，如果视图支持查询边栏组件，则任何适用的查询边栏组件都会延续。

引导式分析将视图类型分类为 **分析类型**. 可以使用以下分析和视图类型：

| 分析类型 | 视图类型 | 描述 |
| --- | --- | --- |
| [!UICONTROL 影响] | [版本](types/release.md) | 比较发布前和发布后相同时期的性能. |
| [!UICONTROL 影响] | [首次使用](types/first-use.md) | 衡量首次功能使用对关键指标的影响. |
| [!UICONTROL 漏斗] | [摩擦](types/friction.md) | 比较步骤之间的转化率. |
| [!UICONTROL 漏斗] | [转化趋势](types/conversion-trends.md) | 跟踪转化率随时间发生的变化. |
| [!UICONTROL 用户增长] | [活动](types/active.md) | 确定新的、保留的、返回的或休眠的用户. |
| [!UICONTROL 净增长] | [净增长](types/net-growth.md) | 您是在获得用户还是在失去用户？ |
| [!UICONTROL 趋势] | [使用情况](types/usage.md) | 随着时间的推移衡量用户参与度. |

{style="table-layout:auto"}

## 访问

如果您的组织已针对引导式分析进行了配置，则可以从Customer Journey Analytics主页访问该组织。

1. 单击 **[!UICONTROL 引导式分析]** 从主页直接跳转到 [使用情况趋势视图](types/usage.md).

   ![登陆页面拼贴](assets/landing-page-tile.png)

1. 单击 **[!UICONTROL 新建]** 查看不同的视图选项并选择不同的起点进行分析。

   ![创建新模式窗口](assets/create-new-modal.png)

## 界面

无论分析类型如何，引导式分析的界面都包含以下主要UI元素：

| 界面预览 | UI 元素 | 描述 |
| --- | --- | --- |
| ![查询边栏](assets/query-rail.png) | 查询边栏 | 配置构成分析的所需组件（事件、属性和区段）。 每种分析类型对可以配置的事件和区段数都实施了不同的限制。 如果切换到新的分析类型，则查询选择将保持在该分析类型的允许限制之内。 |
| ![图表](assets/chart.png) | 图表 | 根据从查询边栏和设置输入的内容，显示返回的数据。 您看到的可视化图表取决于图表上方的视图和设置。 可用视图取决于查询边栏上方的分析类型。 该图表还包括： <ul><li>**工具提示**：将鼠标悬停在任意图表数据点上以显示包含更多信息的工具提示。</li><li>**图例**：将鼠标悬停在图表图例上以显示系列定义（如果可用）。</li><li>**点击操作**：通过左键单击任意数据点显示可用的后续操作。 选项包括 **保存区段**.</li></ul> |
| ![表格](assets/table.png) | 表格 | 基于从查询边栏和设置输入的返回数据的表表示形式。 表中的列取决于图表上方的视图类型。 可用视图取决于查询边栏上方的分析类型。 该表还包括： <ul><li>**点击操作**：通过单击 **[!UICONTROL 更多]** 菜单。 选项包括 **保存区段**.</li></ul> |
| ![可视化设置](assets/visualization-settings.png) | 可视化设置 | 图表上方的多个选项允许您自定义图表和表返回数据的方式。<ul><li>**视图类型**：一个下拉选择器，允许您以不同的方式显示给定分析类型的数据。</li><li>**图表设置**：微调图表和表的显示内容。 可用选项取决于所选视图。</li><li>**日期范围**：日历选择器，用于确定分析的日期范围。 您还可以为趋势视图选择一个间隔，例如每日、每周或每月。</li><li>**分析**：根据您查看的分析得出上下文见解。 您可以使用箭头来导航到其他见解，或使用右上角的灯泡图标显示或隐藏这些见解。</li></ul> |
| ![菜单](assets/menu.png) | 菜单 | 引导式分析右上角的命令，这些命令可为您的分析提供总体操作。<ul><li>**数据视图选择器**：更改分析使用的数据视图。 当您更改数据视图时，查询边栏中的可用组件也会更改。</li><li>**保存**：保存分析。 如果要保存新分析，则会显示一个请求名称和说明的模式窗口。</li><li>**另存为**：将分析与当前分析分开保存，并创建一个副本。 此时将显示一个模式窗口，请求提供新的名称和说明。</li><li>**在工作区中打开**：在Analysis Workspace中重新创建当前的引导式分析。 Workspace项目是在新选项卡中创建的，可防止在引导式分析中工作时发生中断。 它是分析的副本，在打开后不会与原始引导分析保持同步。 当您想要移交给分析团队或深入了解数据（而不是引导式分析所允许的数据）时，请使用此命令。</li><li>**复制到剪贴板**：将图表图形复制到剪贴板，以粘贴到其他应用程序中。 查询边栏和表未包含在图形中。</li><li>**下载PNG**：将图表图形下载为 `.png`. 查询边栏和表未包含在图形中。</li><li>**下载CSV**：将表数据下载为 `.csv`. 查询边栏和图表未包含在文件中。</li></ul> |

{style="table-layout:auto"}

## 配置

引导式分析是Adobe Product Analytics的一部分，是Customer Journey Analytics的付费附加功能。 如果您的组织希望开始使用这一组功能，请联系您的Adobe客户团队。

将您的组织配置为使用引导式分析后，产品配置文件管理员可以在Adobe Admin Console中添加或删除对它的访问权限。

1. 登录到 [Adobe Admin Console](https://adminconsole.adobe.com).
1. 选择 **[!UICONTROL Customer Journey Analytics]** 在产品列表中。
1. 为要编辑的权限选择所需的产品配置文件。
1. 单击 **[!UICONTROL 权限]** 选项卡，然后单击 **[!UICONTROL 编辑]** 下 [!UICONTROL 报告工具].
1. 单击旁边的加号图标 **[!UICONTROL 引导式分析访问]** 在列表中 [!UICONTROL 可用权限项]，以将其添加到列表 [!UICONTROL 包含的权限项].
1. 单击&#x200B;**[!UICONTROL 保存]**。

>[!TIP]
>
>一些管理员更喜欢启用引导式分析，并禁用Analysis Workspace以供新用户Customer Journey Analytics。 在这些用户使用产品和您的组织数据成熟后，您可以启用对Analysis Workspace的访问权限。
