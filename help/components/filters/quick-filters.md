---
description: 在 Analysis Workspace for Customer Journey Analytics 中使用快速筛选器。
title: 快速筛选器
feature: CJA Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 17030d5ac3b488a6c628e6de7aab8b710e5c175a
workflow-type: tm+mt
source-wordcount: '1048'
ht-degree: 76%

---

# 快速筛选器

可在项目中创建快速筛选器以规避完整版[筛选器生成器](/help/components/filters/create-filters.md)的复杂操作。快速筛选器

* 应用为 [仅限项目的过滤器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/quick-filters.html#project-only).
* 允许有最多 3 条规则
* 不容纳嵌套容器或顺序规则。

要比较快速筛选器与完整的组件列表筛选器的作用，请转到[此处](/help/components/filters/filters-overview.md)。

以下是一个关于快速过滤器的视频（请注意，它改用术语“快速区段”。） 但是，功能是相同的。

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## 先决条件 {#prereqs}

任何人都可以创建快速过滤器。 但是，您需要在 [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html#analytics-tools) 以保存快速过滤器，或在过滤器生成器中将其打开。

## 创建快速筛选器 {#create}

在自由格式表中，单击面板标题中的筛选条件+ 图标：

![区段筛选器](assets/quick-seg1.png)

| 设置 | 描述 |
| --- | --- |
| [!UICONTROL 名称] | 筛选器的默认名称为该筛选器中的规则名称的组合。可以将筛选器重命名为更友好的名称。 |
| [!UICONTROL 包括/排除] | 可在筛选器定义中包括或排除组件，但不得既包括又排除。 |
| [!UICONTROL “点击”/“访问”/“访客”容器] | 快速筛选器仅包括一个[筛选器容器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html#filter-containers)，从中可在筛选器中包括（或从筛选器中排除）某个维度/指标/日期范围。[!UICONTROL 访客]包含访客在不同的访问和页面查看间专属的总体数据。通过[!UICONTROL 访问]容器可设置规则以根据访问划分访客的数据，而通过[!UICONTROL 点击]容器可根据个别页面查看划分访客信息。默认容器为[!UICONTROL 点击]。 |
| [!UICONTROL 组件] (Dimension/量度/日期范围) | 通过添加组件（维度、量度、日期范围或维度值）可定义最多 3 条规则。有 3 种方法可以找到正确的组件：<ul><li>只需开始打字，[!UICONTROL 快速筛选器生成器]即自动查找相应的组件。</li><li>使用下拉列表查找组件。</li><li>从左边栏中拖放组件。</li></ul> |
| [!UICONTROL 运算符] | 使用下拉菜单查找标准运算符和[!UICONTROL 非重复计数]运算符。请参阅[筛选器运算符](operators.md)。 |
| 加号 (+) | 添加另一条规则。 |
| AND/OR 限定符 | 可将“AND”或“OR”限定符添加到规则，但不得在单个筛选器定义中混用“AND”和“OR”。 |
| [!UICONTROL 应用] | 将此筛选器应用于面板。如果此筛选器不包含任何数据，则系统将询问您是否要继续。 |
| [!UICONTROL 打开生成器] | 打开筛选器生成器。在筛选器生成器中保存或应用筛选器后，即不再将它视为“快速筛选器”。它成为组件列表筛选器库的一部分。 |
| [!UICONTROL 取消] | 取消此快速筛选器 - 不要应用它。 |
| [!UICONTROL 日期范围] | 该验证器使用面板日期范围执行其数据查找。但在快速筛选器中应用的任何日期范围都将取代面板顶部的面板日期范围。 |
| 预览（右上角） | 让您查看您的筛选器是否有效以及该筛选器的作用范围。表示在应用此筛选器时预计将看到的数据集的划分方式。您可能会收到一条通知，表明此筛选器没有数据。在这种情况下，可继续操作或更改筛选器定义。 |

结合使用维度和量度的筛选器的示例如下：

![筛选器定义示例](assets/quick-seg2.png)

该筛选器显示在顶部。请注意它的蓝色条纹边栏，与左侧筛选器库中组件级筛选器的蓝色边栏不同。

![筛选器组件位置](assets/quick-seg3.png)

## 编辑快速筛选器 {#edit}

1. 将光标悬停在快速筛选器上并选择铅笔图标。
1. 编辑筛选器定义或筛选器名称。
1. 单击[!UICONTROL 应用]。

## 保存快速筛选器 {#save}

可选择在[!UICONTROL 快速筛选器生成器]中或[!UICONTROL 筛选器生成器]中保存快速筛选器。

>[!IMPORTANT]
>保存或应用筛选器后，在快速筛选器生成器中就无法再编辑它，而只能在常规的筛选器生成器中编辑它。

### 在快速筛选器生成器中保存 {#save2}

1. 应用快速筛选器后，将光标悬停在它上并选择信息（“i”）图标。
1. 单击&#x200B;**[!UICONTROL 使其对所有项目都可用，并将它添加到组件列表]**。
1. （可选）为筛选器重命名。
1. 单击&#x200B;**[!UICONTROL 保存]**。

请注意筛选器的边栏如何从蓝色条纹变为更浅的蓝色。它现在显示在左边栏中的组件列表中。

### 在筛选器生成器中保存 {#save3}

1. 将光标悬停在快速筛选器上并选择信息（“i”）图标。
1. 选择&#x200B;**[!UICONTROL 保存筛选器]**
1. 将名称保持不变或为筛选器重命名。

   返回工作区，并注意筛选器现在如何具有浅蓝色边栏。这表示在快速筛选器生成器中无法再编辑/打开它。通过保存它，它就成为组件列表的一部分。

   ![筛选器组件列表](assets/quick-seg4.png)

应用筛选器后，可选择将它添加到筛选器组件列表，并使其对所有项目都可用。

1. 将光标悬停在保存的筛选器上并选择铅笔图标。

1. 在筛选器生成器的顶部，注意此对话框：

   ![筛选器对话框](assets/project-only.png)

1. 选中&#x200B;**[!UICONTROL 使其对所有项目都可用，并添加到组件列表]**&#x200B;旁边的复选框。
1. 单击&#x200B;**[!UICONTROL 保存]**。
1. 所有项目的筛选器组件列表中现在都显示该筛选器。
1. 还可与组织中的其他人员[共享该筛选器](/help/components/filters/manage-filters.md)。

## 仅用于项目的筛选器是什么？ {#project-only}

仅限项目的过滤器是仅适用于在中创建这些项目的当前项目的过滤器。 它们在其他项目中不可用，并且无法共享给其他用户。 它们旨在快速探索数据，而无需在左边栏中创建和保存过滤器。 可以在面板拖放区域中使用快速过滤器或 [临时过滤器](/help/components/filters/ad-hoc-filters.md).

如果您在 [!UICONTROL 过滤器生成器]，则会显示仅限项目的通知。 如果未选中“使此过滤器可用……” 单击 **[!UICONTROL 应用]**，则该区段仍将保留为仅项目过滤器。

>[!NOTE]
>
>如果从过滤器生成器中应用快速过滤器，则该过滤器将无法再在 [!UICONTROL 快速过滤器生成器].

![“仅用于项目”未选中](assets/project-only-unchecked.png)

如果选中“使此过滤器可用……” 单击 **[!UICONTROL 保存]**，则左边栏组件列表中会提供该过滤器，以供在其他项目中使用。 也可以从过滤器管理器中与其他用户共享该功能。

![“仅用于项目”已选中](assets/project-only-checked.png)

