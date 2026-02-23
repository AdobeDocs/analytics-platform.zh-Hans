---
description: 了解如何在Analysis Workspace中使用快速区段。
title: 快速区段
feature: Workspace Basics, Filters, Segments
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 84%

---

# 快速区段

快速区段允许您快速探索工作区项目中的数据，而无需在[区段生成器](/help/components/segments/seg-create.md)中创建区段。



>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace 中的快速区段](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/components/filters/create-a-quick-filter){target="_blank"}以观看演示视频。

>[!ENDSHADEBOX]


如果您想使用快速区段，请注意：

* 快速区段是直接在工作区项目中创建的。因此，快速区段仅适用于您在其中创建该快速区段的工作区项目。您的工作区项目中的快速区段不适用于其他项目，也不能共享给其他用户。
* 在快速区段中，您只能指定三个条件。
* 快速区段不支持嵌套容器或顺序条件。
* 您可以在共享工作区项目中编辑快速区段。因此，其他用户可以编辑您与这些用户共享的工作区项目中的快速区段。

## 创建

快速区段适用于面板。您可以为工作区项目中的每个面板创建一个或多个快速区段。Analysis Workspace 中的任何用户都可创建快速区段。

要创建快速区段，请执行以下操作：

* 选择面板顶部的 ![SegmentAdd](/help/assets/icons/FilterAdd.svg)。<br/>然后，直接在[快速区段生成器](#quick-segment-builder)中编辑区段。
* 将组件从组件面板拖到面板标题中的区段放置区。放下后，将鼠标悬停在区段上，然后选择![编辑](/help/assets/icons/Edit.svg)，以在[快速区段生成器](#quick-segment-builder)中编辑区段。

使用拖放操作创建快速区段时，请注意：

* 并非所有组件类型都受支持。不支持计算量度，仅支持可以构建区段的维度和量度。
* 对于维度和量度组件，[快速区段生成器](#quick-segment-builder)会自动创建一个 `exists` 条件。例如，如果拖放&#x200B;**[!UICONTROL City]**，则会创建条件&#x200B;**[!UICONTROL City]** **[!UICONTROL exists]**。
* 对于维度值，[快速区段生成器](#quick-segment-builder)会自动创建&#x200B;**[!UICONTROL 等于]**&#x200B;条件。 例如，如果从&#x200B;**[!UICONTROL 城市]**&#x200B;维度列表中拖放&#x200B;**[!UICONTROL 阿姆斯特丹]**，则会创建条件&#x200B;**[!UICONTROL 城市]** **[!UICONTROL 等于]** `Amsterdam`。
* 如果拖放&#x200B;**[!UICONTROL 未指定]**&#x200B;或&#x200B;**[!UICONTROL 无]**，[快速区段生成器](#quick-segment-builder)将自动创建&#x200B;**[!UICONTROL 不存在]**&#x200B;条件。

您创建的快速区段出现在面板顶部。快速区段有一个淡蓝色的细长左侧边栏。如果使用[快速区段生成器](#quick-segment-builder)时快速区段处于编辑模式，该快速区段的背景为浅蓝色。

您在面板中创建的快速区段的结果将（使用 AND 逻辑）应用于该面板中的所有可视化图表。


## 管理

要管理快速区段，请将鼠标悬停在具体的&#x200B;**[!UICONTROL 快速区段]**&#x200B;上。

* 选择![编辑](/help/assets/icons/Edit.svg)，打开[快速区段生成器](#quick-segment-builder)，编辑快速区段。
* 选择 ![InfoOutline](/help/assets/icons/InfoOutline.svg) 打开弹出窗口。弹出窗口中会显示有关该区段的信息。您可以选择&#x200B;**[!UICONTROL 使其可用于所有项目并添加到您的组件列表]**，以将区段添加到组件面板中的![区段](/help/assets/icons/Segmentation.svg) **[!UICONTROL 区段]**&#x200B;组件列表。您会看到&#x200B;**[!UICONTROL 保存快速区段]**&#x200B;对话框，提示您为区段指定名称。选择&#x200B;**[!UICONTROL 保存]**&#x200B;以继续。您的[!UICONTROL 快速区段]会变成&#x200B;**[!UICONTROL 区段]**。您无法再使用[快速区段构建器](#quick-segment-builder)编辑该区段。相反，您必须使用[区段生成器](seg-builder.md)，将该区段作为常规区段进行编辑。

## 快速区段生成器

请参阅下面的快速区段生成器的示例。在这个例子中，生成器打开生成一个名为 `Call Reason = Order Change AND Online Orders is greater than or equal 1` 的快速区段。顶部的两个快速区段都适用于&#x200B;**[!UICONTROL 平均订单价值仪表板]**&#x200B;面板及其中的所有可视化图表，例如[!UICONTROL 每个国家/地区的平均订单价值]自由格式表。

![快速区段生成器](assets/quick-filter-builder.png)

快速区段生成器由以下区域和按钮组成。

### 标题区域

标题区域决定了快速区段的名称、类型和范围。它还显示了快速区段结果的视觉效果。

| 元素 | 描述 |
|---|---|
| **[!UICONTROL 名称]** | 该名称是从快速区段的定义自动得出的。 |
| **[!UICONTROL 人员]** <br/>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) ![警报](/help/assets/icons/Alert.svg) | 预览快速分段后得到的数据可视化效果。通过条形图和百分比可以洞察总体数据中有多少是快速区段结果的一部分。![警报](/help/assets/icons/AlertRed.svg)表示快速区段未返回数据。 |
| **[!UICONTROL 包括]**<br/>**[!UICONTROL 排除]** | 从下拉列表![ChevronDown](/help/assets/icons/ChevronDown.svg)中选择是否要从面板中的数据包括或排除快速区段的结果。 |
| **[!UICONTROL 事件]**<br/>**[!UICONTROL 会话]**<br/>**[!UICONTROL 人员]** | 从下拉菜单![ChevronDown](/help/assets/icons/ChevronDown.svg)中选择快速区段的范围。 |

### 条件区域

在条件区域可指定条件（最多三个）。对于每个条件，您可以指定以下内容：

| 元素 | 描述 |
|---|---|
| **[!UICONTROL 维度]**<br/>**[!UICONTROL 量度]**<br/>**[!UICONTROL 日期范围]** | 从下拉菜单![ChevronDown](/help/assets/icons/ChevronDown.svg)中选择是否要为维度、量度或日期范围指定条件。 |
| **[!UICONTROL *组件&#x200B;*]** | 条件的组件字段。您可以&#x200B;[!UICONTROL *通过输入来添加*]&#x200B;组件，从列表中选择组件，或者从组件面板中拖放组件。您只能将相似的组件放在条件的组件字段上。例如，您只能将维度组件从组件面板拖放到维度条件上。<br/>您还可以通过拖放操作来替换现有组件。<br/>选择 ![CrossSize75](/help/assets/icons/CrossSize75.svg) 从组件字段中删除该组件。 |
| **[!UICONTROL *运算符&#x200B;*]** | 组件的运算符。有关更多信息，请参阅[运算符](seg-operators.md)。仅适用于维度和量度。 |
| **[!UICONTROL *值&#x200B;*]** | 条件的值。根据所选的运算符，可以从列表中选择值或者输入一个值。 |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | 选择从快速区段中删除一个条件。 |

### 按钮

| 按钮 | 描述 |
|---|---|
| **[!UICONTROL AND]**<br/>**[!UICONTROL OR]** | 仅当您定义多个条件时才可用。从下拉菜单![ChevronDown](/help/assets/icons/ChevronDown.svg)中选择两个条件。 该选择决定了快速区段的布尔逻辑。当有三个条件时，您不能混合逻辑。布尔逻辑是 **[!UICONTROL AND]** 或 **[!UICONTROL OR]**。 |
| ![AddCircle](/help/assets/icons/AddCircle.svg) | 在您的快速区段中添加另一个条件。只有在您为快速区段定义了一个或两个条件后，此按钮才可用。 |
| **[!UICONTROL 应用]** | 将更改应用于快速区段。 |
| **[!UICONTROL 打开生成器]** | 系统会提示您确认&#x200B;**[!UICONTROL 您确定吗？]**&#x200B;对话框。如果您选择&#x200B;**[!UICONTROL 确定]**，您将无法再在[快速区段生成器](#quick-segment-builder)中更改您的区段。您的快速区段已重命名为&#x200B;**[!UICONTROL 区段]**，并且现在有一个深蓝色的细长左侧边栏。<br/>常规[区段生成器](seg-builder.md)打开时会显示以下选项：**[!UICONTROL 使此区段可用于您的所有项目，并将其添加到您的组件列表中]**。 <ul><li>如果选择此选项并选择&#x200B;**[!UICONTROL 应用]**，则该区段将添加到组件面板中的![区段](/help/assets/icons/Segmentation.svg) **[!UICONTROL 区段]**&#x200B;组件列表中。</li><li>如果您不选择此选项，并选择&#x200B;**[!UICONTROL 应用]**，该区段就仍然是仅限于工作区项目的区段。</li></ul> |
| **[!UICONTROL 取消]** | 选择取消创建或编辑快速区段。 |

## 快速区段与区段

快速区段正如其名称所示。您可以快速创建和编辑快速区段，并立即在面板中查看效果。

与快速区段相比，普通区段具有以下优势。

* 普通区段可应用于您所有的工作区项目
* 使用嵌套和分层[容器](seg-builder.md#containers)和序列（使用[顺序区段](seg-sequential-build.md)）的区段支持更大的复杂性。


