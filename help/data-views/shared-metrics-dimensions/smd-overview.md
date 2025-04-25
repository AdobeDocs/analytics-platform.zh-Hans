---
title: 共享量度和维度概述
description: 在多个数据视图中使用相同的维度或量度引用。
source-git-commit: 263767028893d9b04e5c8f8ae067b3e6283e4053
workflow-type: tm+mt
source-wordcount: '1245'
ht-degree: 0%

---

# 共享量度和维度概述

共享量度和维度提供了一个管理可用于任意数量数据视图的维度和量度的中心位置。 这些组件对于使用多个数据视图的组织特别有用，尤其是当这些数据视图共享通用组件设置时。 对共享量度和维度所做的更改会立即应用于它共享到的每个数据视图。 在编辑单个数据视图时，共享维度和量度可通过组件名称旁边的![共享组件图标](/help/assets/icons/CCLibrary.svg)图标来标识。

虽然共享维度和量度允许跨多个数据视图使用通用组件，但它们不能跨连接共享。

## 工作流

大多数组织都使用以下总体工作流来随时间推移删除重复维度和量度并维护它们：

1. 从每个数据视图导入可能在多个数据视图之间共享的组件。 如果多个数据视图中存在相同的维度或量度，Adobe建议导入该组件的所有实例。 虽然此最佳实践会导入重复项，但也会导入这些重复项，以便可以对这些重复项进行重复数据删除并保留其对Workspace项目的引用。
1. 查看使用相同组件ID但具有不同组件设置的所有组件。 对于每个重复组件组，选择所需的组件设置，以将其应用于共享该组件ID的所有其他组件。
1. 查看使用相同组件ID并具有相同组件设置的所有组件。 可以轻松安全地合并这些维度或量度。

## [!UICONTROL 共享量度和维度]管理器

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 数据视图]** > **[!UICONTROL 共享的量度和维度]**

导航到此UI会显示当前可在多个数据视图之间共享的所有维度和量度。 右上角包含两个按钮，用于将组件添加到此界面：

* **[!UICONTROL 导入]**：打开一个模式窗口，允许您选择数据视图，然后允许您选择可用于共享的组件。
* **[!UICONTROL 新建]**：打开[共享组件编辑器](shared-component-editor.md)。

在这两个按钮的正下方，会显示四个概述卡片：

![概览卡片预览](assets/overview-cards.png)

* **个量度**：此连接的数据视图之间可共享的量度总数。 每个连接最多可包含10,000个共享量度。
* **维度**：此连接中可在数据视图之间共享的维度总数。 每个连接最多可包含10,000个共享维度。
* **要审阅的重复组件**：跨多个数据视图导入组件时，某些维度或量度可能会共享相同的组件ID。 此概述信息卡中的数字显示具有相同组件ID但不同组件设置的组件总数。 选择&#x200B;**[!UICONTROL 审阅]**&#x200B;将启用一个筛选器，通过该筛选器可选择所需的组件，以作为具有相同ID的所有其他组件的真实来源。
* **可用于合并的组件**：如果某个维度或量度共享相同的组件ID和相同的组件设置，则它们实际上相同，并且已准备好进行重复数据删除。 选择&#x200B;**[!UICONTROL 审核]**&#x200B;将启用一个过滤器，通过该过滤器可以将具有相同组件ID的所有组件合并到一个共享维度或量度中。

所有共享维度和量度都显示在四个概述卡片的下方。

![可用维度和量度预览](assets/shared-metrics-dimensions.png)

* **筛选器**：选择![筛选器图标](../../assets/icons/Filter.svg)图标以显示或隐藏可用的筛选器。 可用过滤器如下：
   * **[!UICONTROL 组件类型]**：仅查看维度或仅查看量度。
   * **[!UICONTROL 数据集]**：仅查看数据集包含在某个组件共享到的数据视图中的组件。
   * **[!UICONTROL 数据视图]**：仅查看共享到该数据视图的组件。
   * **[!UICONTROL 创建者]**：仅查看给定用户创建的组件。
   * **[!UICONTROL 重复]**：仅查看与另一个组件具有相同组件ID的组件。 这些筛选器与通过概述卡片查看组件相同。
* **搜索**：使用![搜索图标](../../assets/icons/Search.svg)图标按名称搜索组件。
* **[!UICONTROL 连接]**：更改[连接](/help/connections/overview.md)的下拉列表。 共享维度和量度始终特定于单个连接。
* **[!UICONTROL 自定义表]**：选择![自定义表图标](/help/assets/icons/ColumnSetting.svg)图标以显示或隐藏表中的列。 可用选项包括：
   * **[!UICONTROL 字段名]**：共享维度或量度的名称。 此字段始终可见。
   * **[!UICONTROL 类型]**：指示组件是维度还是量度。 此字段始终可见。
   * **[!UICONTROL 数据集类型]**：数据集的类型。 大多数数据集是事件数据集。
   * **[!UICONTROL 共享到数据视图]**：此组件共享到的所有数据视图。 此字段始终可见。 选择链接可打开一个模式窗口，其中列出了此组件可用的所有数据视图。
   * **[!UICONTROL 数据集]**：此组件共享到的每个数据视图中包含的所有数据集。 选择链接可打开一个模式窗口，其中列出了组件的所有数据集。
   * **[!UICONTROL 创建者]**：创建组件或将组件导入共享量度和维度界面的人员的姓名。
   * **[!UICONTROL 架构类型]**：存储数据的格式。 示例包括`string`、`double`或`boolean`。
   * **[!UICONTROL 组件ID]**：维度或量度的组件ID。 必须查看此界面中共享相同组件ID的任何组件并为其去重。
   * **[!UICONTROL 架构]**：维度或量度的架构路径。 例如，`web.webPageDetails.URL`。
   * **[!UICONTROL 描述]**：组件的[描述](/help/data-views/component-settings/overview.md)。
   * **[!UICONTROL 上下文标签]**：组件的[上下文标签](/help/data-views/component-settings/overview.md)。
   * **[!UICONTROL 包含/排除值]**：列出[包含/排除值](/help/data-views/component-settings/include-exclude-values.md)下指定的规则数。
   * **[!UICONTROL 数据使用标签]**：架构字段的[数据使用标签](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview)。
   * **[!UICONTROL 已弃用]**：指示是否设置了已弃用的标志。
   * **[!UICONTROL 格式]**：值显示的格式。 布尔值通常显示为`True | False`，量度通常显示为`Decimal`等。
   * **[!UICONTROL 指标去重]**：组件的[指标去重](/help/data-views/component-settings/metric-deduplication.md)设置。
   * **[!UICONTROL 行为]**：组件的[行为](/help/data-views/component-settings/behavior.md)设置。
   * **[!UICONTROL 归因]**：组件的[归因](/help/data-views/component-settings/attribution.md)设置。
   * **[!UICONTROL 无值选项]**：组件的[无值选项](/help/data-views/component-settings/no-value-options.md)。
   * **[!UICONTROL 值分段]**：组件的[值分段](/help/data-views/component-settings/value-bucketing.md)设置。
   * **[!UICONTROL 持久性]**：组件的[持久性](/help/data-views/component-settings/persistence.md)设置。
   * **[!UICONTROL 小写]**：指示组件是否已根据组件的[行为](/help/data-views/component-settings/behavior.md)设置启用小写。
   * **[!UICONTROL 子字符串]**：组件的[子字符串](/help/data-views/component-settings/substring.md)设置。
   * **[!UICONTROL 摘要数据组]**：组件的[摘要数据组](/help/data-views/component-settings/summary-data-group.md)设置。
   * **[!UICONTROL 创建日期]**：创建或导入组件的日期。
   * **[!UICONTROL 上次修改时间]**：如果组件在创建后已修改，则为上次修改该组件的日期。
* **[!UICONTROL 作业历史记录]**：选择![历史记录图标](/help/assets/icons/History.svg)图标以打开一个模式窗口，其中显示从单个数据视图导入维度和量度的所有实例。

## 编辑组件或将组件共享到数据视图

使用组件旁边的复选框可显示您可以执行的所有可用操作。 支持多种选择。

![可用操作预览](assets/smd-actions.png)

* ![铅笔图标](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**：在[共享组件编辑器](shared-component-editor.md)中打开选定的维度和量度，您可以调整其[组件设置](/help/data-views/component-settings/overview.md)。 选择要编辑的多个组件时，它们将在组件编辑器中打开。 在组件编辑器中，您可以按住Shift并单击“组件”来编辑多个组件的相同字段。
* ![共享图标](/help/assets/icons/Share.svg) **[!UICONTROL 共享到数据视图]**：打开一个窗口，其中显示所选连接中所有可用的数据视图。 选中要使其成为可用组件的每个数据视图的复选框，然后选择&#x200B;**[!UICONTROL 共享]**。
* ![取消共享图标](/help/assets/icons/SaveTo.svg) **[!UICONTROL 取消共享到数据视图]**：打开一个窗口，其中显示该组件当前共享的所有数据视图。 选中要删除此组件可用性的每个数据视图的复选框，然后选择&#x200B;**[!UICONTROL 取消共享]**。
* ![复制图标](/help/assets/icons/Copy.svg) **[!UICONTROL 复制]**：创建选定组件的副本。 将为重复的组件生成新的组件ID。
* ![删除图标](/help/assets/icons/Delete.svg) **[!UICONTROL 删除]**：从界面中删除选定的组件。 如果选定组件与任何数据视图共享，则它们将被取消共享。
