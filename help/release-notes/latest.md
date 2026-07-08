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
source-git-commit: 4dd845eaf5f101e21a8e754ac588cb837398b975
workflow-type: tm+mt
source-wordcount: 666
ht-degree: 41%

---

# 当前Customer Journey Analytics发行说明（2026年7月）

**上次更新日期**：2026年7月8日

这些发行说明涵盖2026年7月发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。 因此，这些发行说明每月更新几次。 请定期检查。

## 新增功能或更新后的功能

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| -----------|-----------|-----------|
| **子事件分析** <br/>子事件分析允许您在比事件级别更精细的级别上分析数据。 您可以对事件中的单个容器进行分段，而不是筛选整个事件。 <p>例如，您可以按特定产品类别进行分段，而不包括同一订单中购买的所有其他产品。 您还可以将属于事件数据的对象或数组定义为数据视图中的单独容器。</p><p>（文档链接见下文。）</p> | 2026年7月15日 | 2026年7月底 |
| **B2B edition：在Customer Journey Analytics B2B edition中，基于帐户的连接现在也支持临时和关系数据集** <br/>临时和关系数据集。<p>（文档链接见下文。）</p> | | 2026年7月20日 |
| **Content Analytics：付费媒体数据** <br/>付费媒体现已作为Content Analytics的第三个渠道提供。<p>（文档链接见下文。）</p> | | 2026年7月31日 |
| **连接使用情况界面更新** <br/>在管理连接时，您现在可以在“使用情况”界面中查看每个模块的使用详细信息，例如Customer Journey Analytics或Customer Journey Analytics B2B edition。 <p>此外，您现在可以按月划分每个模块的使用情况报表。</p><p>（文档链接见下文。）</p> | | 2026年7月31日 |
| **CX Enterprise Co-worker：从Adobe Analytics迁移到Customer Journey Analytics时验证您的数据** <br/>CX Enterprise Co-worker的一项新技能允许您根据现有Adobe Analytics实施的数据验证Customer Journey Analytics实施中的数据。 <p>这项技能可根据需要自动分别比较每个维度、量度和趋势。 它还可以将所有Adobe Analytics报表包与所有Customer Journey Analytics数据视图进行比较。 然后，该技能可生成由AI驱动的见解和推荐，您可实施这些见解和推荐，以方便您迁移到Customer Journey Analytics。</p><p>（文档链接见下文。）</p> | | 2026年7月底 |

### Customer Journey Analytics 中的修复

**Analysis Workspace**： AN-457527、AN-451161、AN-459034、AN-458071、AN-458398
**组件**：
**连接**： AN-457065
**Content Analytics**：
**引导式分析**：
**导出**：
**数据视图**： AN-453201
**数据摄取**：
**实施**：
**Report Builder**： AN-457533， AN-453683
**报告**： AN-457607、AN-447692、AN-451259、AN-455713
**分段**：
**计划报告**： AN-450715
**共享的量度和维度**：
**受众分析**：
**其他**： AN-457063

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

