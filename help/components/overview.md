---
title: Customer Journey Analytics 中有哪些组件？
description: 了解 Customer Journey Analytics 提供了哪些组件，以及如何在报告中使用它们。
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 100%

---

# 组件概述

组件是 Customer Journey Analytics 中的功能，可以在可视化图表（例如自由格式表）中使用，或者用于补充报告功能。

要从主 Customer Journey Analytics 界面管理组件：

1. 从顶部栏中选择&#x200B;**[!UICONTROL 组件]**。
1. 选择&#x200B;**[!UICONTROL 组件]**&#x200B;以查看您可以管理的组件的概述，或者直接从菜单中选择您想要管理的组件。

您可以管理以下组件：

* [区段](segments/seg-overview.md)：构建、管理、共享强大的、有针对性的受众区段，并将其应用到您的报告中。使用区段可以根据相关特征或交互识别人员的子集。
* [计算量度](calc-metrics/calc-metr-overview.md)：使用量度和公式作为新组件以便在报告中使用
* [日期范围](date-ranges/create.md)：自定义和优化 Analysis Workspace 中提供的日期范围。
* [注释](/help/components/annotations/overview.md)：向您的组织传达上下文数据的细微差别和洞察。
* [智能警报](/help/components/c-intelligent-alerts/intelligent-alerts.md)：允许您根据变化的百分比或特定数据点收到通知。
* [已计划项目](/help/analysis-workspace/export/t-schedule-report.md#scheduled-projects-manager)：管理您已计划项目。
* [偏好设置](/help/analysis-workspace/user-preferences.md)：管理 Analysis Workspace 的偏好设置。
* [受众](/help/components/audiences/audiences-overview.md)：在 Experience Platform 中创建并将 Customer Journey Analytics 中的受众发布到 [Real-Time Customer Data Platform](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/profile/home)，以进行目标选择和个性化。
* [导出内容](/help/components/exports/manage-export-locations.md)：管理您的导出帐户和位置。


## Analysis Workspace 组件

Analysis Workspace 中的组件包括量度、维度、区段和日期范围，您可以将其拖放到 Workspace 项目中的面板和可视化图表中。您创建的自定义组件会被添加到这些面板中，例如计算量度或自定义日期范围。

要访问“组件”面板，请在按钮面板中选择![Curate](/help/assets/icons/Curate.svg)**[!UICONTROL 组件]**。

![Workspace panel highlighting the Components icon in the left-rail](assets/components.png)

请参阅[创建项目](/help/analysis-workspace/home.md)，以了解有关如何在项目中使用组件的信息。


## 管理组件 {#actions}

您可以使用 Analysis Workspace 中的&#x200B;**[!UICONTROL 组件]**&#x200B;菜单快速创建新组件。请参阅 [Analysis Workspace 菜单](/help/analysis-workspace/home.md#menu)，以了解更多详细信息。

您可以管理组件（逐个管理或通过选择多个组件来进行管理）。

1. 选择一个或多个组件。

1. 从上下文菜单或从 ![MoreVertical](/help/assets/icons/MoreVertical.svg) 组件操作按钮（位于“组件”顶部）中，选择以下操作之一。


   >[!TIP]
   >
   >通过按住 **[!UICONTROL Shift]** 键或按住 **[!UICONTROL Command]** 键 (macOS) 或 **[!UICONTROL Ctrl]** 键 (Windows) 可选择多个组件。


   ![显示标签、收藏、批准、共享和删除的组件操作列表。](assets/component-menu.gif){width=100%}

   | 组件操作 | 描述 |
   |--- |--- |
   | ![Label](/help/assets/icons/Label.svg) [!UICONTROL **标记**] | 通过将标记应用于组件来组织或管理组件。然后，您可以通过选择![Filter](/help/assets/icons/Filter.svg)或者键入 `#` 在左侧面板中按标记搜索。标记在组件管理器中也可用作过滤器。 |
   | ![Star](/help/assets/icons/Star.svg) [!UICONTROL **收藏夹**] | 将组件添加到您的收藏夹列表中。与标记相似，您可在左侧面板中按“收藏夹”进行搜索，然后在组件管理器中对其进行过滤。 |
   | ![StarOutline](/help/assets/icons/StarOutline.svg) **[!UICONTROL 取消收藏]** | 将组件从您的收藏夹列表中移除。 |
   | ![复选标记](/help/assets/icons/Checkmark.svg) [!UICONTROL **批准**] | 将组件标记为“已批准”可告知用户该组件得到了组织的批准。与标记一样，您可以在左侧面板中按“已批准”进行搜索和筛选。![Checkmark](/help/assets/icons/Checkmark.svg)标识的是已批准的组件。 |
   | ![Share](/help/assets/icons/ShareAlt.svg) [!UICONTROL **分享**] | 将组件与组织中的用户共享。此选项仅对自定义组件可用，例如区段或计算量度。 |
   | ![Delete](/help/assets/icons/Delete.svg) [!UICONTROL **删除**] | 删除不再需要的组件。此选项仅对自定义组件可用，例如区段或计算量度。 |

自定义组件也可通过其相应的组件管理器进行管理。例如，参阅[管理区段](/help/components/segments/seg-manage.md)。

## 管理组件列表

您可以在 Analysis Workspace 的左侧面板中对组件列表进行搜索、筛选和排序，以找到特定组件。

### 搜索

1. 在左侧面板中选择&#x200B;**组件** ![Components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)。

2. 在搜索字段中，开始键入要在项目中使用的组件名称。

   颜色和图标标识的是组件的类型。**维度** ![Dimension icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) 是橙色的，**区段** ![Segment icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) 是蓝色的，**日期范围** ![Date range icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) 是紫色的，**量度** ![Metric icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) 是绿色的。<br/>Adobe 图标 ![AdobeLogo](/help/assets/icons/AdobeLogoSmall.svg) 表示计算量度模板或区段模板。计算器图标 ![Calculator icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) 表示您的组织中某位管理员创建的计算量度。

3. 从下拉菜单中选择组件。

### 筛选

1. 在左侧面板中选择&#x200B;**组件**&#x200B;图标 ![Components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)。

2. 选择&#x200B;**筛选** ![Data Dictionary Filter icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)，或在搜索字段中输入 `#`。

3. 选择以下任一过滤器选项以过滤组件列表：

   | 图标 | 筛选选项 | 描述 |
   |---------|---|----------|
   | ![Checkmark](/help/assets/icons/Checkmark.svg) | **[!UICONTROL 已批准]** | 仅显示标记为由管理员批准的组件。 |
   | ![Star](/help/assets/icons/Star.svg) | **[!UICONTROL 收藏夹]** | 仅显示收藏夹列表中的组件。<br/>有关将组件添加到收藏夹列表的信息，请参阅[管理组件](#manage-components)。 |
   | ![Dimensions](/help/assets/icons/Dimensions.svg) | **[!UICONTROL 维度]** | 仅显示维度的组件。 |
   | ![Event](/help/assets/icons/Event.svg) | **[!UICONTROL 量度]** | 仅显示量度的组件。 |
   | ![Segmentation](/help/assets/icons/Segmentation.svg) | **[!UICONTROL 区段]** | 仅显示区段的组件。 |
   | ![Calendar](/help/assets/icons/Calendar.svg) | **[!UICONTROL 日期范围]** | 仅显示日期范围的组件。 |
   | ![Label](/help/assets/icons/Label.svg) | **[!UICONTROL *标记名称&#x200B;*]** | 仅显示具有特定选定标记的组件。Adobe 模板有一个专用标记，它是 Adobe 提供的[默认计算量度](/help/components/calc-metrics/default-calcmetrics.md)。 |

   在筛选中选择 ![CrossSize75](/help/assets/icons/CrossSize75.svg) 以删除该筛选。

4. 您可以选择对组件列表进行排序，如[对组件列表进行排序](#sort-the-component-list)中所述。

### 排序

<!-- {{release-limited-testing-section}}-->

1. （可选）对组件列表应用任何筛选条件，如[筛选组件列表](#filter-the-component-list)中所述。

2. 在左侧面板中选择&#x200B;**组件** ![Components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)。

3. 选择&#x200B;**排序** ![Sort components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)，然后选择以下任一筛选选项对组件列表进行排序。

可以使用以下排序选项：

{{components-sort-options}}

## 访问权限

在 Analysis Workspace 中，管理员可以[管理](/help/analysis-workspace/curate-share/curate.md)哪些组件在报告中对用户可见。
