---
description: 了解有关 Adobe Analysis Workspace 及其相关组件中的已知限制
title: 已知限制
feature: Workspace Basics
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: ht
source-wordcount: '307'
ht-degree: 100%

---

# 已知限制

以下是 Analysis Workspace 及其相关组件中的已知限制列表：

## 表格

* 将日期范围或量度用作表的行时，无法添加日期比较列。
* 当区段用作表的行时，将禁用通过所选内容创建量度。此外，通过所选内容创建量度不应应用于日期对齐列。
* 划分行的条件格式不能使用自定义范围。
* 当应用通过汇总行值设置来计算总数时（通常与静态行项目一起使用），表总行数不能趋势化。

## 可视化图表

* 使用区段的可视化图表（如[!UICONTROL 流失]、[!UICONTROL 流量]、[!UICONTROL 同类群组]和[!UICONTROL 直方图]）不能接受计算量度作为输入。
* [!UICONTROL 流量]：登入/退出维度（例如，[!UICONTROL 进入页面]）不能在流量中使用。
* [!UICONTROL 同类群组]：非整数不能用作同类群组标准。

## 区段

* 某些量度和维度不可分段，如[!UICONTROL 事件]、[!UICONTROL 人员]等。
* 在[面板放置区](/help/analysis-workspace/c-panels/panels.md)中创建的临时区段是一种快速区段。它们不出现在 Workspace 的左侧面板或区段管理器中，除非它们被公开。有关更多信息，请参阅[快速区段](/help/components/segments/seg-quick.md)。

## 计算量度

* 计算量度不能用于某些可视化图表。请参阅[可视化图表](#visualizations)。
* 计算量度无法在[!UICONTROL 归因]面板中使用，因为计算量度本身可以包括单独的归因模型。
* 如果从 Workspace 创建计算量度（而不是从[!UICONTROL 组件 > 区段]创建），则某些组件和操作符不可用。例如，[!UICONTROL IP 地址]。

## 日期范围

* 自定义日期范围不支持[!UICONTROL 去年今日]、[!UICONTROL 上个月今日]，等等。


## 报告设置

* [!UICONTROL 报告设置]页面上的某些设置不适用。Analysis Workspace 只使用底部的[!UICONTROL 语言/货币/编码]设置：[!UICONTROL 千位分隔符]、[!UICONTROL 计划报告编码]和 [!UICONTROL CSV 分隔符]。

