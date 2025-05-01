---
title: 组件设置
description: 查看数据视图组件的核心设置。
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 97%

---

# 组件设置 {#component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_settings"
>title="组件设置"
>abstract="查看和配置名称、描述以及其他与组件相关的设置。选中此框可以在报告中对非管理员用户隐藏此组件。管理员仍可通过在 Workspace 项目中选择&#x200B;**[!UICONTROL 显示所有组件]**&#x200B;来访问该组件。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_contextlabels"
>title="上下文标签"
>abstract="移除上下文标签可能会影响需要该组件的特定面板或报告。"

<!-- markdownlint-enable MD034 -->


以下信息描述了数据视图组件使用的设置。

![本节中描述的组件设置](../assets/component-settings.png)

| 设置 | 描述/用例 |
| --- | --- |
| [!UICONTROL 组件类型] | 必填。使您可将组件从“量度”变为“维度”或反之亦然。更改此下拉列表选择会将该组件移至其各自包括的组件区域。 |
| [!UICONTROL 组件名称] | 必填。使您可指定在 Analysis Workspace 中显示的易记名称。可将组件重命名以给予其一个数据视图专属的名称。 |
| [!UICONTROL 描述] | 可选，但推荐。向其他用户提供有关组件的信息。 |
| [!UICONTROL 标记] | 可选。可让您使用自定义或现成标记为组件添加标记，以便于在 Analysis Workspace UI 中搜索/筛选。 |
| [!UICONTROL 上下文标签] | 可选。可应用于组件的可用系统定义标签的下拉菜单。 <p>以下情况下可能需要这些标签：</p> <ul><li>使用 Analysis Workspace 项目中的[“试验”面板](/help/analysis-workspace/c-panels/experimentation.md)，定义一组可用于试验报告的组件。<p>请参阅[与 Journey Optimizer 集成](/help/integrations/ajo.md#data-view)以及[ Target 报告](/help/integrations/at.md)。</p></li><li>使用 Adobe 提供的模板时。默认情况下，Adobe 提供的一些模板不起作用，因为它们包含数据视图中没有的组件。<p>对于每个缺失的组件，数据视图中都会提供一个匹配的上下文标签。您需要将匹配的上下文标签添加到数据视图中已有的组件，或者向数据视图添加新组件并向其中添加上下文标签。</p><p>有关详细信息，请参阅文章[创建和管理模板](/help/analysis-workspace/templates/create-templates.md)中的[将缺失的组件添加到给定模板的数据视图](/help/analysis-workspace/templates/create-templates.md#add-missing-components-to-the-data-view-for-a-given-template)。</p> |
| [!UICONTROL 架构字段名] | 架构字段的名称。 |
| [!UICONTROL 数据集类型] | 必填。显示组件来自哪个数据集类型（事件、查询或轮廓）的不可编辑字段。 |
| [!UICONTROL 数据集] | 一个不可编辑的字段，它显示该组件来源于哪个数据集。此字段可以包含多个数据集。 |
| [!UICONTROL 架构类型] | 一个不可编辑的字段，它显示该组件的数据类型。虽然您可以在 Platform 中使用任何受支持的架构字段类型，但 Customer Journey Analytics 并非支持所有字段类型。支持的数据类型有：`Integer`、`Int`、`Long`、`Double`、`Float`、`Number`、`Short`、`Byte`、`String` 和 `Boolean`。目前在查找数据集中仅允许有 `String` 架构数据类型。 |
| [!UICONTROL 组件 ID] | 必填。[Customer Journey Analytics API](https://adobe.io/cja-apis/docs) 使用此字段来引用组件。数据视图中的每个组件都必须是唯一的。Adobe 自动为每个组件生成一个 ID；但是，您可以单击编辑图标并修改组件 ID。更改组件 ID 将破坏所有包含此组件的现有 Workspace 项目。虽然每个组件在单个数据视图中都需要唯一的 ID，但可在其他数据视图中使用相同的组件 ID。如果在其他数据视图中使用相同的组件 ID，则可让 Workspace 项目在数据视图间保持兼容。<br/>对于基于轮廓和查找功能的组件，组件 ID 具有基于数据集 ID 的 ID 前缀（例如： `642b28fcc1f0ee1c074265a0.person.name.firstName`）。当您想重用基于轮廓或查找功能的组件时（如 `person.name.firstName`），并在不同的数据视图中配置该组件时，请确保在数据视图中对组件 ID 的重命名是唯一的（例如：`myUniqueID.person.name.firstName`）。 |
| [!UICONTROL 路径] | 必需。显示组件来自的架构路径的不可编辑字段。 |
| [!UICONTROL 数据使用情况标签] | 在 Adobe Experience Platform 中分配给此组件的任何数据使用标签。[了解详情](/help/data-views/data-governance.md)。 |
| [!UICONTROL 在报告中隐藏组件] | 使您可从非管理员的数据视图策划该组件。管理员仍可通过在 Analysis Workspace 项目中单击[!UICONTROL 显示所有组件]而访问该组件。 |

{style="table-layout:auto"}



>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [组件类型设置](https://video.tv.adobe.com/v/333112/?quality=12&learn=on){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]


