---
title: 指标去重组件设置
description: 仅计入指标在报表中第一次出现的情况。
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: a236b2126c4b998b4d97caab014556e3ee3a9e83
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 100%

---

# 指标去重组件设置 {#metric-deduplication-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_metric_deduplication"
>title="量度去重"
>abstract="将某个量度配置为只有非重复发生的数量值。"

<!-- markdownlint-enable MD034 -->


通过指标去重，可将指标配置为仅以非重复的方式计入值。

![量度去重](../assets/metric-deduplication.png)

| 设置 | 描述 |
| --- | --- |
| [!UICONTROL 指标去重] | 一个复选框，通过它，可启用指标去重。默认禁用。 |
| [!UICONTROL 去重范围] | 使您可决定唯一检查回溯多远。<br>**会话**：仅计入会话第一次出现该指标的情况。<br>**人员**：仅计入报表时段中第一次出现该指标的情况。 |
| [!UICONTROL 去重 ID] | 并非对指标本身应用去重，而是使您可根据维度应用指标去重。对于“购买 ID”等维度应用去重很有用。 |
| [!UICONTROL 要保留的值] | <ul><li>**保留第一个实例**：如果指标的初始实例有效，则使用此项。最常见的情况可能是购买确认。即使有人无意中重新加载了页面，使我们得到的是购买确认的另一个实例，但初始事件仍有效。</li><li>**保留最后一个实例**：如果收集最后一个实例更有意义，则使用此项。示例：某人更新自己的在线配置文件。我们只需在每个会话中计算这些更新的其中之一。但是，他们可能会在会话期间多次更新自己的配置文件。如果我们保留第一个实例，则可能会有与该事件无关的活动。在这种情况下，保留最后一个实例更有意义。</li></ul> |

{style="table-layout:auto"}

>[!CAUTION]
>
>在 UTC 时间的足月前评估在&#x200B;_人员_&#x200B;范围的去重。如果某些实例发生在足月内但在报告日期外，则不足月报告时段可能并不显示所有第一个或最后一个实例。
