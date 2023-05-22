---
title: 跨 Adobe Analytics 和 CJA 报告功能比较数据处理
description: 了解各种报告功能的数据处理差异
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '1202'
ht-degree: 74%

---

# 比較Adobe Analytics和Customer Journey Analytics的資料處理。

您通常需要先處理資料，才對報表有用。 您可以在歷程的多個階段處理該資料，從收集資料到產生報表或視覺效果。

在Adobe Analytics中，大部分資料處理會在收集資料後立即進行。 VISTA規則、處理規則、行銷管道處理規則等功能可支援此功能 **收集時間處理**.
然後會儲存資料，您可以在報告時套用其他處理。 例如，劃分維度、套用區段或選取不同的歸因模型。 此 **報告時間處理** 會立即發生。

在Adobe Analytics中，報表時間處理通常比收集時發生的處理量小。

![Adobe Analytics集合時間處理](../assets/aa-processing.png)

相較之下，Customer Journey Analytics(CJA)的設計目的是在組織和儲存資料之前，只需要最少的前置收集時間處理。 CJA的底層架構更適合在報告時間處理儲存的資料，並提供其強大的報告時間處理功能，不僅在工作區中，更重要的是，透過以下定義 [元件](/help/data-views/component-settings/overview.md) 和 [衍生欄位](/help/data-views/derived-fields/derived-fields.md) 在您的資料檢視中。

![CJA報告時間處理](../assets/cja-processing.png)

了解各种报告功能的数据处理差异有助于了解哪些量度在哪里可用以及它们存在差异的可能原因。

例如，由于在 Adobe Analytics 中作为量度的“访问”是在进行数据处理时定义的，而 CJA 中作为量度的“会话”是在报告时计算的，因此这两个量度可能会因 CJA 数据视图中用于会话定义的规则而异。

此外，在 Analytics Source Connector 创建的数据集中，访问和会话都不是可用的量度，因此需要您在查询逻辑中定义会话，以便进行比较。

## 术语 {#terms}

下表定义了适用于 Adobe Analytics 和 CJA 的各类处理逻辑的术语：

| 术语 | 定义 | 注释 |
| --- | --- | --- |
| 集合時間處理 | 在儲存資料以用於報告和分析之前，收集和處理資料時執行的邏輯。 | 这种逻辑会融入历史数据中，因此通常不容易改变。 |
| 報告時間處理 | 在运行报告时执行的逻辑。 | 该逻辑能够以无损的方式应用于报告运行时的未来和历史数据。 |
| 点击级别逻辑 | 逐行应用的逻辑。 | 示例：处理规则、VISTA、某些营销渠道规则。 |
| 访问级别逻辑 | 在访问级别应用的逻辑。 | 示例：访问和会话定义。 |
| 访客级别逻辑 | 在访客级别应用的逻辑。 | 示例：跨设备/跨渠道访客拼接。 |
| 区段（过滤器）逻辑 | 評估事件/造訪/訪客（事件/工作階段/人員）區段（篩選器）規則。 | 示例：购买红色鞋款的顾客。 |
| 计算量度 | 评估客户创建的自定义量度，这些量度可以基于复杂的公式，其中包括区段和过滤器。 | 示例：购买红色鞋款的人数。 |
| 属性逻辑 | 计算属性的逻辑。 | 示例：eVar 持久性。 |
| 组件设置 | 將自訂套用至量度或維度，例如歸因、行為、格式等 | 範例：根據範圍組合數值的值分組 |
| 自定义字段 | 在資料檢視中定義元件時，邏輯會套用至結構描述或標準欄位。 | 範例：建立新的行銷管道維度 |

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
| [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=zh-Hans) 报告 | <ul><li>實作為Adobe Experience Platform資料收集的一部分</li></ul> | <ul><li>会话定义</li><li>[数据视图](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=zh-Hans)设置<li>属性逻辑</li><li>计算量度</li><li>过滤器逻辑</li></ul> | <ul><li>访问级别的营销渠道规则</li></ul> | <ul><li>為了善用跨管道分析，必須使用拼接資料集。</li></ul> |

{style="table-layout:auto"}
