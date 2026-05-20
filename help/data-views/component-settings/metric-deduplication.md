---
title: 重复量度删除组件设置
description: 仅计入量度在报告中第一次出现的情况。
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
role: Admin
autotag-review: '2026-05-19T09:10:57.728Z'
TQID: 'https://experienceleague.adobe.com/bCgBjD9r0cQ3O73fEip-EQHItMHQSX-2AECydDxR9Ms'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 342
ht-degree: 79%

---

# 重复量度删除组件设置 {#metric-deduplication-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_deduplication"
>title="重复量度删除"
>abstract="将量度配置为仅对不重复出现的值进行计数。"

<!-- markdownlint-enable MD034 -->


通过重复量度删除，可将量度配置为仅对不重复出现的值进行计数。

![重复量度删除](../assets/metric-deduplication.png)

| 设置 | 描述 |
| --- | --- |
| [!UICONTROL 重复量度删除] | 一个复选框，通过它，可启用重复量度删除。 默认禁用。 |
| [!UICONTROL 重复数据删除范围] | 使您可决定唯一检查回溯多远。<br/>**[!UICONTROL 全局帐户&#x200B;]**：只计算报表时段中第一次出现该量度的日期。<br/>**[!UICONTROL 帐户]**：只计算报表时段中第一次出现该量度的日期。<br/>**[!UICONTROL 机会&#x200B;]**：只计算报表时段中第一次出现该量度的日期。<br/>**[!UICONTROL 购买群组]**：只计算报表时段中第一次出现该量度的时间。<br/>**[!UICONTROL 人员&#x200B;]**：只计算报表时段中第一次出现该量度的时间。<br>**[!UICONTROL 会话]**：只计算会话第一次出现该量度的时间。<br> |
| [!UICONTROL 重复数据删除 ID] | 并非对量度本身应用重复数据删除，而是使您可根据维度应用重复量度删除。 对于“购买 ID”等维度应用重复数据删除很有用。 |
| [!UICONTROL 要保留的值] | <ul><li>**保留第一个实例**：如果量度的初始实例有效，则使用此项。 最常见的情况可能是购买确认。 即使有人无意中重新加载了页面，使我们得到的是购买确认的另一个实例，但初始事件仍有效。</li><li>**保留最后一个实例**：如果收集最后一个实例更有意义，则使用此项。 示例：某人更新自己的在线轮廓。 我们只需在每个会话中计算这些更新的其中之一。 但是，他们可能会在会话期间多次更新自己的轮廓。 如果我们保留第一个实例，则可能会有与该事件无关的活动。 在这种情况下，保留最后一个实例更有意义。</li></ul> |

{style="table-layout:auto"}

>[!CAUTION]
>
>在 UTC 时间的足月前评估在&#x200B;_人员_&#x200B;范围的重复数据删除。 如果某些实例发生在足月内但在报告日期外，则不足月报告时段可能并不显示所有第一个或最后一个实例。
