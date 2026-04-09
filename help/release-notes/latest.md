---
title: 当前 Customer Journey Analytics 发行说明
description: 查看最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7fc7475001505749cf59aa82a62e5abb7e81ea97
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 39%

---

# 当前Customer Journey Analytics发行说明（2026年4月）

**上次更新时间**：2026年4月9日

这些发行说明涵盖2026年4月发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| -----------|-----------|-----------|
| **意大利语支持**<br/> Customer Journey Analytics中的Analysis Workspace现在支持意大利语区域设置(it-IT)。 <p>Customer Journey Analytics支持Experience Platform UI中支持的所有语言，如Experience Platform UI的[浏览器和语言支持](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/landing/platform-ui/browser-language-support#language-support)中所述。</p><p>您可以在Experience Platform中[更改默认语言](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language)。</p> | | 2026年4月8日 |
| **Adobe工程代理中的数据验证** <br/>Data Engineering Agent中提供了新的数据验证技能。 在Customer Journey Analytics中分析数据之前，这些技能可帮助团队直接在Adobe Experience Platform中快速评估数据质量。 <p>数据验证技能支持按需验证、字段级验证和数据集级验证，从而将统计摘要与对无效或异常值的智能检测结合起来。 </p><p>使用数据验证技能可减少手动QA工作量，并加快跨数据工程工作流的受信任数据载入和转换。</p><p>（文档链接见下文。）<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/zh-hans/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 2026年4月底 <p>（原计划于2026年3月31日发布）</p> |
| **用于Customer Journey Analytics的MCP服务器** <br/>您现在可以使用MCP（模型上下文协议）将Customer Journey Analytics绑定到现有代理工作流中。 您可以使用自然语言请求报表和见解。<p>（文档链接见下文。）</p> | | 2026年4月底 |
| **流媒体服务：支持计划数据** <br/>您现在可以上传过去直播流媒体内容的计划数据，以便更轻松、更准确地跟踪收视率。<p>以下是支持计划数据上传的直播内容示例：</p><ul><li>FAST（免费广告支持电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。 您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>如需了解更多信息，请参阅[上传计划数据以跟踪实时内容](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>（原计划于 2025 年 10 月 29 日发布）</p> |
| **多维度API报告**<br/>&#x200B;在单一API请求中报告多个维度并执行维度级别的搜索。 [了解详情](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim) | | 2026 年 3 月 |
| **多列API排序**<br/>&#x200B;对API请求中的多个维度和量度对象进行排序。 在同一排序定义中混合使用维度和量度。 [了解详情](https://developer.adobe.com/cja-apis/docs/endpoints/reporting/multidim#multi-column-sorting) | | 2026 年 3 月 |

## Customer Journey Analytics 中的修复

**Analysis Workspace**： AN-442813、AN-442410、AN-442231、AN-441943、AN-441717、AN-434855、AN-429777、AN-429048、AN-428892、AN-428189、AN-425215
**组件**：
**连接**： AN-442824、AN-440937、AN-440092、AN-429781
**Content Analytics**：
**引导式分析**：
**导出**：
**数据视图**： AN-442809、AN-434824、AN-434210、AN-424000
**实施**：
**Report Builder**： AN-441136、AN-438147、AN-425150
**报告**： AN-443900、AN-441811、AN-441506、AN-440919、AN-440545、AN-440505、AN-440300
**分段**：
**计划报告**：
**共享的量度和维度**：
**Other**： AN-423359、AN-406242、AN-397985

## 相关资产

* [之前的 2025 Customer Journey Analytics 发行说明](/help/release-notes/2025.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hans)
* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
