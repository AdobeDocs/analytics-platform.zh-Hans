---
title: 比较 Adobe Analytics 和 Customer Journey Analytics 报告功能的数据处理
description: 了解各种报告功能的数据处理差异
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
feature: Basics
role: User
source-git-commit: 0e9dc47b80db142801a94dcbf31470d99a610949
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 65%

---

# 比较 Adobe Analytics 和 Customer Journey Analytics 的数据处理

您通常需要能够在数据可用于报告之前对其进行处理。您可以在从收集数据到生成报告或可视化的过程中的多个阶段处理这些数据。

在 Adob&#x200B;e Analytics 中，大部分数据处理是在收集数据后立即进行的。Vista 规则、处理规则、营销渠道处理规则等功能可用于支持&#x200B;**标识理。**&#x200B;然后，数据会被存储，并且您可以在报告时应用其他处理。例如，细分维度、应用分段或选择不同的归因模型。该&#x200B;**报告时处理**&#x200B;会即时发生。

在 Adob&#x200B;e Analytics 中，报告时处理通常意味着比收集时发生的处理量要少的处理量。

![Adobe Analytics 收集时处理](../assets/aa-processing.png)

相比之下，Customer Journey Analytics设计为在组织和存储数据之前只需最少的前期收集时间处理。 Customer Journey Analytics的底层架构设计用于在报告时处理存储的数据。 Customer Journey Analytics不仅在Analysis Workspace中提供了强大的报表时间处理功能。 通过定义数据视图中的[组件](/help/data-views/component-settings/overview.md)和[派生字段](/help/data-views/derived-fields/derived-fields.md)，还可以使用其他报表时间处理功能。

![Customer Journey Analytics 报告时处理](../assets/cja-processing.png)

了解各种报告功能的数据处理差异有助于了解哪些量度在哪里可用以及它们存在差异的可能原因。

例如，*访问次数*&#x200B;被定义为Adobe Analytics中数据处理时的量度。 在报告时，在Customer Journey Analytics中将&#x200B;*会话*&#x200B;计算为指标。 因此，根据Customer Journey Analytics数据视图中会话定义的规则，这两个量度可能会有所不同。

此外，在Analytics Source Connector创建的数据集中，访问和会话量度不可用。 因此，需要您在查询逻辑中定义会话，以便进行比较。

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
| 计算量度 | 评估客户创建的自定义量度。 计算量度可以基于复杂的公式，包括区段。 | 例如，购买红色鞋子的人数。 |
| 属性逻辑 | 计算属性的逻辑。 | 示例：eVar 持久性。 |
| 组件设置 | 将自定义项应用于量度或维度，如归因、行为、格式等 | 示例：基于范围组合数值的值分段 |
| 派生字段 | 在数据视图中定义组件时应用于架构或标准字段的逻辑。 | 示例：创建新的营销渠道维度 |

{style="table-layout:auto"}

随着时间的推移，Adobe Analytics 和现在的 Customer Journey Analytics 通过允许在报告运行时执行访问和人员级别的数据逻辑，从而提高了其灵活性。

## 数据处理类型 {#types}

Adobe Analytics和Customer Journey Analytics执行的数据处理步骤以及这些步骤的时间因功能而异。 下表总结了每个功能的数据处理类型以及何时应用数据处理。

| 功能 | 在处理时应用 | 在报告时应用 | 不可用 | 注释 |
| --- | --- | --- | --- | --- |
| [Adobe Analytics](https://experienceleague.adobe.com/zh-hans/docs/analytics)报表<br/>（不包括高级归因功能或具有报表时间处理的虚拟报表包） | <ul><li>[处理规则](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/c-processing-rules/processing-rules)</li><li>[VISTA 规则](https://experienceleague.adobe.com/en/docs/analytics/technotes/terms)</li><li>点击级别的[营销渠道规则](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules)</li><li>访问级别的营销渠道规则（见注释）</li><li>访问的定义</li><li>属性逻辑</li></ul> | <ul><li>区段逻辑</li><li>计算量度</li></ul> | <ul><li>Cross-Device Analytics（见注释）</li></ul> | <ul><li>跨设备分析需要使用具有报表时间处理的虚拟报表包。</li><li>“访问级别的营销渠道规则”包括以下内容：**所访问的第一个页面**、**覆盖最后一个接触渠道**&#x200B;以及&#x200B;**营销渠道过期规定**。（见[文档](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels)。）</li></ul> |
| Adobe Analytics [Data Warehouse](https://experienceleague.adobe.com/zh-hans/docs/analytics/export/data-warehouse/data-warehouse) | <ul><li>处理规则</li><li>VISTA 规则</li><li>点击级别的营销渠道规则</li><li>访问级别的营销渠道规则</li><li>访问的定义</li><li>属性逻辑</li></ul> | <ul><li>区段逻辑</li></ul> | <ul><li>计算量度</li><li>跨设备分析</li></ul> |     |
| Adobe Analytics [数据馈送](https://experienceleague.adobe.com/zh-hans/docs/analytics/export/analytics-data-feed/data-feed-overview) | <ul><li>处理规则</li><li>VISTA 规则</li><li>点击级别的营销渠道规则</li><li>访问级别的营销渠道规则</li><li>访问定义（visitnum 字段）</li><li>属性逻辑（在 post 列中）</li></ul> |   | <ul><li>区段逻辑</li><li>计算量度</li><li>跨设备分析</li></ul> | <ul><li>数据馈送中某些与营销渠道相关的列中的 ID 映射不包括在数据馈送中。（请参阅[数据馈送文档](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference)。）</li></ul> |
| Adobe Analytics [现场直播](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> 处理规则</li><li>VISTA 规则</li><ul> |   | <ul><li>点击级别的营销渠道规则</li><li>访问级别的营销渠道规则</li><li>访问逻辑</li><li>属性逻辑</li><li>区段逻辑</li><li>计算量度</li><li>跨设备分析</li></ul> |  |
| Adobe Analytics [高级归因功能](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/overview) | <ul><li>处理规则</li><li>VISTA 规则</li><li>访问的定义（见注释）</li><li>Cross-Device Analytics（见注释）</li></ul> | <ul><li>点击级别的营销渠道规则（见注释）</li><li>访问级别的营销渠道规则（见注释）属性逻辑</li><li>区段逻辑</li><li>计算量度</li></ul> |  | <ul><li>跨设备分析需要使用具有报表时间处理的虚拟报表包。</li><li>核心Analytics中的高级归因功能使用在报告时完全派生的营销渠道（即派生的中间值）。</li><li>高级归因功能使用处理时间访问定义，但在报表时间处理虚拟报表包中使用时除外。</li></ul> |
| 具有[报告时处理](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-report-time-processing)的 Adobe Analytics 虚拟报告包 | <ul><li>处理规则</li><li>VISTA 规则</li><li>[跨设备分析](https://experienceleague.adobe.com/en/docs/analytics/components/cda/overview)</li></ul> | <ul><li>访问的定义</li><li>属性逻辑</li><li>区段逻辑</li><li>计算量度</li><li>其他虚拟报告包报告时处理设置</li></ul> | <ul><li>点击级别的营销渠道规则</li><li>访问级别的营销渠道规则</li></ul> | <ul><li>请参阅虚拟报告包报告时处理[文档](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-report-time-processing)。</li></ul> |
| Adobe Experience Platform 数据湖中基于数据集的 [Analytics Source Connector](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics) | <ul><li>处理规则</li><li>VISTA 规则</li><li>点击级别的营销渠道规则</li><li>基于字段的拼接（参见注释）</li></ul> |   | <ul><li>[访问级别的营销渠道规则](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels)</li><li>访问逻辑</li><li>属性逻辑</li><li>区段逻辑</li></ul> | <ul><li>应用您自己的区段逻辑和计算量度</li><li>基于字段的拼接除了具有由 Analytics Source Connector 创建的数据集之外，还会创建一个单独的拼接数据集。</li></ul> |
| [Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-landing) 报告 | <ul><li>作为 Adob&#x200B;e Experience Platform 数据收集的一部分实施</li></ul> | <ul><li>会话定义</li><li>[数据视图](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/data-views)设置<li>属性逻辑</li><li>计算量度</li><li>区段逻辑</li></ul> | <ul><li>访问级别的营销渠道规则</li></ul> | <ul><li>使用拼合的数据集以利用跨渠道分析。</li></ul> |

{style="table-layout:auto"}
