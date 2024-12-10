---
description: 在 Analysis Workspace for Customer Journey Analytics 中使用快速过滤器。
title: 快速过滤器
feature: Workspace Basics
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 4ce1b22cce3416b8a82e5c56e605475ae6c27d88
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 2%

---

# 快速过滤器

快速筛选器允许您快速浏览Workspace项目中的数据，而无需在[筛选器生成器](/help/components/filters/create-filters.md)中创建筛选器。


+++ 以下视频演示了如何使用快速过滤器。

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)


+++

当您想要使用快速筛选器时，请注意：

* 快速筛选器直接在Workspace项目中创建。 因此，快速过滤器仅适用于创建快速过滤器的Workspace项目。 您的Workspace项目中的快速筛选器在其他项目中不可用，因此无法共享给其他用户。
* 在快速筛选中，只能指定三个条件。
* 快速筛选器不支持嵌套容器或顺序条件。
* 您可以在共享的Workspace项目中编辑快速筛选器。 因此，其他用户可以在您与这些用户共享的Workspace项目中编辑快速过滤器。

## 创建

快速筛选器适用于面板。 您可以为Workspace项目中的每个面板创建一个或多个快速过滤器。 Analysis Workspace中的任何用户都可以创建快速过滤器。

要创建快速过滤器，请执行以下操作：

* 选择面板顶部的![筛选添加](/help/assets/icons/FilterAdd.svg)。 <br/>然后，直接在[快速筛选器生成器](#quick-filter-builder)中编辑筛选器。
* 将组件从组件面板拖到面板标题中的过滤器拖放区域。 删除后，将光标悬停在筛选器上并选择![编辑](/help/assets/icons/Edit.svg)以在[快速筛选器生成器](#quick-filter-builder)中编辑筛选器。

使用拖放操作创建快速过滤器时，请注意：

* 并非所有组件类型都受支持。 计算量度不受支持，并且仅支持从中生成过滤器的维度和量度。
* 对于维度和量度组件，[快速筛选器生成器](#quick-filter-builder)会自动创建`exists`条件。 例如，如果拖放`City`，则会创建条件`City exists`。
* 对于维度值，[快速筛选器生成器](#quick-filter-builder)会自动创建`equals`条件。 例如，如果从`City`维度中拖放`amsterdam`，则会创建条件`City equals amsterdam`。
* 如果拖放`unspecified`或`none`，[快速筛选器生成器](#quick-filter-builder)将自动创建`does not exist`条件。

您创建的快速过滤器将显示在面板顶部。 快速滤镜有一个浅蓝色细的左栏。 使用[快速筛选器生成器](#quick-filter-builder)处于编辑模式时，快速筛选器的背景为浅蓝色。

您在面板中创建的快速过滤器的结果将应用（使用AND逻辑）到属于面板的所有可视化图表。


## 管理

若要管理快速筛选器，请将光标悬停在特定&#x200B;**[!UICONTROL 快速筛选器]**&#x200B;上。

* 选择![编辑](/help/assets/icons/Edit.svg)以打开[快速筛选器生成器](#quick-filter-builder)并编辑快速筛选器。
* 选择![信息大纲](/help/assets/icons/InfoOutline.svg)以打开弹出窗口。 弹出窗口显示有关过滤器的信息。 您可以选择&#x200B;**[!UICONTROL 使其对所有项目都可用，并添加到组件列表]**&#x200B;若要将该筛选器添加到组件面板中的![筛选器](/help/assets/icons/Segmentation.svg) **[!UICONTROL 筛选器]**&#x200B;组件列表。 您看到&#x200B;**[!UICONTROL 保存快速筛选器]**&#x200B;对话框，提示您指定筛选器的名称。 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以继续。 您的[!UICONTROL 快速筛选器]将变为&#x200B;**[!UICONTROL 筛选器]**。 您无法再使用[快速筛选器生成器](#quick-filter-builder)编辑筛选器。 相反，您必须使用[筛选器生成器](filter-builder.md)将筛选器编辑为常规筛选器。

## 快速筛选器生成器

有关快速过滤器生成器的示例，请参阅下文。 在此示例中，为标题为`Call Reason = Order Change AND Online Orders is greater than or equal 1`的快速过滤器打开了生成器。 顶部的两个快速筛选器都适用于[!UICONTROL 平均订单值仪表板]面板及其中的所有可视化图表，例如[!UICONTROL 每个国家/地区的平均订单值]自由格式表。

![快速过滤器生成器](assets/quick-filter-builder.png)

快速过滤器生成器包含以下区域和按钮。

### 标题区域

标题区域决定快速过滤器的名称、类型和范围。 它还会显示快速筛选器结果的可视化图表。

| 元素 | 描述 |
|---|---|
| **[!UICONTROL 名称]** | 该名称自动从快速筛选器定义派生。 |
| **[!UICONTROL 人员]** <br/>![复选标记圆](/help/assets/icons/CheckmarkCircle.svg) ![警报](/help/assets/icons/Alert.svg) | 预览由快速筛选器生成的数据的可视化图表。 条形图和百分比可让您深入了解快速过滤器结果中的整体数据量。 红色的![警报](/help/assets/icons/Alert.svg)表示快速过滤器未返回数据。 |
| **[!UICONTROL 包括]**<br/>**[!UICONTROL 排除]** | 从下拉列表![ChevronDown](/help/assets/icons/ChevronDown.svg)中选择是否要从面板中的数据包括或排除快速筛选的结果。 |
| **[!UICONTROL 事件]**<br/>**[!UICONTROL 会话]**<br/>**[!UICONTROL 人员]** | 从下拉列表![ChevronDown](/help/assets/icons/ChevronDown.svg)中选择快速过滤器的范围。 |

### 条件区域

条件区域指定条件（最多三个）。 对于每个条件，您可以指定以下内容：

| 元素 | 描述 |
|---|---|
| **[!UICONTROL Dimension]**<br/>**[!UICONTROL 指标]**<br/>**[!UICONTROL 日期范围]** | 从下拉列表![ChevronDown](/help/assets/icons/ChevronDown.svg)中选择是否要为维度、量度或日期范围指定条件。 |
| **[!UICONTROL *组件&#x200B;*]** | 条件的组件字段。 您可以&#x200B;[!UICONTROL *键入以添加*]&#x200B;组件，从列表中选择组件，或者从组件面板中拖放组件。 您只能在条件的组件字段上拖放类似的组件。 例如，您只能在维度条件上从组件面板中放置维度组件。 <br/>您也可以通过拖放来替换现有组件。<br/>选择![CrossSize75](/help/assets/icons/CrossSize75.svg)以从组件字段中删除该组件。 |
| **[!UICONTROL *操作员&#x200B;*]** | 组件的运算符。 有关详细信息，请参阅[运算符](operators.md)。 仅适用于维度和量度。 |
| **[!UICONTROL *值&#x200B;*]** | 条件的值。 根据所选运算符，可以从列表中选择值或输入值。 |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | 选择以从快速筛选条件中删除条件。 |

### 按钮

| 按钮 | 描述 |
|---|---|
| **[!UICONTROL 和]**<br/>**[!UICONTROL 或]** | 仅在定义多个条件时可用。 从条件之间的下拉列表![ChevronDown](/help/assets/icons/ChevronDown.svg)中选择。 该选择确定快速过滤器的布尔逻辑。 当有三个条件时，不能混用逻辑。 布尔逻辑为&#x200B;**[!UICONTROL AND]**&#x200B;或&#x200B;**[!UICONTROL OR]**。 |
| ![AddCircle](/help/assets/icons/AddCircle.svg) | 向快速筛选器添加另一个条件。 仅当为快速过滤器定义了一个或两个条件时，此按钮才可用。 |
| **[!UICONTROL 应用]** | 将更改应用于快速过滤器。 |
| **[!UICONTROL 打开生成器]** | 系统将提示您使用&#x200B;**[!UICONTROL 进行确认。是否确定？]**&#x200B;对话框。 如果您选择&#x200B;**[!UICONTROL 确定]**，则无法再在[快速筛选器生成器](#quick-filter-builder)中修改您的筛选器。您的快速筛选器已重命名为&#x200B;**[!UICONTROL 筛选器]**，现在左栏中的蓝色细条较深。<br/>常规[筛选器生成器](filter-builder.md)打开，其中包含&#x200B;**[!UICONTROL 使此筛选器对所有项目都可用，并将其添加到组件列表]**。 <ul><li>如果选择此选项并选择&#x200B;**[!UICONTROL 应用]**，则筛选器将添加到组件面板中的![筛选器](/help/assets/icons/Segmentation.svg) **[!UICONTROL 筛选器]**&#x200B;组件列表中。</li><li>如果不选择此选项并选择&#x200B;**[!UICONTROL 应用]**，则筛选器仍然是仅用于Workspace项目的筛选器。</li></ul> |
| **[!UICONTROL 取消]** | 选择可取消创建或编辑快速过滤器。 |

## 快速过滤器与过滤器

快速筛选器就是其命名的确切内容。 您可以快速内联创建和编辑快速筛选器，并立即在面板中查看效果。

与快速过滤器相比，过滤器具有以下优势。

* 过滤器可在您的所有Workspace项目中提供
* 过滤器支持使用嵌套和分层容器以及序列（使用序列过滤器）来提高复杂性。


