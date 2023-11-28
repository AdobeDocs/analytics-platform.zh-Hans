---
title: 如何在Report Builder中选择数据视图
description: 介绍如何在Adobe Report Builder中选择数据视图
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: bf765144-34f8-465b-b06d-53e4ca91014a
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 3%

---

# 选择数据视图

您可以从下拉列表中选择数据视图，或从单元格中选择数据视图，然后使用新的数据视图自动更新数据块。

**从单元格选择数据视图**

从单元格中选择数据视图，可以轻松地使用不同的数据视图刷新数据块。 如果您的组织有多个数据视图在结构上彼此相似或相同，那么您可以使用从单元格中选择的数据视图刷新数据块，而不是使用单独的数据块创建全新的报表。 如果您拥有包含自定义组件和布局的复杂数据块格式，这也很有用。

要从单元格中选择数据视图，请先构建一个数据块，并将多个数据视图分配给数据块外部的单元格。 然后，使用单元格面板中的数据视图从不同的数据视图刷新数据块。

1. 创建数据块。
有关创建数据块的信息，请参见 [创建数据块](/help/report-builder/create-a-data-block.md).

1. 单击 *单元格图标* 在 *数据视图* 部分。

   ![创建单元格图标高亮显示的新数据块窗口。](/help/report-builder/assets/cell-icon.png)

1. 选择单元格位置以将数据视图添加到所选单元格。

   您可能希望选择一个距离数据块单元格足够远的单元格，以便它们不会重叠。

1. 确认所选的单元格位置。

1. 选择要分配给单元格的数据视图。

   ![显示“选择数据”视图的“Report Builder快速编辑”窗格。](/help/report-builder/assets/select-data-view.png)

1. 单击&#x200B;**应用**。

   完成数据块后，可以使用与选定单元格不同的数据视图刷新数据块。

   **更改单元格中的数据视图**

1. 单击您在步骤3中选择的数据视图单元格位置。

   此时会显示一个下拉菜单，其中列出了您之前在步骤5中选择的数据视图。

1. 从下拉列表中选择其他数据视图。

1. （可选） **选择刷新数据块** 发生更改时。

1. 单击&#x200B;**应用**。

   Report Builder使用选定的数据视图刷新数据块。
