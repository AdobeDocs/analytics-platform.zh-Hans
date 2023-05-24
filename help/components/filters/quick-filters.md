---
description: 在 Analysis Workspace for Customer Journey Analytics 中使用快速过滤器。
title: 快速过滤器
feature: CJA Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 37%

---

# 快速过滤器

利用快速筛选器，可轻松浏览给定项目中的数据，而无需在中创建更复杂的组件列表筛选器。 [筛选器生成器](/help/components/filters/create-filters.md).

创建快速过滤器时，请考虑以下事项：

* 快速筛选器仅适用于创建它们的项目。 此类过滤器在其他项目中不可用，无法共享给其他用户。 
* 最多允许3个规则。
* 不支持嵌套容器或顺序规则。

以下视频演示了如何使用快速滤镜。 (注意：本视频使用术语“快速区段”而不是“快速过滤器”。 但是，功能是相同的。)

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## 创建快速过滤器 {#create}

Analysis Workspace中的任何用户都可以创建快速过滤器。

要创建快速过滤器，请执行以下操作：

1. 选择以下方法之一开始创建快速过滤器：

   * **临时（拖放）：** 从左边栏中，将组件拖到旁边的拖放区域 **筛选条件** 图标，然后选择 **编辑** 图标来调整过滤器。

      ![编辑临时过滤器](assets/filter-adhoc-edit.png)

      >[!NOTE]
      >
      > 创建快速过滤器时，请考虑以下事项（拖放）：
      > * 不支持以下组件类型：计算量度和维度，以及无法从中生成过滤器的量度。
      > * 对于完整的维度和事件，Analysis Workspace将创建“存在”事件过滤器。 示例：`Hit where eVar1 exists` 或 `Hit where event1 exists`。
      > * 如果将“未指定”或“无”拖入过滤器放置区域，则它自动转换为“不存在”过滤器，以使其在筛选时受到正确对待。



   * **使用过滤器图标：** 在自由格式表中，选择 **筛选条件** 图标。

      ![区段过滤器](assets/quick-seg1.png)

1. 调整以下任意设置：

   | 设置 | 描述 |
   | --- | --- |
   | [!UICONTROL 名称] | 过滤器的默认名称为该过滤器中的规则名称的组合。 可以将过滤器重命名为更友好的名称。 |
   | [!UICONTROL 包括/排除] | 可在过滤器定义中包括或排除组件，但不得既包括又排除。 |
   | [!UICONTROL “点击”/“访问”/“访客”容器] | 快速过滤器仅包括一个[过滤器容器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html#filter-containers)，从中可在过滤器中包括（或从过滤器中排除）某个维度/指标/日期范围。[!UICONTROL 访客] 包含所有访问和页面查看中特定人员的总体数据。 A [!UICONTROL 访问] 容器允许您设置规则以根据访问划分人员数据，并且 [!UICONTROL 点击] 通过容器，可根据各个页面查看次数划分人员信息。 默认容器为[!UICONTROL 点击]。 |
   | [!UICONTROL 组件]（维度/量度/日期范围） | 通过添加组件（维度、量度、日期范围或维度值）可定义最多 3 条规则。有 3 种方法可以找到正确的组件：<ul><li>只需开始打字，快速过滤器生成器即自动查找相应的组件。</li><li>使用下拉列表查找组件。</li><li>从左边栏中拖放组件。</li></ul> |
   | [!UICONTROL 运算符] | 使用下拉菜单查找标准运算符和[!UICONTROL 非重复计数]运算符。请参阅[过滤器运算符](operators.md)。 |
   | 加号 (+) | 添加另一条规则。 |
   | AND/OR 限定符 | 可将“AND”或“OR”限定符添加到规则，但不得在单个过滤器定义中混用“AND”和“OR”。 |
   | [!UICONTROL 应用] | 将此过滤器应用于面板。如果该过滤器不包含任何数据，则会询问您是否要继续。 |
   | [!UICONTROL 打开生成器] | 打开过滤器生成器。 在过滤器生成器中保存或应用过滤器后，即不再将它视为“快速过滤器”。 它成为组件列表过滤器库的一部分。 <p>要使组件在所有项目和左边栏中都可用，请选择选项 [!UICONTROL **使该过滤器对所有项目都可用，并将其添加到组件列表**].</p><p>有关更多信息，请参阅部分 [将快速筛选器另存为组件列表筛选器](#save-a-quick-filter-as-a-component-list-filter) 本文章中。</p><p>**注意：** 仅限在中拥有过滤器创建权限的用户 [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html#analytics-tools?lang=zh-Hans) 可以打开过滤器生成器。</p> |
   | [!UICONTROL 取消] | 取消此快速过滤器（不要应用它）。 |
   | [!UICONTROL 日期范围] | 该验证器使用面板日期范围执行其数据查找。但在快速过滤器中应用的任何日期范围都将取代面板顶部的面板日期范围。 |
   | 预览（右上角） | 让您查看您的过滤器是否有效以及该过滤器的作用范围。 表示在应用此过滤器时预计将看到的数据集的划分方式。 您可能会收到一条通知，表明此过滤器没有数据。在这种情况下，可继续操作或更改过滤器定义。 |

1. 选择 [!UICONTROL **应用**] 以保存更改。

## 编辑快速过滤器 {#edit}

1. 将鼠标悬停在要编辑的快速筛选器上，然后选择 **编辑** 图标。

   ![编辑临时过滤器](assets/filter-adhoc-edit.png)

1. 编辑过滤器定义或过滤器名称。
1. 选择 [!UICONTROL **应用**] 以保存更改。

## 将快速筛选器另存为组件列表筛选器 {#save}

>[!IMPORTANT]
>
> 保存快速过滤器时，请考虑以下事项：
> 
> * 要保存快速过滤器，您需要以下位置中的过滤器创建权限： [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html#analytics-tools?lang=zh-Hans).
> 
> * 保存或应用过滤器后，在快速过滤器生成器中无法再编辑它。 相反，您必须使用常规过滤器生成器。


您可以选择将快速筛选器另存为组件列表筛选器。 组件列表过滤器的优势包括：

* 所有工作区项目中的可用性
* 支持更复杂的过滤器以及顺序过滤器

您可以从快速筛选器生成器中或从 [!UICONTROL 筛选器生成器].

### 在快速筛选器生成器中保存 {#save2}

1. 应用快速过滤器后，将光标悬停在其上并选择信息(“i”)图标。
1. 选择 **[!UICONTROL 使其对所有项目都可用，并添加到组件列表]**.
1. （可选）为过滤器重命名。
1. 选择&#x200B;**[!UICONTROL 保存]**。

   该过滤器现在显示在左边栏的组件列表中。 另请注意，筛选器的边栏从浅蓝色变为深蓝色，这表示在快速筛选器生成器中无法再编辑或打开它。

### 在筛选器生成器中保存 {#save3}

1. 应用快速过滤器后，将光标悬停在其上并选择信息(“i”)图标。
1. 选择&#x200B;**[!UICONTROL 保存过滤器]**
1. （可选）重命名过滤器，然后选择 [!UICONTROL **应用**].

   返回工作区，并注意筛选器的边栏从浅蓝色变为深蓝色，这表示在快速筛选器生成器中无法再编辑或打开它。 通过保存它，它就成为组件列表的一部分。

   ![过滤器组件列表](assets/quick-seg4.png)

应用过滤器后，可选择将它添加到过滤器组件列表，并使其对所有项目都可用。

1. 将光标悬停在保存的过滤器上并选择铅笔图标。

1. 选择 [!UICONTROL **打开生成器**].

1. 在过滤器生成器的顶部，注意此对话框：

   ![过滤器对话框](assets/project-only-filter-dialog.png)

1. 选中旁边的复选框 **[!UICONTROL 使该过滤器对所有项目都可用，并将其添加到组件列表。]**

1. 选择&#x200B;**[!UICONTROL 保存]**。

   所有项目的过滤器组件列表中现在都显示该过滤器。还可与组织中的其他人员[共享该过滤器](/help/components/filters/manage-filters.md)。

## 快速过滤器示例

以下过滤器示例将维度和量度结合使用：

![过滤器定义示例](assets/quick-seg2.png)

