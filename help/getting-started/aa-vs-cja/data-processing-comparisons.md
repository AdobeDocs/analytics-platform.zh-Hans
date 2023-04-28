---
title: 跨 Adobe Analytics 和 CJA 报告功能比较数据处理
description: 了解各种报告功能的数据处理差异
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
source-git-commit: 80d0b95f3bc3d785d9ca7e4b50aa1bd8440373c2
workflow-type: tm+mt
source-wordcount: '1012'
ht-degree: 91%

---

# 比较Adobe Analytics和Customer Journey Analytics的数据处理情况。

<!--

You often need the ability to process data before it is useful for reporting. You can process that data at several stages in the journey that spans from collecting data to generating your report or visualization.

In Adobe Analytics most of that processing of data occurs immediately after collecting the data. Functionalties like VISTA Rules, Processing Rules, Marketing Channels Processing Rules are available to support this **collection-time processing**. 
The data is then stored and at report time you can apply additional processing. For example, break down dimensions, apply segmentation, or  select a different attribution model. This **report-time processing** happens on the fly. 

In Adobe Analytics, report-time processing commonly represents a smaller amount of processing  than what happens at collection-time.

![Adobe Analytics collection-time processing](../assets/aa-processing.png)

In contrast, Customer Journey Analytics (CJA) is designed to require minimal upfront collection-time processing before data being is organized and stored. The underlying architecture of CJA is more designed to work with the stored data at report-time and offers its powerful report-time processing functionality not only in  Workspace but also, even more importantly, through the definition of components in your Data Views. 

![CJA report-time processing](../assets/cja-processing.png)

-->


了解各种报告功能的数据处理差异有助于了解哪些量度在哪里可用以及它们存在差异的可能原因。

例如，由于在 Adobe Analytics 中作为量度的“访问”是在进行数据处理时定义的，而 CJA 中作为量度的“会话”是在报告时计算的，因此这两个量度可能会因 CJA 数据视图中用于会话定义的规则而异。

此外，在 Analytics Source Connector 创建的数据集中，访问和会话都不是可用的量度，因此需要您在查询逻辑中定义会话，以便进行比较。

## 术语 {#terms}

下表定义了适用于 Adobe Analytics 和 CJA 的各类处理逻辑的术语：

| 术语 | 定义 | 注释 |
| --- | --- | --- |
| 收集时间处理 | 收集和处理数据时执行的逻辑，然后再存储以用于报告和分析目的。 | 这种逻辑会融入历史数据中，因此通常不容易改变。 |
| 报告时处理 | 在运行报告时执行的逻辑。 | 该逻辑能够以无损的方式应用于报告运行时的未来和历史数据。 |
| 点击级别逻辑 | 逐行应用的逻辑。 | 示例：处理规则、VISTA、某些营销渠道规则。 |
| 访问级别逻辑 | 在访问级别应用的逻辑。 | 示例：访问和会话定义。 |
| 访客级别逻辑 | 在访客级别应用的逻辑。 | 示例：跨设备/跨渠道访客拼接。 |
| 区段（过滤器）逻辑 | 评估点击/访问/访客（事件/会话/人员）区段（过滤器）规则。 | 示例：购买红色鞋款的顾客。 |
| 计算量度 | 评估客户创建的自定义量度，这些量度可以基于复杂的公式，其中包括区段和过滤器。 | 示例：购买红色鞋款的人数。 |
| 属性逻辑 | 计算属性的逻辑。 | 示例：eVar 持久性。 |
| 组件设置 | 对量度或维度应用自定义，例如归因、行为、格式等 | 示例：值分段以根据范围组合数值 |
| 自定义字段 | 逻辑适用于架构或标准字段，作为在数据视图中定义组件的一部分。 | 示例：创建新营销渠道维度 |

{style="table-layout:auto"}

随着时间的推移，Adobe Analytics 和现在的 Customer Journey Analytics 通过允许在报告运行时执行访问和访客级别的数据逻辑，提高了其灵活性。

## 数据处理类型 {#types}

为 Adobe 和 CJA 执行的数据处理步骤以及这些步骤的时间因 Analytics 功能而异。下表总结了每个分析功能的数据处理类型，以及何时应用数据处理。

| 功能 | 在处理时应用 | 在报告时应用 | 不可用 | 注释 |
| --- | --- | --- | --- | --- |
| [核心 AA ](https://experienceleague.adobe.com/docs/analytics.html?lang=zh-Hans)报告<br/>（不包括 Attribution IQ 或具有报告时间处理的虚拟报告包） | <ul><li>[处理规则](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=zh-Hans)</li><li>[VISTA 规则](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=zh-Hans)</li><li>点击级别的[营销渠道规则](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules.html?lang=zh-Hans)</li><li>访问级别的营销渠道规则（见注释）</li><li>访问的定义</li><li>属性逻辑</li></ul> | <ul><li>区段逻辑</li><li>计算量度</li></ul> | <ul><li>Cross-Device Analytics（见注释）</li></ul> | <ul><li>CDA 需要使用具有报告时间处理的虚拟报告包。</li><li>“访问级别的营销渠道规则”包括以下内容：**所访问的第一个页面**、**覆盖最后一个接触渠道**&#x200B;以及&#x200B;**营销渠道过期规定**。（见[文档](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=zh-Hans)。）</li></ul> |
| 核心 AA [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=zh-Hans) | <ul><li>处理规则</li><li>VISTA 规则</li><li>点击级别的营销渠道规则</li><li>访问级别的营销渠道规则</li><li>访问的定义</li><li>属性逻辑</li></ul> | <ul><li>区段逻辑</li></ul> | <ul><li>计算量度</li><li>跨设备分析</li></ul> |  |
| 核心 AA [数据馈送](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=zh-Hans) | <ul><li>处理规则</li><li>VISTA 规则</li><li>点击级别的营销渠道规则</li><li>访问级别的营销渠道规则</li><li>访问定义（visitnum 字段）</li><li>属性逻辑（在 post 列中）</li></ul> |  | <ul><li>区段逻辑</li><li>计算量度</li><li>跨设备分析</li></ul> | <ul><li>数据馈送中某些与营销渠道相关的列中的 ID 映射不包括在数据馈送中。（请参阅[数据馈送文档](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hans)。）</li></ul> |
| 核心 AA [直播](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> 处理规则</li><li>VISTA 规则</li><ul> |  | <ul><li>点击级别的营销渠道规则</li><li>访问级别的营销渠道规则</li><li>访问逻辑</li><li>属性逻辑</li><li>区段逻辑</li><li>计算量度</li><li>跨设备分析</li></ul> |  |
| 核心 AA [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=zh-Hans) | <ul><li>处理规则</li><li>VISTA 规则</li><li>访问的定义（见注释）</li><li>Cross-Device Analytics（见注释）</li></ul> | <ul><li>点击级别的营销渠道规则（见注释）</li><li>访问级别的营销渠道规则（见注释）属性逻辑</li><li>区段逻辑</li><li>计算量度</li></ul> |  | <ul><li>CDA 需要使用具有报告时间处理的虚拟报告包。</li><li>核心分析中的 Attribution IQ 使用完全在报告时衍生的营销渠道（即衍生中值）</li><li>除在报告时间处理 VRS 中使用外，Attribution IQ 使用的是处理时间访问定义。</li></ul> |
| 具有[报告时间处理的](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=zh-Hans) Core AA 虚拟报告包（VRS RTP） | <ul><li>处理规则</li><li>VISTA 规则</li><li>[跨设备分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=zh-Hans)</li></ul> | <ul><li>访问的定义</li><li>属性逻辑</li><li>区段逻辑</li><li>计算量度</li><li>其他 VRS RTP 设置</li></ul> | <ul><li>点击级别的营销渠道规则</li><li>访问级别的营销渠道规则</li></ul> | <ul><li>见 VRS RTP [文档](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=zh-Hans)。</li></ul> |
| 在 AEP 数据湖中基于 [ Analytics Source Connector ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hans)的数据集 | <ul><li>处理规则</li><li>VISTA 规则</li><li>点击级别的营销渠道规则</li><li>基于字段的拼接（参见注释）</li></ul> |  | <ul><li>[访问级别的营销渠道规则](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=zh-Hans)</li><li>访问逻辑</li><li>属性逻辑</li><li>过滤器逻辑</li></ul> | <ul><li>必须应用您自己的过滤器逻辑和计算度量</li><li>基于字段的拼接除了具有由 Analytics Source Connector 创建的数据集之外，还会创建一个单独的拼接数据集。</li></ul> |
| [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=zh-Hans) 报告 | <ul><li>作为Adobe Experience Platform数据收集的一部分实施</li></ul> | <ul><li>会话定义</li><li>[数据视图](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=zh-Hans)设置<li>属性逻辑</li><li>计算量度</li><li>过滤器逻辑</li></ul> | <ul><li>访问级别的营销渠道规则</li></ul> | <ul><li>若要利用基于字段的拼接，则必须使用拼接的数据集。</li></ul> |

{style="table-layout:auto"}
