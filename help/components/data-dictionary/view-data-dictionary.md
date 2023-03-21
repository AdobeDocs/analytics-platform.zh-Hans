---
description: Analysis Workspace 中的数据词典允许用户对 Analysis Workspace 中的各种组件进行编目和跟踪，包括组件的预期用途、批准情况、重复情况等等。
title: 查看数据词典
feature: Components
role: User, Admin
source-git-commit: 733e0e358aa34ce126687f01ffb6d89f9b0c4210
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 75%

---

# 查看数据词典中的组件信息

“数据词典”允许您查看有关组件的信息，包括组件描述、相似组件、组件经常使用的其他组件等等。

要查看数据词典中的组件信息：

1. 前往包含要查看组件的 Analysis Workspace 项目。

1. 选择 Analysis Workspace 左侧栏中的&#x200B;[!UICONTROL **数据词典**]&#x200B;图标。（[数据字典概述](/help/components/data-dictionary/data-dictionary-overview.md)中的“访问数据字典”一节中描述了访问数据词典的其他方法。）

   显示“数据词典”窗口。

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. 确保在下拉菜单中选择了包含您要查看的组件的报告包。默认情况下，会显示您已在使用的报告包。

1. （可选）在搜索字段中，开始键入要查看组件的名称。

   组件类型可通过颜色和图标进行标识。 **Dimension** ![Dimension图标](assets/dimension-icon.png) 橙色， **区段** ![区段图标](assets/segment-icon.png) 是蓝色的， **日期范围** ![日期范围图标](assets/date-range-icon.png) 是紫色的， **量度** ![“量度”图标](assets/default-metric-icon.png) 为绿色。 Adobe图标 ![Adobe图标](assets/default-calc-metric-icon.png) 指示计算量度模板或区段模板以及计算器图标 ![计算器图标](assets/calculated-metric-icon-created.png) 指示了由您组织中的Analytics管理员创建的计算量度。

{{dd-filter-criteria}}

1. 从组件列表中，选择要查看的组件。

   显示有关组件的以下信息：

   {{dd-component-information}}

1. （可选）将组件从数据词典拖入 Analysis Workspace。