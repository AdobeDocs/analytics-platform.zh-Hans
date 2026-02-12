---
title: 当前 Customer Journey Analytics 发行说明
description: 查看最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 5107f1a3e602afbb1536e7832a060c70aa898966
workflow-type: tm+mt
source-wordcount: '1192'
ht-degree: 39%

---

# 当前Customer Journey Analytics发行说明（2026年2月）

**上次更新时间**：2026年2月12日

这些发行说明涵盖2026年2月发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ------- | ---- |
| **标题覆盖** <p>您可以在Content Analytics中指定标头名称和密码标头值。 此[标头覆盖配置](/help/content-analytics/config/guided.md#header-overrides)确保Content Analytics发送自定义HTTP标头以绕过任何已实施的机器人检测或关机流量技术。</p> |  | 2026年2月2 |
| **在自由格式表中包含多个维度列**<p>现在，您可以在自由格式表中最多包含 5 个维度列，从而并排查看多个维度项。每一行的维度项将作为一个拼接后的单一维度项进行处理。</p><p>您可以对包含多个维度列的自由格式表应用筛选、排序、细分等操作，以实现更深入、更定制化的分析。</p><p>此前，自由格式表中只能包含 1 个维度列。</p><p>有关详细信息，请参阅[在自由格式表中包含多个维度列](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md)。</p> | 2026 年 1 月 28 日 | 2026 年 2 月 18 日 |
| **按多个列对表格进行排序**<p>现在，您可以在 Analysis Workspace 中按多个列（无论是维度还是量度）对自由格式表的数据进行排序。</p><p>当按多个列进行排序时，数据将根据您为每个列指定的优先级进行排序。优先级编号会显示在排序图标旁。</p><p>有关详细信息，请参阅[筛选和排序自由格式表](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。</p> | 2026 年 1 月 28 日 | 2026 年 2 月 18 日 |
| **完整的表导出改进**<p>完整的表导出包括以下增强功能：</p><p>导出创建和配置增强功能</p><ul><li>从“导出”页面创建导出。 以前，您只能通过右键单击表格来创建从Analysis Workspace的导出。</li><li>创建导出时添加新帐户或位置。</li><li>自动创建文件名并放置导出文件的文件夹。 这允许文件名是可预测的并以逻辑方式组织到文件夹中。 以前，文件名不可预测，并且被分组到单个文件夹中。</li><li>支持将数据导出为Parquet文件，以提高数据仓库兼容性。 以前，仅支持CSV和JSON。</li></ul><p>导出管理增强功能</p><ul><li>从“导出”页面续订或取消一个或多个导出。</li><li>从“日志”页面重新发送一个或多个导出。</li><li>在导出失败或即将过期时向单个用户或组发送电子邮件。</li><li>导出失败更精确的错误消息。</li></ul><p>计算指标、区段和维度增强功能</p><ul><li>支持更多计算量度函数。 以前，仅支持简单的数学函数。</li><li>创建导出时应用区段。</li><li>支持双数据类型维度以提高精度。</li></ul><p>管理增强功能</p><ul><li>管理员现在可以查看所有导出和日志，无论导出和日志是由谁创建的。</li></ul><p>（文档链接见下文。）</p> | 2026年2月25日 | 2026年3月11日<p>（原计划于2026年3月4日）</p> |
| **Content Analytics：散点可视化图表缩略图和预览** <p>现在，在Content Analytics中查看散点图可视化图表时，将鼠标悬停在图表中的点上时，会显示资源的缩略图。 此缩略图允许您快速轻松地查看图表中表示的内容。</p><p>（文档链接见下文。）</p> | 2026年2月17日 | 2026年3月2日 |
| **Content Analytics：条形图可视化缩略图和预览** <p>现在，在Content Analytics中查看水平条形图可视化时，将鼠标悬停在图表中的条形图上时，会显示资源的缩略图。 此缩略图允许您快速轻松地查看图表中表示的内容。</p><p>（文档链接见下文。）</p> | 2026年2月23日 | 2026年3月9日 |
| **更新为近似非重复计数函数**<p>Approximate Count Distinct函数中使用的HLL概率算法将很快更新。 使用此函数得出的数字输出可能与历史数字略有不同，如下所示：<ul><li>当计算非常少量的唯一值时，将改进结果以使用精确计数，而不是使用估计值。</li><li>在计数任何更大的数字时，计数估计将保持本次更新之前的准确性（估计准确性在准确数字的5%之内，即时间的95%）。</li></ul><p>有关Approximate Count Distinct函数的更多信息，请参阅[高级函数](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct)中的[Approximate Count Distinct](/help/components/calc-metrics/cm-adv-functions.md)</p> |  | 2026 年 3 月 |
| **支持 Data Mirror**  <p>通过对 Experience Platform 中的特定源连接器提供基于模型的架构以及变更数据捕获（CDC）功能的支持，Customer Journey Analytics 将能够支持 [!DNL Snowflake]、[!DNL Azure Databricks] 和 [!DNL Google BigQuery] 等数据仓库解决方案的 [Data Mirror](/help/data-mirror/data-mirror.md) 功能。</p><p>要访问 Beta 版本，请联系您的 Adobe 帐户团队。</p> | Beta 版：2025 年 9 月 24 日 | 待定 |
| **流媒体服务：支持计划数据** <p>您现在可以更轻松、更准确地跟踪收视率，上传过去实时流媒体内容的计划数据。</p><p>以下是支持计划数据上传的直播内容示例：</p><ul><li>FAST（免费广告支持电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>如需了解更多信息，请参阅[上传计划数据以跟踪实时内容](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>（原计划于 2025 年 10 月 29 日发布）</p> |
| **合并来自多个IMS组织的报表包**<p>您可以使用Analytics Source Connector合并来自多个IMS组织的报告包。 此[跨IMS数据映射](/help/getting-started/aa-vs-cja/mapping-data-ims-orgs.md)功能允许组织拥有其客户数据的组合视图，即使该客户数据分布在多个IMS组织中也是如此。 <p>**注意：**&#x200B;此配置仅在向 Adobe 客户关怀团队提交请求后才可用。</p> |  | 2026年2月12日 |

## Customer Journey Analytics 中的修复

**Analysis Workspace**： AN-421930、AN-424997、AN-424194、AN-425515、AN-425254、AN-423174、AN-428834、AN-306540、AN-426014、AN-427801
**组件**：
**Content Analytics**：
**引导式分析**：
**导出**： AN-422041、AN-421599、AN-422112
**数据视图**：
**实现**：
**Report Builder**： AN-391415、AN-425125
**报告**： AN-425817、AN-424362、AN-425752、AN-425278、AN-422249、AN-403446、AN-424727、AN-426791、AN-427985
**分段**： AN-428905、AN-428232
**计划报告**： AN-425484、AN-425137
**共享的量度和维度**：
**Other**： AN-428833、AN-425074


## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| **TLS 1.2密码套件移除** | 2026年2月11日 | 管理员须知： Adobe计划于2026年5月27日从Adobe数据收集服务器中删除对以下TLS 1.2密码包的支持。<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>大多数实施不需要客户操作。 此更改主要影响从使用过时TLS库的旧版本机应用程序发送的Analytics数据，以及少量使用过时浏览器或操作系统的Web访客。 取消对这些密码包的支持可增强安全性，并使Adobe与现代加密标准保持一致。 目前，不到0.1%的数据收集流量依赖这些密码套件。</p> |

## 相关资产

* [之前的 2025 Customer Journey Analytics 发行说明](/help/release-notes/2025.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hans)
* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
