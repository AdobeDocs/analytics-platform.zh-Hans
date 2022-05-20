---
title: 归因最佳实践
description: 确定归因模型的最佳实践是什么？
feature: Attribution
exl-id: d612dc79-24e4-4d50-bccd-dfb58328bd4e
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: ht
source-wordcount: '391'
ht-degree: 100%

---

# 归因最佳实践

为您的组织选择适合的归因模型取决于许多考虑因素。本文探讨了一种方法论和一些通用的最佳实践。

## 步骤 1：探索性分析

>[!NOTE]
>此分析需要在您选择归因模型之前进行。

此阶段最初包括了解客户行为和定义转化量度。根据转化量度，Analysis Workspace 等工具以及从多个渠道获取数据源（例如，展示数据）可以帮助您更好地理解

* 在转化前有多少客户接触了不同的营销渠道？
* 这些行为的比例/分布。

例如，如果 50% 的客户在转化前接触了 3 个渠道，这 3 个渠道之间有什么互动吗？然后，您可以进行漏斗上层和漏斗下层分析以扩展您的理解。

### 漏斗上层分析

漏斗上层分析可分析用于创建品牌和产品意识的渠道。例如，大部分电视广告的目标是品牌意识。您可能使用[“时间衰减”归因模型](/help/analysis-workspace/attribution/models.md)，因为随着时间的推移，人们会忘记您的电视广告。

### 漏斗下层分析

在这个分析中，假设人们已经知道您的品牌，您希望他们转化。使用电子邮件、推送通知或 Facebook 广告。

## 步骤 2：基于规则的归因

此步骤的目的是验证您的假设。

**示例 1**

比如您的假设是“我第一次接触的渠道比最后一次接触的渠道对转化的影响更大”。然后，您会使用[“反向 J 型”归因模型](/help/analysis-workspace/attribution/models.md)来检验这个假设。此模型将 60% 的点数分给第一个接触点。

**示例 2**

您的假设可能是：“在我们的行业（例如，旅游业）中，归因时段为 60 或 90 天，而不是 30 天，因为客户在购买产品之前会进行大量研究。”然后，您会将[回溯时段](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html#lookback-windows)更改为 90 天。

## 步骤 3：使用算法归因

因为要验证大量可能的假设和组合非常困难，所以您可以使用[算法归因](/help/analysis-workspace/attribution/algorithmic.md)，让内置算法来完成这项工作。如果您已经找到了能够回答所有问题且完全适合的完美归因模型，那么您显然就不需要采取这一步骤。

## 其他注意事项

* 您可能需要使用数据科学家的服务，而不是仅仅依靠 Analysis Workspace。
