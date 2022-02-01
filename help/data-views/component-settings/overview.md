---
title: 组件设置
description: 查看数据视图组件的核心设置。
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 95%

---

# 组件设置

数据视图组件使用的核心设置。

![组件设置](../assets/component-settings.png)

| 设置 | 描述/用例 |
| --- | --- |
| [!UICONTROL 组件类型] | 必填。使您可将组件从“指标”变为“维度”或反之。更改此下拉列表会将该组件移至其各自包括的组件区域。 |
| [!UICONTROL 组件名称] | 必填。使您可指定在 Analysis Workspace 中显示的易记名称。可将组件重命名以给予其一个数据视图专属的名称。 |
| [!UICONTROL 描述] | 可选，但推荐。向其他用户提供有关组件的信息。 |
| [!UICONTROL 标记] | 可选。可让您使用自定义或现成标记为组件添加标签，以便于在 Analysis Workspace UI 中搜索/筛选。 |
| [!UICONTROL 字段名称] | 架构字段的名称。 |
| [!UICONTROL 数据集类型] | 必填。显示组件来自哪个数据集类型（事件、查询或个人资料）的不可编辑字段。 |
| [!UICONTROL 数据集] | 一个不可编辑的字段，它显示该组件来源于哪个数据集。此字段可以包含多个数据集。 |
| [!UICONTROL 架构数据类型] | 一个不可编辑的字段，它显示该组件的数据类型。虽然您可以在 Platform 中使用任何受支持的架构字段类型，但 CJA 并非支持所有字段类型。支持的数据类型有：`Integer`、`Int`、`Long`、`Double`、`Float`、`Number`、`Short`、`Byte`、`String` 和 `Boolean`。目前在查找数据集中仅允许有 `String` 架构数据类型。 |
| [!UICONTROL 组件 ID] | 必填。[CJA API](https://adobe.io/cja-apis/docs) 使用此字段引用组件。数据视图中的每个组件都必须是唯一的。Adobe 自动为每个组件生成一个 ID；但是，您可以单击编辑图标并修改组件 ID。更改组件 ID 将破坏所有包含此组件的现有工作区项目。虽然每个组件在单个数据视图中都需要唯一的 ID，但可在其他数据视图中使用相同的组件 ID。如果在其他数据视图中使用相同的组件 ID，则可让工作区项目在数据视图间保持兼容。 |
| [!UICONTROL 架构路径] | 必填。显示组件来自的架构路径的不可编辑字段。 |
| [!UICONTROL 在报告中隐藏组件] | 使您可从非管理员的数据视图策划该组件。管理员仍可通过在 Analysis Workspace 项目中单击[!UICONTROL 显示所有组件]而访问该组件。 |
