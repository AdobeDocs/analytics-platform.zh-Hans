---
description: 了解如何在Analysis Workspace中使用项目中的组件
title: 在Analysis Workspace中使用组件
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 97%

---

# 在项目中使用组件

组件构成了 Analysis Workspace 中任何项目的实际数据。组件由维度、量度、区段和日期范围组成。要在项目中添加组件，您可以将其拖放到可视化图表或面板中。

请参阅[组件概述](/help/components/overview.md)，了解有关可添加的组件类型的更多信息。

>[!TIP]
>
>请参阅 ![InfoOutline](/help/assets/icons/InfoOutline.svg) 了解有关每个组件的信息。请参阅[组件信息](#component-info)了解更多信息

## 在项目中添加组件

1. [在 Analysis Workspace 中创建项目](/help/analysis-workspace/build-workspace-project/create-projects.md)。

1. 给 Analysis Workspace 中的项目[添加面板](/help/analysis-workspace/c-panels/panels.md#create-a-panel)或者[添加可视化图表](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。如果您将组件添加到一个空白项目，就会创建一个自由格式表可视化图表。

1. 从按钮面板选择![策划](/help/assets/icons/Curate.svg) **[!UICONTROL 组件]**。您可以在左侧面板中看到所有可用的组件。请参阅[界面](/help/analysis-workspace/home.md#interface)了解更多详细信息。

1. 滚动到或搜索要添加的组件，然后将其拖放到项目中的面板或可视化图表中。

1. 您可以选择将某个组件拖放到面板标题中的区段放置区。此拖放操作将该组件定义为一个区段，并将该区段应用于该面板内的所有内容。
有关如何使用面板上的区段放置区将面板分段，请参阅[面板概述](/help/analysis-workspace/c-panels/panels.md)中的[放置区](/help/analysis-workspace/c-panels/panels.md#drop-zone)。

1. 有关更多详细信息，请参阅以下部分：

   * [在项目中添加维度](#add-dimensions-to-a-project)

   * [在项目中添加量度](#add-metrics-to-a-project)

   * [在项目中添加区段](#add-segments-to-a-project)

   * [在项目中添加日期范围](#add-date-ranges-to-a-project)

### 在项目中添加维度

[维度](/help/components/dimensions/overview.md)是 Customer Journey Analytics 中的变量，通常包含字符串值。相反，[量度](/help/components/calc-metrics/calc-metr-overview.md)包含与维度相关的数字值。基本报告根据数值列（量度）显示字符串值的行（维度）。

1. 如[在项目中添加组件](#add-components-to-a-project)中所述，开始在 Analysis Workspace 的项目中添加维度。

1. 选择以下方法之一来添加维度，并确定要分析的数据类型：

   ![添加维度](/help/components/assets/add-dimension.gif)

   * 将维度拖放到 Analysis Workspace 中的某个可视化图表（例如自由格式表）中。

   * 将左侧面板中的一个或多个维度拖放到区段放置区，以创建快速区段，如[在项目中添加区段](#add-filters-to-a-project)中所述。

1. 您可以选择通过其他组件来细分 Analysis Workspace 中的维度和维度项。请参阅[细分 Workspace 中的维度](/help/components/dimensions/t-breakdown-fa.md)了解更多信息。

有关如何在 Analysis Workspace 中使用维度的更多信息，请参阅[预览维度](/help/components/dimensions/view-dimensions.md)、[细分维度](/help/components/dimensions/t-breakdown-fa.md)和[时间划分维度](/help/components/dimensions/time-parting-dimensions.md)。

### 在项目中添加量度

量度允许您量化 Analysis Workspace 中的数据点。它们最常用作可视化中的列，并与维度相关联。

要在 Analysis Workspace 的项目中添加量度：

1. 如[在项目中添加组件](#add-components-to-a-project)中所述，开始在 Analysis Workspace 的项目中添加量度。



1. 选择以下方法之一在 Analysis Workspace 中添加量度：

   ![添加量度](/help/components/assets/add-metric.gif)

   * 将一个量度拖放到一个空的自由格式表中的量度放置区，以查看该量度在该项目的日期范围内的趋势。

   * 有维度存在时拖动一个量度，可为每个维度项查看该量度。

   * 将量度拖到某个现有量度标题的顶部，可将其替换。

   * 将量度拖到某个现有量度标题的左侧或右侧附近，可添加新量度。

   * 将量度拖到某个现有量度标题的上方或下方，可创建量度重叠。


请参阅[量度](/help/components/apply-create-metrics.md)了解有关量度的更多信息。

### 在项目中添加区段

[区段](/help/components/segments/seg-overview.md)允许您根据相关特征或特定交互来识别人员、会话或事件的子集。

您可以通过以下任一方法在 Analysis Workspace 中使用区段：

* 在面板中添加区段：
在面板中添加区段后，这些区段会应用于该面板内的所有内容。
有关如何使用面板上的区段放置区将面板分段，请参阅[面板概述](/help/analysis-workspace/c-panels/panels.md)中的[放置区](/help/analysis-workspace/c-panels/panels.md#drop-zone)。

* 在可视化图表中添加区段：
在自由格式表的一列中添加区段后，这些区段就会应用于该表列内的所有内容。您还可以添加区段作为流失可视化图表的一部分。

* 在组件中使用区段：
如果您要定义[计算量度](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md)、[注释](/help/components/annotations/create-annotations.md#annotation-builder)或[区段](/help/components/segments/seg-builder.md)等组件，您就可以使用区段作为定义的一部分。


### 在项目中添加日期范围

[日期范围](/help/components/date-ranges/overview.md)确定了 Analysis Workspace 中的报告时间范围，可以应用于项目内的一个或多个面板以及某些可视化图表（如自由格式表）。

每个面板在默认情况下包含一个日期范围。有多种方法可以更新面板的日期范围。更新 Analysis Workspace 中面板日期范围的一种方法是从左侧面板拖动一个日期范围组件：

1. 或者，也可以如[在项目中添加组件](#add-components-to-a-project)中所述，在 Analysis Workspace 中给项目添加日期范围。

1. 从左侧面板将日期范围拖放到：

   * 当前日期范围，以更改面板的日期范围。

     ![拖放日期范围](assets/add-date-range.gif)

   * 自由格式表可视化图表中的量度或维度。请参阅[使用日期范围](/help/components/date-ranges/overview.md#use-date-ranges)了解更多信息。

有关如何在 Analysis Workspace 中使用和管理日期范围的更多信息，请参阅[日期范围概述](/help/components/date-ranges/overview.md)。

## 组件信息

您可以将鼠标悬停在任何组件上以显示![更多信息](/help/assets/icons/InfoOutline.svg)。选择后，会显示一个包含该组件附加信息的弹出窗口。

![组件信息](assets/component-info.png)

根据您的访问控制，您可以：

* 访问组件的![书签](/help/assets/icons/Bookmark.svg) [!UICONTROL 数据字典]定义。
* 访问用于定义组件的![编辑](/help/assets/icons/Edit.svg)组件生成器或者数据视图。
