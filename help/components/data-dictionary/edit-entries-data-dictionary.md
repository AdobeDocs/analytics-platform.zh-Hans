---
description: Analysis Workspace 中的数据词典允许用户对 Analysis Workspace 中的各种组件进行编目和跟踪，包括组件的预期用途、批准情况、重复情况等等。
title: 编辑数据词典中的条目
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: de04792035aa7c235751019ee9f9fe5b74b9b102
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 60%

---

# 编辑数据词典中的组件条目

Customer Journey Analytics管理员可以在数据字典中编辑给定数据视图的组件条目。 所做的任何更改均对数据视图的所有用户可见。

要编辑数据词典中的组件：

1. 前往包含要编辑组件的 Analysis Workspace 项目。

1. 在Analysis Workspace的按钮面板中选择&#x200B;**数据字典**&#x200B;图标。 （[数据字典概述](/help/components/data-dictionary/data-dictionary-overview.md)中的“访问数据字典”一节中描述了访问数据词典的其他方法。）

   显示“数据词典”窗口。

   ![显示字典运行状况的数据字典管理员视图](assets/data-dictionary-admin.png)

1. 确保在下拉菜单中选择正确的数据视图。 默认情况下，将显示您已在中的数据视图。

1. （可选）在搜索字段中，开始键入要编辑的组件的名称。

   组件的类型可以通过颜色和图标来识别。**Dimension** ![Dimension图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg)为橙色，**筛选器** ![区段图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg)为蓝色，**日期范围** ![日期范围图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)为紫色，**量度** ![量度图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg)为绿色。 Adobe图标表示计算指标模板或过滤器模板，计算器图标![计算器图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg)表示由您组织中的Analytics管理员创建的计算指标。

   {{dd-filter-criteria}}

1. （可选）选择&#x200B;**排序**&#x200B;图标![对组件图标进行排序](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)，然后选择以下任一过滤器选项对组件列表进行排序：

{{components-sort-options}}

1. 从组件列表中，选择要编辑的组件。

1. 选择组件名称旁边的&#x200B;**编辑**&#x200B;图标，即![“数据词典编辑”图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)。

1. 编辑有关组件的以下任何信息：

{{dd-component-information}}

1. 单击&#x200B;**保存**&#x200B;图标，即![“数据词典保存”图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg)来保存您的更改。
