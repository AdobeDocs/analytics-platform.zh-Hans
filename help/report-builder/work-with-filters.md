---
title: 如何在Report Builder中使用过滤器Customer Journey Analytics
description: 介绍如何在CJA的Report Builder中使用过滤器
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
source-git-commit: b655813816b2a8e0d47b035eefa11926f106ee0e
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%

---


# 在Report Builder中使用过滤器

在创建新数据块时或从“命令”面板中选择&#x200B;**编辑数据块**&#x200B;选项时，可以应用过滤器。

## 将过滤器应用于数据块

要将过滤器应用于整个数据块，请双击过滤器，或将组件列表中的过滤器拖放到表的过滤器部分。

## 将过滤器应用于单个量度

要将过滤器应用于单个量度，请将过滤器拖放到表中的某个量度上。 您还可以单击&#x200B;**...**&#x200B;图标，在“表”窗格中的量度右侧，然后选择&#x200B;**过滤器量度**。 要查看已应用的过滤器，请将鼠标悬停在“表”窗格中的某个量度上或选择该量度。 已应用过滤器的量度将显示过滤器图标。

<!-- ![](./assets/image24.png) -->

![](./assets/filter_by.png)

## 快速编辑过滤器

您可以使用“快速编辑”面板来添加、删除或替换现有数据块的过滤器。

选择电子表格中的单元格范围时，“快速编辑”面板中的&#x200B;**Filters**&#x200B;链接会显示该选择中数据块使用的过滤器的摘要列表。

使用“快速编辑”面板编辑过滤器

1. 从一个或多个数据块中选择单元格范围。

   ![](./assets/select_multiple_dbs.png)

1. 单击过滤器链接以启动快速编辑 — 过滤器面板。

   ![](./assets/quick_edit_filters.png)

### 添加或删除过滤器

您可以使用“添加/删除”选项添加或删除过滤器。

1. 在“快速编辑过滤器”面板中选择&#x200B;**Add/Remove**&#x200B;选项卡。

   应用于选定数据块的所有过滤器都列在“快速编辑过滤器”面板中。 应用于所选数据块的过滤器列在&#x200B;**应用于所有选定数据块**&#x200B;标题下。 应用于某些数据块（但并非所有数据块）的过滤器列在&#x200B;**应用于1个或多个选定数据块**&#x200B;标题下。

   当选定的数据块中存在多个过滤器时，您可以使用&#x200B;**Add Filter**&#x200B;搜索字段搜索特定过滤器。

   ![](./assets/add_filter.png)

1. 从&#x200B;**Add filter**&#x200B;下拉菜单中选择过滤器，以添加过滤器。

   可搜索过滤器列表包括所有可访问的过滤器，这些过滤器存在于一个或多个选定数据块中的数据视图中，以及组织中全局可用的所有过滤器。

   添加过滤器会将该过滤器应用到所选内容中的所有数据块。

1. 要删除过滤器，请在&#x200B;**已应用的过滤器**&#x200B;列表中单击过滤器右侧的删除图标&#x200B;**x**。

1. 单击&#x200B;**Apply**&#x200B;以保存更改并返回到集线器面板。

   Report Builder会显示一条消息，确认应用的过滤器更改。

### 替换过滤器

您可以将现有过滤器替换为其他过滤器，以更改数据的过滤方式。

1. 在“快速编辑过滤器”面板中，选择&#x200B;**Replace**&#x200B;选项卡。

   ![](./assets/replace_filter.png)

1. 使用&#x200B;**搜索列表**&#x200B;搜索字段查找特定过滤器。

1. 选择要替换的一个或多个过滤器。

1. 在替换为字段中搜索一个或多个过滤器。

   选择过滤器会将其添加到&#x200B;**替换为**...列表。

   ![](./assets/replace_screen_new.png)

1. 单击&#x200B;**应用**。

   Report Builder会更新过滤器列表以反映替换内容。