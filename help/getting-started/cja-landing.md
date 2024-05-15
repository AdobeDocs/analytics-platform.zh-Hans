---
title: Customer Journey Analytics 指南
description: Customer Journey Analytics 登陆页面。
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: 6b5a9050d6c13e3c9d637a3ed992840a46058cee
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 59%

---

# Customer Journey Analytics 指南

本技术文档指南为 Customer Journey Analytics 提供了自助服务。Customer Journey Analytics允许您从所选的任何渠道（在线和离线）将客户数据导入Adobe Experience Platform。 然后，像现在使用Analysis Workspace分析现有数字数据一样分析这些数据。

通过Customer Journey Analytics，您可以控制如何在Analysis Workspace中将任何通用客户ID上的在线和离线数据进行关联， 等分析。

## 新增功能

大致了解 Customer Journey Analytics 产品和文档中的最新增强！有关功能、改进和修复的完整列表，请查看详细的[发行说明](../release-notes/latest.md)。访问 [文档更新页面](../release-notes/doc-changes.md) 以掌握最新更改。

>[!BEGINTABS]

>[!TAB BI扩展*]

BI扩展允许SQL访问您在Customer Journey Analytics中定义的数据视图。 您现在可以使用常用的BI工具，根据Customer Journey Analytics用户在其Analysis Workspace项目中使用的数据视图创建报表和功能板。

[![图像](assets/learn-more-button.svg)](/help/data-views/bi-extension.md)

<span style="color:gray">*_您必须具有Select程序包或更高版本才能使用BI扩展。_</span>


<!--
>[!TAB Improved Audience Publising] 

Audiences that are published from Customer Journey Analytics are now available in the new **Audiences** section in Adobe Experience Platform. Audiences are now available in Experience Platform seconds after they are published from Customer Journey Analytics. Improved sorting and filter options in Experience Platform for Customer Journey Analytics audiences. 

[![image](assets/learn-more-button.svg)](/help/components/audiences/publish.md)

-->


>[!TAB 新文档]

新文档现已在以下位置提供：<ul><li>如何从Adobe Analytics升级到Customer Journey Analytics。</li><li>数据导出用例以及所需的Experience Platform和客户历程功能。 </li></ul>选择 **[!UICONTROL 了解详情]** 有关本文档和其他文档更新。

[![图像](assets/learn-more-button.svg)](/help/release-notes/doc-changes.md)

>[!TAB 预测]

预测是 Analysis Workspace 的一项功能，用于以任何支持的时间粒度（每小时、每天、每周、每月和每年）预测标准量度或计算量度。预测仅适用于与时间序列相关的数据。

[![图像](assets/learn-more-button.svg)](/help/analysis-workspace/c-forecast/forecasting.md)

>[!TAB 引导式分析* - 留存率]

一种新的视图类型，其中显示所需的日期范围内在其初次参与后回归的用户所占的百分比。横轴表示用户初次参与后经历的天数。纵轴表示再次参与的用户所占的百分比。

[![图像](assets/learn-more-button.svg)](/help/guided-analysis/types/retention-rates.md)

<span style="color:gray">*_引导式分析是 Customer Journey Analytics 的付费附加组件 Adobe Product Analytics 的一部分。_</span>


>[!TAB 引导式分析* - 趋势线]

“使用情况”视图中现在有趋势线叠加层可用，它们有助于更清晰地描绘数据中的模式。可用的趋势线的类型包括线性趋势线、对数趋势线和均线。

[![图像](assets/learn-more-button.svg)](/help/guided-analysis/types/usage.md)

<span style="color:gray">*_引导式分析是 Customer Journey Analytics 的付费附加组件 Adobe Product Analytics 的一部分。_</span>

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
    <div><strong>摄取和使用数据</strong><br/>了解将数据摄取到Experience Platform并用于分析和在Customer Journey Analytics中生成报表必须使用的选项。</div>
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

了解Customer Journey Analytics与Adobe Analytics的对比。 以及如何在解决方案中获取您的数据，然后准备、查看、分析和普及这些数据，以及产生的分析和报告。

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
      <strong>数据视图</strong><br/><a href="/help/data-views/data-views.md">概述</a> - <a href="/help/data-views/create-dataview.md">创建或编辑</a> - <a href="/help/data-views/session-settings.md">会话设置</a> - <a href="/help/data-views/derived-fields/derived-fields.md">派生字段</a> - <a href="/help/data-views/component-reference.md">组件引用</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>工作区项目</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">基本</a> 和 <a href="/help/analysis-workspace/perform-adv-analysis.md">高级分析</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">项目</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">可视化图表</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">面板</a>
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
<a href="https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">教程</a> - <a href="https://helpx.adobe.com/cn/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Customer Journey Analytics 产品描述</a> - <a href="https://helpx.adobe.com/cn/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Adobe Analytics（Customer Journey Analytics 附加组件）产品描述</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">Customer Journey Analytics API</a>
</td>
<td><strong>数据摄取</strong><br/><a href="/help/data-ingestion/data-ingestion.md">概述</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">Web SDK</a> - <a href="/help/data-ingestion/aepmobilesdk.md">Mobile SDK</a> - <a href="/help/data-ingestion/batch.md">批处理</a> - <a href="/help/data-ingestion/streaming.md">流式处理</a> - <a href="/help/data-ingestion/sources.md">源</a> - <a href="/help/data-ingestion/serverapi.md">服务器 API</a>
</td>
</tr></table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>随时了解最新动态、为社区做出贡献并提升您的 Customer Journey Analytics 体验！</b><br>请访问Adobe Analytics社区，与其他从业人员讨论该功能。 <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community">立即加入社区！</a></td></tr></tbody></table>
