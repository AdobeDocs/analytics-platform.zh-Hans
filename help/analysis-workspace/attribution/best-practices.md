---
title: 归因最佳实践
description: 有关决定归因模型的最佳实践是什么？
source-git-commit: 3839639858edbd019ef467ca5fb1791f48864100
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 2%

---


# 归因最佳实践

为您的组织选择正确的归因模型取决于多项注意事项。 本文探讨了方法和一些一般最佳实践。

## 步骤1:探索分析

>[!NOTE]
>在您选择归因模型之前，需要先进行此分析。

此阶段最初包括了解客户行为并定义转化量度。 根据转化量度，诸如[数据馈送](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=en)（用于原始数据）或Analysis Workspace之类的工具可帮助您了解

* 有多少客户在转化之前接触了不同的营销渠道？
* 这些行为的比例/分布。

例如，如果50%的客户在转化前接触3个渠道，那么这3个渠道之间是否存在任何交互？
然后，您可以进行上漏斗和下漏斗分析以扩大您的了解。

### 上漏斗分析

上漏斗分析可分析用于提升品牌或产品知名度的渠道。 例如，大多数电视广告的目标都是品牌意识。 您可以使用[&quot;时间衰减&quot;归因模型](/help/analysis-workspace/attribution/models.md)，因为随着时间的推移，人们会忘记您的电视广告。

### 漏斗下限分析

在此分析中，我们假定用户已经了解您的品牌并希望他们进行转化。 使用电子邮件或推送通知或Facebook广告。

## 步骤2:基于规则的归因

此步骤旨在验证您的假设。

**示例 1**

假设您的假设是“与最近联系渠道相比，我的首次联系渠道对转化的影响更大。 然后，您将使用[&quot;反向J曲线&quot;归因模型](/help/analysis-workspace/attribution/models.md)来测试此假设。 此模型将60%的点数分给首次接触点。

**示例 2**

你的假设可能是：“在我们的行业（如旅游行业），归因时间范围是60天或90天，而不是30天，因为客户在购买产品之前会进行大量研究。 然后，您会将[回顾窗口](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=en#lookback-windows)更改为90天。

## 步骤3:使用算法归因

由于很难验证大量可能的假设和组合，因此您可以使用[算法归因](/help/analysis-workspace/attribution/algorithmic.md)将此工作留给内置算法。 如果您已经找到可回答您所有问题且最适合的完美归因模型，则显然您无需执行此步骤。

## 其他注意事项

* 您可能需要使用数据科学家的服务，而不是仅仅依赖Analysis Workspace。
* 您可以依赖原始数据，如Adobe数据馈送中的数据。
* 例如，如果要考虑展示次数数据，请考虑使用[Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hans)。

