---
title: 比较 Adobe Analytics 和 Customer Journey Analytics 报告功能的数据处理
description: 了解各种报告功能的数据处理差异
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
feature: Basics
role: User
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 100%

---

# 比较 Adobe Analytics 和 Customer Journey Analytics 的数据处理

您通常需要能够在数据可用于报告之前对其进行处理。您可以在从收集数据到生成报告或可视化的过程中的多个阶段处理这些数据。

在 Adob&#x200B;e Analytics 中，大部分数据处理是在收集数据后立即进行的。Vista 规则、处理规则、营销渠道处理规则等功能可用于支持&#x200B;**标识理。**&#x200B;然后，数据会被存储，并且您可以在报告时应用其他处理。例如，细分维度、应用分段或选择不同的归因模型。该&#x200B;**报告时处理**&#x200B;会即时发生。

在 Adob&#x200B;e Analytics 中，报告时处理通常意味着比收集时发生的处理量要少的处理量。

![Adobe Analytics 收集时处理](../assets/aa-processing.png)

相比之下，Customer Journey Analytics 会在组织和存储数据之前要求进行最少的提前标识理。Customer Journey Analytics 的底层架构旨在在报告时处理存储的数据，并且不仅在 Workspace 中提供强大的报告时处理功能，并且更重要的是，还可通过在“数据”视图中定义[组件](/help/data-views/component-settings/overview.md)和[派生字段](/help/data-views/derived-fields/derived-fields.md)使用这种功能。

![Customer Journey Analytics 报告时处理](../assets/cja-processing.png)

了解各种报告功能的数据处理差异有助于了解哪些量度在哪里可用以及它们存在差异的可能原因。

例如，由于在 Adobe Analytics 中作为量度的“访问”是在进行数据处理时定义的，而 Customer Journey Analytics 中作为量度的“会话”是在报告时计算的，因此这两个量度可能会因 Customer Journey Analytics 数据视图中用于会话定义的规则而异。

此外，在 Analytics Source Connector 创建的数据集中，访问和会话都不是可用的量度，因此需要您在查询逻辑中定义会话，以便进行比较。

## 术语 {#terms}

下表定义了适用于 Adobe Analytics 和 Customer Journey Analytics 的各类处理逻辑的术语：

| 术语 | 定义 | 注释 |
| --- | --- | --- |
| 收集时处理 | 收集和处理数据时，在为报告和分析目的而存储之前，所执行的逻辑。 | 这种逻辑会融入历史数据中，因此通常不容易改变。 |
| 报告时处理 | 在运行报告时执行的逻辑。 | 该逻辑能够以无损的方式应用于报告运行时的未来和历史数据。 |
| 点击级别逻辑 | 逐行应用的逻辑。 | 示例：处理规则、VISTA、某些营销渠道规则。 |
| 访问级别逻辑 | 在访问级别应用的逻辑。 | 示例：访问和会话定义。 |
| 访客级别逻辑 | 在人员级别应用的逻辑。 | 示例：跨设备/跨渠道人员拼接。 |
| 区段逻辑 | 评估事件/访问/人员（事件/会话/人员）分段规则。 | 示例：购买红色鞋款的顾客。 |
| 计算量度 | 评估客户创建的自定义量度，这些量度可以基于复杂的公式，其中包括区段。 | 示例：购买红鞋的人数。 |
| 属性逻辑 | 计算属性的逻辑。 | 示例：eVar 持久性。 |
| 组件设置 | 将自定义应用于量度或维度，例如归因、行为、格式等 | 示例：基于范围组合数值的值分段 |
| 派生字段 | 作为在“数据”视图中定义组件的一部分，逻辑应用于架构或标准字段。 | 示例：创建新的营销渠道维度 |

{style="table-layout:auto"}

随着时间的推移，Adobe Analytics 和现在的 Customer Journey Analytics 通过允许在报告运行时执行访问和人员级别的数据逻辑，从而提高了其灵活性。

## 数据处理类型 {#types}

为 Adobe Analytics 和 Customer Journey Analytics 执行的数据处理步骤以及这些步骤的时间因功能而异。下表总结了每个分析功能的数据处理类型，以及何时应用数据处理。

| 功能 | 在处理时应用 | 在报告时应用 | 不可用 | 注释 |
| --- | --- | --- | --- | --- |
| [Adobe Analytics](https://experienceleague.adobe.com/docs/analytics.html) 报告<br/>（不包括 Attribution IQ 或具有报告时处理的虚拟报告包） | <ul><li>[处理规则](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=zh-Hans)</li><li>[VISTA 规则](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html)</li><li>点击级别的[营销渠道规则](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules.html)</li><li>访问级别的营销渠道规则（见注释）</li><li>访问的定义</li><li>属性逻辑</li></ul> | <ul><li>区段逻辑</li><li>计算量度</li></ul> | <ul><li>Cross-Device Analytics（见注释）</li></ul> | <ul><li>CDA 需要使用具有报告时处理的虚拟报告包。</li><li>“访问级别的营销渠道规则”包括以下内容：**所访问的第一个页面**、**覆盖最后一个接触渠道**&#x200B;以及&#x200B;**营销渠道过期规定**。（见[文档](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html)。）</li></ul> |
| Adobe Analytics [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=zh-Hans) | <ul><li>处理规则</li><li>VISTA 规则</li><li>点击级别的营销渠道规则</li><li>访问级别的营销渠道规则</li><li>访问的定义</li><li>属性逻辑</li></ul> | <ul><li>区段逻辑</li></ul> | <ul><li>计算量度</li><li>跨设备分析</li></ul> |     |
| Adobe Analytics [数据馈送](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=zh-Hans) | <ul><li>处理规则</li><li>VISTA 规则</li><li>点击级别的营销渠道规则</li><li>访问级别的营销渠道规则</li><li>访问定义（visitnum 字段）</li><li>属性逻辑（在 post 列中）</li></ul> |   | <ul><li>区段逻辑</li><li>计算量度</li><li>跨设备分析</li></ul> | <ul><li>数据馈送中某些与营销渠道相关的列中的 ID 映射不包括在数据馈送中。（请参阅[数据馈送文档](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html)。）</li></ul> |
| Adobe Analytics [现场直播](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> 处理规则</li><li>VISTA 规则</li><ul> |   | <ul><li>点击级别的营销渠道规则</li><li>访问级别的营销渠道规则</li><li>访问逻辑</li><li>属性逻辑</li><li>区段逻辑</li><li>计算量度</li><li>跨设备分析</li></ul> |  |
| Adobe Analytics [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html) | <ul><li>处理规则</li><li>VISTA 规则</li><li>访问的定义（见注释）</li><li>Cross-Device Analytics（见注释）</li></ul> | <ul><li>点击级别的营销渠道规则（见注释）</li><li>访问级别的营销渠道规则（见注释）属性逻辑</li><li>区段逻辑</li><li>计算量度</li></ul> |  | <ul><li>CDA 需要使用具有报告时处理的虚拟报告包。</li><li>核心分析中的 Attribution IQ 使用完全在报告时衍生的营销渠道（即衍生中值）</li><li>除在报告时处理虚拟报告包中使用外，Attribution IQ 使用的是处理时访问定义。</li></ul> |
| 具有[报告时处理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=zh-Hans)的 Adobe Analytics 虚拟报告包 | <ul><li>处理规则</li><li>VISTA 规则</li><li>[跨设备分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html)</li></ul> | <ul><li>访问的定义</li><li>属性逻辑</li><li>区段逻辑</li><li>计算量度</li><li>其他虚拟报告包报告时处理设置</li></ul> | <ul><li>点击级别的营销渠道规则</li><li>访问级别的营销渠道规则</li></ul> | <ul><li>请参阅虚拟报告包报告时处理[文档](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=zh-Hans)。</li></ul> |
| Adobe Experience Platform 数据湖中基于数据集的 [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html) | <ul><li>处理规则</li><li>VISTA 规则</li><li>点击级别的营销渠道规则</li><li>基于字段的拼接（参见注释）</li></ul> |   | <ul><li>[访问级别的营销渠道规则](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html)</li><li>访问逻辑</li><li>属性逻辑</li><li>区段逻辑</li></ul> | <ul><li>必须应用您自己的分段逻辑和计算量度</li><li>基于字段的拼接除了具有由 Analytics Source Connector 创建的数据集之外，还会创建一个单独的拼接数据集。</li></ul> |
| [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html) 报告 | <ul><li>作为 Adob&#x200B;e Experience Platform 数据收集的一部分实施</li></ul> | <ul><li>会话定义</li><li>[数据视图](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html)设置<li>属性逻辑</li><li>计算量度</li><li>区段逻辑</li></ul> | <ul><li>访问级别的营销渠道规则</li></ul> | <ul><li>必须使用拼接数据集才能利用跨渠道分析。</li></ul> |

{style="table-layout:auto"}
