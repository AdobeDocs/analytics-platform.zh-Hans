---
title: Customer Journey Analytics 中有哪些组件？
description: 了解Customer Journey Analytics提供了哪些组件，以及如何在报表中使用它们。
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 79%

---

# 组件概述

组件是 Customer Journey Analytics 中的功能，可以在报告中使用，或者用于补充报告功能。您可以通过以下步骤管理这些组件：

1. 使用您的 Adobe ID 凭据登录 [analytics.adobe.com](https://analytics.adobe.com)。
2. 在标题菜单中，导航到[!UICONTROL 组件] > [!UICONTROL 组件]。

您可以管理以下组件：

* [**批注**](/help/components/annotations/overview.md)：向您的组织传达上下文数据的细微差别和见解。
* [**受众**](/help/components/audiences/audiences-overview.md)：创建在Customer Journey Analytics中发现的受众并将其发布到 [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans) Adobe Experience Platform (RTCDP)，用于客户定位和个性化。
* [**过滤器**](filters/filters-overview.md)：构建、管理、共享强大集中的受众过滤器，并将其应用于您的报表。 过滤器让您可以根据用户特征或交互情况来识别用户子集。
* [**计算量度**](calc-metrics/calc-metr-overview.md)：使用量度和公式作为新组件以便在报告中使用
* [**数据字典**](/help/components/data-dictionary/data-dictionary-overview.md)：帮助用户和管理员跟踪并更好地了解其Analytics环境中的组件。
* [**日期范围**](date-ranges/create.md)：自定义和优化 Analysis Workspace 中提供的日期范围.
* [**Dimension**](/help/components/dimensions/view-dimensions.md)：Dimension是通常包含字符串值的变量。 常见维度包括页面和反向链接域。
* [**量度**](/help/components/apply-create-metrics.md)：用于量化Analysis Workspace中的数据点。
* [**项目**](/help/analysis-workspace/home.md)：组织和维护 Analysis Workspace 中的项目.

## Analysis Workspace 组件

Analysis Workspace 中的组件包括量度、维度、区段和时间粒度，您可以将这些组件拖放到项目中。您创建的自定义组件会被添加到这些面板中，例如自定义日期范围。

要访问“组件”面板，请单击左边栏中的&#x200B;**[!UICONTROL 组件]**&#x200B;图标。您可以使用左边栏图标或[热键](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)在面板（空白面板、[自由格式面板](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)、[快速分析面板](/help/analysis-workspace/c-panels/quickinsight.md)或[Attribution IQ](/help/analysis-workspace/c-panels/attribution.md) 面板）、[可视化图表](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)和“组件”之间切换。

![“组件”图标](assets/components.png)

请参阅[创建项目](/help/analysis-workspace/home.md)，以了解有关在项目中使用组件的信息。

## 组件操作

您可以通过多种方式管理组件（逐个选择或通过选择多个组件）。右键单击组件，或单击组件列表顶部的&#x200B;**[!UICONTROL 操作]**。

>[!NOTE]
>
>这些操作不适用于“时间”组件。

| 组件操作 | 描述 |
| --- | --- |
| 标记 | 通过对组件应用标记来组织或管理组件。然后，它显示在相应的组件管理器中，如 [!UICONTROL Analytics] > [!UICONTROL 组件] > [!UICONTROL 过滤器]，或 [!UICONTROL Analytics] > [!UICONTROL 组件] > [!UICONTROL 项目] |
| 收藏 | 将组件添加到您的收藏夹列表中。然后，它显示在相应的组件管理器中，如 [!UICONTROL Analytics] > [!UICONTROL 组件] > [!UICONTROL 过滤器]，或 [!UICONTROL Analytics] > [!UICONTROL 组件] > [!UICONTROL 项目]。 |
| 批准 | 批准组件以使其成为规范。然后，它显示在相应的组件管理器中，如 [!UICONTROL Analytics] > [!UICONTROL 组件] > [!UICONTROL 过滤器]，或 [!UICONTROL Analytics] > [!UICONTROL 组件] > [!UICONTROL 项目] |
| 共享 | 仅适用于过滤器。 |
| 删除 | 仅适用于过滤器。 |

观看有关创建量度、过滤器和日期的视频：

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## 管理组件 {#actions}

您可以直接在左侧边栏中管理组件。

1. 右键单击一个组件。

   或

   选择一个组件，然后选择组件列表顶部的&#x200B;**操作**（3 点）图标。

   >[!TIP]
   >
   >   通过按住 Shift 或按住 Command (Mac) 或 Ctrl (Windows) 可选择多个组件。


   ![“组件操作”列表](assets/component-actions.png)

   | 组件操作 | 描述 |
   |--- |--- |
   | [!UICONTROL **标记**] | 通过将标记应用于组件而组织或管理组件。然后，您可以通过单击过滤器或者键入 # 在左边栏中按标记搜索。标记在组件管理器中也可用作过滤器。 |
   | [!UICONTROL **收藏**] | 将组件添加到您的收藏夹列表中。与标记相似，您可在左边栏中按“收藏”进行搜索，然后在组件管理器中对其进行过滤。 |
   | [!UICONTROL **批准**] | 将组件标记为“已批准”可告知用户该组件得到了组织的批准。与标记相似，您可在左边栏中按“已批准”进行搜索，然后在组件管理器中对其进行过滤。 |
   | [!UICONTROL **共享**] | 将组件与组织中的用户共享。此选项仅适用于自定义组件，例如过滤器或计算量度。 |
   | [!UICONTROL **删除**] | 删除不再需要的组件。此选项仅适用于自定义组件，例如过滤器或计算量度。 |

自定义组件也可通过其相应的组件管理器进行管理。例如， [管理过滤器](/help/components/filters/manage-filters.md).

## 搜索、筛选并对组件列表进行排序

您可以在 Analysis Workspace 的左侧边栏中对组件列表进行搜索、筛选和排序，以快速找到特定组件。

### 搜索组件列表

1. 在左侧边栏中选择&#x200B;**组件**&#x200B;图标 ![组件图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)。

2. 在搜索字段中，开始键入要在项目中使用的组件名称。

   组件的类型可以通过颜色和图标来识别。**Dimension** ![Dimension图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) 是橙色的， **过滤器** ![过滤器图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) 是蓝色的， **日期范围** ![日期范围图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) 是紫色的，而且 **量度** ![“量度”图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) 是绿色的。 Adobe图标 ![Adobe图标](assets/default-calc-metric-icon.png) 指示计算指标模板或过滤器模板，以及计算器图标 ![计算器图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) 指示由贵组织中的Analytics管理员创建的计算指标。

3. 当组件出现在下拉列表中时选中它。

### 过滤组件列表

1. 在左侧边栏中选择&#x200B;**组件**&#x200B;图标 ![组件图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)。

2. 选择 **筛选** 图标 ![“数据字典过滤器”图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg))。

   或

   在搜索字段中键入井号 (#)。

3. 选择以下任一筛选条件选项以过滤组件列表：

   | 选项 | 函数 |
   |---------|----------|
   | [!UICONTROL **已批准**] | 仅显示标记为由管理员批准的组件。 |
   | [!UICONTROL **收藏夹**] | 仅显示收藏夹列表中的组件。有关将组件添加到收藏夹列表的信息，请参阅 [管理组件](#manage-components). |
   | [!UICONTROL **维度**] | 仅显示维度的组件。 |
   | [!UICONTROL **指标**] | 仅显示指标的组件。 |
   | [!UICONTROL **筛选器**] | 仅显示属于筛选器的组件。 |
   | [!UICONTROL **日期范围**] | 仅显示日期范围的组件。 |
   | [!UICONTROL **显示所有**] | 显示所有组件。仅管理员有此选项可用。 |
   | [!UICONTROL **未批准**] | 仅显示未标记为由管理员批准的组件。作为管理员，这有助于确定需要您审阅和批准的组件。仅管理员有此选项可用。 |

4. （可选）要进一步细化列表，您可以对组件列表进行排序，如[对组件列表进行排序](#sort-the-component-list)中所述。

### 对组件列表进行排序

{{release-limited-testing-section}}

1. （可选）对组件列表应用任何筛选条件，如[筛选组件列表](#filter-the-component-list)中所述。

2. 在左侧边栏中选择&#x200B;**组件**&#x200B;图标 ![组件图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)。

3. 选择&#x200B;**排序**&#x200B;图标 ![为组件排序图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)，然后选择以下任一过滤器选项对组件列表进行排序：

   {{components-sort-options}}

## 组件访问权限

在 Analysis Workspace 中，管理员可[管理](/help/analysis-workspace/curate-share/curate.md)哪些组件在报告中对用户可见。
