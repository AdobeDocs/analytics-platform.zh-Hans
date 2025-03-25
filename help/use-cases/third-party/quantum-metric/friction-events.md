---
title: 将量子量度摩擦事件添加到Customer Journey Analytics
description: 使用在量子量度中收集的摩擦事件，在Customer Journey Analytics中增加深入见解。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: 1b7d5159-39b2-4ba4-be64-f448ae53c70e
source-git-commit: 10a70743d292e50ca5aea3225897e7097fa4fc8a
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 0%

---

# 将量子量度摩擦事件添加到Customer Journey Analytics

Quantum Metric收集页面加载缓慢、页面加载错误、范围点击等摩擦事件。 这些事件可以作为用户历程中的补充事件传递到Customer Journey Analytics。 利用这些组合数据，您可以更好地了解摩擦对下游指标的影响。

## 先决条件：

此用例有两个要求：

* 您必须有权使用Quantum量度的&#x200B;**开发操作**&#x200B;包。
* 您必须使用Adobe Experience Platform数据收集中的标记。

## 步骤1：使用量子量度标记扩展捕获摩擦事件

Quantum Metric CSM团队可帮助您确定要添加的正确架构元素，并帮助您修改实施以收集要在Customer Journey Analytics中使用的所需数据。 有关更多信息，请与您的Quantum Metric客户成功经理联系。

最终，您将希望开始跟踪字段中的摩擦事件名称。

## 步骤2：确认包含的数据集字段

确认连接中的数据集现在具有所需数据集中的量子量度会话ID。

## 步骤3：将一个或多个维度和量度添加到Customer Journey Analytics中的数据视图

编辑现有数据视图，在Customer Journey Analytics中将会话ID添加为可用维度。

1. 登录到[experience.adobe.com](https://experience.adobe.com)。
1. 导航到Customer Journey Analytics，然后在顶部菜单中选择&#x200B;**[!UICONTROL 数据视图]**。
1. 选择所需的现有数据视图。
1. 在左侧找到“量子量度摩擦”事件字段列表，并将其拖动到中间的量度区域。
1. 在右窗格中，将[包含/排除值](/help/data-views/component-settings/include-exclude-values.md)设置设置为要跟踪的所需摩擦事件。 您可以将多个摩擦事件添加到同一量度以组合它们。 您还可以将摩擦事件字段的另一个副本拖动到量度区域，以作为单独的量度跟踪其他摩擦事件。
1. 创建所有所需的维度和量度后，单击&#x200B;**[!UICONTROL 保存]**。

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
* 为体验摩擦事件的访客创建并应用过滤器，以便进行更深入的分析
