---
title: 数据馈送中的分段
description: 了解如何将区段应用于Customer Journey Analytics数据馈送，并了解日期范围区段如何与馈送的报表窗口进行交互。
keywords: 点击流；数据馈送；数据馈送；分段；区段；日期范围
feature: Components
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: c7fc5df2a0fd7393b48bfe6bdfa7dccdfffde46c
workflow-type: tm+mt
source-wordcount: 357
ht-degree: 0%

---


# 数据馈送中的分段

{{release-limited-testing}}

Customer Journey Analytics中的数据馈送支持分段，以便您过滤每个馈送交付中包含的行。 您可以在数据视图级别、馈送级别应用区段，或同时应用两者。

## 应用区段的地方

您可以将区段应用到数据馈送中的两个位置：

- **数据视图**：在数据视图中配置的区段，适用于使用该数据视图的所有馈送。
- **数据馈送**：除了任何数据视图区段之外，还直接应用于单个馈送的区段。

配置这两个区段后，Customer Journey Analytics会将其合并 — 只有满足这两个区段的行才会包含在信息源输出中。

## 包含日期范围的区段

您可以在数据馈送中使用包含日期范围的区段。 但是，报告窗口始终由信息源的计划提交（每小时或每天）定义。 如果区段包含日期范围，则它会过滤数据馈送窗口中的行，而不会移动或展开窗口本身。

这与Analysis Workspace不同，在后一种情况下，应用包含日期范围的区段会更改活动报表窗口以匹配区段的日期范围。

## 区段鉴别和回顾日期范围

对于使用人员或会话容器的区段，资格由&#x200B;**回顾日期范围**&#x200B;设置决定，而不只是投放时间范围决定。 如果人员在回顾日期范围内符合条件，则包含该人员在投放窗口中的所有事件。 容器设置确定范围：

- **事件容器**：仅包含与投放窗口中的区段条件匹配的事件。
- **会话容器**：包括投放窗口内符合条件的会话中的所有事件，其中会话资格将在回看日期范围内进行评估。
- **人员容器**：对于在回顾日期范围内符合条件的任何人员，将包含投放窗口内的所有事件。

有关回顾日期范围及其对区段鉴别的影响的详细信息，请参阅[创建数据馈送](/help/components/exports/cja-data-feeds/create-feed.md)。

