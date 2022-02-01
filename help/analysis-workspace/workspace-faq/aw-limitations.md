---
description: Adobe Analysis Workspace 及其相关组件中的已知限制列表
title: Analysis Workspace 中的已知限制
feature: FAQ
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 69%

---

# Analysis Workspace 中的已知限制

以下是 Analysis Workspace 及其相关组件中的已知限制列表：

## 表格

* 将日期范围或量度用作表的行时，无法添加日期比较列。
* 当过滤器用作表的行时，将禁用通过所选内容创建量度。 此外，通过所选内容创建量度不应应用于日期对齐列。
* 划分行的条件格式不能使用自定义范围。
* 当应用通过汇总行值设置来计算总数时（通常与静态行项目一起使用），表总行数不能趋势化。
* [!UICONTROL 贡献分析]只能在&#x200B;__[!UICONTROL 每日]粒度下运行。它不能针对[!UICONTROL 每小时]、[!UICONTROL 每周]等数据运行。

## 可视化图表

* 利用过滤器的可视化图表，例如 [!UICONTROL 流失], [!UICONTROL 流量], [!UICONTROL 同类群组]和 [!UICONTROL 直方图]，无法接受计算量度作为输入。
* [!UICONTROL 流量]：登入/退出维度（例如，[!UICONTROL 进入页面]）不能在流量中使用。
* [!UICONTROL 同类群组]：非整数不能用作同类群组标准。

## 组件>过滤器

* 某些量度和维度无法过滤，例如 [!UICONTROL 发生次数], [!UICONTROL 独特访客]等。
* 在 [面板拖放区域](/help/analysis-workspace/c-panels/panels.md) 将不会显示在工作区或过滤器组件管理器的左边栏中，除非将它们公开。 可以通过编辑过滤器并选择 **[!UICONTROL 将此过滤器设为公用]**.

## “组件”>“计算量度”

* 计算量度不能用于某些可视化图表。请参阅上面的“可视化”。
* 计算量度无法在[!UICONTROL 归因]面板中使用，因为计算量度本身可以包括单独的归因模型。
* 如果从工作区中创建计算量度（而不是从中创建），则某些组件和运算符将不可用 [!UICONTROL 组件>过滤器])。 例如，[!UICONTROL IP 地址]。

## “组件”>“日期范围”

* 自定义日期范围不支持[!UICONTROL 去年今日]、[!UICONTROL 上个月今日]，等等。


## “组件”>“报表设置”

* [!UICONTROL 报表设置]页面上的某些设置不适用。Analysis Workspace 只使用底部的[!UICONTROL 语言/货币/编码]设置：[!UICONTROL 千位分隔符]、[!UICONTROL 计划报表编码]和 [!UICONTROL CSV 分隔符]。

## 归因 IQ

* [!UICONTROL 归因 IQ] 中不支持量度的子集。有关完整列表，请参阅[归因 IQ 常见问题解答](../attribution/faq.md)。
