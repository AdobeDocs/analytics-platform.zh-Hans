---
description: 在 Analysis Workspace for Customer Journey Analytics 中使用快速过滤器。
title: 快速过滤器
feature: CJA Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 17030d5ac3b488a6c628e6de7aab8b710e5c175a
workflow-type: ht
source-wordcount: '1048'
ht-degree: 100%

---

# 快速过滤器

可在项目中创建快速过滤器以规避完整版[过滤器生成器](/help/components/filters/create-filters.md)的复杂操作。快速过滤器

* 作为 [仅用于项目的过滤器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/quick-filters.html#project-only) 应用。
* 允许有最多 3 条规则
* 不容纳嵌套容器或顺序规则。

要比较快速过滤器与完整的组件列表过滤器的作用，请转到[此处](/help/components/filters/filters-overview.md)。

这是一段关于快速过滤器的视频（请注意，它使用了术语“快速片段”。） 但是，功能是相同的。

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## 先决条件 {#prereqs}

任何人都可以创建快速过滤器。 不过，您需要具有 [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html#analytics-tools) 中的过滤器创建权限才能在过滤器生成器中保存或打开快速过滤器。

## 创建快速过滤器 {#create}

在自由格式表中，单击面板标题中的筛选条件+ 图标：

![区段过滤器](assets/quick-seg1.png)

| 设置 | 描述 |
| --- | --- |
| [!UICONTROL 名称] | 过滤器的默认名称为该过滤器中的规则名称的组合。 可以将过滤器重命名为更友好的名称。 |
| [!UICONTROL 包括/排除] | 可在过滤器定义中包括或排除组件，但不得既包括又排除。 |
| [!UICONTROL “点击”/“访问”/“访客”容器] | 快速过滤器仅包括一个[过滤器容器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html#filter-containers)，从中可在过滤器中包括（或从过滤器中排除）某个维度/指标/日期范围。[!UICONTROL 访客]包含访客在不同的访问和页面查看间专属的总体数据。通过[!UICONTROL 访问]容器可设置规则以根据访问划分访客的数据，而通过[!UICONTROL 点击]容器可根据个别页面查看划分访客信息。默认容器为[!UICONTROL 点击]。 |
| [!UICONTROL 组件]（维度/量度/日期范围） | 通过添加组件（维度、量度、日期范围或维度值）可定义最多 3 条规则。有 3 种方法可以找到正确的组件：<ul><li>只需开始打字，[!UICONTROL 快速过滤器生成器]即自动查找相应的组件。</li><li>使用下拉列表查找组件。</li><li>从左边栏中拖放组件。</li></ul> |
| [!UICONTROL 运算符] | 使用下拉菜单查找标准运算符和[!UICONTROL 非重复计数]运算符。请参阅[过滤器运算符](operators.md)。 |
| 加号 (+) | 添加另一条规则。 |
| AND/OR 限定符 | 可将“AND”或“OR”限定符添加到规则，但不得在单个过滤器定义中混用“AND”和“OR”。 |
| [!UICONTROL 应用] | 将此过滤器应用于面板。如果此过滤器不包含任何数据，则系统将询问您是否要继续。 |
| [!UICONTROL 打开生成器] | 打开过滤器生成器。 在过滤器生成器中保存或应用过滤器后，即不再将它视为“快速过滤器”。它成为组件列表过滤器库的一部分。 |
| [!UICONTROL 取消] | 取消此快速过滤器 - 不要应用它。 |
| [!UICONTROL 日期范围] | 该验证器使用面板日期范围执行其数据查找。但在快速过滤器中应用的任何日期范围都将取代面板顶部的面板日期范围。 |
| 预览（右上角） | 让您查看您的过滤器是否有效以及该过滤器的作用范围。 表示在应用此过滤器时预计将看到的数据集的划分方式。您可能会收到一条通知，表明此过滤器没有数据。在这种情况下，可继续操作或更改过滤器定义。 |

结合使用维度和量度的过滤器的示例如下：

![过滤器定义示例](assets/quick-seg2.png)

该过滤器显示在顶部。请注意它的蓝色条纹边栏，与左侧过滤器库中组件级过滤器的蓝色边栏不同。

![过滤器组件位置](assets/quick-seg3.png)

## 编辑快速过滤器 {#edit}

1. 将光标悬停在快速过滤器上并选择铅笔图标。
1. 编辑过滤器定义或过滤器名称。
1. 单击[!UICONTROL 应用]。

## 保存快速过滤器 {#save}

可选择在[!UICONTROL 快速过滤器生成器]中或[!UICONTROL 过滤器生成器]中保存快速过滤器。

>[!IMPORTANT]
>保存或应用过滤器后，在快速过滤器生成器中就无法再编辑它，而只能在常规的过滤器生成器中编辑它。

### 在快速过滤器生成器中保存 {#save2}

1. 应用快速过滤器后，将光标悬停在它上并选择信息（“i”）图标。
1. 单击&#x200B;**[!UICONTROL 使其对所有项目都可用，并将它添加到组件列表]**。
1. （可选）为过滤器重命名。
1. 单击&#x200B;**[!UICONTROL 保存]**。

请注意过滤器的边栏如何从蓝色条纹变为更浅的蓝色。它现在显示在左边栏中的组件列表中。

### 在过滤器生成器中保存 {#save3}

1. 将光标悬停在快速过滤器上并选择信息（“i”）图标。
1. 选择&#x200B;**[!UICONTROL 保存过滤器]**
1. 将名称保持不变或为过滤器重命名。

   返回工作区，并注意过滤器现在如何具有浅蓝色边栏。这表示在快速过滤器生成器中无法再编辑/打开它。通过保存它，它就成为组件列表的一部分。

   ![过滤器组件列表](assets/quick-seg4.png)

应用过滤器后，可选择将它添加到过滤器组件列表，并使其对所有项目都可用。

1. 将光标悬停在保存的过滤器上并选择铅笔图标。

1. 在过滤器生成器的顶部，注意此对话框：

   ![过滤器对话框](assets/project-only.png)

1. 选中&#x200B;**[!UICONTROL 使其对所有项目都可用，并添加到组件列表]**&#x200B;旁边的复选框。
1. 单击&#x200B;**[!UICONTROL 保存]**。
1. 所有项目的过滤器组件列表中现在都显示该过滤器。
1. 还可与组织中的其他人员[共享该过滤器](/help/components/filters/manage-filters.md)。

## 仅用于项目的过滤器是什么？ {#project-only}

仅用于项目的过滤器是指只适用于其所在当前项目的过滤器。此类过滤器在其他项目中不可用，无法共享给其他用户。 它们用于快速浏览数据，且无需在左边栏中创建和保存数据过滤器。 可以在面板拖放区域中使用快速过滤器或[临时过滤器](/help/components/filters/ad-hoc-filters.md)创建仅用于项目的过滤器。

如果在[!UICONTROL 过滤器生成器]中打开了仅用于项目过滤器，则会显示“仅用于项目”通知。 如果不选中“使此过滤器可用…” 且不点击 **[!UICONTROL 应用]**，则该区段仍然是仅用于项目的过滤器。

>[!NOTE]
>
>注意：如果从过滤器生成器应用快速过滤器，则无法再在 [!UICONTROL 快速过滤器生成器] 中打开它。

![“仅用于项目”未选中](assets/project-only-unchecked.png)

如果选中“使此过滤器可用…” 并点击 **[!UICONTROL 保存]**，则该过滤器在左边栏组件列表中可用于其他项目。还可以从过滤器管理器与其他用户共享。

![“仅用于项目”已选中](assets/project-only-checked.png)

