---
title: Customer Journey Analytics 中有哪些组件？
description: 了解 Customer Journey Analytics 提供了哪些组件，以及如何在报表中使用它们。
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 33%

---

# 组件概述

组件是Customer Journey Analytics中的功能，可用于可视化（如自由格式表）或补充报表功能。

要从主Customer Journey Analytics界面管理组件，请执行以下操作：

1. 从顶部栏中选择&#x200B;**[!UICONTROL 组件]**。
1. 选择&#x200B;**[!UICONTROL 组件]**&#x200B;以查看可管理组件的概述，或直接从菜单中选择要管理的组件。

您可以管理以下组件：

* [过滤器](filters/filters-overview.md)：构建、管理、共享强大的、有针对性的受众过滤器，并将其应用到您的报告中。利用过滤器可根据特征或交互辨别一部分人。
* [计算量度](calc-metrics/calc-metr-overview.md)：使用量度和公式作为新组件以便在报告中使用
* [日期范围](date-ranges/create.md)：自定义和优化 Analysis Workspace 中提供的日期范围。
* [注释](/help/components/annotations/overview.md)：向您的组织传达上下文数据的细微差别和见解。
* [智能警报](/help/components/c-intelligent-alerts/intelligent-alerts.md)：允许您根据更改的百分比或特定数据点接收通知。
* [计划项目](/help/analysis-workspace/export/t-schedule-report.md#scheduled-projects-manager)：管理您的计划项目。
* [首选项](/help/analysis-workspace/user-preferences.md)：管理Analysis Workspace的首选项。
* [受众](/help/components/audiences/audiences-overview.md)：创建受众并将受众从Customer Journey Analytics发布到Experience Platform中的[Real-time Customer Data Platform](https://experienceleague.adobe.com/en/docs/experience-platform/profile/home)，以进行定位和个性化。
* [导出](/help/components/exports/manage-export-locations.md)：管理您的导出帐户和位置。


## Analysis Workspace 组件

Analysis Workspace中的组件包括量度、维度、过滤器和日期范围，您可以将这些组件拖放到Workspace项目中的面板和可视化图表上。 您创建的自定义组件将添加到这些面板中，例如计算量度或自定义日期范围。

要访问“组件”面板，请在按钮面板中选择![策划](/help/assets/icons/Curate.svg) **[!UICONTROL 组件]**。

![突出显示左侧边栏中“组件”图标的 Workspace 面板](assets/components.png)

有关如何使用项目中的组件的信息，请参阅[创建项目](/help/analysis-workspace/home.md)。


+++ 观看视频，了解组件的可能性：

>[!VIDEO](https://video.tv.adobe.com/v/23979)

+++

## 管理组件 {#actions}

您可以使用Analysis Workspace中的&#x200B;**[!UICONTROL 组件]**&#x200B;菜单快速创建新组件。 有关详细信息，请参阅[Analysis Workspace菜单](/help/analysis-workspace/home.md#menu)。

您可以管理组件（逐个或通过选择多个组件）。

1. 选择一个或多个组件。

1. 从上下文菜单或![MoreVertical](/help/assets/icons/MoreVertical.svg)组件操作按钮（位于组件顶部）中，选择以下操作之一。


   >[!TIP]
   >
   >按住&#x200B;**[!UICONTROL Shift]**&#x200B;或&#x200B;**[!UICONTROL Command]**(在macOS上)或&#x200B;**[!UICONTROL Ctrl]**（在Windows上）可选择多个组件。


   ![组件操作列表，其中显示了“标记”、“收藏”、“批准”、“共享”和“删除”。](assets/component-menu.gif){width=100%}

   | 组件操作 | 描述 |
   |--- |--- |
   | ![标签](/help/assets/icons/Label.svg) [!UICONTROL **标签**] | 通过将标记应用于组件而组织或管理组件。然后，您可以通过选择![筛选器](/help/assets/icons/Filter.svg)筛选器或键入`#`在左侧面板中按标记进行搜索。 标记在组件管理器中也可用作过滤器。 |
   | ![星级](/help/assets/icons/Star.svg) [!UICONTROL **收藏**] | 将组件添加到您的收藏夹列表中。与标记类似，您可以在左侧面板中按“收藏夹”进行搜索，然后在组件管理器中对其进行过滤。 |
   | ![星形大纲](/help/assets/icons/StarOutline.svg) **[!UICONTROL 取消收藏]** | 从收藏夹列表中删除该组件。 |
   | ![复选标记](/help/assets/icons/Checkmark.svg) [!UICONTROL **批准**] | 将组件标记为“已批准”可告知用户该组件得到了组织的批准。与标记类似，您可在左侧面板中按“已批准”进行搜索和过滤。 ![复选标记](/help/assets/icons/Checkmark.svg)标识已批准的组件。 |
   | ![共享](/help/assets/icons/Share.svg) [!UICONTROL **共享**] | 将组件与组织中的用户共享。此选项仅对自定义组件可用，例如过滤器或计算量度。 |
   | ![删除](/help/assets/icons/Delete.svg) [!UICONTROL **删除**] | 删除不再需要的组件。此选项仅对自定义组件可用，例如过滤器或计算量度。 |

自定义组件也可通过其相应的组件管理器进行管理。例如，请参阅[管理筛选器](/help/components/filters/manage-filters.md)。

## 管理组件列表

您可以在Analysis Workspace的左侧面板中搜索、筛选和排序组件列表，以定位特定组件。

### 搜索

1. 在左侧面板中选择&#x200B;**组件** ![组件图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)。

2. 在搜索字段中，开始键入要在项目中使用的组件名称。

   颜色和图标用于标识组件的类型。 **Dimension** ![Dimension图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg)为橙色，**筛选器** ![筛选器图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg)为蓝色，**日期范围** ![日期范围图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)为紫色，**量度** ![量度图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg)为绿色。<br/>Adobe图标![AdobeLogo](/help/assets/icons/AdobeLogoSmall.svg)表示计算指标模板或筛选器模板。 计算器图标![计算器图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg)表示组织中的管理员已创建的计算量度。

3. 从下拉列表中选择组件。

### 筛选

1. 在左侧面板中选择&#x200B;**组件**&#x200B;图标![组件图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)。

2. 选择&#x200B;**筛选器** ![数据字典筛选器图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)，或在搜索字段中输入`#`。

3. 选择以下任一过滤器选项以过滤组件列表：

   | 图标 | 筛选器选项 | 描述 |
   |---------|---|----------|
   | ![复选标记](/help/assets/icons/Checkmark.svg) | **[!UICONTROL 已批准]** | 仅显示标记为由管理员批准的组件。 |
   | ![颗星](/help/assets/icons/Star.svg) | **[!UICONTROL 收藏夹]** | 仅显示收藏夹列表中的组件。<br/>有关将组件添加到收藏夹列表的信息，请参阅[管理组件](#manage-components)。 |
   | ![维度](/help/assets/icons/Dimensions.svg) | **[!UICONTROL 维度]** | 仅显示维度的组件。 |
   | ![事件](/help/assets/icons/Event.svg) | **[!UICONTROL 指标]** | 仅显示指标的组件。 |
   | ![区段划分](/help/assets/icons/Segmentation.svg) | **[!UICONTROL 过滤器]** | 仅显示过滤器组件。 |
   | ![日程表](/help/assets/icons/Calendar.svg) | **[!UICONTROL 日期范围]** | 仅显示属于日期范围的组件。 |
   | ![标签](/help/assets/icons/Label.svg) | **[!UICONTROL *标记名称&#x200B;*]** | 仅显示具有特定选定标记的组件。 专用标记可用于Adobe模板，该模板是来自Adobe的[默认计算指标](/help/components/calc-metrics/default-calcmetrics.md)。 |

   在筛选器中选择![CrossSize75](/help/assets/icons/CrossSize75.svg)以删除该筛选器。

4. 您可以选择对组件列表进行排序，如[对组件列表进行排序](#sort-the-component-list)中所述。

### 排序

<!-- {{release-limited-testing-section}}-->

1. （可选）对组件列表应用任何过滤器，如[筛选组件列表](#filter-the-component-list)中所述。

2. 在左侧面板中选择&#x200B;**组件** ![组件图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)。

3. 选择&#x200B;**排序** ![组件排序图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)，然后选择以下任何筛选器选项对组件列表进行排序。

可以使用以下排序选项：

{{components-sort-options}}

## 访问权限

在Analysis Workspace中，管理员可以[策划](/help/analysis-workspace/curate-share/curate.md)哪些组件在报表中对用户可见。
