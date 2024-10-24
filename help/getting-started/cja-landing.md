---
title: Customer Journey Analytics 指南
description: Customer Journey Analytics 登陆页面。
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: ce04e69d2c933f893eeeff04abb0f56fb4000e6f
workflow-type: ht
source-wordcount: '820'
ht-degree: 100%

---

# Customer Journey Analytics 指南

本技术文档指南为 Customer Journey Analytics 提供了自助服务。通过 Customer Journey Analytics，您可以将客户数据从您选择的任何渠道（在线和离线）带入 Adobe Experience Platform。然后，就像现在使用 Analysis Workspace 分析现有数字数据一样分析这些数据。

借助 Customer Journey Analytics，您可以控制如何在 Analysis Workspace 的任何常见客户 ID 上连接在线和离线数据，从而进行属性、筛选条件、流量、沉降等操作。 

## 新增功能

大致了解 Customer Journey Analytics 产品和文档中的最新增强！有关功能、改进和修复的完整列表，请查看详细的[发行说明](../release-notes/latest.md)。访问 [文档更新页面](../release-notes/doc-changes.md) 以了解最新更改。

>[!BEGINTABS]

>[!TAB AI 助手]

AI 助手是一种对话体验，允许从业者快速执行任务——无论是理解概念、解决问题还是搜索信息。它还允许非专家执行专家任务并提高整体工作质量。

[![图像](assets/learn-more-button.svg)](/help/ai-assistant.md)


>[!TAB 引导式分析]

引导式分析现在可直接在 Analysis Workspace 中使用，用户使用该功能可以创建具有来自面板、可视化内容和引导式分析的全面洞察的仪表板。

[![图像](assets/learn-more-button.svg)](/help/guided-analysis/overview.md)

>[!TAB 警报]

警报允许您根据变化的百分比或特定数据点收到通知。您可以预览警报触发的频率、通过电子邮件或 SMS 发送警报、创建堆叠警报等。

[![图像](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)

>[!TAB 摘要数据]

允许您引入没有人员 ID 的时间序列数据。该时间序列数据可用于支持各种用例，例如

- 将高级性能指标作为事件级数据的一部分或在其旁边呈现。
- 以小时或每天的频率上传目标或目的，然后根据事件级量度定位这些目标或目的。

[![图像](assets/learn-more-button.svg)](/help/data-views/summary-data.md)

>[!TAB 基于图形的拼接*]

通过基于图形的拼接，您可以使用体验平台标识服务提供的标识图更好地了解客户历程： <ul><li>连接具有不同标识符的数据集，无需提取、转换和加载额外数据以反映单个标识符。</li> <li>通过跨数据集共享标识，提高单个数据集中首选或黄金标识的覆盖率。</li><li>将 Real-Time Customer Data Platform 和 Journey Optimizer 中创建的轮廓与 Customer Journey Analytics 中的人员进行对齐。</li></ul>

[![图像](assets/learn-more-button.svg)](/help/stitching/overview.md#graph-based-stitching)

*_您必须拥有 Prime 包才能进行基于图形的拼接。_*

>[!TAB 查找 B2B]

作为配置连接的一部分，您可以转换特定 B2B 查找模式的数据集，以更好地支持基于人员的 B2B 数据查找。

[![图像](assets/learn-more-button.svg)](/help/connections/transform-datasets-b2b-lookups.md)

>[!TAB 派生字段]

现在可以使用新的派生字段函数（数学、下一个、上一个、总结、重复数据删除）和附加函数模板（如跳出率、友好数据集名称、假日季节、月度目标、简单机器人检测等）。

[![图像](assets/learn-more-button.svg)](/help/data-views/derived-fields/derived-fields.md)

>[!TAB BI 扩展*]

BI 扩展允许 SQL 访问您在 Customer Journey Analytics 中定义的数据视图。现在，您可以使用您最喜欢的 BI 工具，根据 Customer Journey Analytics 用户在创建 Analysis Workspace 项目时使用的相同数据视图来创建报告和仪表板。

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
      <strong>与 Adobe Analytics 比较</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">概述</a> - <a href="/help/getting-started/aa-to-cja.md">演变</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">使用 Adobe Analytics 数据</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">功能支持</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">术语</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">数据处理</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>连接</strong><br/><a href="/help/connections/overview.md">概述</a> - <a href="/help/connections/create-connection.md">创建</a> - <a href="/help/connections/manage-connections.md">管理</a> - <a href="/help/stitching/overview.md">拼接</a> - <a href="/help/connections/combined-dataset.md">合并事件数据集</a> - <a href="/help/connections/standard-lookups.md">标准查找</a>
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
      <strong>共享、导出、集成</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">项目</a> - <a href="/help/mobile-app/home.md">Analytics 功能板 </a> - <a href="/help/report-builder/report-buider-overview.md">Report Builder</a>  - <a href="/help/components/exports/manage-exports.md">云导出</a> - <a href="/help/integrations/overview.md">集成</a>
    </td>
  </tr>
</table>

## 其他资源

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/zh-hans/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">教程</a> - <a href="https://helpx.adobe.com/cn/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Customer Journey Analytics 产品描述</a> - <a href="https://helpx.adobe.com/cn/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Adobe Analytics（Customer Journey Analytics 附加组件）产品描述</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">Customer Journey Analytics APIs</a> - <a href="/help/ai-assistant.md">AI 助手</a>
</td>
<td><strong>数据摄取</strong><br/><a href="/help/data-ingestion/data-ingestion.md">概述</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">Web SDK</a> - <a href="/help/data-ingestion/aepmobilesdk.md">Mobile SDK</a> - <a href="/help/data-ingestion/batch.md">批处理</a> - <a href="/help/data-ingestion/streaming.md">流式处理</a> - <a href="/help/data-ingestion/sources.md">源</a> - <a href="/help/data-ingestion/serverapi.md">服务器 API</a>
</td>
</tr>
</table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>随时了解最新动态、为社区做出贡献并提升您的 Customer Journey Analytics 体验！</b><br>访问 Adobe Analytics 社区，与同类从业者讨论其功能。<a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community">立即加入社区！</a></td></tr></tbody></table>
