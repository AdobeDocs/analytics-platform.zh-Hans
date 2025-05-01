---
title: 将量子量度摩擦事件添加到Customer Journey Analytics
description: 将Quantum Metric收集的摩擦事件添加到Customer Journey Analytics行为数据，以加深对CJA的分析。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: 1b7d5159-39b2-4ba4-be64-f448ae53c70e
source-git-commit: 11dc62cda2ceb7afabd3abd0944420601c8fa235
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 1%

---

# 将量子量度摩擦事件添加到Customer Journey Analytics

Quantum Metric收集页面加载缓慢、页面加载错误、范围点击等摩擦事件。 这些事件可以作为用户历程中的补充事件传递到Customer Journey Analytics。 利用这些组合数据，您可以更好地了解摩擦对下游指标的影响。

## 先决条件：

此用例有两个要求：

* 您必须有权使用Quantum量度的&#x200B;**开发操作**&#x200B;包。
* 您必须使用Adobe Experience Platform数据收集中的标记。

## 步骤1：创建架构字段以容纳量子量度摩擦事件

此使用案例需要专用架构字段才能将数据发送到。 您可以在架构中的任意所需位置创建此字段，然后根据需要对其进行命名。 如果您的组织对名称或位置没有首选项，则会提供示例值。

1. 登录到[experience.adobe.com](https://experience.adobe.com)。
1. 导航到&#x200B;**[!UICONTROL 数据收集]** > **[!UICONTROL 架构]**。
1. 从列表中选择所需的架构。
1. 选择所需对象旁边的![添加字段图标](/help/assets/icons/AddCircle.svg)图标。 例如，在`Implementation Details`旁边。
1. 在右侧，输入所需的[!UICONTROL 名称]。 例如，`qmErrorName`。
1. 输入所需的[!UICONTROL 显示名称]。 例如，`Quantum Metric error name`。
1. 选择[!UICONTROL 类型]作为&#x200B;**[!UICONTROL 字符串]**。
1. 选择&#x200B;**[!UICONTROL 保存]**。

## 步骤2：使用量子量度标记扩展捕获摩擦事件

有关如何设置标记以包含Quantum量度数据的说明，请参阅Adobe Experience Platform目标指南中的[Quantum量度扩展](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric)。 使用此扩展可将更多行传递到现有数据集。

使用Adobe Experience Platform数据收集中的标记手动设置摩擦事件的名称，以便将其包含在XDM对象中并进行分析。 一种方法是使用规则的自定义代码：

```js
_satellite.setVar('qm_error_name','error rage click');
return true;
```

然后，将动态设置的数据元素添加到XDM对象：

![Quantum量度错误名称屏幕快照](assets/error-name.png)

## 步骤3：将一个或多个维度和量度添加到Customer Journey Analytics中的数据视图

编辑现有数据视图，在Customer Journey Analytics中将会话ID添加为可用维度。

1. 登录到[experience.adobe.com](https://experience.adobe.com)。
1. 导航到Customer Journey Analytics，然后在顶部菜单中选择&#x200B;**[!UICONTROL 数据视图]**（可选），从&#x200B;**[!UICONTROL 数据管理]**&#x200B;中选择。
1. 选择所需的现有数据视图。
1. 在左侧找到“量子量度摩擦”事件字段列表，并将其拖动到中间的量度区域。
1. 在右窗格中，将[包含/排除值](/help/data-views/component-settings/include-exclude-values.md)设置设置为要跟踪的所需摩擦事件。 您可以将多个摩擦事件添加到同一量度以组合它们。 您还可以将摩擦事件字段的另一个副本拖动到量度区域，以作为单独的量度跟踪其他摩擦事件。
1. 创建所有所需的维度和量度后，单击&#x200B;**[!UICONTROL 保存]**。
1. 有关错误事件的完整列表，请参阅您的Quantum度量文档。 如果您还有其他问题，请与您的Quantum Metric客户支持代表联系，或通过[Quantum Metric客户请求门户](https://community.quantummetric.com/s/public-support-page)提交请求。

## 第4步：在Analysis Workspace中将维度和量度与其余数据结合使用

通过量度摩擦事件数据与您的其余访客数据一起收集，您可以像在Customer Journey Analytics中使用任何其他维度或量度一样使用这些数据。

1. 登录到[experience.adobe.com](https://experience.adobe.com)。
1. 导航到Customer Journey Analytics，然后在顶部菜单中选择&#x200B;**[!UICONTROL Workspace]**。
1. 选择现有项目，或创建项目。
1. 创建[自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。
1. 将所需的维度和量度拖动到Workspace画布以供分析。

可能的分析想法包括：

* 随时间呈现摩擦事件数据的趋势
* 在流失或漏斗可视化图表中，将Customer Journey Analytics事件作为某些步骤添加，并将量子量度摩擦事件作为其他步骤添加。 通过此报告，您可以查看访客最常遇到问题的地方。
* 为体验摩擦事件的访客创建并应用区段，以便进行更深入的分析
