---
title: 当前 Customer Journey Analytics 发行说明
description: 查看最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 94dffc915f624309bca4709ba9140b64b3e3aa41
workflow-type: tm+mt
source-wordcount: '986'
ht-degree: 45%

---

# 当前Customer Journey Analytics发行说明（2026年1月）

**上次更新时间**：2026年1月14日

这些发行说明涵盖2026年1月发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **在Customer Journey Analytics中分析Experience Platform配置文件数据集中的受众** | 您现在可以将Experience Platform配置文件数据集中的受众成员资格数据摄取到Customer Journey Analytics连接。 受众将可用作新维度，以便在Analysis Workspace中使用。<p>这可以通过Customer Journey Analytics中的新功能来摄取XDM对象映射，进而能够摄取用户档案AudienceID。</p><p>以前，只能将简单的XDM映射引入Customer Journey Analytics。</p><p>除了能够向Analysis Workspace中的任何项目添加受众数据作为维度外，还提供以下新的Workspace模板：</p><ul><li>Audience Analytics概述</li><li>同意策略概述</li></ul><p>有关详细信息，请参阅[受众分析概述](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/audience-analysis/audience-analysis-overview.html?lang=zh-Hans)。</p> | 2025 年 10 月 22 日 | 2026年1月27日 <p> （原计划于2026年1月22日）</p> |
| **数据故事讲述：从 Workspace 报告生成幻灯片演示文稿** | 您现在可以基于 Analysis Workspace 报告自动生成幻灯片演示文稿（采用 .pptx 格式）。Workspace 会检测报告中的关键洞察，并将其转化为适用于利益相关者的幻灯片。<p>该功能可减少呈现发现结果、构建管理层叙述以及传达业务影响所需的时间和精力。</p><p>有关更多信息，请参阅[数据故事讲述：从 Workspace 报告生成幻灯片演示文稿](/help/analysis-workspace/curate-share/generate-slides.md)。</p> | 2025 年 10 月 22 日 | 2026年1月28日 |
| **在自由格式表中包含多个维度列** | 现在，您在自由格式表中最多可以包含5个维度列，从而允许您并排查看多个维度项目。 每一行维度项目的行为类似于单个连接的维度项目。<p>您可以将过滤器、排序、划分等应用于具有多个维度列的自由格式表，从而创建更深入、更自定义的分析。</p><p>以前，在自由格式表中只能包含1个维度列。</p><p>有关详细信息，请参阅[在自由格式表中包含多个维度列](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md)。</p> | 2026年1月28日 | 2026年2月18日 |
| **按多个列对表进行排序** | 您现在可以在Analysis Workspace中按多个列对自由格式表的数据进行排序，无论它们是维度还是量度。<p>当您为多个列排序数据时，将根据您分配给每个列的优先级对数据排序。 优先级编号显示在排序图标旁边。</p><p>有关详细信息，请参阅[筛选和排序自由格式表](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#sort-tables-by-multiple-columns-advanced-sorting)中的[按多个列对表进行排序](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。</p> | 2026年1月28日 | 2026年2月18日 |
| **合并来自多个IMS组织的数据源** | 您现在可以使用Analytics Source Connector合并来自多个IMS组织的多个数据源。 这允许组织拥有其客户数据的组合视图，即使该客户数据分布在多个IMS组织也是如此。 <p>**注意：**&#x200B;只有通过向Adobe客户关怀部门提交请求才能使用此配置。</p>  <p>（文档链接见下文。）</p> |  | 2026 年 1 月 30 日 |
| **连接中的拼接** | Customer Journey Analytics中的拼合过程现在变得更加简单。 现在不再需要复制数据集后对复制的数据集进行拼接，而是在将数据摄取到 Customer Journey Analytics 中时进行拼接，这样就无需再复制数据集和架构。 <p>此外，您现在可以[通过更新的连接接口](/help/stitching/use-stitching-ui.md)开始自行拼接，而不必通过Adobe客户关怀部门请求拼接。</p><p> *由于需要做额外的工作和假日季节的关系，先前通知的发行日期被推迟。 目前正计划分阶段推出，以确保稳定性，并尽量减少假期的干扰。*</p> | 2025 年 10 月 28 日 | 2026 年 1 月 30 日 |
| **支持 Data Mirror** | 通过对 Experience Platform 中的特定源连接器提供基于模型的架构以及变更数据捕获（CDC）功能的支持，Customer Journey Analytics 将能够支持 [!DNL Snowflake]、[!DNL Azure Databricks] 和 [!DNL Google BigQuery] 等数据仓库解决方案的 [Data Mirror](/help/data-mirror/data-mirror.md) 功能。<p>要访问 Beta 版本，请联系您的 Adobe 帐户团队。</p> | Beta 版：2025 年 9 月 24 日 | 待定 |
| **流媒体服务：支持计划数据** | 您现在可以上传过去直播流媒体内容的计划数据，以便更轻松、更准确地跟踪观看人数。<p>以下是支持计划数据上传的直播内容示例：</p><ul><li>FAST（免费广告支持电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>如需了解更多信息，请参阅[上传计划数据以跟踪实时内容](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>（原计划于 2025 年 10 月 29 日发布）</p> |

## Customer Journey Analytics 中的修复

**Analysis Workspace**： AN-423389、AN-423316、AN-422636、AN-422482、AN-422121、AN-422116、AN-422027、AN-421134、AN-420187、AN-406271、AN-406188、AN-405997、AN-405983、AN-405796、AN-405033、AN-404893、AN-404871、AN-404842、AN-404713、AN-404502、AN-404353、AN-404352、AN-404048 an-403241、AN-402523、AN-400795、AN-396149、AN-390990、AN-390646、AN-383484、AN-376980 371729 347570 404835
**组件**：
**Content Analytics**：
**引导式分析**： AN-421274
**导出**：
**数据视图**： AN-421891、AN-404627
**实现**：
**Report Builder**： AN-422120、AN-421937、AN-406296、AN-402951、AN-399748
**报告**：
**分段**：
**计划报告**： AN-423087、AN-422686
**共享的量度和维度**：
**Other**： AN-422946、AN-422775、AN-422273、AN-422100、AN-420045、AN-404891、AN-390912


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
