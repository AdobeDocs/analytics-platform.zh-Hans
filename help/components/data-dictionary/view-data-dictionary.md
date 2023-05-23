---
description: Analysis Workspace 中的数据词典允许用户对 Analysis Workspace 中的各种组件进行编目和跟踪，包括组件的预期用途、批准情况、重复情况等等。
title: 查看数据词典
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: b38b5b54ebbf301a3e59156d484bf5d69974b4a4
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 51%

---

# 查看数据词典中的组件信息

“数据词典”允许您查看有关组件的信息，包括组件描述、相似组件、组件经常使用的其他组件等等。

要查看数据词典中的组件信息：

1. 前往包含要查看组件的 Analysis Workspace 项目。

1. 选择 Analysis Workspace 左侧栏中的&#x200B;[!UICONTROL **数据词典**]&#x200B;图标。（[数据字典概述](/help/components/data-dictionary/data-dictionary-overview.md)中的“访问数据字典”一节中描述了访问数据词典的其他方法。）

   显示“数据词典”窗口。

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. 確定已在下拉式選單中選取包含您要檢視之元件的資料檢視。 依預設，系統會顯示您已在的資料檢視。

1. （可选）在搜索字段中，开始键入要查看组件的名称。

   元件型別可由顏色和圖示識別。 **Dimension** ![Dimension圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) 是橙色， **區段** ![「區段」圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) 是藍色的， **日期範圍** ![日期範圍圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) 是紫色的，並且 **量度** ![量度圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) 是綠色的。 Adobe圖示 ![Adobe圖示](assets/default-calc-metric-icon.png) 表示計算量度範本或區段範本，以及計算器圖示 ![計算器圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) 表示貴組織中Analytics管理員建立的計算量度。

{{dd-filter-criteria}}

1. （可選）選取 **排序** 圖示 ![排序元件圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)，然後選取下列任一篩選選項來排序元件清單：

   {{components-sort-options}}

1. 从组件列表中，选择要查看的组件。

   显示有关组件的以下信息：

   {{dd-component-information}}

1. （可选）将组件从数据词典拖入 Analysis Workspace。
