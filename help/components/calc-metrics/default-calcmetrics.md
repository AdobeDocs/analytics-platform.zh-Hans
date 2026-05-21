---
description: Adobe 提供了各种可供您使用的计算量度。 此页面列出了这些量度及其预期用途。
title: 计算量度模板
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
TQID: https://experienceleague.adobe.com/-jngIXgXeFZZkfL5jSHLuX8ZmcWU5rIfLqb26ovn6QY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 549
ht-degree: 85%

---

# 计算量度模板

Customer Journey Analytics提供了以下计算量度模板以涵盖最常见的用例。 这些由 Adobe 定义的计算量度通过一个 ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) 小徽标被标识。 要快速筛选这些量度，请在[组件筛选器](/help/components/overview.md#filter)中选择![标签](/help/assets/icons/Label.svg) **[!UICONTROL Adobe模板]**。

| 计算量度名称 | 描述<br/>公式 |
|---------|----------|
| **[!UICONTROL 会话开始比率]** | 任何维度项在会话的第一个事件上出现的百分比。<p>当您将[!UICONTROL 会话开始][标准组件](/help/data-views/component-reference.md)纳入您的[数据视图](/help/data-views/create-dataview.md)时，此计算量度会自动添加到工作区。</p>摘要：**（** ![事件](/help/assets/icons/Event.svg) **会话开始** ![划分](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **会话** **）** |
| **[!UICONTROL 每人逗留时间]** | 某人在任何给定维度项上逗留的平均时间。<p>当您将[!UICONTROL 逗留时间（秒）][标准组件](/help/data-views/component-reference.md)纳入您的[数据视图](/help/data-views/create-dataview.md)时，此计算量度会自动添加到工作区。 “排除最后一个会话事件”区段将应用于“人员”量度。 区段不包括数据集中每个会话的最后一个事件。 这种排除功能可帮助您在排除最终操作本身的同时，分析导致事件或操作（如购买或提交表单）的用户行为。</p>摘要：**（** ![事件](/help/assets/icons/Event.svg) **逗留时间（秒）** ![划分](/help/assets/icons/Divide.svg) ![分段](/help/assets/icons/Segmentation.svg) **排除会话的最后一个事件（** ![事件](/help/assets/icons/Event.svg) **人员））** |
| **[!UICONTROL 每人的会话次数]** | 每个人的平均会话次数。<p>摘要：**（** ![事件](/help/assets/icons/Event.svg) **会话** ![划分](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **人员** **）** |
| **[!UICONTROL 每次会话逗留的时间]** | 每个会话在任何给定维度项上逗留的平均时间。<p>当您将[!UICONTROL 逗留时间（秒）][标准组件](/help/data-views/component-reference.md)纳入您的[数据视图](/help/data-views/create-dataview.md)时，此计算量度会自动添加到工作区。 “排除会话的最后一个事件”区段将应用于“会话”量度。 区段不包括数据集中每个会话的最后一个事件。 这种排除功能可帮助您在排除最终操作本身的同时，分析导致事件或操作（如购买或提交表单）的用户行为。</p>摘要：**（** ![事件](/help/assets/icons/Event.svg) **逗留时间（秒）** ![划分](/help/assets/icons/Divide.svg) ![分段](/help/assets/icons/Segmentation.svg) **排除会话的最后一个事件（** ![事件](/help/assets/icons/Event.svg) **会话））** |
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
