---
title: 如何在Report Builder中选择数据视图
description: 介绍如何选择数据视图
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
source-git-commit: 6ad244cd08d4984168cb37b4a9ad5db4943b9435
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 3%

---


# 选择数据视图

您可以从下拉列表中选择一个数据视图，或从单元格中选择一个数据视图，然后使用新的数据视图自动更新数据块。

**从单元格选择数据视图**

从单元格中选择数据视图，可以轻松地使用不同的数据视图刷新数据块。 如果贵组织在结构上具有多个彼此相似或相同的数据视图，则您可以使用从单元格中选择的数据视图来刷新数据块，而不是使用单独的数据块创建全新的报表。 如果您具有包含自定义组件和布局的复杂数据块格式，则此功能也会很有帮助。

要从单元格中选择数据视图，请先构建数据块，并将多个数据视图分配给数据块外的单元格。 然后，使用单元格面板中的数据视图从不同的数据视图刷新数据块。

1. 创建数据块。
有关创建数据块的信息，请参阅 [创建数据块](/help/report-builder/create-a-data-block.md).

1. 单击 *单元格图标* 在 *数据视图* 中。

   ![单元格图标](/help/report-builder/assets/cell-icon.png)

1. 选择一个单元格位置，以将数据视图添加到选定的单元格。

   您可能希望选择一个距离数据块单元格足够远的单元格，以便它们不会重叠。

1. 确认所选单元格位置。

1. 选择要分配给单元格的数据视图。

   ![单元格图标](/help/report-builder/assets/select-data-view.png)

1. 单击&#x200B;**应用**。

   完成数据块后，您可以使用与选定单元格不同的数据视图刷新数据块。

   **从单元格更改数据视图**

1. 单击您在步骤3中选择的数据视图单元格位置。

   此时会显示一个下拉菜单，其中列出了您之前在步骤5中选择的数据视图。

1. 从下拉列表中选择其他数据视图。

1. （可选） **选择刷新数据块** 更改时。

1. 单击&#x200B;**应用**。

   Report Builder使用选定的数据视图刷新数据块。
