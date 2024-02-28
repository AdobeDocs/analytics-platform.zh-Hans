---
title: 组件设置
description: 查看数据视图组件的核心设置。
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: aa0a6715c216730e0768cfa870ea75f315455101
workflow-type: ht
source-wordcount: '491'
ht-degree: 100%

---

# 组件设置

以下信息描述了数据视图组件使用的设置。

![本节中描述的组件设置](../assets/component-settings.png)

| 设置 | 描述/用例 |
| --- | --- |
| [!UICONTROL 组件类型] | 必填。使您可将组件从“量度”变为“维度”或反之亦然。更改此下拉列表选择会将该组件移至其各自包括的组件区域。 |
| [!UICONTROL 组件名称] | 必填。使您可指定在分析工作区中显示的易记名称。可将组件重命名以给予其一个数据视图专属的名称。 |
| [!UICONTROL 描述] | 可选，但推荐。向其他用户提供有关组件的信息。 |
| [!UICONTROL 标记] | 可选。可让您使用自定义或现成标记为组件添加标签，以便于在分析工作区 UI 中搜索/筛选。 |
| [!UICONTROL 上下文标签] | 可选。可应用于组件的现有系统定义标签的下拉列表。可能需要这些标签来定义用于在 Analysis 工作区项目或面板中报告的一组组件。 |
| [!UICONTROL 架构字段名] | 架构字段的名称。 |
| [!UICONTROL 数据集类型] | 必填。显示组件来自哪个数据集类型（事件、查询或个人资料）的不可编辑字段。 |
| [!UICONTROL 数据集] | 一个不可编辑的字段，它显示该组件来源于哪个数据集。此字段可以包含多个数据集。 |
| [!UICONTROL 架构类型] | 一个不可编辑的字段，它显示该组件的数据类型。虽然您可以在 Platform 中使用任何受支持的架构字段类型，但 Customer Journey Analytics 并非支持所有字段类型。支持的数据类型有：`Integer`、`Int`、`Long`、`Double`、`Float`、`Number`、`Short`、`Byte`、`String` 和 `Boolean`。目前在查找数据集中仅允许有 `String` 架构数据类型。 |
| [!UICONTROL 组件 ID] | 必填。[Customer Journey Analytics API](https://adobe.io/cja-apis/docs) 使用此字段来引用组件。数据视图中的每个组件都必须是唯一的。Adobe 自动为每个组件生成一个 ID；但是，您可以单击编辑图标并修改组件 ID。更改组件 ID 将破坏所有包含此组件的现有工作区项目。虽然每个组件在单个数据视图中都需要唯一的 ID，但可在其他数据视图中使用相同的组件 ID。如果在其他数据视图中使用相同的组件 ID，则可让 Workspace 项目在数据视图间保持兼容。<br/>对于基于配置文件和查找功能的组件，组件 ID 具有基于数据集 ID 的 ID 前缀（例如： `642b28fcc1f0ee1c074265a0.person.name.firstName`）。当您想重用基于配置文件或查找功能的组件时（如 `person.name.firstName`），并在不同的数据视图中配置该组件时，请确保在数据视图中对组件 ID 的重命名是唯一的（例如：`myUniqueID.person.name.firstName`）。 |
| [!UICONTROL 路径] | 必需。显示组件来自的架构路径的不可编辑字段。 |
| [!UICONTROL 数据使用情况标签] | 在 Adobe Experience Platform 中分配给此组件的任何数据使用标签。[了解详情](/help/data-views/data-governance.md)。 |
| [!UICONTROL 在报告中隐藏组件] | 使您可从非管理员的数据视图策划该组件。管理员仍可通过在分析工作区项目中单击[!UICONTROL 显示所有组件]而访问该组件。 |

{style="table-layout:auto"}

以下是关于数据视图中组件设置的视频：

>[!VIDEO](https://video.tv.adobe.com/v/333112/?quality=12)
