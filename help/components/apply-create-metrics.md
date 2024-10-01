---
description: 可通过两种方式在 Analysis Workspace 中使用量度。
title: 量度
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 20%

---

# 指标

指标允许您量化 Analysis Workspace 中的数据点。它们最常用作可视化中的列，并与维度相关联。

## 指标类型

Adobe 提供了多种类型的指标，可供在 Analysis Workspace 中使用：


* **标准量度**：标准量度的示例包括人员、会话、事件。

* **计算指标** ![计算器](/help/assets/icons/Calculator.svg)：基于标准指标、静态数字或算法函数的用户定义指标。

* **计算量度模板** ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) ：Adobe定义的与计算量度行为相似的量度。 您可以在Workspace项目中按原样使用它们，也可以保存副本以自定义逻辑。

您可以查看某个量度是否获得批准![批准图标](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)。 如果您想了解有关某个量度的更多详细信息，请将鼠标悬停在该量度上，然后选择![信息图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)。 有关详细信息，请参阅[组件信息](use-components-in-workspace.md#component-info)。



## 在 Analysis Workspace 中使用量度

量度在Analysis Workspace中的使用非常灵活。 将量度拖动到空的自由格式表，可查看在项目日期期间该量度的趋势。 此外，您还可以拖曳存在维度的量度，以便将该量度与每个维度项目进行比较。 将量度拖动到现有量度标题上方会替换该量度，如果将量度拖动到标题旁边，则可以并排查看这两个量度。

有关如何将量度和其他类型的组件添加到Analysis Workspace的信息，请参阅[在Analysis Workspace中使用组件](/help/components/use-components-in-workspace.md)。

## 计算量度

计算量度允许您使用简单的运算符或统计函数轻松配置量度之间的关系。 有关详细信息，请参阅[计算量度概述](/help/components/calc-metrics/calc-metr-overview.md)。

<!--

There are several ways to create calculated metrics. See [Create calculated metrics]()

### Create calculated metrics for all projects

You can use the calculated metric builder to create calculated metrics. When created in this way, calculated metrics are available in the component list and can then be used in projects throughout your organization. 

For information about how to access the calculated metrics builder, see [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

### Create calculated metrics for a single project

You can create quick calculated metrics that are available only for the project where they were created.

To create a calculated metric for a single project:

1. In Analysis Workspace, open the project where you want to create the calculated metric.

1. In a freeform table, select **[!UICONTROL Create metric from selection]** from the context menu in a column header.

   ![Workspace panel highlighting Create from selection](assets/create-metric-from-selection.png)

1. To create a calculated metric for this project only, choose from the following options:

   * [!UICONTROL **Divide**]
   
   * [!UICONTROL **Subtract**]

   * [!UICONTROL **Add**]

   * [!UICONTROL **Multiply**]

   Or, to open the calculated metric builder and create the calculated metric for all projects, select [!UICONTROL **Open in Calculated Metric Builder**], then continue with [Build metrics](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).


<!-- This video really shows an AA example using hits, etc.  Not suitable for CJA... >
+++ See the following video on how to create an implementation-less calculated metric from within Analysis Workspace.

[Calculated Metrics: Implementation-less metrics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html) (3:42)


>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

+++

-->

## 比较不同归因模型的指标

如果您想要轻松快速地将一个归因模型与另一个量度进行比较，请从量度的上下文菜单中选择&#x200B;**[!UICONTROL 比较归因模型]**。

![Workspace面板高亮显示比较归因模型](assets/compare-attribution.png)

此快捷键可让您快速轻松地比较归因模型。
