---
title: Customer Journey Analytics 指南
description: Customer Journey Analytics 登陆页面。
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: 2f5bd8bec1580077675d249fa0431d84ee2269fa
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 94%

---

# Customer Journey Analytics 指南

本技术文档指南为 Customer Journey Analytics 提供了自助服务。通过 Customer Journey Analytics，可从所选的任何渠道（在线和离线）将客户数据纳入 Adobe Experience Platform，然后像当今使用 Analysis Workspace 分析现有数字数据一样分析这些数据。

通过 Customer Journey Analytics，可控制如何在 Analysis Workspace 中通过任何通用客户 ID 为在线和离线数据建立关联，最终可在客户数据上进行归因、筛选、流量、流失等分析。

## 新增功能

大致了解 Customer Journey Analytics 产品和文档中的最新增强！有关功能、改进和修复的完整列表，请查看详细的[发行说明](../release-notes/latest.md)。通过访问[文档更新页面](../release-notes/doc-changes.md)，可及时了解我们文档的最新更改。

>[!BEGINTABS]

>[!TAB 预测]

预测功能是一种Analysis Workspace功能，可用于预测具有任何受支持时间粒度（每小时、每天、每周、每月和每年）的标准或计算量度。 预测仅适用于与时间序列相关的数据。

[![图像](assets/learn-more-button.svg)](/help/analysis-workspace/c-forecast/forecasting.md)


>[!TAB 引导式分析* - 留存率]

一种新的视图类型，其中显示所需的日期范围内在其初次参与后回归的用户所占的百分比。横轴表示用户初次参与后经历的天数。纵轴表示再次参与的用户所占的百分比。

[![图像](assets/learn-more-button.svg)](/help/guided-analysis/types/retention-rates.md)

<span style="color:gray">*_引导式分析是 Customer Journey Analytics 的付费附加组件 Adobe Product Analytics 的一部分。_</span>


>[!TAB 引导式分析* - 趋势线]

“使用情况”视图中现在有趋势线叠加层可用，它们有助于更清晰地描绘数据中的模式。可用的趋势线的类型包括线性趋势线、对数趋势线和均线。

[![图像](assets/learn-more-button.svg)](/help/guided-analysis/types/usage.md)

<span style="color:gray">*_引导式分析是 Customer Journey Analytics 的付费附加组件 Adobe Product Analytics 的一部分。_</span>


>[!TAB 关键量度摘要可视化]

在使用关键量度摘要可视化时，根据您选择的“比较日期范围”选项是相对于主要日期范围还是固定日期，现在可自动更新比较日期范围。

[![图像](assets/learn-more-button.svg)](/help/analysis-workspace/visualizations/key-metric.md)

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

了解 Customer Journey Analytics 与 Adobe Analytics 的比较情况，以及如何在解决方案中获取数据，然后准备、查看、分析和民主化这些数据以及生成的分析和报告。

<table style="table-layout:auto">
  <tr style="border: 0;">
    <td>
      <img src="./assets/analytics.svg" width="35px"><br/>
      <strong>与 Adobe Analytics 比较</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">概述</a> - <a href="/help/getting-started/aa-to-cja.md">演变</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">使用 Adobe Analytics 数据</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">功能支持</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">术语</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">数据处理</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>连接</strong><br/><a href="/help/connections/overview.md">概述</a> - <a href="/help/connections/create-connection.md">创建</a> - <a href="/help/connections/manage-connections.md">管理</a> - <a href="/help/stitching/overview.md">拼接</a> - <a href="/help/connections/combined-dataset.md">合并事件数据集</a> - <a href="/help/connections/standard-lookups.md">标准查找</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/>
      <strong>数据视图</strong><br/><a href="/help/data-views/data-views.md">概述</a> - <a href="/help/data-views/create-dataview.md">创建或编辑</a> - <a href="/help/data-views/session-settings.md">会话设置</a> - <a href="/help/data-views/derived-fields/derived-fields.md">派生字段</a> - <a href="/help/data-views/component-reference.md">组件参考</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Workspace 项目</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">基本</a>和<a href="/help/analysis-workspace/perform-adv-analysis.md">高级分析</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">项目</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">可视化</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">面板</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong>引导式分析</strong><br/><a href="/help/guided-analysis/overview.md">概述</a> - <a href="/help/guided-analysis/types/active.md">用户增长</a> - <a href="/help/guided-analysis/types/usage.md">趋势</a> - <a href="/help/guided-analysis/types/friction.md">漏斗</a> - <a href="/help/guided-analysis/types/release.md">影响</a> - <a href="/help/guided-analysis/industry-use-cases.md">行业用例</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
      <strong>共享、导出、集成</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">项目</a> - <a href="/help/mobile-app/home.md">Analytics 功能板</a> - <a href="/help/report-builder/report-buider-overview.md">Report Builder</a>  - <a href="/help/integrations/overview.md">集成</a>
    </td>
  </tr>
</table>

## 其他资源

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/overview.html" target="_blank">教程</a> - <a href="https://helpx.adobe.com/cn/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Customer Journey Analytics 产品描述</a> - <a href="https://helpx.adobe.com/cn/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Adobe Analytics（Customer Journey Analytics 附加组件）产品描述</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">Customer Journey Analytics API</a>
</td>
<td><strong>数据摄取</strong><br/><a href="/help/data-ingestion/data-ingestion.md">概述</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">Web SDK</a> - <a href="/help/data-ingestion/aepmobilesdk.md">Mobile SDK</a> - <a href="/help/data-ingestion/batch.md">批处理</a> - <a href="/help/data-ingestion/streaming.md">流式处理</a> - <a href="/help/data-ingestion/sources.md">源</a> - <a href="/help/data-ingestion/serverapi.md">服务器 API</a>
</td>
</tr></table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>随时了解最新动态、为社区做出贡献并提升您的 Customer Journey Analytics 体验！</b><br>访问 Adobe Analytics 社区，与同类从业者讨论功能。<a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community">立即加入社区！</a></td></tr></tbody></table>
