---
title: 当前 Customer Journey Analytics 发行说明
description: 查看最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a16043f1bb15deba1332ed39438214597647b9b4
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 67%

---

# 当前Customer Journey Analytics发行说明（2025年10月）

**上次更新时间**：2025年10月14日

这些发行说明涵盖2025年10月至11月初的发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **包含在折线图可视化图表和迷你图中的筛选条件** | 现在，应用于自由格式表过滤器的任何搜索过滤器条件始终包含在迷你图中。 此外，您还可以在任何连接的折线图可视化图表中包含搜索筛选条件。<p>您可以通过选择所连接表的指标列标题中的迷你图，将折线图可视化配置为包含搜索筛选条件。</p><p>以前，搜索筛选条件未包含在迷你图或连接的线可视化图表中。</p><p>有关详细信息，请参阅[查看自由格式表的趋势数据](/help/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md)。</p> | | 2025 年 10 月 15 日 |
| **数据storytelling：从Workspace报表生成幻灯片演示文稿** | 您现在可以基于Analysis Workspace报告自动生成幻灯片演示文稿（采用.pptx格式）。 Workspace会检测报表中的关键见解，并将其转换为适用于利益相关者的幻灯片。<p>此功能可减少展示发现、构建管理层叙述和传达业务影响所需的时间和精力。</p><p>（文档链接见下文。）</p> | 2025年10月22日 | 2026 年 1 月  |
| **实时报告** | Customer Journey Analytics 中的实时报告功能可以实时显示并更新 Analysis Workspace 的一个或多个面板中的数据和可视化图表。<br/><br/>（文档链接见下文。） | 2025 年 9 月 18 日（原计划于 2025 年 8 月 15 日发布） | 2025年10月27日 |
| **支持 Data Mirror** | 通过为Experience Platform中的特定源连接器支持基于模型的架构和更改数据捕获(CDC)功能，Customer Journey Analytics将能够支持Data Warehouse解决方案（如[!DNL Snowflake]、[!DNL Azure Databricks]和[!DNL Google BigQuery]）的数据镜像功能。<p>要访问 Beta 版本，请联系您的 Adobe 帐户团队。</p><p>（文档链接见下文。）</p> | Beta版本： 2025年9月24日 | 待定 |
| **连接中的拼接** | 简化 Customer Journey Analytics 拼接。现在不再需要复制数据集后对复制的数据集进行拼接，而是在将数据摄取到 Customer Journey Analytics 中时进行拼接，这样就无需再复制数据集和架构。 <p>此外，您现在无需再通过客户支持部门请求拼接，而是可以从更新后的 Connections UI 自行启动拼接功能。</p><p> *由于需要更多工作，之前公布的发布日期被推迟。新的发布日期与假期重叠，因此额外限制了发布。目前正计划分阶段推出，以确保稳定性，并尽量减少假期的干扰。*</p> <p>（文档链接见下文。）</p> | 2025年10月28日 | 2026年4月30日 |
| **流媒体服务：支持计划数据** | 您现在可以上传过去直播流媒体内容的计划数据，以便更轻松、更准确地跟踪观看人数。<p>以下是支持计划数据上传的直播内容示例：</p><ul><li>FAST（免费广告支持电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>（文档链接见下文。）<!--For more information, see [Upload schedule data to track live content](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/track-schedule-data)--></p> |  | 2025 年 10 月 29 日 |
| **Analytics源连接器： Experience Platform中的搜索报告包** | 现在，具有大量报表包的客户可以在Analytics Source Connector数据流工作流中搜索他们想要连接的报表包。 <p>以前，客户必须在可能很长的报表包列表中进行分页。</p><p>（文档链接见下文。） | | 2025年10月30日 |
| **流媒体：更新了用于将流媒体数据收集到 Adobe Experience Platform 的 XDM 字段** | 将流媒体数据收集到 Adobe Experience Platform 时，不再使用流媒体参数文档中“XDM 字段路径”标题下显示的 XDM 字段路径。在 2025 年 5 月 9 日之前实施了 Analytics 源连接器以将流媒体数据收集到平台的客户，必须将其现有配置迁移到 mediaReporting 字段路径，参见流媒体参数文档中“报告 XDM 字段路径”标题下的段落。<p> 这些字段路径位于以下页面并标记为“已弃用”：[音频和视频参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[广告参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/ad-parameters)、[章节参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/chapter-parameters)、[播放器状态参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/player-state-parameters)和[质量参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/quality-parameters)。（2025 年 5 月 9 日之后实施 Analytics 源连接器，并且只使用 mediaReporting XDM 路径的客户无需采取任何行动。）</p><p>在已弃用的 XDM 字段路径上的数据摄取将继续进行，直到 2025 年 10 月底。之后，已弃用的字段路径将被完全移除，并且不再显示在 Adobe Experience Platform Schema UI 中，届时起将只使用 mediaReporting 字段路径发送数据。</p><p>有关详细信息请参阅[将 Analytics 源连接器实施迁移到更新后的 XDM 流媒体字段](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)。</p><p>请联系您的 Adobe Consulting 服务或帐户团队以获取迁移支持。 </p> |  | 2025 年 10 月 |

## Customer Journey Analytics 中的修复

**Analysis Workspace**： AN-400507、AN-400265、AN-399209、AN-397146、AN-394992、AN-390795
**组件**：
**Content Analytics**：
**导出**： AN-399012、AN-388578
**引导式分析**：
**实现**： AN-397551、AN-397550、AN-397190、AN-396127
**Report Builder**： AN-401127、AN-400618、AN-392971、AN-391692
**报告**：
**分段**：
**计划报告**：
**共享的量度和维度**：
**其他**：


## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 | | |

## 相关资产

* [之前的 2025 Customer Journey Analytics 发行说明](/help/release-notes/2025.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hans)
* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
