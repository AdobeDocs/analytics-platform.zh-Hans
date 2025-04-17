---
description: 在Analysis Workspace for Customer Journey Analytics中使用快速区段
title: 快速区段
feature: Workspace Basics
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 716d6423c0cc8b91aa4951952191e0fd0e627c0f
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 59%

---

# 快速区段

快速区段允许您快速浏览Workspace项目中的数据，而无需在[区段生成器](/help/components/filters/create-filters.md)中创建区段。



>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace 中的快速区段](https://video.tv.adobe.com/v/341466/?quality=12&learn=on){target="_blank"}以观看演示视频。

>[!ENDSHADEBOX]


当您想要使用快速区段时，请注意：

* 快速区段直接在Workspace项目中创建。 因此，快速区段仅适用于在其中创建快速区段的Workspace项目。 您的Workspace项目中的快速区段在其他项目中不可用，无法共享给其他用户。
* 在快速区段中，只能指定三个条件。
* 快速区段不支持嵌套容器或顺序条件。
* 您可以在共享的Workspace项目中编辑快速区段。 因此，其他用户可以在与这些用户共享的Workspace项目中编辑快速区段。

## 创建

快速区段适用于面板。 您可以为Workspace项目中的每个面板创建一个或多个快速区段。 Analysis Workspace中的任何用户都可以创建快速区段。

要创建快速区段，请执行以下操作：

* 选择面板顶部的![SegmentAdd](/help/assets/icons/FilterAdd.svg)。 <br/>然后，直接在[快速区段生成器](#quick-filter-builder)中编辑该区段。
* 将组件从组件面板拖到面板标题中的区段拖放区域。 放置后，将鼠标悬停在区段上并选择![编辑](/help/assets/icons/Edit.svg)以在[快速区段生成器](#quick-filter-builder)中编辑该区段。

使用拖放创建快速区段时，请注意：

* 并非所有组件类型都受支持。计算量度不受支持，并且仅支持从中生成区段的维度和量度。
* 对于维度和量度组件，[快速区段生成器](#quick-filter-builder)会自动创建`exists`条件。 例如，如果您拖放 `City`，则会创建条件 `City exists`。
* 对于维度值，[快速区段生成器](#quick-filter-builder)会自动创建`equals`条件。 例如，如果从 `City` 维度拖放 `amsterdam`，则会创建条件 `City equals amsterdam`。
* 如果拖放`unspecified`或`none`，[快速区段生成器](#quick-filter-builder)将自动创建`does not exist`条件。

您创建的快速区段将显示在面板顶部。 快速区段的左栏略为浅蓝色。 使用[快速区段生成器](#quick-filter-builder)处于编辑模式时，快速区段的背景为浅蓝色。

您在面板中创建的快速区段的结果将应用（使用AND逻辑）到作为面板一部分的所有可视化图表。


## 管理

要管理快速区段，请将鼠标悬停在特定&#x200B;**[!UICONTROL 快速区段]**&#x200B;上。

* 选择![编辑](/help/assets/icons/Edit.svg)以打开[快速区段生成器](#quick-filter-builder)并编辑快速区段。
* 选择 ![InfoOutline](/help/assets/icons/InfoOutline.svg) 打开弹出窗口。弹出窗口中会显示有关该过滤器的信息。您可以选择&#x200B;**[!UICONTROL 使其对所有项目都可用，并添加到组件列表]**&#x200B;将该区段添加到组件面板中的![区段](/help/assets/icons/Segmentation.svg) **[!UICONTROL 区段]**&#x200B;组件列表。 您看到&#x200B;**[!UICONTROL 保存快速区段]**&#x200B;对话框，提示您指定区段的名称。 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以继续。您的[!UICONTROL 快速区段]将变为&#x200B;**[!UICONTROL 区段]**。 不能再使用[快速区段生成器](#quick-filter-builder)编辑该区段。 相反，您必须使用[区段生成器](filter-builder.md)将该区段编辑为常规区段。

## 快速区段生成器

有关快速区段生成器的示例，请参阅下文。 在这个例子中，生成器被打开以进行名为 `Call Reason = Order Change AND Online Orders is greater than or equal 1` 的快速过滤。顶部的两个快速过滤器都适用于[!UICONTROL 平均订单价值仪表板]面板，及其中的所有可视化图表，例如[!UICONTROL 每个国家/地区的平均订单价值]自由格式表。

![快速区段生成器](assets/quick-filter-builder.png)

快速过滤器生成器由以下区域和按钮组成。

### 标题区域

标题区域决定了快速过滤器的名称、类型和范围。它还显示了快速过滤结果的视觉效果。

| 元素 | 描述 |
|---|---|
| **[!UICONTROL 名称]** | 该名称是从快速过滤器的定义自动得出的。 |
| **[!UICONTROL 人员]** <br/>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) ![警报](/help/assets/icons/Alert.svg) | 预览快速过滤后得到的数据可视化效果。通过条形图和百分比可以了解总体数据中有多少是快速过滤结果的一部分。红色 ![警报](/help/assets/icons/Alert.svg) 表示快速过滤器没有返回数据。 |
| **[!UICONTROL 包括]**<br/>**[!UICONTROL 排除]** | 从下拉列表中选择 ![ChevronDown](/help/assets/icons/ChevronDown.svg) 是否要在面板中的数据中包含或排除快速过滤的结果。 |
| **[!UICONTROL 事件]**<br/>**[!UICONTROL 会话]**<br/>**[!UICONTROL 人员]** | 从下拉列表中选择 ![ChevronDown](/help/assets/icons/ChevronDown.svg) 快速过滤的范围。 |

### 条件区域

在条件区域可指定条件（最多三个）。对于每个条件，您可以指定以下内容：

| 元素 | 描述 |
|---|---|
| **[!UICONTROL 维度]**<br/>**[!UICONTROL 量度]**<br/>**[!UICONTROL 日期范围]** | 从下拉菜单 ![ChevronDown](/help/assets/icons/ChevronDown.svg) 中选择是否要为维度、量度或日期范围指定条件。 |
| **[!UICONTROL *组件&#x200B;*]** | 条件的组件字段。您可以&#x200B;[!UICONTROL *通过输入来添加*]&#x200B;组件，从列表中选择组件，或者从组件面板中拖放组件。您只能将相似的组件放在条件的组件字段上。例如，您只能将维度组件从组件面板拖放到维度条件上。<br/>您还可以通过拖放操作来替换现有组件。<br/>选择 ![CrossSize75](/help/assets/icons/CrossSize75.svg) 从组件字段中删除该组件。 |
| **[!UICONTROL *运算符&#x200B;*]** | 组件的运算符。有关更多信息，请参阅[运算符](operators.md)。仅适用于维度和量度。 |
| **[!UICONTROL *值&#x200B;*]** | 条件的值。根据所选的运算符，可以从列表中选择值或者输入一个值。 |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | 选择从快速过滤器中删除一个条件。 |

### 按钮

| 按钮 | 描述 |
|---|---|
| **[!UICONTROL AND]**<br/>**[!UICONTROL OR]** | 仅当您定义多个条件时才可用。从条件之间的下拉列表 ![ChevronDown](/help/assets/icons/ChevronDown.svg) 中进行选择。该选择决定了快速过滤器的布尔逻辑。当有三个条件时，您不能混合逻辑。布尔逻辑是 **[!UICONTROL AND]** 或 **[!UICONTROL OR]**。 |
| ![AddCircle](/help/assets/icons/AddCircle.svg) | 向您的快速过滤器中添加另一个条件。仅当您为快速过滤器定义了一个或两个条件时，此按钮才可用。 |
| **[!UICONTROL 应用]** | 将更改应用于快速过滤器。 |
| **[!UICONTROL 打开生成器]** | 系统会提示您确认&#x200B;**[!UICONTROL 您确定吗？]**&#x200B;对话框。如果您选择&#x200B;**[!UICONTROL 确定]**，您将无法再在[快速过滤器生成器](#quick-filter-builder)中修改您的过滤器。您的快速过滤器已重命名为&#x200B;**[!UICONTROL 过滤器]**，并且现在左侧有一个深蓝色的细条。<br/>常规[过滤器生成器](filter-builder.md)打开时会显示以下选项：**[!UICONTROL 使此过滤器可用于您的所有项目，并将其添加到您的组件列表中]**。 <ul><li>如果选择此选项，并选择&#x200B;**[!UICONTROL 应用]**，则过滤器会被添加到组件面板中的 ![过滤器](/help/assets/icons/Segmentation.svg) **[!UICONTROL 过滤器]**&#x200B;组件列表中。</li><li>如果您不选择此选项，并选择&#x200B;**[!UICONTROL 应用]**，则过滤器仍为仅限于工作区项目的过滤器。</li></ul> |
| **[!UICONTROL 取消]** | 选择取消创建或编辑快速过滤器。 |

## 快速过滤器与普通过滤器

快速过滤器正如其名称所示。您可以快速创建和编辑快速过滤器，并立即在面板中查看效果。

与快速过滤器相比，普通过滤器确实有以下优势。

* 普通过滤器可应用于您所有的工作区项目
* 普通过滤器使用嵌套和分层容器以及序列（使用序列过滤器）支持更复杂的用途。


