---
title: 有关归因的常见问题解答
description: 获取有关归因的常见问题解答。
feature: Attribution
role: User, Admin
exl-id: 8e05957a-f954-4e61-aeed-cd2bd2fe11f8
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 2%

---

# 常见问题解答

以下是有关归因的常见问题解答。

+++##使用归因时，*无*&#x200B;行项是什么？

*无*&#x200B;行项目是一个全包项，它表示在回顾窗口内发生的不含任何接触点的所有转化。 要减少归因于&#x200B;*无*&#x200B;行项目的转化的次数，请尝试使用更长的回顾时间范围。

+++

<!--
+++## Why do I sometimes see dates outside of my reporting window when using attribution models?

Some visit-based metrics, such as [Entries](/help/components/metrics/entries.md) or [Bounce Rate](/help/components/metrics/bounce-rate.md), can attribute data to a period before the reporting window start date range. This situation is due to attribution models using a lookback window, which determines how far back attribution should look to give credit for metrics. The most common scenario is when visits span midnight. For example:

1. A user visits your home page at 11:55 PM on September 7.
1. They visit several pages, the last of which occurred at 12:05 AM September 8.
1. A week later, you run a daily trended report with the date range September 8 - September 14.

Hit-based metrics, like [Page views](/help/components/metrics/page-views.md), would produce expected output; data trended each day from September 8 - September 14. However, visit-based metrics would also show the above visit on September 7. The visit's attributed entry occurred on September 7, and the lookback window by default is September 1 - September 31.

Bounce rate always shows 0% on September 7 in this example. This metric is defined as `Bounces divided by Entries`, a hit-based metric divided by a visit-based metric. Bounces consist of a single image request, so they cannot span multiple days, Any bounces on September 7 happened outside the reporting window, causing the guaranteed 0% bounce rate for that day. Other hit-based metrics would also show 0 for September 7 in this report, since those hits are not within the reporting window either.

Consider another similar example. The only difference between the following example and the above example are the dates:

1. A user visits your home page at 11:55 PM on August 31.
1. They visit several pages, the last of which occurred at 12:05 AM September 1.
1. A week later, you run a daily trended report with the date range September 1 - September 7.

In this example, Entries and Bounce rate would not show data from August 31. The lookback window and reporting window both start on September 1, so data cannot be attributed from August 31.

+++
-->

<!-- not relevant anymore due to introduction of separation of container and lookback window 
+++## When should I use a visit, visitor, or custom attribution lookback?

The choice of attribution lookback depends on your use case. If conversions typically take longer than a single visit, a visitor or custom lookback is recommended. For longer conversion cycles, custom lookback windows are best as they are the only type that can pull in data from prior to the reporting window.

+++
-->

<!--
+++## How do props and eVars compare when using attribution?

Attribution is recalculated at report runtime, so there is no difference between a prop or eVar (or any other dimension) for the sake of attribution modeling. Props can persist using any lookback window or attribution model, and eVar allocation/expiration settings are ignored.

+++
-->


+++##归因模型在其他Analytics功能中是否可以使用？

是的。归因模型也可用作数据视图中量度组件的组件设置的一部分。 请参阅[归因组件设置](/help/data-views/component-settings/attribution.md)。 对于维度组件，您可以使用持久性。 持久性表示给定的维度值能否在从中设置它的事件之外归因于指标。 它使用分配和到期的组合。 有关详细信息，请参阅[持久性组件设置](/help/data-views/component-settings/persistence.md)

+++


<!--
+++## Are attribution models only available if I'm using a virtual report suite with report time processing enabled?

Attribution models are available outside of virtual report suites. While they use report time processing on the backend, attribution models are available to both standard report suites and virtual report suites.

+++
-->


+++##支持哪些维度和量度？

您在数据视图中定义的所有非标准量度都支持归因。

+++



+++##归因是否适用于查找数据？

是，完全支持来自查找数据的维度。

+++

<!--
+++## Does attribution work with data sources?

Yes, most data sources are supported. Attribution is not possible with summary-level data sources because these data sources do not tie to an Analytics visitor identifier.

Transaction ID data sources are treated like any other hit. Transaction ID data sources don't use the special processing that normally is used in traditional reporting. In other words, when using report time processing, Transaction ID hits have eVar values propagated from hits which occur near the timestamp of the Transaction ID hit. The values are not propagated from hits that occurred near the time of the original transaction.

When possible, attribution relies on the MID column value that is sent within an event in the data source, rather than a persisted value. The attribution model is applied to the MID column values in the data source, on-the-fly. For example, when you use [Last Touch attribution](models.md) the model starts from each instance of a metric. And walks backward sequentially in the hits until the model reaches the last value observed in the MID column.

When not possible, attribution uses the MID value in the *prior record* in the data source for evaluation. This prior record might not be ordered sequentially by timestamp, given that AA does not support out-of-order data.

Due to the records not being ordered sequentially, the expected values from applying persistence can impact the amount of time that exists between the provided transaction ID timestamp and the original transaction.

+++
-->

<!--
+++## Does attribution work with the Advertising Analytics integration?

Metadata dimensions, such as match type and keyword, work with attribution. However, metrics (including impressions, cost, clicks, average position, and average quality score) use summary-level data sources, and are therefore incompatible.

+++



+++## How does attribution work with marketing channels?

When marketing channels were first introduced, they came with only first and last touch dimensions. Explicit first/last touch dimensions are no longer needed with the current version of attribution. Adobe provides generic [!UICONTROL Marketing Channel] and [!UICONTROL Marketing Channel Detail] dimensions so you can use them with your desired attribution model. These generic dimensions behave identically to [!UICONTROL Last Touch Channel] dimensions, but are labeled differently to prevent confusion when using marketing channels with a different attribution model.

Since marketing channel dimensions depend on a traditional visit definition (as defined by their processing rules), their visit definition cannot be changed using virtual report suites.

+++


+++## How does attribution work with multi-value variables, such as list vars?

Some dimensions in Analytics can contain multiple values on a single hit. Common examples include list vars and the products variable.

When attribution is applied to multi-value hits, all values in the same hit get the same credit. Since many values can receive this credit, the report total can be different than if you summed each individual line item. The report total is deduplicated, while each individual dimension item gets proper credit.

+++


+++## How does attribution work with segmentation?

Attribution always runs before segmentation, and segmentation runs before report filters are applied. This concept also applies to virtual report suites using segments.

For example, if you create a virtual report suite with a "Display Hits" segment applied, you could see other channels in a table using some attribution models.

![Display-only virtual report suite](assets/vrs-aiq-example.png)

>[!NOTE]
>
>If a segment suppresses hits containing your metric, those metric instances are not attributed to any dimension. However, a similar report filter simply hides some dimension items, without any impact on metrics processed per the attribution model. As a result, a segment can return lower values than a filter with a comparable definition.

+++
-->