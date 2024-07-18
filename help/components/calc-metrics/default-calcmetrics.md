---
description: Adobe提供了多种您可以使用的计算指标。 本页列出了这些量度及其预期用途。
title: 默认计算量度
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 28%

---

# 默认计算量度

Customer Journey Analytics提供了以下计算指标以涵盖最常见的用例：

| 计算量度名称 | 描述 | 公式 |
|---------|----------|---------|
| 会话开始比率 | 在会话的第一个事件中发生的任何维度项目的百分比。<p>当您在[数据视图](/help/data-views/create-dataview.md)中包含`[Session Starts]` [标准组件](/help/data-views/component-reference.md)时，此计算量度会自动添加到Workspace中。</p> | `[Session Starts] / [Sessions]` |
| 每人逗留时间 | 某人在任何给定维度项上逗留的平均时间。<p>当您在[数据视图](/help/data-views/create-dataview.md)中包含`[Time Spent (seconds)]` [标准组件](/help/data-views/component-reference.md)时，此计算量度会自动添加到Workspace中。</p> | `[Time Spent (seconds)] / [Users]` |
| 每人的会话 | 每个人的平均会话数。 | `[Sessions] / [Users]` |
| 每个会话逗留时间 | 每个会话在任何给定维度项上逗留的平均时间。<p>当您在[数据视图](/help/data-views/create-dataview.md)中包含`[Time Spent (seconds)]` [标准组件](/help/data-views/component-reference.md)时，此计算量度会自动添加到Workspace中。</p> | `[Time Spent (seconds)] / [Sessions]` |
| 会话结束比率 | 在会话的最后一个事件中发生的任何维度项目的百分比。 <p>当您在[数据视图](/help/data-views/create-dataview.md)中包含`[Session Ends]` [标准组件](/help/data-views/component-reference.md)时，此计算量度会自动添加到Workspace中。</p> | `[Session Ends] / [Sessions]` |

{style="table-layout:auto"}
