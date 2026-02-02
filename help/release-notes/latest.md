---
title: 当前 Customer Journey Analytics 发行说明
description: 查看最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 0eb56aa15104cec3dd08aa28bcfff6dd8966f14a
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 97%

---

# 当前 Customer Journey Analytics 发行说明（2026 年 1 月）

**上次更新日期**：2026 年 1 月 14 日

本发行说明涵盖 2026 年 1 月的发布周期。Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **在 Customer Journey Analytics 中分析来自 Experience Platform 轮廓数据集的受众** | 现在，您可以将来自 Experience Platform 轮廓数据集的受众成员关系数据摄取到 Customer Journey Analytics 连接中。受众将作为新的维度在 Analysis Workspace 中可用。<p>这一功能得益于 Customer Journey Analytics 新增的 XDM 对象映射摄取能力，从而可以摄取轮廓受众 ID。</p><p>此前，Customer Journey Analytics 仅支持摄取简单的 XDM 映射。</p><p>除了可以将受众数据作为维度添加到 Analysis Workspace 中的任何项目外，还新增了以下 Workspace 模板：</p><ul><li>Audience Analytics 概述</li><li>同意策略概述</li></ul><p>有关详细信息，请参阅[受众分析概述](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/audience-analysis/audience-analysis-overview.html?lang=zh-Hans)。</p> | 2025 年 10 月 22 日 | 2026 年 1 月 27 日 <p> （原计划于 2026 年 1 月 22 日发布）</p> |
| **数据故事讲述：从 Workspace 报告生成幻灯片演示文稿** | 您现在可以基于 Analysis Workspace 报告自动生成幻灯片演示文稿（采用 .pptx 格式）。Workspace 会检测报告中的关键洞察，并将其转化为适用于利益相关者的幻灯片。<p>该功能可减少呈现发现结果、构建管理层叙述以及传达业务影响所需的时间和精力。</p><p>有关更多信息，请参阅[数据故事讲述：从 Workspace 报告生成幻灯片演示文稿](/help/analysis-workspace/curate-share/generate-slides.md)。</p> | 2025 年 10 月 22 日 | 2026 年 1 月 28 日 |
| **在自由格式表中包含多个维度列** | 现在，您可以在自由格式表中最多包含 5 个维度列，从而并排查看多个维度项。每一行的维度项将作为一个拼接后的单一维度项进行处理。<p>您可以对包含多个维度列的自由格式表应用筛选、排序、细分等操作，以实现更深入、更定制化的分析。</p><p>此前，自由格式表中只能包含 1 个维度列。</p><p>有关详细信息，请参阅[在自由格式表中包含多个维度列](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md)。</p> | 2026 年 1 月 28 日 | 2026 年 2 月 18 日 |
| **按多个列对表格进行排序** | 现在，您可以在 Analysis Workspace 中按多个列（无论是维度还是量度）对自由格式表的数据进行排序。<p>当按多个列进行排序时，数据将根据您为每个列指定的优先级进行排序。优先级编号会显示在排序图标旁。</p><p>有关详细信息，请参阅[筛选和排序自由格式表](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)中的[按多个列对表格进行排序](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#sort-tables-by-multiple-columns-advanced-sorting)。</p> | 2026 年 1 月 28 日 | 2026 年 2 月 18 日 |
| **合并来自多个 IMS 组织的数据源** | 现在，您可以使用 Analytics Source Connector 合并来自多个 IMS 组织的多个数据源。这使组织即使在客户数据分布于多个 IMS 组织的情况下，也能够获得统一的客户数据视图。 <p>**注意：**&#x200B;此配置仅在向 Adobe 客户关怀团队提交请求后才可用。</p>  <p>（文档链接见下文。）</p> |  | 2026 年 1 月 30 日 |
| **连接中的拼接** | Customer Journey Analytics 中的拼接流程现已更加简化。现在不再需要复制数据集后对复制的数据集进行拼接，而是在将数据摄取到 Customer Journey Analytics 中时进行拼接，这样就无需再复制数据集和架构。 <p>此外，您还[通过更新的连接接口](/help/stitching/use-stitching-ui.md)开始拼合自己，而不必通过Adobe客户关怀部门请求拼合。 | 2025 年 10 月 28 日 | 2026 年 1 月 30 日 |
| **支持 Data Mirror** | 通过对 Experience Platform 中的特定源连接器提供基于模型的架构以及变更数据捕获（CDC）功能的支持，Customer Journey Analytics 将能够支持 [!DNL Snowflake]、[!DNL Azure Databricks] 和 [!DNL Google BigQuery] 等数据仓库解决方案的 [Data Mirror](/help/data-mirror/data-mirror.md) 功能。<p>要访问 Beta 版本，请联系您的 Adobe 帐户团队。</p> | Beta 版：2025 年 9 月 24 日 | 待定 |
| **流媒体服务：支持计划数据** | 您现在可以上传过去直播流媒体内容的计划数据，以便更轻松、更准确地跟踪观看人数。<p>以下是支持计划数据上传的直播内容示例：</p><ul><li>FAST（免费广告支持电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>如需了解更多信息，请参阅[上传计划数据以跟踪实时内容](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>（原计划于 2025 年 10 月 29 日发布）</p> |

## Customer Journey Analytics 中的修复

**Analysis Workspace**：AN-423389、AN-423316、AN-422636、AN-422482、AN-422121、AN-422116、AN-422027、AN-421134、AN-420187、AN-406271、AN-406188、AN-405997、AN-405983、AN-405796、AN-405033、AN-404893、AN-404871、AN-404842、AN-404713、AN-404502、AN-404353、AN-404352、AN-404048 an-403241、AN-402523、AN-400795、AN-396149、AN-390990、AN-390646、AN-383484、AN-376980 371729 347570 404835
**组件**：
**Content Analytics**：
**引导式分析**：AN-421274
**导出**：
**数据视图**：AN-421891、AN-404627
**实施**：
**Report Builder**：AN-422120、AN-421937、AN-406296、AN-402951、AN-399748
**报表**：
**分段**：
**计划报表**：AN-423087、AN-422686
**共享量度和维度**：
**其他**：AN-422946、AN-422775、AN-422273、AN-422100、AN-420045、AN-404891、AN-390912


## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 |  |  |

## 相关资产

* [之前的 2025 Customer Journey Analytics 发行说明](/help/release-notes/2025.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hans)
* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
