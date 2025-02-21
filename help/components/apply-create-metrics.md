---
description: 有两种方式可使用 Analysis Workspace 中的指标。
title: 量度
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: 17d3e8ed5986348bb4ba50822dfd9bb43d5a7570
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 8%

---

# 指标

指标允许您量化 Analysis Workspace 中的数据点。它们最常用作可视化中的列，并与维度相关联。

## 在 Analysis Workspace 中使用量度

量度在Analysis Workspace中的使用非常灵活。 将量度拖动到空的自由格式表，可查看在项目日期期间该量度的趋势。 此外，您还可以拖曳存在维度的量度，以便将该量度与每个维度项目进行比较。 将量度拖动到现有量度标题上方会替换该量度，如果将量度拖动到标题旁边，则可以并排查看这两个量度。

有关如何将量度和其他类型的组件添加到Analysis Workspace的信息，请参阅[在Analysis Workspace中使用组件](/help/components/use-components-in-workspace.md)。


## 指标类型

Adobe 提供了多种类型的指标，可供在 Analysis Workspace 中使用：


* **标准量度**：标准量度的示例包括人员、会话、事件。

  与Adobe Analytics相反，Customer Journey Analytics允许您在连接和数据视图范围内灵活定义标准指标。

   * **人员**： Customer Journey Analytics中的人员指标是与人员ID不同的计数。 根据您在连接中配置数据集时选择作为人员ID，人员量度可能具有不同的含义。
   * **会话**：您将Customer Journey Analytics中的“会话”量度定义为数据视图中会话设置配置的一部分。 查看[会话设置](/help/data-views/session-settings.md)。
   * **事件**： Customer Journey Analytics中的Events量度由事件组成，这些事件是您已配置为连接一部分的任何事件数据集的一部分。

* **计算指标** ![计算器](/help/assets/icons/Calculator.svg)：基于标准指标、静态数字或算法函数的用户定义指标。

* **计算量度模板** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) ：Adobe定义的与计算量度行为相似的量度。 您可以在Workspace项目中按原样使用它们，也可以保存副本以自定义逻辑。 查看[默认的计算指标](calc-metrics/cm-workflow/../default-calcmetrics.md)。

您可以查看某个量度是否获得批准![批准图标](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)。 如果您想了解有关某个量度的更多详细信息，请将鼠标悬停在该量度上，然后选择![信息图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)。 有关详细信息，请参阅[组件信息](use-components-in-workspace.md#component-info)。

## 比较不同归因模型的指标

如果您想要轻松快速地将一个归因模型与另一个量度进行比较，请从量度的上下文菜单中选择&#x200B;**[!UICONTROL 比较归因模型]**。

![Workspace面板高亮显示比较归因模型](assets/compare-attribution.png)

此快捷键可让您快速轻松地比较归因模型。

## 创建计算量度

计算量度允许您使用简单的运算符或统计函数轻松配置量度彼此的关系。 有关详细信息，请参阅[计算量度概述](/help/components/calc-metrics/calc-metr-overview.md)。

可通过多种方式创建计算量度。 您选择的方法确定计算量度是从所有项目的组件列表中可用，还是仅用于创建该量度的项目。

### 为所有项目创建计算指标

您可以使用计算指标生成器创建计算指标。 通过这种方式创建时，计算量度在组件列表中可用，然后可在整个组织的项目中使用。

有关如何访问计算量度生成器的信息，请参阅[创建计算量度](/help/components/calc-metrics/cm-workflow/cm-workflow.md)。

### 为单个项目创建计算指标

您可以创建快速计算量度，这些量度仅可用于创建它们的项目。

要为单个项目创建计算指标，请执行以下操作：

1. 在Analysis Workspace中，打开要在其中创建计算指标的项目。

1. 在自由格式表中，右键单击单列的列标题。

   或

   按住Shift键的同时选择两列，然后右键单击其中一个选定的列。

1. 选择&#x200B;**[!UICONTROL 从所选内容创建量度]**

   ![Workspace面板高亮显示从所选内容创建](assets/create-metric-from-selection.png)

1. 要仅为此项目创建计算量度，请从可用选项中进行选择。

   在选中单列时，以下选项可用：

   * [!UICONTROL **Mean**]：创建一个新列，以显示该列的一组维度元素中的平均值。 这使用[Mean](/help/components/calc-metrics/cm-functions.md#mean)函数。

   * [!UICONTROL **中间值**]：创建一个新列，以显示该列维度元素集的中间值。 这使用[Median](/help/components/calc-metrics/cm-functions.md#median)函数。

   * [!UICONTROL **列max**]：创建一个新列，以显示该列维度元素集的最大值。 这使用[Column Maximum](/help/components/calc-metrics/cm-functions.md#column-maximum)函数。

   * [!UICONTROL **列min**]：创建一个新列，以显示该列维度元素集的最小值。 这使用[Column Minimum](/help/components/calc-metrics/cm-functions.md#column-minimum)函数。

   * [!UICONTROL **列sum**]：创建一个新列，该列将某个量度的所有数值相加（跨维度的元素）。 这使用[列Sum](/help/components/calc-metrics/cm-functions.md#column-sum)函数。

   选择两列时，以下选项可用：

   * [!UICONTROL **除**]：创建一个新列来除以两个选定列的值。

   * [!UICONTROL **减**]：创建减去两个选定列的值的新列。

   * [!UICONTROL **添加**]：创建一个新列，用于添加两个选定列的值。

   * [!UICONTROL **乘**]：创建将两个选定列的值相乘的新列。

   * [!UICONTROL **百分比变化**]：创建一个新列，以显示两个选定列的百分比变化。

[计算指标：无实施指标](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=zh-Hans) (3:42)


