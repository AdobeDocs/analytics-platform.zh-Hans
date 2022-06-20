---
title: 比较Adobe Analytics和CJA报表功能中的数据处理情况
description: 了解各种报表功能的数据处理差异
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 22%

---


# 比较Adobe Analytics和CJA报表功能中的数据处理情况

了解各种报表功能在数据处理方面的差异有助于了解哪些量度在何处可用以及它们可能存在差异的原因。

例如，由于“访问次数”是在数据处理时定义的Adobe Analytics中的量度，而“会话次数”是CJA中的量度是在报告时计算的，因此这两个量度可能因CJA数据视图中用于会话定义的规则而异。

此外，在Analytics源连接器创建的数据集中，访问次数和会话均不作为量度可用，因此需要在查询逻辑中定义会话才能进行比较。

## 术语 {#terms}

下表为应用于Adobe Analytics和CJA的不同类型处理逻辑定义了术语：

| 术语 | 定义 | 注释 |
| --- | --- | --- |
| 处理时间逻辑 | 在处理数据时执行的逻辑，然后再存储以用于报告和分析目的。 | 此逻辑已“植入”历史数据中，通常无法轻松更改。 |
| 报告时逻辑 | 运行报表时执行的逻辑。 | 此逻辑可以无损地应用于报表运行时的未来数据和历史数据。 |
| 点击级别逻辑 | 在逐行级别应用的逻辑。 | 示例：处理规则、VISTA、某些营销渠道规则。 |
| 访问级别逻辑 | 在访问级别应用的逻辑。 | 示例：访问和会话定义。 |
| 访客级别逻辑 | 在访客级别应用的逻辑。 | 示例：跨设备/跨渠道访客拼合。 |
| 区段（过滤器）逻辑 | 评估点击/访问/访客（事件/会话/人员）区段（过滤器）规则。 | 示例：买红鞋的人。 |
| 计算量度 | 对客户创建的自定义量度进行评估，这些量度可以基于包括区段和过滤器在内的复杂公式。 | 示例：买红鞋的人数。 |
| 归因逻辑 | 计算归因的逻辑。 | 示例：eVar持久性。 |

{style=&quot;table-layout:auto&quot;}

随着时间的推移，Adobe Analytics和现在的Customer Journey Analytics允许在报表运行时执行访问和访客级别的数据逻辑，从而提高了灵活性。

## 数据处理类型 {#types}

对Adobe Analytics和CJA执行的数据处理步骤以及这些步骤的时间因Analytics功能和Analytics功能而异。 下表概要介绍了每个Analytics功能的数据处理类型以及何时应用了数据处理。

| Analytics功能 | 在处理时应用 | 在报告时应用 | 不可用 | 注释 |
| --- | --- | --- | --- | --- |
| [核心AA](https://experienceleague.adobe.com/docs/analytics.html?lang=zh-Hans) 报告<br/>(不包括具有报表时间处理的Attribution IQ或虚拟报表包) | <ul><li>[处理规则](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=zh-Hans)</li><li>[VISTA 规则](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=en)</li><li>点击级别 [营销渠道规则](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html?lang=zh-hans)</li><li>访问级别的营销渠道规则（请参阅注释）</li><li>访问定义</li><li>归因逻辑</li></ul> | <ul><li>区段逻辑</li><li>计算量度</li></ul> | <ul><li>跨设备分析（请参阅注意）</li></ul> | <ul><li>CDA需要通过报表时间处理来使用虚拟报表包。</li><li>“访问级别营销渠道规则”包括以下内容： **是访问的第一个页面**, **覆盖最近联系渠道**&#x200B;和 **营销渠道到期**. (请参阅 [文档](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=zh-Hans).)</li></ul> |
| 核心AA [data warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=en) | <ul><li>处理规则</li><li>VISTA 规则</li><li>点击级别的营销渠道规则</li><li>访问级别营销渠道规则</li><li>访问定义</li><li>归因逻辑</li></ul> | <ul><li>区段逻辑</li></ul> | <ul><li>计算量度</li><li>Cross-Device Analytics</li></ul> |  |
| 核心AA [数据馈送](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=en) | <ul><li>处理规则</li><li>VISTA 规则</li><li>点击级别的营销渠道规则</li><li>访问级别营销渠道规则</li><li>访问定义（visitnum字段）</li><li>归因逻辑（在帖子列中）</li></ul> |  | <ul><li>区段逻辑</li><li>计算量度</li><li>跨设备分析</li></ul> | <ul><li>数据馈送中某些与营销渠道相关的列的ID映射不会包含在数据馈送中。 (请参阅 [数据馈送文档](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hans).)</li></ul> |
| 核心AA [实时流](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> 处理规则</li><li>VISTA 规则</li><ul> |  | <ul><li>点击级别的营销渠道规则</li><li>访问级别营销渠道规则</li><li>访问逻辑</li><li>归因逻辑</li><li>区段逻辑</li><li>计算量度</li><li>跨设备分析</li></ul> |  |
| 核心AA [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=zh-Hans) | <ul><li>处理规则</li><li>VISTA 规则</li><li>访问定义（请参阅注释）</li><li>跨设备分析（请参阅注意）</li></ul> | <ul><li>点击级别的营销渠道规则（请参阅注释）</li><li>访问级别营销渠道规则（请参阅注意）归因逻辑</li><li>区段逻辑</li><li>计算量度</li></ul> |  | <ul><li>CDA需要通过报表时间处理来使用虚拟报表包。</li><li>核心Analytics中的Attribution IQ使用在报表时完全派生的营销渠道（即派生的中间值）。</li><li>Attribution IQ使用处理时访问定义，但在报表时处理VRS中使用时除外。</li></ul> |
| 核心AA虚拟报表包(包含 [报告时间处理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=zh-Hans) (VRS RTP) | <ul><li>处理规则</li><li>VISTA 规则</li><li>[Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=zh-Hans)</li></ul> | <ul><li>访问定义</li><li>归因逻辑</li><li>区段逻辑</li><li>计算量度</li><li>其他VRS RTP设置</li></ul> | <ul><li>点击级别的营销渠道规则</li><li>访问级别营销渠道规则</li></ul> | <ul><li>请参阅VRS RTP [文档](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en).</li></ul> |
| [Analytics源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hans)AEP数据湖中基于的数据集 | <ul><li>处理规则</li><li>VISTA 规则</li><li>点击级别的营销渠道规则</li><li>基于字段的拼合（请参阅注释）</li></ul> |  | <ul><li>[访问级别营销渠道规则](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en)</li><li>访问逻辑</li><li>归因逻辑</li><li>过滤器逻辑</li></ul> | <ul><li>必须应用您自己的过滤器逻辑和计算量度</li><li>基于字段的拼合除了由Analytics源连接器创建的拼合数据集之外，还会创建一个单独的拼合数据集。</li></ul> |
| [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=en) 报告 | <ul><li>处理规则</li><li>VISTA 规则</li><li>点击级别 [营销渠道规则](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en)</li><li>[连接设置](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hans)</li><li>基于字段的拼合（请参阅注释）</li></ul> | <ul><li>会话定义</li><li>[数据视图设置](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=zh-Hans)</li><li>归因逻辑</li><li>计算量度</li><li>过滤器逻辑</li></ul> | <ul><li>访问级别营销渠道规则</li></ul> | <ul><li>必须使用拼合数据集才能利用基于字段的拼合。</li></ul> |

{style=&quot;table-layout:auto&quot;}