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
source-git-commit: 9c3546c33914feb7a00b5bb78a575dd511cabb5f
workflow-type: tm+mt
source-wordcount: 615
ht-degree: 44%

---

# 当前Customer Journey Analytics发行说明（2026年6月）

**上次更新时间**：2026年6月25日

这些发行说明涵盖2026年6月发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。 因此，这些发行说明每月更新几次。 请定期检查。

## 新增功能或更新后的功能

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| -----------|-----------|-----------|
| **Data Mirror** <br/>[Data Mirror](/help/data-mirror/data-mirror.md)是一种Experience Platform功能，它允许使用关系架构从外部数据仓库解决方案（[!DNL Snowflake]、[!DNL Azure Databricks]和[!DNL Google BigQuery]）将行级别的更改引入（更改数据捕获）到Customer Journey Analytics中。 它保留数据关系，强制唯一性，并支持版本控制，而无需上游提取、转换和加载(ETL)过程。 | 2026 年 3 月 25 日 | 2026年6月17日 |
| **在AI助手中验证您的数据** <br/>您可以使用AI助手来[验证Adobe Experience Platform数据集的数据质量](https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/data-validation)。 由Agent Orchestrator提供的数据验证功能可以对数据集执行统计和语义验证，分析数据集字段，识别数据质量问题，并返回具有可操作洞察信息的自然语言摘要。 | | 2026年6月22日 |

### Customer Journey Analytics 中的修复

**Analysis Workspace**： AN-456858、AN-455865、AN-455706、AN-455592、AN-455484、AN-455180、AN-454999、AN-454170、AN-454145、AN-453793、AN-452921、AN-452009、AN-451958、AN-451643、AN-451600、AN-451525、AN-451477、AN-451262、AN-451161、AN-450772、AN-443594、AN-434416
**组件**：
**连接**： AN-457065、AN-453705
**Content Analytics**： AN-451203， AN-447596
**引导式分析**：
**导出**： AN-452006、AN-451989、AN-440567
**数据视图**： AN-451198
**实施**：
**Report Builder**： AN-440912、AN-457586、AN-457533、AN-455713、AN-455623、AN-455063、AN-454512、AN-454053、AN-453977、AN-453781、AN-453683、AN-451974、AN-451735、AN-451731、AN-451190、AN-449813、AN-447173、AN-447139、AN-446184、AN-445794、AN-445354、AN-442819
**报告**： AN-454589、AN-454517、AN-453982、AN-451822、AN-451497、AN-451463、AN-451259、AN-451215、AN-450661、AN-447699、AN-448375、AN-447692
**分段**：
**计划报告**： AN-451980、AN-451882、AN-450715
**共享的量度和维度**：
**受众分析**： AN-449656、AN-450400
**Other**： AN-457063、AN-454140、AN-453937、AN-453825、AN-452959、AN-452934、AN-452296、AN-451781、AN-450974

## 延迟的功能

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| -----------|-----------|-----------|
| **流媒体服务：支持计划数据** <br/>您现在可以上传过去直播流媒体服务内容的计划数据，以便更轻松、更准确地跟踪观看人数。<p>以下是支持计划数据上传的直播内容示例：</p><ul><li>FAST（免费广告支持电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。 您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>如需了解更多信息，请参阅[上传计划数据以跟踪实时内容](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/track-schedule-data) | 2025 年 10 月 29 日 | 待定<p>（原计划于2025年10月29日）</p> |

>[!MORELIKETHIS]
>
>* [以前的2026年Customer Journey Analytics发行说明](/help/release-notes/2026.md)
>* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hans)
>* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
>* [CX Enterprise发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hans)
>* [Customer Journey Analytics文档更新](/help/release-notes/doc-changes.md)

