---
description: 了解
title: 指标类型和归因
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '188'
ht-degree: 100%

---

# 指标类型和归因

选择指标旁边的齿轮图标允许您指定指标类型和归因模型。

## 指标类型

![](assets/cm_type_alloc.png)

| 指标类型 | 定义 |
|---|---|
| 标准 | 这些指标是在标准 [!DNL Analytics] 报表中使用的相同指标。如果公式包含一个标准指标，它会显示与其相对的非计算指标的相同数据。标准指标可用于创建特定于每个单独行项目的计算指标。例如，[订购次数]/[访问次数]是将特定行项目的订购次数除以特定行项目的访问次数。 |
| 合计 | 使用每个行项目中报告时段的合计。如果公式包含一个合计指标，它会显示每个行项目中的相同合计数。合计指标可用于创建与网站合计数据相比较的计算指标。例如，[订购次数]/[总访问次数]会显示订购次数与网站所有访问次数的比例，而不只是与特定行项目访问次数的比例。 |

## 归因

>[!IMPORTANT]
>有关支持的非默认归因模型和回溯时段的完整列表，请参阅[归因模型和回溯时段](/help/analysis-workspace/attribution/models.md)。
