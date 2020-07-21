---
title: 动态与静态维度值
description: 如何与表中的动态和静态维值交互。
translation-type: tm+mt
source-git-commit: 0477302df92ccab30d9f3a45cc7b22f2112a0c70
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 8%

---


# 自由形式表中的动态维值与静态维值

>[!NOTE]您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html) 略有不同。[了解更多...](/help/getting-started/cja-aa.md)

在自由形式表中，行和列可以包含其中的各种组件值。 这些值可以是动态的（随时间而更改），也可以是静态的（不随时间而更改），具体取决于要构建的分析。

## 动态维度值

动态维值会随时间而改变，并取决于在自由形式表中按排序的度量。 如果要分析给定时间段的顶项，则首选动态维值。

将维放入自由形式表时，将返回动态行。 它们表示与给定度量和时间段的维度对应的顶级项目。 您还可以将维拖放到自由形式表列中，该维会自动扩展到前5个维值。

例如，将“浏览器类型”维拖入表中时，顶部的“浏览器类型”维值（如Microsoft、Apple、Google等） 动态返回到表行。 如果放入列中，前5个浏览器类型维值将动态返回。

动态维值具有行过滤器选项， **不存** 在锁和X图标。

## 静态维值

静态维值不随时间而改变； 它们是自由形式表中始终返回的固定组件。 如果您希望始终分析同一项目(无论是特定活动还是一周中的特定天)，则首选使用静态维度值。

每当您手动选择特定组件值（维度、度量、段、日期范围）并将其拖放到表中时，结果就是行或列的静态列表。 如果选择：

* 从行中，右键单击> [!UICONTROL 仅显示选定行]
* 从列中，右键单击>将项设 [!UICONTROL 置为静态]

例如，当您拖过Microsoft和Apple等特定的浏览器类型项目时，这2个特定项目始终会被拖入表中。

静态维值 **没有** 行筛选器选项。 相反，锁和X图标显示在每个项目上。 单击X图标以从表中删除该维值。

## 混合维度值

不同维的维值可以添加到同一表中。 在这些情况下，行标题将显示“混合维”。 这些维值是静态的。 例如，从浏览器类型维添加特定维值，从浏览器维添加其他维值。

## 自由形式总行数

动态行和静态行在自由形式总行中的行为不同。 默认情况下：

* 动态行是对服务器端和去重复度量(如访问或访客)进行汇总的
* 静态行是在客户端求和的， **不会** 去重复度量。

[了解有关动态行和静态行](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/build-workspace-project/workspace-totals.html) “工作区总选项”的更多信息。
