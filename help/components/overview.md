---
title: 组件概述
description: 了解 CJA 提供了哪些组件，以及如何在报表中使用它们。
translation-type: tm+mt
source-git-commit: c1699c4319b3b840d8420f3ffa1a4bd1c1d9a4d4
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 57%

---


# 组件概述

组件是 Customer Journey Analytics 中的功能，这些功能可在报表中使用，或补充报表功能。您可以通过以下步骤管理这些组件：

1. 使用您的 Adobe ID 凭据登录 [analytics.adobe.com](https://analytics.adobe.com)。
2. 在标题菜单中，导航到[!UICONTROL 组件] > [!UICONTROL 组件]。

您可以管理以下组件：

* [**过滤器**](filters/filters-overview.md)：排除部分数据，以重点关注常见的维度项目
* [**计算量度**](calc-metrics/calc-metr-overview.md)：使用量度和公式作为新组件以便在报表中使用
* [**日期范围**](date-ranges/overview.md)：自定义和优化 Analysis Workspace 中提供的日期范围
* [**项目**](/help/analysis-workspace/home.md)：组织和维护 Analysis Workspace 中的项目

## Analysis Workspace 组件

Analysis Workspace 中的组件包括量度、维度、区段和时间粒度，您可以将这些组件拖放到项目中。您创建的自定义组件会被添加到这些面板中，例如自定义日期范围。

要访问“组件”面板，请单击左边栏中的&#x200B;**[!UICONTROL 组件]**&#x200B;图标。您可以使用左边栏图标或[热键](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)在面板（空白面板、[自由格式面板](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)、[快速分析面板](/help/analysis-workspace/c-panels/quickinsight.md)或[归因 IQ](/help/analysis-workspace/c-panels/attribution.md) 面板）、[可视化图表](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)和“组件”之间切换。

![](assets/components.png)

请参阅[创建项目](/help/analysis-workspace/home.md)，以了解有关在项目中使用组件的信息。

## 组件操作

您可以通过多种方式管理组件（逐个选择或通过选择多个组件）。右键单击组件，或单击组件列表顶部的&#x200B;**[!UICONTROL 操作]**。

>[!NOTE]
>
>这些操作不适用于“时间”组件。

| 组件操作 | 描述 |
|--- |--- |
| 标记 | 通过对组件应用标记来组织或管理组件。然后它会显示在相应的组件管理器中，如“Analytics”>“组件”>“区段”，或“Analytics”>“组件”>“项目” |
| 收藏 | 将组件添加到您的收藏夹列表中。然后它会显示在相应的组件管理器中，如“Analytics”>“组件”>“区段”，或“Analytics”>“组件”>“项目”。 |
| 批准 | 批准组件以使其成为规范。然后它会显示在相应的组件管理器中，如“Analytics”>“组件”>“区段”，或“Analytics”>“组件”>“项目” |
| 共享 | 仅适用于区段。 |
| 删除 | 仅适用于区段。 |

观看有关创建量度、区段和日期的视频：

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## 组件访问权限

管理员可以(通过[Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en#manage-users-and-products))组织哪些组件在报告中向用户公开。 下表显示了这些组件访问权限的行为：

| 特选类型 | 管理员可以 | 非管理员项目所有者（或编辑角色）可以 | 非管理员重复角色 |
| --- | --- | --- | --- |
| **组件在数据视图中“隐藏”** | 所有可用于报告的视图组件（隐藏的组件需要单击“显示全部”） | 不可用于报告 | 不可用于报告 |
| **从数据视图添加或删除的组件** | 仅添加到数据视图的组件（隐藏或未隐藏）。 管理员无法报告未由数据视图定义的字段或组件。 | 仅添加到数据视图的组件，或由用户拥有或与用户共享的组件。 隐藏的组件不可用（如VRS特选）。 | 只有添加到DV的组件不会隐藏，并且已包含在“项目”特选中。 |
| **项目中的精选组件** | 所有可用于报告的视图组件（隐藏的组件需要单击“显示全部”） | 所有非隐藏的数据视图组件（需要单击“显示全部”） | 仅限精选的组件，以及拥有或与用户共享的任何组件 |
| **使用包含隐藏组件的数据视图的精选项目** | 所有可用于报告的数据组件（隐藏和非特选组件需要单击“显示全部”） | 所有非精选项目组件、所有非隐藏数据视图组件，以及用户拥有或共享的任何组件 | 仅限精选的组件，以及用户拥有或共享的任何组件 |

