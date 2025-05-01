---
title: 如何在Report Builder中选择数据视图
description: 介绍如何在Adobe Report Builder中选择数据视图
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: bf765144-34f8-465b-b06d-53e4ca91014a
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 1%

---

# 选择数据视图

您可以从下拉菜单中选择数据视图，或从单元格中选择数据视图，并使用新的数据视图自动更新数据块。

## 从单元格选择数据视图

从单元格中选择数据视图，可以轻松地使用不同的数据视图刷新数据块。 您可以使用从单元格中选择的数据视图刷新数据块，而不是使用单独的数据块创建全新的报表。

在以下情况下，从单元格中选择数据视图会很有帮助：

* 结构相似或相同的多个数据视图。
* 包含自定义组件和布局的复杂数据块格式。

要从单元格中选择数据视图，请先构建一个数据块，并将多个数据视图分配给数据块外部的单元格。 然后，使用单元格&#x200B;]**中的**[!UICONTROL &#x200B;数据视图面板从不同的数据视图刷新数据块。

1. 创建数据块。 有关创建数据块的信息，请参阅[创建数据块](/help/report-builder/create-a-data-block.md)。

1. 在&#x200B;**[!UICONTROL 数据视图]**&#x200B;中选择![数据视图选择器](/help/assets/icons/DataViewSelector.svg)。

1. 使用数据块外部的![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg)选择单元格。

1. 使用拖放从&#x200B;**[!UICONTROL 选择要从单元格]**&#x200B;添加到数据视图的数据视图中添加一个或多个数据视图。 或者，也可以双击数据视图，将该数据视图添加到&#x200B;**[!UICONTROL 包含的数据视图]**&#x200B;列表。

   * 您可以使用![搜索](/help/assets/icons/Search.svg) **[!UICONTROL _选择数据视图_]**&#x200B;来搜索数据视图。
   * 使用![MoreSmall](/help/assets/icons/MoreSmall.svg)打开上下文菜单，以便在&#x200B;**[!UICONTROL 包含的数据视图]**&#x200B;列表中上下移动数据视图。
   * 使用![CrossSize75](/help/assets/icons/CrossSize75.svg)从&#x200B;**[!UICONTROL 包含的数据视图]**&#x200B;列表中删除数据视图。

   ![从单元格中选择数据视图](assets/dataviews-from-a-cell.png){zoomable="yes"}

1. 选择&#x200B;**[!UICONTROL 应用]**&#x200B;将所选数据视图应用到所选单元格。


## 更改单元格中的数据视图

1. 选择工作表中的数据视图单元格位置。
1. 在Report Builder中心中，在&#x200B;**[!UICONTROL 快速编辑]**&#x200B;中选择&#x200B;**[!UICONTROL 单元格]**&#x200B;中的数据视图链接。
1. 从&#x200B;**[!UICONTROL 数据视图]**&#x200B;下拉菜单中选择一个数据视图。

   ![从单元格更改数据视图](assets/change-data-view-from-cell.png){zoomable="yes"}
1. 可选，选择&#x200B;**[!UICONTROL 更改时刷新数据块]**。

1. 选择&#x200B;**[!UICONTROL 应用]**。Report Builder会根据选定的数据视图刷新数据块。
