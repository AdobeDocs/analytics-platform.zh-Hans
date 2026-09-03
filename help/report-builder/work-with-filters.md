---
title: 在Report Builder中使用区段
description: 了解如何在Report Builder中使用区段。
role: User
feature: Report Builder
type: Documentation
exl-id: 1f39d7f4-b508-45d8-9b97-81242c3805d3
solution: Customer Journey Analytics
TQID: https://experienceleague.adobe.com/BOvbE0QbzDPntg55mRGkS-HIh7dUh1inIFgAhAlfLGw
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: f2ef16dc-055a-4bb7-baa5-7039653f3966
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 641
ht-degree: 6%

---

# 使用区段工作

您可以在创建新数据块或从&#x200B;**[!UICONTROL 命令]**&#x200B;面板中选择&#x200B;**[!UICONTROL 编辑数据块]**&#x200B;时应用区段。

## 将区段应用到数据块

要将区段应用于整个数据块，请双击一个区段，或者将区段从组件列表拖放到表的区段部分中。

## 将筛选器应用到单独的量度

要使用区段将过滤器应用于单个量度，请执行以下操作：

* 将&#x200B;**[!UICONTROL 区段]**&#x200B;中的一个或多个区段拖放到表中的某个量度上。

* 或者：

  1. 在&#x200B;**[!UICONTROL 表]**&#x200B;窗格中为特定量度选择![MoreSmall](/help/assets/icons/MoreSmall.svg)，然后选择&#x200B;**[!UICONTROL 筛选量度]**。

     ![区段选项卡显示指标。](./assets/filter-metric.png){zoomable="yes"}

  1. 从&#x200B;**[!UICONTROL 段]**&#x200B;下拉菜单中选择一个或多个段。 区段已添加到&#x200B;**[!UICONTROL 应用的区段]**&#x200B;列表。

     已应用![区段](assets/segments-applied.png)
  1. 选择![CrossSize75](/help/assets/icons/CrossSize75.svg)以从&#x200B;**[!UICONTROL 应用的区段]**&#x200B;列表中删除区段。 或者选择&#x200B;**[!UICONTROL 全部清除]**&#x200B;以从&#x200B;**[!UICONTROL 应用的区段]**&#x200B;列表中删除所有区段。
  1. 选择&#x200B;**[!UICONTROL 应用]**。

要查看应用的筛选器，请将光标悬停在量度上，或者在“表”窗格中选择量度。 已应用区段的量度会显示区段图标。


## 快速编辑区段

您可以使用&#x200B;**[!UICONTROL 快速编辑]**&#x200B;面板为现有数据块添加、删除或替换区段。

在电子表格中选择单元格范围时，**[!UICONTROL 快速编辑]**&#x200B;面板中的&#x200B;**[!UICONTROL 区段]**&#x200B;链接会显示该选区中数据块使用的区段的摘要列表。

要使用&#x200B;**[!UICONTROL 快速编辑]**&#x200B;面板编辑区段，请执行以下操作：

1. 从一个或多个数据块选择单元格范围。

1. 选择&#x200B;**[!UICONTROL 区段]**&#x200B;链接以启动&#x200B;**[!UICONTROL 快速编辑]**&#x200B;**[!UICONTROL 区段]**&#x200B;面板。


### 添加或删除区段

您可以使用“添加/删除”选项添加或删除区段。

1. 在&#x200B;**[!UICONTROL 快速编辑]**&#x200B;**[!UICONTROL 区段]**&#x200B;面板中选择&#x200B;**[!UICONTROL 添加/删除]**&#x200B;选项卡。


   1. 从&#x200B;**[!UICONTROL 段]**&#x200B;下拉菜单中选择一个或多个段。 区段已添加到&#x200B;**[!UICONTROL 应用的区段]**&#x200B;列表。
   1. 选择![CrossSize75](/help/assets/icons/CrossSize75.svg)以从&#x200B;**[!UICONTROL 应用的区段]**&#x200B;列表中删除区段。
   1. 选择&#x200B;**[!UICONTROL 应用]**。

Report Builder显示消息以确认应用的区段更改。

### 替换区段

您可以使用另一个区段替换现有区段，以更改数据的分段方式。

1. 在&#x200B;**[!UICONTROL 快速编辑]**&#x200B;**[!UICONTROL 区段]**&#x200B;面板中选择&#x200B;**[!UICONTROL 替换]**&#x200B;选项卡。

1. 使用&#x200B;**搜索列表**&#x200B;搜索字段来查找特定区段。

1. 选择要替换的一个或多个区段。

1. 从“替换为”下拉菜单中搜索一个或多个区段，以将区段添加到&#x200B;**[!UICONTROL 替换为]**&#x200B;列表。

1. 选择&#x200B;**[!UICONTROL 应用]**。

Report Builder会更新区段列表以反映替换情况。

## 从单元格定义数据块区段

数据块可以从单元格引用区段。 多个数据块可以引用区段的同一单元格，从而允许您一次为多个数据块轻松切换区段。

要从单元格应用区段，请执行以下操作：

1. [创建新数据块](create-a-data-block.md#create-a-data-block)或编辑现有数据块。
1. 选择&#x200B;**[!UICONTROL 区段]**&#x200B;选项卡以定义区段。
1. 选择![DataViewSelector](/help/assets/icons/DataViewSelector.svg)。

   ![从单元格中选择区段](assets/select-segment-from-cell.png){zoomable="yes"}

1. 选择要数据块从中引用区段的单元格。

1. 双击以向单元格添加区段。 或者，将一个或多个区段拖放到&#x200B;**[!UICONTROL 包括的区段]**&#x200B;部分中。

1. 选择&#x200B;**[!UICONTROL 应用]**&#x200B;以创建引用单元格。

1. 从&#x200B;**区段**&#x200B;选项卡，将新创建的引用单元格区段添加到数据块。

   显示Sheet1！J1(All Data)区段的![区段选项卡已添加到表中。](assets/segment-from-cell-applied.png){zoomable="yes"}

1. 选择&#x200B;**[!UICONTROL 完成]**。

要将引用单元格作为区段应用于其他数据块，请在&#x200B;**[!UICONTROL 表]**&#x200B;选项卡的&#x200B;**[!UICONTROL 区段]**&#x200B;列表中将该单元格引用用作区段之一。

### 使用引用单元格更改数据块区段

1. 选择电子表格中的引用单元格。

1. 在&#x200B;**[!UICONTROL 快速编辑]**&#x200B;菜单的&#x200B;**[!UICONTROL 单元格]**&#x200B;的区段下选择链接。

   单元格链接中的![段显示Sheet1！J1 （所有数据）](assets/select-segment-from-cell-in-sheet.png){zoomable="yes"}

1. 从下拉菜单中选择您的区段。

1. 选择&#x200B;**[!UICONTROL 应用]**。
