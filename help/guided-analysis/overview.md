---
title: 引导式分析概述
description: 一种在 Customer Journey Analytics 中分析数据的方法，可让产品团队快速获得高质量的见解。也称为产品分析。
keywords: 产品分析
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: 2b8afe1dbac5057f867437e2bfce27f3bd752d57
workflow-type: ht
source-wordcount: '1397'
ht-degree: 100%

---

# 引导式分析概述

引导式分析使用户能够通过基于 Customer Journey Analytics 的跨渠道数据的引导式工作流程，自助提供有关客户历程的高质量数据和见解。从营销到产品的跨职能团队可以实时连接，以使用和理解这些报告。

>[!NOTE]
>
> 引导式分析目前仅作为 Adobe Product Analytics 的一部分提供，Adobe Product Analytics 是 Customer Journey Analytics 的付费附加组件。如果您的组织想要开始使用这组功能，请联系您的 Adobe 客户团队。

与 Analysis Workspace 和移动记分卡类似，引导式分析使用来自[数据视图](../data-views/data-views.md)中的数据，该视图通过[连接](../connections/overview.md)引用 Adobe Experience Platform 中的数据。在引导式分析中创建的许多报告均可以无缝传输到 Analysis Workspace 以进行其他研究。

以下引导式分析视图可供使用：

| 分析类型 | 视图类型 | 描述 |
| --- | --- | --- |
| [!UICONTROL 功能矩阵] | [参与度](types/engagement.md) | 了解功能参与的广度和宽度 |
| [!UICONTROL 漏斗] | [摩擦](types/friction.md) | 比较步骤之间的转化率。 |
| [!UICONTROL 漏斗] | [转化趋势](types/conversion-trends.md) | 跟踪转化率随时间发生的变化。 |
| [!UICONTROL 影响] | [发布](types/release.md) | 比较发布前和发布后相同时期的性能。 |
| [!UICONTROL 影响] | [首次使用](types/first-use.md) | 衡量功能首次使用对关键指标的影响。 |
| [!UICONTROL 保留] | [保留率](types/retention-rates.md) | 衡量用户持续的返回习惯。 |
| [!UICONTROL 趋势] | [用法](types/usage.md) | 随着时间的推移衡量用户参与度。 |
| [!UICONTROL 趋势] | [频率](types/frequency.md) | 按使用频率衡量参与度。 |
| [!UICONTROL 用户增长] | [活动](types/active.md) | 确定新的、保留的、返回的或非活跃的用户。 |
| [!UICONTROL 用户增长] | [净增长](types/net-growth.md) | 您是在获得用户还是在失去用户？ |
| [!UICONTROL 用户流] | [时间表](types/timeline.md) | 探索会话活动中的模式。 |

{style="table-layout:auto"}

## 访问

如果您的组织配置了引导式分析，您可以从 Customer Journey Analytics 主页访问它。

1. 点击主页上的&#x200B;**[!UICONTROL 引导式分析]**，您可以直接进入[使用趋势视图](types/usage.md)。

   ![登陆页面图块](assets/landing-page-tile.png){style="border:1px solid gray"}

1. 点击&#x200B;**[!UICONTROL 新建]**，查看不同的视图选项，并选择不同的分析起点。

   ![新建模式](assets/create-new-modal.png){style="border:1px solid gray"}

如果您的组织尚未配置引导式分析，请联系您的 Adobe 客户团队。

## 界面

引导式分析的界面遵循问答格式。在查询边栏中生成您的问题，然后通过书面见解、图表和表格获得答案。然后，在下一个问题中您可以提出有关视图类型和可视化设置的问题。

引导式分析使用以下 UI 元素：

| 界面预览 | UI 元素 | 描述 |
| --- | --- | --- |
| ![查询边栏](assets/query-rail.png){style="border:1px solid gray"} | 查询边栏 | 通过选择构成分析的所需组件（事件、属性和区段）来配置您的“问题”。以下选项适用于所有视图类型，并且每个视图都可以使用其他设置。 <ul><li>**分析选择器**：可以切换到新的分析类型的下拉菜单。您的查询选择将会保持在新分析类型允许的限制内。</li><li>**视图选择器**：可根据所生成的查询切换到新视图（“答案”）的下拉菜单。您的查询选择将会保持在新视图类型允许的限制内。</li><li>**活动**：您要测量的事件。每种视图类型对您可以配置的事件数量实施不同的限制。</li><li>**过滤器**：使用“事件”或“区段”部分中的![过滤器](assets/filter.png)图标按特定属性缩小范围。选择属性后，标准过滤条件（例如[!UICONTROL 等于]、[!UICONTROL 包含]或[!UICONTROL 结束于]）和前 1000 个属性值都可用。</li><li>**计为**：要应用于所选事件的计数方法。</li><li>**区段**：您要测量的区段。每种视图类型对您可以配置的区段数量实施不同的限制。</li></ul> |
| ![图表](assets/chart.png){style="border:1px solid gray"} | 图表 | 根据查询边栏和设置的输入返回的数据生成的可视化内容。您看到的可视化效果取决于图表上方的视图和设置。该图表还包括： <ul><li>**工具提示**：将鼠标悬停在任何图表数据点上可显示包含更多信息的工具提示。</li><li>**图例**：将鼠标悬停在图表图例系列上可查看可用的定义、关注该系列并暂时隐藏其他系列。单击图例中的系列可隐藏它。</li><li>**注释**：适用的[注释](../components/annotations/overview.md)在可视化和图例之间可见。它以注释的配置颜色显示为![注释图标](assets/annotation.png)图标。随时间显示数据的视图类型将![注释图标](assets/annotation.png)图标置于配置的日期或日期范围下。不随时间显示数据的视图类型在图表的右下角显示![注释图标](assets/annotation.png)图标。</li><li>**单击操作**：通过左键单击任何数据点来显示可用的下一步操作。选项包括&#x200B;**保存区段**。</li></ul> |
| ![表格](assets/table.png){style="border:1px solid gray"} | 表格 | 根据查询边栏和设置的输入内容返回的数据的表格表示形式。表中的列取决于图表上方的视图类型。该表还包括： <ul><li>**点击操作**：通过切换每行中的![显示隐藏图标](assets/hide-in-chart.png)图标来隐藏或显示图表系列。单击&#x200B;**[!UICONTROL 更多]**&#x200B;菜单可以执行其他操作。选项包括&#x200B;**保存区段**。</li></ul> |
| ![可视化设置](assets/visualization-settings.png){style="border:1px solid gray"} | 可视化设置 | 图表上方的选项允许您提出下一个问题，并自定义图表和表格返回数据的方式。以下选项适用于所有视图类型，并且每个视图都可以使用其他设置。 <ul><li>**图表设置**：微调图表和表格的显示内容。可用选项取决于所选视图。</li><li>**日期范围**：用于确定分析的日期范围的日程表选择器。您还可以选择趋势视图的时间间隔，例如每日、每周或每月。</li><li>**洞察**：上下文的洞察取决于您查看的分析。这些见解为当前的分析提供了洞察结果。如果有多个洞察，您可以使用右侧的箭头查看它们。您可以使用右上角的灯泡图标切换此框的可见性。</li></ul> |
| ![菜单](assets/menu.png){style="border:1px solid gray"} |  菜单 | 引导式分析右上角的命令为您的分析提供总体操作。<ul><li>**数据视图选择器**：更改分析使用的数据视图。当您更改数据视图时，查询边栏中的可用组件也会更改。</li><li>**复制链接**：将分析链接复制到剪贴板。系统会提示您在共享之前进行保存。</li><li>**共享**：打开共享模式，其中包含用于共享给个人用户或群组的更多选项。您可以与其他用户分享分析，或生成链接与任何人分享。</li><li>**保存**：保存分析。如果您要保存新的分析，则会出现一个模式窗口，要求输入名称和描述。</li><li>**另存为**：将分析与当前分析分开保存，创建副本。将会出现一个模式窗口，要求输入新名称和描述。</li><li>**在 Workspace 中打开**：在 Analysis Workspace 中重新创建当前的引导式分析。Workspace 项目会在新选项卡中创建，以防止在引导式分析中出现中断。它是分析的副本，打开后不会与原始引导式分析保持同步。当您想要将任务移交给分析师团队，或者想要比引导式分析更近一步分析数据时，请使用此命令。</li><li>**复制到剪贴板**：将图表图形复制到剪贴板，以便粘贴到其他应用程序中。图形中不包含查询边栏和表格。</li><li>**下载 PNG**：将图表图形下载为  `.png`。图形中不包含查询边栏和表格。</li><li>**下载 CSV**：将表数据下载为  `.csv`。查询边栏和图表不包含在文件中。</li></ul> |

{style="table-layout:auto"}

## 设置

引导式分析是 Customer Journey Analytics 的付费附加组件 Adobe Product Analytics 的一部分。如果您的组织想要开始使用这组功能，请联系您的 Adobe 客户团队。

当您的组织配置为可使用引导式分析时，产品配置文件管理员就可以在 Adobe Admin Console 中添加或删除对其的访问权限。

1. 登录到 [Adobe Admin Console](https://adminconsole.adobe.com)。
1. 在产品列表中选择 **[!UICONTROL Customer Journey Analytics]**。
1. 为您要编辑的权限选择所需的产品配置文件。
1. 单击&#x200B;**[!UICONTROL 权限]**&#x200B;选项卡，然后单击[!UICONTROL 报告工具]下的&#x200B;**[!UICONTROL 编辑]**。
1. 单击 [!UICONTROL 可用权限项目]列表中&#x200B;**[!UICONTROL Guided Analysis Access]**&#x200B;旁边的加号图标，这会将其添加到[!UICONTROL 包含的权限项目]列表中。
1. 单击&#x200B;**[!UICONTROL 保存]**。

>[!TIP]
>
>一些管理员更喜欢为 Customer Journey Analytics 的新用户启用引导式分析并禁用 Analysis Workspace。当这些用户熟悉了产品和您的组织数据后，您就可以启用对 Analysis Workspace 的访问权限。
