---
title: 归因组件设置
description: 允许您设置量度的默认归因。
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 69%

---


# 归因组件设置

归因允许您为量度设置默认归因模型。 在Analysis Workspace中工作时，您可以覆盖给定量度的归因模型。

![归因](../assets/attribution-settings.png)

| 设置 | 描述/用例 |
| --- | --- |
| [!UICONTROL 设置归因] | 在使用此量度时启用默认归因模型。 可以在[!UICONTROL 自由格式表格]或计算量度中覆盖此默认值。 |
| [!UICONTROL 归因模型] | 允许您指定要使用的默认[归因模型](/help/analysis-workspace/attribution/models.md)。 默认为[!UICONTROL 最近联系]。选项有：最近联系、首次联系、线性、参与率、同一接触、U 形、J 曲线、反向 J、时间衰减、自定义、算法。其中一些选项会创建需要填写的其他字段，例如“自定义”或“时间衰减”。您可以使用同一字段创建多个量度，这意味着您可以基于架构中的同一收入字段创建一个[!UICONTROL 最近联系]收入量度和一个[!UICONTROL 首次联系]收入量度。 |
| [!UICONTROL 回顾时间范围] | 允许您为量度指定默认回顾窗口。 选项有：[!UICONTROL 人员]（报告窗口）、[!UICONTROL 会话]、[!UICONTROL 自定义]。选择[!UICONTROL 自定义]时，您还可以选择天数/周数/月数/等（最长为 90 天），和 [!UICONTROL Attribution IQ] 一样。您可以使用同一架构字段创建多个量度，但每个量度都有不同的回顾时间范围。 |
