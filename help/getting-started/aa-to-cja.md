---
title: 从 Adobe Analytics 演变到 Customer Journey Analytics
description: 将Adobe Analytics数据转换为Customer Journey Analytics数据的步骤
role: Admin
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: dbb7edae43fdc970cacf5863ecd13df75deaefad
workflow-type: ht
source-wordcount: '1420'
ht-degree: 100%

---

# 从 Adobe Analytics 演变到 Customer Journey Analytics

随着贵组织不断发展使用Customer Journey Analytics，请探索这些步骤以准备数据并了解这两种技术之间的关键差异。 本文针对管理员受众。

## 准备您的数据

准备 Adobe Analytics 数据以无缝迁移到 Customer Journey Analytics 对于数据完整性和报告一致性至关重要。

### 1. 收集标识 {#identities}

了解客户历程最关键的组成部分也许是在每一步都知道客户是谁。对于 Customer Journey Analytics，拥有一个存在于所有渠道和相应数据的标识符允许在 CJA 中将多个来源拼接在一起。标识示例可能是客户 ID、帐户 ID 或电子邮件 ID。无论标识是什么（可能有多个），请确保为每个 ID 考虑以下内容：

* ID 存在或可以添加到您要带入 CJA 的所有数据源
* ID 填充在每行数据上
* ID 不包含 PII。将散列应用于任何可能敏感的内容。
* ID 在所有源中使用相同的格式（相同的长度、相同的散列方法等）

在 Adobe Analytics 等数据集中，可能并非每行数据都存在标识，但辅助标识确实存在。在这种情况下，跨频道分析（以前称为“基于字段的拼接”）可用于在仅通过其 ECID 识别客户以及收集标识时（例如，当客户认证时）。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=zh-Hans)

### 2. 调整您的变量 {#variables}

将 Adobe Analytics 数据转换为 Customer Journey Analytics 数据的最直接方法是使用 [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html) 将[全局报告包](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans)纳入 Experience Platform 中。该连接器会将您的 Adobe Analytics 变量直接映射到 Experience Platform 中的 XDM 架构和数据集，然后便可以轻松连接到 Customer Journey Analytics。

完整的全局报表包可能并不总是适用于实施。如果您计划将多个报表包引入Customer Journey Analytics，您有2个选项：

* 提前规划以使这些报表包中的变量保持一致。 例如，报表包 1 中的 eVar1 可能指向[!UICONTROL 页面]。在报表包 2 中，eVar1 可能指向[!UICONTROL 内部营销活动]。当被引入 CJA 时，这些变量将混合到一个单一的 eVar1 维度中，从而导致潜在的混乱和不准确的报告。

* 使用[数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html)功能来映射变量。 虽然如果所有报告包都使用相同的常用变量设计，这样会更轻松，但是如果您使用新 Experience Platform [数据准备](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html#mapping)功能，则无需这样做。它允许您通过变量的映射值(位于数据流（或属性）级别)引用变量。

如果您因为 [!UICONTROL Uniques Exceeded] 或 [!UICONTROL Low Traffic] 问题而无法迁移到全局报表包，请了解 CJA [对维度没有基数限制](/help/components/dimensions/high-cardinality.md)。它允许出现并计算任何唯一值。

以下是[将报告包与不同架构相结合](/help/use-cases/aa-data/combine-report-suites.md)的用例。

### 3. （重新）配置您的营销渠道 {#marketing-channels}

传统的 Adobe Analytics 营销渠道设置在 CJA 中的执行方式不同。这有两个原因：

* 摄取到 Adobe Experience Platform 的 Adobe Analytics 数据的处理级别，以及

* Customer Journey Analytics 的报告时间性质

Adobe 发布了](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=zh-Hans)营销渠道实施的[最新先进实践。这些最新的推荐可帮助您用 Attribution IQ 充分利用 Adobe Analytics 中已有的功能。他们还将帮助您在过渡到 Customer Journey Analytics 时取得成功。

### 4. 决定使用 Analytics Source Connector 还是 Experience Platform SDK {#connector-vs-sdk}

Adobe Analytics 客户可以使用 Analytics Source Connector 在 Adobe Experience Platform 和 Customer Journey Analytics 中轻松利用他们的报告包。有关使用 Analytics Source Connector 的信息，请参阅[在 UI 中创建 Adobe Analytics 源连接](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans)。

随着 [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) 数据收集的发展，您可能会迁移到带有 Adobe Experience Platform Edge Network 的 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html) 或 [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html)。虽然 SDK 的典型实施会将数据发送到 Adobe Analytics，但将数据直接发送到 Adobe Experience Platform 的新机会出现了。然后可以将其引入 Customer Journey Analytics，同时还可以维护发送到 Adobe Analytics 的数据。

这种方法极大地扩展了数据收集的可能性：不再有字段数量的限制，也不再需要将数据元素映射到属性、eVar 和 Analytics 中的事件。您可以使用不同类型的无限模式元素，并使用 CJA [数据视图](/help/data-views/data-views.md)以多种方式表示它们。直接发送到 Adobe Experience Platform 时，数据可用性的速度会提高，因为通过 Adobe Analytics 进行数据处理的时间被去除了。

**使用 Experience Platform SDK 的优势:**

* 灵活的模式来定义您需要的任何字段
* 不依赖于 Adobe Analytics 命名法（属性、eVar、事件等）
* 没有字符限制问题（属性有 100 个字符）
* Adobe Experience Platform 中更快的数据可用性推动[实时个性化用例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=zh-Hans)
* [第一方设备 ID](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=zh-Hans) 可提高访客识别的准确性

**使用 Experience Platform SDK 的缺点**

不支持以下 Adobe Analytics 功能或组件：

* 营销渠道
* 机器人筛选
* 地理、域、设备查找
* Analytics for Target (A4T)

## 为重要差异做好准备

### 熟悉报告时间处理 {#report-time}

Adobe Analytics 中的报告依赖于大量数据预处理来生成结果，例如您在 [!UICONTROL eVars] 中看到的持久性。相比之下，Customer Journey Analytics 在报表运行时运行这些计算。

[!UICONTROL 报告时间处理]开启了应用追溯设置和创建变量持久性的多个版本的能力，而无需更改基础数据的收集方式。

这种转变将导致数据报告方式的一些差异，特别是对于任何可能具有较长到期窗口的变量。您可以从使用[虚拟报表包](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html)评估报表时间处理如何影响您的报表开始。

### 识别重要区段和计算量度 {#segments-calcmetrics}

Adobe Analytics 区段（在 CJA 中称为[!UICONTROL 过滤器]）和计算量度与 Customer Journey Analytics 不兼容。在许多情况下，可以使用新的模式和可用数据在 CJA 中重建这些组件。

为了使用户在系统之间过渡时尽可能顺利地进行过渡，请提前计划

1. 确定这些组件中最重要的部分。

1. 记录它们的定义，以及

1. 确定数据中需要哪些字段以在 CJA 中将它们复制为[过滤器](/help/components/filters/filters-overview.md)和[计算量度](/help/components/calc-metrics/calc-metr-overview.md)。

这里有几个视频可以为您指南：

* [将 Adobe Analytics 区段迁移到 Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html)

* [将计算量度从 Adobe Analytics 移动到 Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=zh-Hans)

### 其他注意事项

* 使用 CJA 数据视图的强大功能，您可以在 Customer Journey Analytics 中定义指标和维度时更加灵活。例如，您可以使用维度的值来定义度量。[了解详情](/help/use-cases/data-views/data-views-usecases.md)

* 如果您在 Adobe Analytics 中定义了自定义日程表，那么 CJA 中也将具有类似的[自定义日程表功能](/help/components/date-ranges/custom-date-ranges.md)。您需要确保正确定义日历。

* 在 Customer Journey Analytics 中，您可以定义自定义访问/会话超时，以及定义将启动新会话的量度。您可以创建具有不同会话定义的数据视图，以获得超越 Adobe Analytics 的洞察力。此功能可能对移动数据集特别有益。

* 考虑为用户提供数据字典，或扩展SDR以包含架构元素的Experience Platform字段名称。

## 后续步骤

迁移到 CJA 后，如果您发现任何数据差异，您可以将原始 Adobe Analytics 数据与现在位于 Customer Journey Analytics 中的 Adobe Analytics 数据进行比较。[了解详情](/help/troubleshooting/compare.md)
