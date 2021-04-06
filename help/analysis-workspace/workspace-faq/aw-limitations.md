---
description: Adobe Analysis Workspace 及其相关组件中的已知限制列表
title: Analysis Workspace 中的已知限制
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 69%

---

# Analysis Workspace 中的已知限制

以下是 Analysis Workspace 及其相关组件中的已知限制列表：

## 表格

* 将日期范围或量度用作表的行时，无法添加日期比较列。
* 将过滤器用作表的行时，将禁用从选择创建量度。 此外，通过所选内容创建量度不应应用于日期对齐列。
* 划分行的条件格式不能使用自定义范围。
* 当应用通过汇总行值设置来计算总数时（通常与静态行项目一起使用），表总行数不能趋势化。
* [!UICONTROL 贡献分析]只能在&#x200B;__[!UICONTROL 每日]粒度下运行。它不能针对[!UICONTROL 每小时]、[!UICONTROL 每周]等数据运行。

## 可视化

* 利用过滤器（如[!UICONTROL Flous]、[!UICONTROL Flow]、[!UICONTROL Coother]和[!UICONTROL Histogram]）的可视化无法接受计算量度作为输入。
* [!UICONTROL 流量]：登入/退出维度（例如，[!UICONTROL 进入页面]）不能在流量中使用。
* [!UICONTROL 同类群组]：非整数不能用作同类群组标准。

## 组件>过滤器

* 某些量度和维度无法筛选，如[!UICONTROL 发生次数]、[!UICONTROL 唯一访客]等。
* 在[面板拖放区](/help/analysis-workspace/c-panels/panels.md)中创建的临时过滤器将不会显示在Workspace或过滤器组件管理器的左边栏中，除非公开它们。 这可以通过编辑过滤器并选择&#x200B;**[!UICONTROL 将此过滤器设为公用]**&#x200B;来完成。

## “组件”>“计算量度”

* 计算量度不能用于某些可视化图表。请参阅上面的“可视化”。
* 计算量度无法在[!UICONTROL 归因]面板中使用，因为计算量度本身可以包括单独的归因模型。
* 如果从Workspace创建计算量度(与从[!UICONTROL 组件>过滤器]创建相比)，则某些组件和运算符不可用。 例如，[!UICONTROL IP 地址]。

## “组件”>“日期范围”

* 自定义日期范围不支持[!UICONTROL 去年今日]、[!UICONTROL 上个月今日]，等等。


## “组件”>“报表设置”

* [!UICONTROL 报表设置]页面上的某些设置不适用。Analysis Workspace 只使用底部的[!UICONTROL 语言/货币/编码]设置：[!UICONTROL 千位分隔符]、[!UICONTROL 计划报表编码]和 [!UICONTROL CSV 分隔符]。

## 归因 IQ

* [!UICONTROL 归因 IQ] 中不支持量度的子集。有关完整列表，请参阅[归因 IQ 常见问题解答](../attribution/faq.md)。
