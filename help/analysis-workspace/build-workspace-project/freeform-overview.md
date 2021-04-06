---
description: 带菜单栏和设置的Workspace项目概述
keywords: Analysis Workspace
title: 项目概述
uuid: a68be05d-f31e-4e6d-ad04-c784ecb0eb00
exl-id: 2eeb615c-57a1-4469-8d4a-8a61956bd6e6
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '1165'
ht-degree: 90%

---

# 项目概述

通过 Workspace 项目，可结合数据组件、表格和可视化以得出您的分析结果，并与您组织中的任何人共享。在开始您的第一个项目之前，请了解如何访问、浏览和管理您的项目。

## 项目列表 {#project-list}

当您首次转到&#x200B;**[!UICONTROL “Analytics”]**>**[!UICONTROL “Workspace”]**&#x200B;时，该页面列出您拥有或与您共享的所有项目。这也是 Adobe Analytics 的登陆页面，除非您以前设置过自定义登陆页面。

![](assets/sample-project.png)

Workspace 项目列表页面包含了以下信息：

| 元素 | 描述 |
|---|---|
| [创建新项目](/help/analysis-workspace/home.md) | 单击此链接可重新启动一个新项目。 |
| 管理项目 | 单击此链接将会转到项目组件管理器（**[!UICONTROL Analytics]** > **[!UICONTROL 组件]** > **[!UICONTROL 项目]**），其中列出了您的所有项目，并允许您标记、共享、删除、重命名、批准、复制项目以及将项目导出到 CSV。 |
| 设置为登陆页面 | 将此页面变为您的 Workspace 登陆页面。 |
| [查看教程](/help/analysis-workspace/home.md) | 带您查看 Analysis Workspace 视频教程。 |
| 名称 | Workspace 项目名称。 |
| 所有者 | 创建此项目的人员（您或与您共享此项目的人员）。 |
| 类型 | 指示这是 Workspace 项目还是[移动记分卡](/help/mobile-app/home.md)。 |
| [项目角色](/help/analysis-workspace/curate-share/share-projects.md) | 指示您在项目中的角色 — 所有者、编辑、复制、查看。 |
| 标记 | 应用于项目的标记。 |
| 上次修改时间 | 项目上次修改的日期和时间。 |
| 我收藏的项目 | 要将项目标为收藏，请打开该项目，然后单击其名称旁的星标。下载打开 Workspace 时，它就会出现在此列表中。 |
| 经常查看的项目 | 列出您经常打开的所有项目以方便访问。 |

## 菜单栏 {#menu-bar}

在项目中，菜单提供管理项目、添加组件、查找帮助等选项。还可通过键盘[快捷方式](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)访问每个菜单选项。

![](assets/menu.png)

| 菜单项 | 描述 |
|---|---|
| 项目 | 包括常用于项目管理的操作，如新建、打开、保存、另存为和另存为模板。还可通过单击“刷新项目”而刷新整个项目以检索最新的数据和定义。通过[“下载 CSV 和 PDF”](/help/analysis-workspace/curate-share/download-send.md)选项，可从 Workspace 导出数据。**“项目信息和设置** ”（请参阅下文）优惠了许多用于管理项目的选项。 |
| 编辑 | 撤消或重做您的上一项操作。“全部清除”将您的项目重置为空起点。 |
| 插入 | 从此菜单插入新面板或可视化。还可从左侧边栏插入新面板和可视化。 |
| [组件](/help/components/overview.md) | 从您的项目创建新过滤器、计算量度、日期范围或警报组件。 还可从左侧边栏创建新组件。如果最近更改了组件定义，则“刷新组件”将检索最新定义。 |
| [共享](/help/analysis-workspace/curate-share/send-schedule-files.md) | 组织中的收件人可以管理、共享PDF/CSV项目并将其计划。 |
| 帮助 | 访问帮助文档、视频和 Analytics [Experience League 社区](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community)。管理 Workspace 提示和[调试器](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md)的可见性。查找关于 Workspace 及影响项目[性能](/help/analysis-workspace/workspace-faq/optimizing-performance.md)的各种因素的详细信息。 |
| “共享”按钮或“所有者” | 如果您处于项目的“拥有”或“编辑”角色，则通过右上方的“共享”按钮可一键管理项目接收方。如果您处于项目的“复制”或“查看”角色，则您将看到项目所有者的姓名。 |

### 项目信息和设置 {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL 项目]** > **[!UICONTROL 项目信息和设置]** 提供有关当前活动项目的项目级信息。

![](assets/projectinfo.png)

这些设置包括：

| 设置 | 描述 |
|---|---|
| 项目 名称 | 给项目起的名称。您可以双击该名称以编辑它。 |
| 创建者 | 项目所有者名称 |
| 上次修改时间 | 项目上次修改日期。 |
| 标记 | 列出应用于项目以方便分类的所有标记。 |
| 描述 | 描述有助于明确项目的目的。您可以双击描述以编辑它。 |
| 计算项目中的重复实例 | 指定是否将重复实例计入报表中。注意：此设置不适用于“流”或“流失”可视化。 |
| [项目调色板](/help/analysis-workspace/build-workspace-project/color-palettes.md) | 通过从已为色盲优化过的现成调色板中进行选择或通过指定您的自定义调色板，可更改在 Workspace 中使用的类别调色板。此功能影响 Workspace 中的许多内容，包括大多数可视化。 |
| [视图密度](/help/analysis-workspace/build-workspace-project/view-density.md) | 通过减小左侧边栏、自由格式表和同类群组表的垂直边距，让您可在屏幕上看到更多数据。 |

## 左侧边栏 {#left-rail}

在项目中，可从左侧边栏访问[面板](/help/analysis-workspace/c-panels/panels.md)、表格、[可视化](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)和[组件]。这些都是项目的构建基块。

还可从[空面板](/help/analysis-workspace/c-panels/blank-panel.md)访问可视化和面板。

左边栏中的组件(Dimension、量度、过滤器、日期范围)与活动面板数据视图相关。 活动面板周围将有一个蓝色边框，活动数据视图将列在组件边栏的顶部。

![](assets/left-rail.png)

## 项目画布 {#canvas}

项目画布是将面板、表格、可视化和组件集中在一起以构建您的分析的地方。一个项目可包含许多面板，而每个面板均可包含许多表格和可视化。

当您希望根据时段、视图或分析用例组织项目时，面板非常有用。 活动面板在自身四周将有蓝色边框，并决定在左侧边栏中有哪些组件可用。

根据您为项目选择的起点，您在画布中将首先使用[自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)或[空面板](/help/analysis-workspace/c-panels/blank-panel.md)。最快开始分析的方法是选择一个或多个组件，然后将其拖放到项目画布中。随后将自动为您呈现数据表。[详细了解](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)构建表的不同选项，或利用我们的[培训教程](/help/analysis-workspace/home.md)就构建您的第一个项目获得更多指导。

![](assets/canvas.png)

## 项目管理器 {#manager}

可在&#x200B;**“Analytics”>“组件”>“项目”**&#x200B;下管理 Analysis Workspace 项目。项目管理器显示特定用户已创建的项。可在“管理员”>“Analytics 用户和资源”>“转移资源”下将项目所有权移交给新用户。

在项目管理器中，可执行添加、标记、共享、复制等操作。可在搜索栏中或通过使用左侧边栏中的筛选器选项搜索项目。可按标记、所有者、项目类型等进行筛选。

![](assets/project-manager.png)

以下是项目管理器中的常用操作，可同时对一个或多个项目执行此类操作：

| 操作 | 描述 |
|---|---|
| 添加 | 从头开始创建新项目。 |
| 标记或批准 | 选择“标记”或“批准”以组织您的项目并使其更容易搜索。 |
| [共享](/help/analysis-workspace/curate-share/share-projects.md) | 使项目可供您所在组织中的其他 Analysis Workspace 用户使用。 |
| 删除 | 删除项目。 |
| 重命名 | 编辑项目的名称。 |
| 复制 | 创建项目的副本。此操作创建新项目和项目 ID。其中不复制与原始项目关联的任何共享或时间表。 |
| 导出到 CSV | 将项目下载为 CSV 文件，其中包括纯文本数据。 |
