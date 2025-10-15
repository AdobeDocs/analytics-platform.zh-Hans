---
title: 归因最佳实践
description: 了解最佳实践，以决定使用哪种归因模型。
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: 1b6e1d432bfe4b0574b8ee68bcfa940941f3c36f
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 66%

---

# 归因最佳实践

为您的组织选择适合的归因模型取决于许多考虑因素。本文探索了一种方法论和一些常规的最佳实践：

* [探索性分析](#exploratory-analysis)
* [基于规则的归因](#rule-base-attribution)
* [使用算法归因](#use-algorithmic-attribution)

## 探索性分析

>[!NOTE]
>此分析需要在您选择归因模型之前进行。

此阶段最初包括了解客户行为和定义转化量度。根据转化量度，[数据馈送](https://experienceleague.adobe.com/zh-hans/docs/analytics/export/analytics-data-feed/data-feed-overview)（针对原始数据）或 Analysis Workspace 等工具可以帮助您更好地理解：

* 在转化前接触了不同的营销渠道的客户数量
* 这些行为的比例/分布

例如，如果 50% 的客户在转化前接触了 3 个渠道，这 3 个渠道之间有什么互动吗？然后，您可以进行漏斗上层和漏斗下层分析以扩展您的理解。

### 漏斗上层分析

漏斗上层分析渠道用于创建品牌和产品意识。 例如，大部分电视广告的目标是品牌意识。您可能使用[时间衰减归因模型](/help/analysis-workspace/attribution/models.md)，因为随着时间的推移，人们会忘记您的电视广告。

### 漏斗下层分析

在漏斗下层分析中，假设客户已经知道您的品牌，您希望将其转化。 使用电子邮件、推送通知或 Facebook 广告。

## 基于规则的归因

此步骤的目的是验证您的假设。

**示例 1**

假设您的假设是：“*我的首次联系渠道比最后一次联系渠道对转化的影响更大。*”

在这种情况下，您将使用[反向J型归因模型](/help/analysis-workspace/attribution/models.md)来检验这个假设。 此模型将 60% 的点数分给第一个接触点。

**示例 2**

假设您的假设为：*“在特定行业（例如旅游业）中，归因时段为60或90天，而不是30天，因为客户在购买产品之前会进行大量研究。*”

在这种情况下，您会将[回溯时段](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/models)更改为 90 天。

## 使用算法归因

如果您还没有归因模型可以为您的所有问题提供令人满意的答案，您可以使用[算法归因](/help/analysis-workspace/attribution/algorithmic.md)。 因为要验证大量可能的假设和组合非常困难，所以可以使用算法归因，让内置算法来跨维度项目分配信用。

## 其他注意事项

* 您可能需要使用数据科学家的服务，而不是仅仅依靠 Analysis Workspace。
* 您可以依赖原始数据，就像在 Adobe 数据馈送中一样。
* 例如，如果您要考虑展示数据，请考虑使用[Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-overview)。
