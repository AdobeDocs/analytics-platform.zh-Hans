---
description: Adobe提供各种您可以使用的计算指标。 本页列出了这些量度及其预期用途。
title: 默认计算量度
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
source-git-commit: 5e69b1aceb767343882b9cc85c0011bb1593f4af
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 25%

---

# 默认计算量度

Customer Journey Analytics提供了以下计算量度以涵盖最常见的用例：

| 计算指标名称 | 描述 | 公式 |
|---------|----------|---------|
| 会话开始比率 | 在会话的第一个事件中发生任何维度项目的百分比。<p>此计算量度在包含 `[Session Starts]` [标准组件](/help/data-views/component-reference.md) 在您的 [数据视图](/help/data-views/create-dataview.md).</p> | `[Session Starts] / [Sessions]` |
| 每人逗留时间 | 某人在任何给定维度项上逗留的平均时间。<p>此计算量度在包含 `[Time Spent (seconds)]` [标准组件](/help/data-views/component-reference.md) 在您的 [数据视图](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Users]` |
| 每人的会话 | 每个人的平均会话数。 | `[Sessions] / [Users]` |
| 每个会话逗留时间 | 每个会话在任何给定维度项上逗留的平均时间。<p>此计算量度在包含 `[Time Spent (seconds)]` [标准组件](/help/data-views/component-reference.md) 在您的 [数据视图](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Sessions]` |
| 会话结束比率 | 在会话的最后一个事件中发生的任何维度项目的百分比。 <p>此计算量度在包含 `[Session Ends]` [标准组件](/help/data-views/component-reference.md) 在您的 [数据视图](/help/data-views/create-dataview.md).</p> | `[Session Ends] / [Sessions]` |

{style="table-layout:auto"}
