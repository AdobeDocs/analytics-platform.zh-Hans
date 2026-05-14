---
title: 当前 Customer Journey Analytics 发行说明
description: 查看最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 11f60dbdd2858f173896a131c08229e0c7f29a69
workflow-type: tm+mt
source-wordcount: 819
ht-degree: 45%

---

# 当前Customer Journey Analytics发行说明（2026年5月）

**上次更新日期**：2026年5月13日

这些发行说明涵盖2026年5月发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。 因此，这些发行说明每月更新几次。 请定期检查。

## 新增功能或更新后的功能

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| -----------|-----------|-----------|
| **CJA API Postman集合** <br/>可下载的Postman集合可用于调用CJA API端点。<p>有关详细信息，请参阅[analytics-cja-postman-collections Github存储库](https://github.com/AdobeDocs/analytics-cja-postman-collections)。  </p> | | 2026年5月1日 |
| **用于Customer Journey Analytics的MCP服务器** <br/>Analytics MCP（模型上下文协议）服务器允许您将受支持的MCP客户端连接到Adobe Customer Journey Analytics。 连接后，MCP客户端可以调用特定于产品的工具来检索数据、运行查询或执行作为LLM或代理工作流一部分的受支持操作。 有关详细信息，请参阅[Analytics MCP服务器](https://developer.adobe.com/analytics-mcp/docs/)。<p>如果您在Beta测试期间使用这些MCP服务器，请注意，Beta测试版和生产版端点之间有不同的URL。 请确保在5月31日之前将测试期间创建的任何代理工作流更新为使用生产端点。</p> | | 2026年5月5日 |
| **Content Analytics支持本机移动应用程序体验**<br/>&#x200B;组织可以将其内容性能分析扩展到iOS和Android应用程序，捕获图像资源和精细的体验元素，以了解哪些应用程序内内容可促进用户参与和业务成果。<p> [文档](/help/content-analytics/content-analytics.md)已更新，以描述移动渠道功能和配置。 有关[Content Analytics Mobile SDK扩展](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/)的信息可在[Adobe Developer](https://developer.adobe.com/)上获取。</p><p>分析适用于所有Adobe Content Analytics客户。</p> | | 2026年5月6日 |
| **历程画布增强功能** <br/>历程画布可视化中提供了以下增强功能： <ul><li>从历程中[排除节点](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#exclude-nodes)。</li><li>使用节点的流失数据[创建区段](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#create-a-segment-based-on-a-node-or-arrow)、[趋势](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#view-trend-data)、[受众](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#create-an-audience)和[划分](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#apply-a-breakdown)。</li></ul> | | 2026年5月18日 |
| **Adobe Engineering 代理中的数据验证** <br/>Data Engineering 代理中提供新的数据验证技能。 这些技能可以在 Customer Journey Analytics 分析数据之前，帮助团队直接在 Adobe Experience Platform 中快速评估数据质量。 <p>数据验证技能可以进行按需验证、字段级验证和数据集级验证，将统计摘要与对无效值或异常值的智能检测结合起来。 </p><p>使用数据验证技能可减少手动 QA 工作量，加快各种数据工程工作流中可信数据的加入和转换。</p><p>（文档链接见下文。）<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 2026年5月19日 <p>（原计划于 2026 年 3 月 31 日发布）</p> |
| **Content Analytics：折线图可视化图表缩略图和预览** <br/>[缩略图和预览](/help/content-analytics/report/report.md)现在可用于Content Analytics折线图可视化图表中的资源和体验。 |  | 2026年5月20日 |
| **流媒体服务：支持计划数据** <br/>您现在可以上传过去直播流媒体服务内容的计划数据，以便更轻松、更准确地跟踪观看人数。<p>以下是支持计划数据上传的直播内容示例：</p><ul><li>FAST（免费广告支持电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。 您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>如需了解更多信息，请参阅[上传计划数据以跟踪实时内容](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>（原计划于 2025 年 10 月 29 日发布）</p> |

{style="table-layout:auto"}


## Customer Journey Analytics 中的修复

**Analysis Workspace**： AN-446522、AN-445779、AN-445759、AN-444676、AN-442813、AN-441943、AN-441717、AN-441538、AN-441123、AN-440976、AN-440952、AN-440919、AN-439797、AN-434855、AN-429777、AN-429048、AN-428892、AN-428189、AN-425215、AN-
**组件**：
**连接**： AN-449652、AN-444560、AN-442824、AN-440937、AN-440092、AN-439823、AN-429781
**Content Analytics**：
**引导式分析**：
**导出**： AN-438953， AN-437115
**数据视图**： AN-442809
**实施**：
**Report Builder**： AN-448697、AN-447128、AN-441148、AN-441136、AN-438147、AN-425150
**报告**： AN-445123、AN-442231、AN-442169、AN-441811、AN-441733、AN-440505、AN-440300、AN-434824、AN-434210、AN-424000、AN-423359、AN-406242
**分段**：
**计划报告**：
**共享的量度和维度**：
**Other**： AN-449159、AN-444661、AN-443900、AN-397985

## 相关资产

* [之前的 2025 Customer Journey Analytics 发行说明](/help/release-notes/2025.md)
* [Adobe Analytics发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hans)
* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
* [Adobe Experience Cloud发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
