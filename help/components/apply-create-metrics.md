---
description: 有两种方式可使用 Analysis Workspace 中的指标。
title: 量度
feature: Metrics
exl-id: 4edfb5d7-da20-4bd8-8041-387b291daf96
source-git-commit: 202a726dc68853f55a24e566c656c92785e3b3f0
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 51%

---

# 指标

指标允许您量化 Analysis Workspace 中的数据点。它们最常用作可视化中的列，并与维度相关联。

## 指标类型

Adobe 提供了多种类型的指标，可供在 Analysis Workspace 中使用：

* **标准量度**：标准量度的示例包括人员、会话、事件。

* **计算量度** ![“计算量度”图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg)：基于标准指标、静态数字或算法函数的用户定义指标。

* **计算量度模板**  <img src="./assets/adobe-logo.svg" width="18"> ：Adobe定义的指标，其行为与计算指标类似。 您可以在 Workspace 项目中按原样使用它们，或保存副本以自定义其逻辑。


![UI中的量度](assets/cja-metrics.png)

您可以查看某个量度是否获得批准 ![“已批准”图标](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  还是不行。 如果您想了解有关某个量度的更多详细信息，请将指针悬停在该量度上，然后选择 ![信息图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg).


量度在Analysis Workspace中的使用非常灵活。 将一个指标拖到一个空的自由格式表中，以查看该指标在项目日期期间的趋势。当存在维度时，您还可以拖动量度，以查看该量度与每个维度项目的比较。 将量度拖动到现有量度标题之上会替换该量度，将量度拖动到标题旁会让您并排查看这两个量度。

## 计算指标

通过计算指标，您可以使用简单的运算符或统计函数轻松查看指标之间的相互关系。可通过以下几种方式创建计算指标：

您可以选择 **[!UICONTROL 组件]** > **[!UICONTROL 计算量度]**. 这会将您转到 [计算指标生成器](/help/components/calc-metrics/calc-metr-overview.md)，您可以从现有量度构建自定义量度。

为了更便于快速创建计算量度，**[!UICONTROL 从所选内容创建量度]**&#x200B;已添加到自由格式表中的列右键单击菜单。在选定一个或多个标头列单元格时，会显示该选项。

![从选定范围中创建](assets/create-metric-from-selection.png)

[计算指标：无实施指标](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=zh-Hans) (3:42)

## 比较不同归因模型的指标

如果您希望快速轻松地将一个归因模型与另一个归因模型进行比较，请右键单击某个量度并选择 **[!UICONTROL 比较归因模型]**：

![比较归因模型](assets/compare-attribution.png)

此快捷键可让您快速、轻松地将一个归因模型与另一个归因模型进行比较，而无需将归因模型拖动到某个量度中且不必对其进行两次配置。
