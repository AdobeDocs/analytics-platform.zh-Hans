---
title: 当前的Customer Journey Analytics发行说明
description: 查看最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad333ea6-e90d-4c8f-8d61-9f8690784d6fid: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: d3c978ee-1ff0-4475-968a-721e2dd99ef1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 07846fea9f2d7fd966bcd924025aeae0c157cf9e
workflow-type: tm+mt
source-wordcount: 910
ht-degree: 30%

---

# 当前Customer Journey Analytics发行说明（2026年8月）

**上次更新日期**：2026年8月5日

这些发行说明涵盖2026年8月发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。 因此，这些发行说明每月更新几次。 请定期检查。

## 新增功能或更新后的功能

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| -----------|-----------|-----------|
| **历程画布增强功能**<br>&#x200B;现已提供以下历程画布增强功能：<ul><li>将历程与先前的时间范围进行比较。 将当前历程与4周前、2个季度前、1年前或自定义日期范围前的历程进行比较。</li><li>对于所选节点，显示历程中任意时间点上所选节点之后排名最前的维度项目。 当所选节点是分析中的关键事件，并且您想要查看用户随后在任何时候执行的操作时，可使用此选项。<p>以前，只有顶级的直接节点才能显示在选定节点之前或之后。 </p></li><li>更改节点之间箭头的形状和样式。 在节点之间拖动箭头可更改箭头的形状（曲率），右键单击箭头可将其样式更改为下列任一类型：实线、虚线、点线、虚线点或动画。</li></ul><p></p>有关详细信息，请参阅[配置历程画布可视化图表](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。 |  | 2026年8月18日 |
| **支持其他数据使用标签**<br> Customer Journey Analytics现在支持数据集内元素的以下其他数据使用标签：<ul><li>C2 — 限制第三方数据导出（现在可用）</li><li>C3 — 限制可直接识别的数据组合（现在可用）</li><li>C9 — 限制数据科学（计划于8月或9月发布）</li></ul><p>有关详细信息，请参阅[标签、策略和营销操作](/help/data-views/data-governance.md)。</p> | | 2026年8月或9月 |
| **同意策略筛选和报告**<br>&#x200B;您现在可以报告哪些访客与您的Adobe Experience Platform同意策略匹配。 （同意策略维度和量度会添加到连接中的数据视图。）<p>此外，您可以先排除非同意访客，然后再将其数据摄取到Customer Journey Analytics。</p><p>有关更多信息，请参阅同意报表和筛选概述。</p> | | 2026年8月 |
| **Content Analytics：付费媒体数据** <br/>付费媒体现已作为Content Analytics的第三个渠道提供。<p>（文档链接见下文。）</p> | | 2026年8月31日 |
| **B2B：人员到帐户拼接**<br> B2B帐户拼接使用帐户信息丰富了您的事件数据集，并支持在Customer Journey Analytics中跨整个客户历程进行完整分析。 <p>当事件缺少帐户ID（Customer Journey Analytics B2B edition摄取时需要帐户ID）时，帐户拼接将使用您提供的人员到帐户映射数据集自动派生和添加该信息。</p><p>（文档链接见下文。）</p> | | 2026年8月底或9月底 |
| **CJA报表API首次调用指南**<br> Adobe Customer Journey Analytics API首次调用指南提供了配置基本报表请求的说明和示例。 | | 2026年8月10日 |
| **CJA报表API日期趋势指南**<br> Adobe Customer Journey Analytics API日期趋势指南提供了配置基本报表请求的说明和示例。 | | 2026年8月17日 |

### Customer Journey Analytics 中的修复

**Analysis Workspace**： AN-466867、AN-465995、AN-465315、AN-465313、AN-464375、AN-463634、AN-463248、AN-463175、AN-463049、AN-462347、AN-462124、AN-461922、AN-458398、AN-457849、AN-455002、AN-453357、AN-456863、AN-459816、AN-459034、AN-460774、AN-460671、AN-457760、AN-443594
**组件**：
**连接**： AN-464934、AN-460768
**Content Analytics**：
**引导式分析**：
**导出**： AN-451819、AN-448419、AN-456001
**数据视图**： AN-453201、AN-441965、AN-460967
**数据摄取**： AN-462123、AN-451836、AN-453790、AN-459000、AN-456057、AN-461271、AN-459016、AN-460935
**实施**：
**Report Builder**： AN-465346、AN-464768、AN-464580、AN-464301、AN-463048、AN-462800、AN-457042、AN-461033、AN-459042、AN-454250、AN-451735、AN-450776、AN-450200、AN-451665
**报告**： AN-463576、AN-462400、AN-456394、AN-455619、AN-459530、AN-454103、AN-452866、AN-461181
**分段**： AN-459002、AN-457730、AN-457146
**计划报告**： AN-455009、AN-460037、AN-462093
**共享的量度和维度**：
**受众分析**： AN-458292
**Other**： AN-466935、AN-462116、AN-454493、AN-457666、AN-457557、AN-456742、AN-437975、AN-460959

## 延迟的功能

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| -----------|-----------|-----------|
| **流媒体服务：支持计划数据** <br/>您现在可以上传过去直播流媒体服务内容的计划数据，以便更轻松、更准确地跟踪观看人数。<p>以下是支持计划数据上传的直播内容示例：</p><ul><li>FAST（免费广告支持电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。 您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>有关详细信息，请参阅[上传计划数据以跟踪实时内容](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/track-schedule-data)。 | 2025 年 10 月 29 日 | 待定<p>（原计划于2025年10月29日）</p> |

>[!MORELIKETHIS]
>
>* [以前的2026年Customer Journey Analytics发行说明](/help/release-notes/2026.md)
>* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hans)
>* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
>* [CX Enterprise发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hans)
>* [Customer Journey Analytics文档更新](/help/release-notes/doc-changes.md)

