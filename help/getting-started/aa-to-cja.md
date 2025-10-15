---
title: Adobe Analytics 的演化
description: 将 Adobe Analytics 数据转换为 Customer Journey Analytics 数据的步骤
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 4dcf9ab808475cc3cc48cab4c076b6c3cfb66f8a
workflow-type: tm+mt
source-wordcount: '1075'
ht-degree: 100%

---

# Adobe Analytics 的演化

## 准备您的现有数据

准备 Adobe Analytics 数据以无缝迁移到 Customer Journey Analytics 对于数据完整性和报告一致性至关重要。

### 收集身份标识

了解客户历程最关键的组成部分也许是在每一步都知道客户是谁。对于 Customer Journey Analytics，拥有一个存在于所有渠道和相应数据的标识符允许在 Customer Journey Analytics 中将多个来源拼接在一起。身份标识示例可能是客户 ID、帐户 ID 或电子邮件 ID。无论身份标识是什么（可能有多个），请确保为每个 ID 考虑以下内容：

* ID 存在或可以添加到您要带入 Customer Journey Analytics 的所有数据源
* ID 填充在每行数据上
* ID 不包含 PII。将散列应用于任何可能敏感的内容。
* ID 在所有源中使用相同的格式（相同的长度、相同的散列方法等）

在 Adobe Analytics 等数据集中，可能并非每行数据都存在身份标识，但辅助身份标识确实存在。在这种情况下，当仅通过客户的 ECID 识别客户时以及收集身份标识时（例如，当客户进行身份验证时），可使用[跨渠道分析（也称为“拼接”）](/help/stitching/overview.md)消除行间差距。

### 使您的变量保持一致

将 Analytics 数据转换为 Customer Journey Analytics 数据的最直接方法是使用 [Adobe Analytics Source Connector](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/prepare/global-rs) 将[全局报告包](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)纳入 Experience Platform 中。该连接器会将您的 Adobe Analytics 变量直接映射到 Experience Platform 中的 XDM 架构和数据集，然后便可以轻松连接到 Customer Journey Analytics。

完整的全局报告包可能并不总是适用于实施。如果您计划将多个报告包引入Customer Journey Analytics，您有2个选项：

* 提前规划以使这些报告包中的变量保持一致。 例如，报告包 1 中的 eVar1 可能指向[!UICONTROL 页面]。在报告包 2 中，eVar1 可能指向[!UICONTROL 内部营销活动]。当将这些变量引入 Customer Journey Analytics 后，会被混合为一个统一的 eVar1 维度，从而可能导致报表结果混淆或不准确。

* 使用[数据准备](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/data-prep/home)功能来映射变量。 虽然如果所有报告包都使用相同的常用变量设计，这样会更轻松，但是如果您使用新 Experience Platform [数据准备](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)功能，则无需这样做。它允许您通过变量的映射值(位于数据流（或属性）级别)引用变量。

如果您因为 [!UICONTROL Uniques Exceeded] 或 [!UICONTROL Low Traffic] 问题而无法迁移到全局报告包，请注意 Customer Journey Analytics [对维度没有基数限制。](/help/components/dimensions/high-cardinality.md)它允许出现并计算任何唯一值。

以下是[将报告包与不同架构相结合](/help/use-cases/aa-data/combine-report-suites.md)的用例。

### （重新）配置您的营销渠道

传统的 Adobe Analytics 营销渠道设置在 Customer Journey Analytics 中的执行方式不同。存在差异的原因有两个：

* 摄取到 Adobe Experience Platform 的 Adobe Analytics 数据的处理级别，以及

* Customer Journey Analytics 的报告时性质

Adobe 发布了](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/marketing-channels/mchannel-best-practices)营销渠道实施的[最新先进实践。这些更新后的建议可帮助您充分利用 Adobe Analytics 中已有的高级归因功能，发挥其最大效能。这些建议同时也为您顺利过渡至 Customer Journey Analytics 打下良好基础。

随着 Customer Journey Analytics 数据视图中引入[派生字段](../data-views/derived-fields/derived-fields.md)，现已可通过[营销渠道功能模板](../data-views/derived-fields/derived-fields.md#function-templates)以非破坏性、可追溯的方式支持营销渠道功能。

## 迁移到 Customer Journey Analytics 时做好应对重大差异的准备

随着贵组织不断发展使用Customer Journey Analytics，请探索这些步骤以准备数据并了解这两种技术之间的关键差异。本文针对管理员受众。

### 熟悉报告时处理 {#report-time}

Adobe Analytics 中的报告依赖于大量数据预处理来生成结果，例如您在 [!UICONTROL eVars] 中看到的持久性。相比之下，Customer Journey Analytics 在报告运行时运行这些计算。

[!UICONTROL 报告时处理]开启了应用追溯设置和创建变量持久性的多个版本的能力，而无需更改基础数据的收集方式。

这一转变会导致数据的报告方式出现一些差异，尤其是在处理具有较长过期时间的变量时。您可以从使用[虚拟报告包](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/virtual-report-suites/vrs-report-time-processing)评估报告时处理如何影响您的报告开始。

### 识别重要区段和计算量度 {#segments-calcmetrics}

Adobe Analytics 区段和计算量度与 Customer Journey Analytics 不兼容。在许多情况下，可以使用新的架构和可用数据在 Customer Journey Analytics 中重建这些组件。

为了使用户在系统之间过渡时尽可能顺利地进行过渡，请提前计划

1. 确定这些组件中最重要的部分。

2. 记录它们的定义，以及

3. 明确在数据中需要哪些字段，以便在 Customer Journey Analytics 中将其复制为[区段](/help/components/segments/seg-overview.md)和[计算量度](/help/components/calc-metrics/calc-metr-overview.md)。

这里有几个视频可以为您指南：

* [将 Adobe Analytics 区段迁移到 Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/filters/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=zh-Hans)

* [将计算量度从 Adobe Analytics 移动到 Customer Journey Analytics](https://experienceleague.adobe.com/zh-hans/docs/customer-journey-analytics-learn/tutorials/components/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics)

### 其他注意事项

* 使用 Customer Journey Analytics 数据视图的强大功能，您可以在 Customer Journey Analytics 中定义量度和维度时更加灵活。例如，您可以使用维度的值来定义度量。[了解详情](/help/use-cases/data-views/data-views-usecases.md)

* 如果您在 Adobe Analytics 中定义了自定义日程表，那么 Customer Journey Analytics 中也将具有类似的[自定义日程表功能](/help/components/date-ranges/overview.md)。您需要确保正确定义日历。

* 在 Customer Journey Analytics 中，您可以自定义会话超时时长，并可设定一个用于触发新会话的量度。您可以创建具有不同会话定义的数据视图，以获得超越 Adobe Analytics 的洞察力。此功能可能对移动数据集特别有益。

* 建议为您的用户提供一份数据字典。或扩展 SDR，将架构元素对应的 Experience Platform 字段名称包含在内。

### 后续步骤

迁移到 Customer Journey Analytics 后，如果您发现任何数据差异，您可以将原始 Adobe Analytics 数据与现在位于 Customer Journey Analytics 中的 Adobe Analytics 数据进行比较。[了解详情](/help/troubleshooting/compare.md)
