---
title: 指导分析概述
description: 一种分析Customer Journey Analytics中的数据的方法，使产品团队能够快速获得高质量的见解。 也称为Product Analytics。
keywords: 产品分析
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: a8ead81a8de8dcab4c12cbbe9cba56c4ce8417a3
workflow-type: tm+mt
source-wordcount: '1360'
ht-degree: 2%

---

# 指导分析概述

引导式分析使用户能够通过基于Customer Journey Analytics的跨渠道数据构建的引导式工作流为客户历程提供高质量数据和见解。 从营销到产品，跨职能团队可以实时建立联系，以使用和了解这些报表。

>[!NOTE]
>
> 目前，引导式分析仅作为Customer Journey Analytics的付费附加功能Adobe Product Analytics的一部分提供。 如果贵组织希望开始使用这一组功能，请与您的Adobe客户团队联系。

与Analysis Workspace和移动记分卡类似，引导式分析使用来自 [数据视图](../data-views/data-views.md)，用于通过Adobe Experience Platform中的引用 [连接](../connections/overview.md). 在引导式分析中创建的许多报告都可以无缝地传输到Analysis Workspace以供进一步研究。

可以使用以下引导式分析视图：

| 分析类型 | 视图类型 | 描述 |
| --- | --- | --- |
| [!UICONTROL 漏斗] | [摩擦](types/friction.md) | 比较步骤之间的转化率。 |
| [!UICONTROL 漏斗] | [转化趋势](types/conversion-trends.md) | 跟踪转化率随时间发生的变化。 |
| [!UICONTROL 影响] | [版本](types/release.md) | 比较发布前和发布后各个相等时间段的性能。 |
| [!UICONTROL 影响] | [首次使用](types/first-use.md) | 衡量首次使用功能对关键指标的影响。 |
| [!UICONTROL 维系] | [留存率](types/retention-rates.md) | 衡量用户的持续回访习惯。 |
| [!UICONTROL 趋势] | [用法](types/usage.md) | 测量一段时间内用户参与的情况。 |
| [!UICONTROL 趋势] | [频率](types/frequency.md) | 按使用频率测量参与度。 |
| [!UICONTROL 用户增长] | [活动](types/active.md) | 确定新人、留住人员、回访人员或休眠人员。 |
| [!UICONTROL 用户增长] | [净增长](types/net-growth.md) | 您是在获得用户还是在失去用户？ |
| [!UICONTROL 用户流] | [时间表](types/timeline.md) | 浏览会话活动中的模式。 |

{style="table-layout:auto"}

## 访问

如果您的组织已针对引导式分析进行了配置，则可以从Customer Journey Analytics主页访问该分析。

1. 单击 **[!UICONTROL 引导式分析]** ，这会将您直接转到 [使用趋势视图](types/usage.md).

   ![登陆页面拼贴](assets/landing-page-tile.png){style="border:1px solid gray"}

1. 单击 **[!UICONTROL 新建]** 查看不同的视图选项，并为您的分析选择不同的起点。

   ![创建新模式窗口](assets/create-new-modal.png){style="border:1px solid gray"}

如果贵组织尚未进行引导式分析配置，请联系您的Adobe客户团队。

## 界面

引导式分析的界面遵循问答格式。 在查询边栏中形成您的问题，然后通过书面分析、图表和表格获得答案。 然后，您可以询问有关视图类型和可视化图表设置的下一个问题。

引导式分析使用以下UI元素：

| 界面预览 | UI 元素 | 描述 |
| --- | --- | --- |
| ![查询边栏](assets/query-rail.png){style="border:1px solid gray"} | 查询边栏 | 选择构成分析的所需组件（事件、属性和区段）来配置您的“问题”。 以下选项适用于所有视图类型，额外设置适用于每个视图。 <ul><li>**分析选择器**：一个下拉列表，可让您切换到新的分析类型。 查询选择将维持在新分析类型的允许限制之内。</li><li>**视图选择器**：一个下拉列表，可让您为所构成的查询切换到新视图（“答案”）。 查询选择将维持在新视图类型的允许限制之内。</li><li>**活动**：要测量的事件。 每种视图类型对可配置的事件数都强制实施不同的限制。</li><li>**过滤器**：使用 ![筛选](assets/filter.png) 图标，按特定属性进行缩小。 选择某个属性时，两个标准筛选条件(例如 [!UICONTROL 等于]， [!UICONTROL 包含]，或 [!UICONTROL 结束于])和前1000个属性值均可用。</li><li>**计为**：要应用于选定事件的计数方法。</li><li>**区段**：要测量的区段。 每种视图类型对可配置的区段数强制实施不同的限制。</li></ul> |
| ![图表](assets/chart.png){style="border:1px solid gray"} | 图表 | 基于从查询边栏和设置输入的返回数据的可视化图表。 您看到的可视化图表取决于图表上方的视图和设置。 该图表还包括： <ul><li>**工具提示**：将鼠标悬停在任意图表数据点上以显示包含更多信息的工具提示。</li><li>**图例**：将鼠标悬停在图表图例系列上可查看可用定义，关注该系列，并暂时隐藏其他系列。 通过单击图例隐藏系列。</li><li>**注释**：适用 [注释](../components/annotations/overview.md) 在可视化和图例之间可见。 它显示为 ![“注释”图标](assets/annotation.png) 图标的配置颜色。 显示一段时间内数据的视图类型位置 ![“注释”图标](assets/annotation.png) 图标来显示配置日期或日期范围。 视图类型不会显示一段时间内的数据，但会显示 ![“注释”图标](assets/annotation.png) 图标图标。</li><li>**点击操作**：通过左键单击任意数据点显示可用的后续操作。 选项包括 **保存区段**.</li></ul> |
| ![表格](assets/table.png){style="border:1px solid gray"} | 表格 | 基于从查询边栏和设置输入的返回数据的表表示形式。 表中的列取决于图表上方的视图类型。 该表还包括： <ul><li>**点击操作**：通过切换 ![显示隐藏图标](assets/hide-in-chart.png) 图标。 单击 **[!UICONTROL 更多]** 菜单。 选项包括 **保存区段**.</li></ul> |
| ![可视化设置](assets/visualization-settings.png){style="border:1px solid gray"} | 可视化设置 | 图表上方的选项，允许您询问下一个问题并自定义图表和表返回数据的方式。 以下选项适用于所有视图类型，额外设置适用于每个视图。 <ul><li>**图表设置**：微调图表和表的显示内容。 可用选项取决于所选视图。</li><li>**日期范围**：日历选取器，用于确定分析的日期范围。 您还可以为趋势视图选择一个间隔，如每日、每周或每月。</li><li>**Insights**：上下文见解取决于您查看的分析。 您可以使用箭头标记其他见解，或使用右上角的灯泡图标显示或隐藏这些见解。</li></ul> |
| ![菜单](assets/menu.png){style="border:1px solid gray"} | 菜单 | 引导式分析右上角的命令，这些命令可为您的分析提供总体操作。<ul><li>**数据视图选择器**：更改分析使用的数据视图。 当您更改数据视图时，查询边栏中的可用组件也会更改。</li><li>**复制链接**：将指向分析的链接复制到剪贴板。 系统将提示您先保存，然后再共享。</li><li>**共享**：打开共享模式窗口，其中包含用于共享到单个用户或组的更多选项。 系统将提示您先保存，然后再共享。</li><li>**保存**：保存分析。 如果要保存新的分析，则会出现一个模式窗口，要求输入名称和说明。</li><li>**另存为**：将分析与当前分析分开保存，并创建一个副本。 此时将显示一个模式窗口，请求提供新的名称和说明。</li><li>**在工作区中打开**：在Analysis Workspace中重新创建当前引导式分析。 Workspace项目是在新选项卡中创建的，可防止在引导式分析中工作时发生中断。 它是分析的副本，在打开后不会与原始引导分析保持同步。 当您想要移交给分析团队或深入了解引导式分析所允许的数据时，请使用此命令。</li><li>**复制到剪贴板**：将图表图形复制到剪贴板，以粘贴到其他应用程序中。 查询边栏和表未包含在图形中。</li><li>**下载PNG**：将图表图形下载为 `.png`. 查询边栏和表未包含在图形中。</li><li>**下载CSV**：将表数据下载为 `.csv`. 查询边栏和图表未包含在文件中。</li></ul> |

{style="table-layout:auto"}

## 设置

引导式分析是Adobe Product Analytics的一部分，是Customer Journey Analytics的付费附加功能。 如果贵组织希望开始使用这一组功能，请与您的Adobe客户团队联系。

您的组织准备好使用引导式分析后，产品配置文件管理员可以在Adobe Admin Console中添加或删除对它的访问权限。

1. 登录到 [Adobe Admin Console](https://adminconsole.adobe.com).
1. 选择 **[!UICONTROL Customer Journey Analytics]** 在产品列表中。
1. 为要编辑的权限选择所需的产品配置文件。
1. 单击 **[!UICONTROL 权限]** 选项卡，然后单击 **[!UICONTROL 编辑]** 下 [!UICONTROL 报告工具].
1. 单击旁边的加号图标 **[!UICONTROL 引导式分析访问]** 在列表中 [!UICONTROL 可用的权限项]，以将其添加到列表 [!UICONTROL 包含的权限项].
1. 单击&#x200B;**[!UICONTROL 保存]**。

>[!TIP]
>
>一些管理员更喜欢启用引导式分析，并禁用Analysis Workspace以供新用户Customer Journey Analytics。 在这些用户使用产品和您的组织数据成熟后，您可以启用对Analysis Workspace的访问权限。
