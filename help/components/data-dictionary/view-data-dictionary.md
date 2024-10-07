---
description: Analysis Workspace 中的数据词典允许用户对 Analysis Workspace 中的各种组件进行编目和跟踪，包括组件的预期用途、批准情况、重复情况等等。
title: 查看组件信息
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: df0fd0af8a22c84705c3dea11065132359dd80ff
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 73%

---

# 查看组件信息

“数据词典”允许您查看有关组件的信息，包括组件描述、相似组件、组件经常使用的其他组件等等。

要查看数据词典中的组件信息：

1. 前往包含要查看组件的 Analysis Workspace 项目。

1. 选择Analysis Workspace左侧面板中的&#x200B;[!UICONTROL **数据字典**]&#x200B;图标。 （[数据字典概述](/help/components/data-dictionary/data-dictionary-overview.md)中的“访问数据字典”一节中描述了访问数据词典的其他方法。）

   显示“数据词典”窗口。

   ![显示Dimension、指标、区段和日期范围的快速筛选的“数据字典”窗口](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. 确保在下拉菜单中选择了包含要查看的组件的数据视图。 默认情况下，将显示您已在中的数据视图。

1. （可选）在搜索字段中，开始键入要查看组件的名称。

   组件的类型可以通过颜色和图标来识别。**Dimension** ![Dimension图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg)为橙色，**筛选器** ![区段图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg)为蓝色，**日期范围** ![日期范围图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)为紫色，**量度** ![量度图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg)为绿色。 Adobe 图标![ Adobe 图标](assets/default-calc-metric-icon.png)表示计算量度模板或过滤器模板，计算器图标![计算器图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg)表示由您组织的 Analytics 管理员创建的计算量度。

{{dd-filter-criteria}}

1. （可选）选择&#x200B;**排序**&#x200B;图标![对组件图标进行排序](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)，然后选择以下任一过滤器选项对组件列表进行排序：

   {{components-sort-options}}

1. 从组件列表中，选择要查看的组件。

   显示有关组件的以下信息：

   {{dd-component-information}}

1. （可选）将组件从数据词典拖入 Analysis Workspace。
