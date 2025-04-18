---
description: Adobe 提供了各种可供您使用的计算量度。此页面列出了这些量度及其预期用途。
title: 计算量度模板
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: eb9b749a5c61da3b4b5d2eeeed93bf5e4702a415
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 97%

---

# 计算量度模板

 Customer Journey Analytics 提供以下计算量度模板，以涵盖最常见的用例。这些Adobe定义的计算量度由一个![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg)小型徽标来标识。 要快速过滤这些量度，请在[组件过滤器](/help/components/overview.md#filter)中选择![标签](/help/assets/icons/Label.svg) **[!UICONTROL Adobe 模板]**。

| 计算量度名称 | 描述<br/>公式 |
|---------|----------|
| **[!UICONTROL 会话开始比率]** | 任何维度项在会话的第一个事件上出现的百分比。<p>当您将[!UICONTROL 会话开始][标准组件](/help/data-views/component-reference.md)纳入您的[数据视图](/help/data-views/create-dataview.md)时，此计算量度会自动添加到工作区。</p>摘要：**（** ![事件](/help/assets/icons/Event.svg) **会话开始** ![划分](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **会话** **）** |
| **[!UICONTROL 每人逗留时间]** | 某人在任何给定维度项上逗留的平均时间。<p>当您将[!UICONTROL 逗留时间（秒）][标准组件](/help/data-views/component-reference.md)纳入您的[数据视图](/help/data-views/create-dataview.md)时，此计算量度会自动添加到工作区。“排除会话中的最后一个事件”过滤器已应用于“人员”量度。该过滤器会排除数据集中每个会话的最后一个事件。这种排除功能可帮助您在排除最终操作本身的同时，分析导致事件或操作（如购买或提交表单）的用户行为。</p>摘要：**（** ![事件](/help/assets/icons/Event.svg) **逗留时间（秒）** ![划分](/help/assets/icons/Divide.svg) ![分段](/help/assets/icons/Segmentation.svg) **排除会话的最后一个事件（** ![事件](/help/assets/icons/Event.svg) **人员））** |
| **[!UICONTROL 每人的会话次数]** | 每个人的平均会话次数。<p>摘要：**（** ![事件](/help/assets/icons/Event.svg) **会话** ![划分](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **人员** **）** |
| **[!UICONTROL 每次会话逗留的时间]** | 每个会话在任何给定维度项上逗留的平均时间。<p>当您将[!UICONTROL 逗留时间（秒）][标准组件](/help/data-views/component-reference.md)纳入您的[数据视图](/help/data-views/create-dataview.md)时，此计算量度会自动添加到工作区。“排除会话中的最后一个事件”过滤器已应用于“会话”量度。该过滤器会排除数据集中每个会话的最后一个事件。这种排除功能可帮助您在排除最终操作本身的同时，分析导致事件或操作（如购买或提交表单）的用户行为。</p>摘要：**（** ![事件](/help/assets/icons/Event.svg) **逗留时间（秒）** ![划分](/help/assets/icons/Divide.svg) ![分段](/help/assets/icons/Segmentation.svg) **排除会话的最后一个事件（** ![事件](/help/assets/icons/Event.svg) **会话））** |
| **[!UICONTROL 会话结束率]** | 任何维度项在会话的最后一个事件上出现的百分比。 <p>当您将[!UICONTROL 会话结束][标准组件](/help/data-views/component-reference.md)纳入您的[数据视图](/help/data-views/create-dataview.md)时，此计算量度会自动添加到工作区。</p>摘要：**（** ![事件](/help/assets/icons/Event.svg) **会话结束** ![划分](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **会话** **）** |
| **[!UICONTROL Web 会话]** | 网站上发生的会话数。 |
| **[!UICONTROL 调查完成率]** | 人们开始调查后完成调查的比率。 |
| **[!UICONTROL 多渠道会话比率]** | 包含多个渠道（例如网络流量和移动流量）的会话与仅包含单个渠道的会话之间的比率。 |
| **[!UICONTROL 多渠道人数比率]** | 参与多个渠道的人数与仅参与单个渠道的人数的比例。 |
| **[!UICONTROL 移动应用程序会话]** | 移动应用程序上发生的会话数。 |
| **[!UICONTROL Web + 应用程序跨渠道会话]** | 发生的会话数（包括网络流量和移动流量）。 |
| **[!UICONTROL 通话成本]** | 呼叫中心通话的总成本。<!-- <p>Summary: Call length</p> --> |
| **[!UICONTROL 平均通话持续时间]** | 呼叫中心接到的通话的平均持续时间。 |
| **[!UICONTROL 每次通话的平均成本]** | 呼叫中心接到的通话的平均成本。 |
| **[!UICONTROL 平均通话调查得分]** | 有关呼叫中心接到的通话的平均调查分数。 |

{style="table-layout:auto"}
