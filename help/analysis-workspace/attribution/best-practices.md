---
title: 归因最佳实践
description: 了解最佳实践，以决定使用哪种归因模型。
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
TQID: https://experienceleague.adobe.com/noNo2rP-srAtUJbG-kYgipLHknMsWWZR4iJwDv-2ioc
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 466
ht-degree: 63%

---

# 归因最佳实践

为您的组织选择合适的归因模型取决于多种因素。 本文探索了一种方法论和一些常规的最佳实践：

* [探索性分析](#exploratory-analysis)
* [基于规则的归因](#rule-base-attribution)
* [使用算法归因](#use-algorithmic-attribution)

## 探索性分析

>[!NOTE]
>此分析需要在您选择归因模型之前进行。

此阶段最初包括了解客户行为和定义转化量度。 根据转化量度，[数据馈送](https://experienceleague.adobe.com/zh-hans/docs/analytics/export/analytics-data-feed/data-feed-overview)（针对原始数据）或 Analysis Workspace 等工具可以帮助您更好地理解：

* 在转化前接触了不同的营销渠道的客户数量
* 这些行为的比例/分布

例如，如果 50% 的客户在转化前接触了 3 个渠道，这 3 个渠道之间有什么互动吗？
然后，您可以进行漏斗上层和漏斗下层分析，以加深您的理解。

### 漏斗上层分析

漏斗上层分析渠道用于创建品牌和产品意识。 例如，大部分电视广告的目标是品牌意识。 您可能使用[时间衰减归因模型](/help/analysis-workspace/attribution/models.md)，因为随着时间的推移，人们会忘记您的电视广告。

### 漏斗下层分析

在漏斗下层分析中，假设客户已经知道您的品牌，您希望将其转化。 使用电子邮件、推送通知或 Facebook 广告。

## 基于规则的归因

此步骤的目的是验证您的假设。

**示例 1**

假设您的假设是：“*我的首次联系渠道比最后一次联系渠道对转化的影响更大。*”

在这种情况下，您将使用[反向J型归因模型](/help/analysis-workspace/attribution/models.md)来检验这个假设。 此模型将 60% 的点数分配给第一个接触点。

**示例 2**

假设您的假设为：*“在特定行业（例如旅游业）中，归因时段为60或90天，而不是30天，因为客户在购买产品之前会进行大量研究。*”

在这种情况下，您会将[回溯时段](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/models)更改为 90 天。

## 使用算法归因

如果您还没有归因模型可以为您的所有问题提供令人满意的答案，您可以使用[算法归因](/help/analysis-workspace/attribution/algorithmic.md)。 由于很难验证大量可能的假设和组合，因此算法归因使用内置算法在各个维度项之间分配点数。

## 其他注意事项

* 您可能需要使用数据科学家的服务，而不是仅仅依靠 Analysis Workspace。
* 您可以依赖原始数据，就像在 Adobe 数据馈送中一样。
* 例如，如果您要考虑展示数据，请考虑使用[Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-overview)。

