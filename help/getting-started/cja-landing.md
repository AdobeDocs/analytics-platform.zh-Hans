---
title: Customer Journey Analytics 指南
description: Customer Journey Analytics 登陆页面。
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: d8ff5191ea96b8871f6aaba1fc28211c22a13e0d
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 96%

---

# Customer Journey Analytics 指南

本技术文档指南为 Customer Journey Analytics 提供了自助服务。通过 Customer Journey Analytics，您可以将客户数据从您选择的任何渠道（在线和离线）带入 Adobe Experience Platform。然后，就像现在使用 Analysis Workspace 分析现有数字数据一样分析这些数据。

使用 Customer Journey Analytics，您可以控制如何在 Analysis Workspace 的任何常见客户 ID 上连接在线和离线数据，从而进行属性、区段、流量、流失等操作。 

## 新增功能

大致了解 Customer Journey Analytics 产品和文档中的最新增强！有关功能、改进和修复的完整列表，请查看详细的[发行说明](../release-notes/latest.md)。 访问[文档更新页面](../release-notes/doc-changes.md)以及时了解最新的文档更新。

>[!BEGINTABS]

>[!TAB 实时报告*]

Customer Journey Analytics 中的实时报告功能可以实时显示并更新 Analysis Workspace 的一个或多个面板中的数据和可视化图表。

[![图像](assets/learn-more-button.svg)](/help/components/real-time/real-time.md)

*_您必须拥有Ultimate包才能进行实时报告。_*

>[!TAB B2B Edition]

Customer Journey Analytics B2B Edition 提供有助于推动收入增长的可操作的帐户洞察，帮助 B2B 公司协调其营销活动、销售和产品团队。帐户是数据模型的中心，因此所有分析都集中在帐户历程上。

[![图像](assets/learn-more-button.svg)](/help/getting-started/cja-b2b-edition.md)

>[!TAB 派生字段函数]

新增的派生字段函数：[日期运算](/help/data-views/derived-fields/derived-fields.md#date-math)、[深度](/help/data-views/derived-fields/derived-fields.md#depth)以及[类型转换](/help/data-views/derived-fields/derived-fields.md#typecast)。

[![图像](assets/learn-more-button.svg)](/help/data-views/derived-fields/derived-fields.md)

>[!TAB Content Analytics]

Content Analytics 可让您快速轻松地调查大量内容数据，以了解趋势、发现异常、识别内容疲劳并从内容曝光度中获取见解。

[![图像](assets/learn-more-button.svg)](/help/content-analytics/content-analytics.md)

>[!TAB 事件深度]

事件深度是一个新的标准维度，它提供了新的方法来衡量和更好地理解事件在客户会话中的位置。通过事件深度维度，可以详细跟踪和分析特定事件在会话中用户交互顺序流中的发生位置。

[![图像](assets/learn-more-button.svg)](/help/components/dimensions/overview.md#standard-dimensions)


>[!TAB 共享量度和维度]

共享量度和维度是一个用于管理维度和量度的集中地点，使其可以在任意数量的数据视图中使用。这些组件对于使用多个数据视图的组织来说特别有用，尤其是在这些数据视图共享通用组件设置的情况下。

[![图像](assets/learn-more-button.svg)](/help/data-views/shared-metrics-dimensions/smd-overview.md)


<!--
>[!TAB AI Assistant] 

AI Assistant is a conversational experience that allows practitioners to perform tasks at a fast pace - whether its understanding concepts, troubleshooting problems, or searching through information. It also allows non-experts to perform expert tasks and increases the overall quality of work.

[![image](assets/learn-more-button.svg)](/help/ai-assistant.md)


>[!TAB Guided Analysis] 

Guided Analysis is now available directly from within Analysis Workspace, enabling users to create dashboards with comprehensive insights from panels, visualizations, and guided analyses.

[![image](assets/learn-more-button.svg)](/help/guided-analysis/overview.md)



>[!TAB Intelligent captions v2] 

Intelligent captions are now supported, with additional interface improvements, for [Line](/help/analysis-workspace/visualizations/line.md) (including multi-line), [Bar](/help/analysis-workspace/visualizations/bar.md), [Horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md), [Area](/help/analysis-workspace/visualizations/area.md) (including multiple Area lines), [Donut](/help/analysis-workspace/visualizations/donut.md), [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), and [Flow](/help/analysis-workspace/visualizations/c-flow/flow.md) visualizations.

[![image](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)


>[!TAB Alerts] 

Alerts allow you to be notified based on changed percentages or specific data points. You can preview how often an alert will trigger, send alerts by email or SMS, create stacked alerts, and more.

[![image](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)


>[!TAB Summary data] 

Allows you to bring in time-series data that does not have a person ID. This time-series data can be used to support various use cases, such as 

- Presenting high-level performance indicators as part of or next to event-level data. 
- Uploading targets or goals at an hourly or daily basis, then positioning these targets or goals against event-level metrics. 

[![image](assets/learn-more-button.svg)](/help/data-views/summary-data.md)

-->

>[!TAB 基于图形的拼合*]

通过基于图形的拼合，您可以使用体验平台身份标识服务提供的身份标识图更好地了解客户历程： <ul><li>连接具有不同标识符的数据集，无需提取、转换和加载额外数据以反映单个标识符。</li> <li>通过跨数据集共享身份标识，提高单个数据集中首选或黄金身份标识的覆盖率。</li><li>将 Real-Time Customer Data Platform 和 Journey Optimizer 中创建的轮廓与 Customer Journey Analytics 中的人员进行对齐。</li></ul>

[![图像](assets/learn-more-button.svg)](/help/stitching/overview.md#graph-based-stitching)

*_您必须拥有 Prime 包才能进行基于图形的拼合。_*

>[!TAB BI 扩展*]

BI 扩展允许 SQL 访问您在 Customer Journey Analytics 中定义的数据视图。您现在可以使用自己喜欢的 BI 工具（Power BI Desktop、Tableau Desktop、Looker、Juyter Notebook 和 RStudio）根据与 Customer Journey Analytics 用户在其分析工作区项目中使用的相同的数据视图创建报告和仪表板。[提供了用例](/help/use-cases/data-views/bi-extension-usecases.md)。

[![图像](assets/learn-more-button.svg)](/help/data-views/bi-extension.md)

*_您必须拥有 Select 包或更高版本才能使用 BI 扩展。_*


>[!ENDTABS]

## 从基础知识开始

首先阅读以下链接上的材料以熟悉 Customer Journey Analytics 的功能。

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
    <a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/aa-vs-cja.png"></a>
    <div><strong>不只是在线数据</strong><br/>了解 Customer Journey Analytics 与 Adobe Analytics 的比较情况、共享哪些功能以及如何使用 Analytics 数据。</div>
    </td>
    <td>
    <a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/data-ingestion.png"></a>
    <div><strong>摄取和使用数据</strong><br/>了解有关将数据摄取到 Experience Platform 并将其用于 Customer Journey Analytics 中的分析和报告的选项。</div>
    </td>
    <td>
    <a href="/help/guided-analysis/overview.md"><img src="./assets/product-analytics.png"></a>
    <div><strong>引导式分析</strong><br/>了解如何使用工作流获取有关客户产品体验的数据和见解。通过引导分析使用 Product Analytics...
    </div>
    </td>
    <td>
    <a href="/help/analysis-workspace/home.md"><img src="./assets/workspace.png"></a>
    <div><strong>Analysis Workspace</strong><br/>使用 Analysis Workspace 执行基本和高级分析，例如归因、流量图和流失图、维度细分。</div>
    </td>
  </tr>
  <tr style="border: 0;">
    <td align="center"><a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/guided-analysis/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/analysis-workspace/home.md"><img src="./assets/learn-more-button.svg"></a></td>
    </tr>
</table>


## 浏览文档

了解 Customer Journey Analytics 怎样与 Adobe Analytics 相比较。以及如何将数据放入解决方案中，然后准备、查看、分析和大众化这些数据以及由此产生的分析和报告。

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
      <img src="./assets/analytics.svg" width="35px"><br/>
      <strong>与 Adobe Analytics 比较</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">概述</a> - <a href="/help/getting-started/aa-to-cja.md">演进过程</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">使用 Adobe Analytics 数据</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">功能支持</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">术语</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">数据处理</a> - <a href="/help/getting-started/cja-b2b-edition.md">Customer Journey Analytics B2B Edition</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>连接</strong><br/><a href="/help/connections/overview.md">概述</a> - <a href="/help/connections/create-connection.md">创建</a> - <a href="/help/connections/manage-connections.md">管理</a> - <a href="/help/stitching/overview.md">拼合</a> - <a href="/help/connections/combined-dataset.md">合并事件数据集</a> - <a href="/help/connections/standard-lookups.md">标准查找</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/>
      <strong>数据视图</strong><br/><a href="/help/data-views/data-views.md">概述</a> - <a href="/help/data-views/create-dataview.md">创建或编辑</a> - <a href="/help/data-views/session-settings.md">会话设置</a> - <a href="/help/data-views/derived-fields/derived-fields.md">派生字段</a> - <a href="/help/data-views/summary-data.md">摘要数据</a> - <a href="/help/data-views/component-reference.md">组件参考</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Workspace 项目</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">基本</a>和<a href="/help/analysis-workspace/perform-adv-analysis.md">高级分析</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">项目</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">可视化</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">面板</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong>引导式分析</strong><br/><a href="/help/guided-analysis/overview.md">概述</a> - <a href="/help/guided-analysis/types/active-growth.md">用户增长</a> - <a href="/help/guided-analysis/types/trends.md">趋势</a> - <a href="/help/guided-analysis/types/funnel.md">漏斗</a> - <a href="/help/guided-analysis/types/release-impact.md">影响</a> - <a href="/help/guided-analysis/industry-use-cases.md">行业用例</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
      <strong>共享、导出、集成</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">项目</a> - <a href="/help/mobile-app/home.md">Analytics 功能板 </a> - <a href="/help/report-builder/rb-overview.md">Report Builder</a>  - <a href="/help/components/exports/manage-exports.md">云导出</a> - <a href="/help/integrations/overview.md">集成</a>
    </td>
  </tr>
</table>

## 其他资源

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/zh-hans/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">教程</a> - <a href="https://helpx.adobe.com/cn/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Customer Journey Analytics 产品描述</a> - <a href="https://helpx.adobe.com/cn/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Adobe Analytics（Customer Journey Analytics 附加组件）产品描述</a> - <a href="https://helpx.adobe.com/cn/legal/product-descriptions/customer-journey-analytics-b2b.html" target="_blank">Customer Journey Analytics B2B Edition 产品描述</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">Customer Journey Analytics API</a> - <a href="/help/ai-assistant.md">AI 助手</a>
</td>
<td><strong>数据摄取</strong><br/><a href="/help/data-ingestion/data-ingestion.md">概述</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">Web SDK</a> - <a href="/help/data-ingestion/aepmobilesdk.md">Mobile SDK</a> - <a href="/help/data-ingestion/batch.md">批处理</a> - <a href="/help/data-ingestion/streaming.md">流式处理</a> - <a href="/help/data-ingestion/sources.md">源</a> - <a href="/help/data-ingestion/serverapi.md">服务器 API</a>
</td>
</tr>
</table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>随时了解最新动态、为社区做出贡献并提升您的 Customer Journey Analytics 体验！</b><br>访问 Adobe Analytics 社区，与同类从业者讨论其功能。<a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community">立即加入社区！</a></td></tr></tbody></table>
