---
description: Adobe提供了多种您可以使用的计算指标。 本页列出了这些量度及其预期用途。
title: 计算量度模板
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: d37734ae415722fc609715868c37a36f2becdbf6
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 8%

---

# 计算量度模板

Customer Journey Analytics提供了以下计算指标模板，用于涵盖最常见的用例。 这些Adobe定义的计算指标由小型![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg)徽标标识。 若要快速筛选这些指标，请在[组件筛选器](/help/components/overview.md#filter)中选择![标签](/help/assets/icons/Label.svg) **[!UICONTROL Adobe模板]**。

| 计算量度名称 | 描述<br/>公式 |
|---------|----------|
| **[!UICONTROL 会话开始速率]** | 在会话的第一个事件中发生的任何维度项目的百分比。<p>当您在[数据视图](/help/data-views/create-dataview.md)中包含[!UICONTROL 会话开始] [标准组件](/help/data-views/component-reference.md)时，此计算量度会自动添加到Workspace。</p>摘要： **（** ![事件](/help/assets/icons/Event.svg) **会话开始** ![除](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **会话** **）** |
| 每个人&#x200B;**[!UICONTROL 逗留时间]** | 某人在任何给定维度项上逗留的平均时间。<p>当您在[数据视图](/help/data-views/create-dataview.md)中包含[!UICONTROL 逗留时间（秒）] [标准组件](/help/data-views/component-reference.md)时，此计算量度会自动添加到Workspace。 过滤器“排除会话的最后一个事件”应用于“人员”量度。 过滤器不包括数据集中每个会话的最后一个事件。 此排除项可帮助您分析导致事件或操作（例如购买或表单提交）的用户行为，同时排除最终操作本身。</p>摘要： **(** ![事件](/help/assets/icons/Event.svg) **逗留时间（秒）** ![除](/help/assets/icons/Divide.svg) ![分段](/help/assets/icons/Segmentation.svg) **排除会话的最后一个事件（** ![事件](/help/assets/icons/Event.svg) **人员） )** |
| 每人&#x200B;**[!UICONTROL 个会话]** | 每个人的平均会话数。<p>摘要： **（** ![事件](/help/assets/icons/Event.svg) **会话** ![分配](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **人员** **）** |
| 每个会话&#x200B;**[!UICONTROL 逗留时间]** | 每个会话在任何给定维度项上逗留的平均时间。<p>当您在[数据视图](/help/data-views/create-dataview.md)中包含[!UICONTROL 逗留时间（秒）] [标准组件](/help/data-views/component-reference.md)时，此计算量度会自动添加到Workspace。 过滤器“排除会话的最后一个事件”应用于“会话”量度。 过滤器不包括数据集中每个会话的最后一个事件。 此排除项可帮助您分析导致事件或操作（例如购买或表单提交）的用户行为，同时排除最终操作本身。</p>摘要： **(** ![事件](/help/assets/icons/Event.svg) **逗留时间（秒）** ![除](/help/assets/icons/Divide.svg) ![分段](/help/assets/icons/Segmentation.svg) **排除会话的最后一个事件（** ![事件](/help/assets/icons/Event.svg) **会话） )** |
| **[!UICONTROL 会话结束速率]** | 在会话的最后一个事件中发生的任何维度项目的百分比。 <p>当您在[数据视图](/help/data-views/create-dataview.md)中包含[!UICONTROL 会话结束] [标准组件](/help/data-views/component-reference.md)时，此计算量度会自动添加到Workspace。</p>摘要： **（** ![事件](/help/assets/icons/Event.svg) **会话结束** ![除](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **会话** **）** |

{style="table-layout:auto"}
