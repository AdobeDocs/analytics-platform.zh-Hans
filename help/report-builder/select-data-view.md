---
title: 如何在Report Builder中选择数据视图
description: 介绍如何在Adobe Report Builder中选择数据视图
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 802a8f0b-10c2-4adc-a4ec-25f3d28f3002
source-git-commit: f09dffe3d134c423b69f6ca75337f3aca3f51410
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 3%

---

# 选择数据视图

您可以从下拉列表中选择数据视图，或从单元格中选择数据视图，然后使用新的数据视图自动更新数据块。

**从单元格选择数据视图**

从单元格中选择数据视图，可以轻松地使用不同的数据视图刷新数据块。 如果您的组织有多个数据视图，它们在结构上彼此相似或相同，您便可以使用从单元格中选择的数据视图刷新数据块，而不是使用单独的数据块创建全新的报表。 如果您拥有包含自定义组件和布局的复杂数据块格式，这也很有用。

要从单元格中选择数据视图，请首先构建一个数据块，并将多个数据视图分配给数据块外的单元格。 然后，使用单元格中的数据视图面板从不同的数据视图刷新数据块。

1. 创建数据块。
有关创建数据块的信息，请参见 [创建数据块](/help/report-builder/create-a-data-block.md).

1. 单击 *单元格图标* 在 *数据视图* 部分。

   ![单元格图标](/help/report-builder/assets/cell-icon.png)

1. 选择单元格位置以将数据视图添加到所选单元格。

   您可能希望选择一个距离数据块单元格足够远的单元格，以便它们不会重叠。

1. 确认选定的单元格位置。

1. 选择要分配给单元格的数据视图。

   ![单元格图标](/help/report-builder/assets/select-data-view.png)

1. 单击&#x200B;**应用**。

   完成数据块后，可以使用选定单元格中的其他数据视图刷新数据块。

   **更改单元格中的数据视图**

1. 单击您在步骤3中选择的数据视图单元格位置。

   此时会显示一个下拉菜单，其中列出了您之前在步骤5中选择的数据视图。

1. 从下拉列表中选择其他数据视图。

1. （可选） **选择刷新数据块** 更改时。

1. 单击&#x200B;**应用**。

   Report Builder会使用选定的数据视图刷新数据块。
