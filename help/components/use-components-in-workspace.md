---
description: 了解如何在Analysis Workspace中将组件添加到项目
title: 使用 Analysis Workspace 中的组件
feature: Components
role: User
exl-id: 97bdfb9e-a27e-4a6b-b6cc-21a292398037
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 7%

---

# 使用 Analysis Workspace 中的组件

组件构成了Analysis Workspace中任何项目的实际数据。 组件由维度、量度、区段和日期范围组成。 您可以将组件拖到可视化图表或面板中，以将其添加到项目中。

有关可添加的组件类型的更多信息，请参阅[组件概述](/help/components/overview.md)。

>[!TIP]
>
>有关每个组件的信息，请使用![InfoOutline](/help/assets/icons/InfoOutline.svg)。 有关详细信息，请参阅[组件信息](#component-info)

## 将组件添加到项目

1. [在Analysis Workspace中创建项目](/help/analysis-workspace/build-workspace-project/create-projects.md)。

1. [添加面板](/help/analysis-workspace/c-panels/panels.md#create-a-panel)或[将可视化图表](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)添加到Analysis Workspace中的项目。 如果您将组件添加到空白项目，则已经为您创建了自由格式表可视化图表。

1. 从按钮面板中选择![策划](/help/assets/icons/Curate.svg) **[!UICONTROL 组件]**。 您会在左侧面板中看到所有可用的组件。 有关详细信息，请参阅[接口](/help/analysis-workspace/home.md#interface)。

1. 滚动到或搜索要添加的组件，然后将其拖动到项目中的面板或可视化图表。

1. 您可以选择将组件拖动到面板标题中的区段放置区域。 此拖放操作将组件定义为区段，并将区段应用于面板内的所有内容。
有关如何使用面板上的区段放置区域对面板进行分段的信息，请参阅[面板概述](/help/analysis-workspace/c-panels/panels.md)中的[放置区域](/help/analysis-workspace/c-panels/panels.md#drop-zone)。

1. 有关更多详细信息，请参阅以下部分：

   * [将维度添加到项目](#add-dimensions-to-a-project)

   * [将量度添加到项目](#add-metrics-to-a-project)

   * [将区段添加到项目](#add-segments-to-a-project)

   * [向项目添加日期范围](#add-date-ranges-to-a-project)

### 将维度添加到项目

[维度](/help/components/dimensions/overview.md)是Customer Journey Analytics中通常包含字符串值的变量。 相反，[量度](/help/components/calc-metrics/calc-metr-overview.md)包含与维度相关的数字值。基本报告根据数值列（量度）显示字符串值的行（维度）。

1. 开始向Analysis Workspace中的项目添加维度，如[将组件添加到项目](#add-components-to-a-project)中所述。

1. 选择以下方法之一来添加维度，并确定要分析的数据类型：

   ![添加维度](/help/components/assets/add-dimension.gif)

   * 将维度拖动到Analysis Workspace中的可视化图表（例如自由格式表）。

   * 将左侧面板中的一个或多个维度拖到区段拖放区域以创建快速区段，如[将区段添加到项目](#add-filters-to-a-project)中所述。

1. 您可以选择在Analysis Workspace中与其他组件一起划分维度和维度项。 有关详细信息，请参阅[在Workspace中划分维度](/help/components/dimensions/t-breakdown-fa.md)。

有关如何在Analysis Workspace中使用维度的详细信息，请参阅[预览维度](/help/components/dimensions/view-dimensions.md)、[划分维度](/help/components/dimensions/t-breakdown-fa.md)和[时间划分维度](/help/components/dimensions/time-parting-dimensions.md)。

### 将量度添加到项目

指标允许您量化 Analysis Workspace 中的数据点。它们最常用作可视化中的列，并与维度相关联。

要在Analysis Workspace中将指标添加到项目，请执行以下操作：

1. 开始向Analysis Workspace中的项目添加量度，如[将组件添加到项目](#add-components-to-a-project)中所述。



1. 选择以下方法之一以在Analysis Workspace中添加量度：

   ![添加指标](/help/components/assets/add-metric.gif)

   * 将量度拖动到空的自由格式表中的量度放置区，可查看在项目的日期期间内的量度趋势。

   * 当存在维度时，拖动一个量度以查看每个维度项目的该量度。

   * 将一个指标拖到现有指标标题的顶部即可替换它。

   * 将指标拖动到现有指标标题右侧的左侧以添加新指标。

   * 将量度拖动到现有量度标题上方或下方以创建量度重叠。


有关量度的详细信息，请参阅[量度](/help/components/apply-create-metrics.md)。

### 将区段添加到项目

[区段](/help/components/filters/filters-overview.md)允许您根据特性或特定交互来识别人员、会话或事件的子集。

您可以通过以下任意方式在Analysis Workspace中使用区段：

* 将区段添加到面板
将区段添加到面板时，区段将应用于面板中的所有内容。
有关如何使用面板上的区段放置区域对面板进行分段的信息，请参阅[面板概述](/help/analysis-workspace/c-panels/panels.md)中的[放置区域](/help/analysis-workspace/c-panels/panels.md#drop-zone)。

* 将区段添加到可视化图表
向自由格式表中的列添加区段时，区段会应用于表列中的所有内容。 您还可以添加区段作为流失可视化图表的一部分。

* 在组件中使用区段
当您定义[计算量度](/help/components/calc-metrics/cm-workflow/metrics-with-segments.md)、[注释](/help/components/annotations/create-annotations.md#annotation-builder)甚至[区段](/help/components/filters/filter-builder.md)等组件时，可以将区段用作定义的一部分。


### 向项目添加日期范围

[日期范围](/help/components/date-ranges/overview.md)决定Analysis Workspace中的报表时间范围，可以应用于项目中的一个或多个面板，也可以应用于某些可视化图表（如自由格式表）。

默认情况下，每个面板都包含日期范围。 有多种方法可以更新面板的日期范围。 在Analysis Workspace中更新面板日期范围的一种方法是从左侧面板拖动日期范围组件：

1. （可选）向Analysis Workspace中的项目添加日期范围，如[将组件添加到项目](#add-components-to-a-project)中所述。

1. 将日期范围从左侧面板拖放到：

   * 当前日期范围，用于修改面板的日期范围。

     ![删除日期范围](assets/add-date-range.gif)

   * 自由格式表可视化图表中的量度或维度。 有关详细信息，请参阅[使用日期范围](/help/components/date-ranges/overview.md#use-date-ranges)。

有关如何在Analysis Workspace中使用和管理日期范围的更多信息，请参阅[日期范围概述](/help/components/date-ranges/overview.md)。

## 组件信息

您可以将鼠标悬停在任何组件上以显示![更多信息](/help/assets/icons/InfoOutline.svg)。 选中后，将显示一个弹出窗口，其中包含有关组件的其他信息。

![组件信息](assets/component-info.png)

根据您的访问控制，您可以：

* 访问组件的![书签](/help/assets/icons/Bookmark.svg) [!UICONTROL 数据字典]定义。
* 访问定义了组件的![Edit](/help/assets/icons/Edit.svg)组件生成器或数据视图。
