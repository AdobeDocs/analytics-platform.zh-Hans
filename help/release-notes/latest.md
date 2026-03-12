---
title: 当前 Customer Journey Analytics 发行说明
description: 查看最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 1cfb49bd02da6f35d124cdec8f2df71f451d0fe7
workflow-type: tm+mt
source-wordcount: '1616'
ht-degree: 23%

---

# 当前Customer Journey Analytics发行说明（2026年3月）

**上次更新时间**：2026年3月11日

这些发行说明涵盖2026年3月发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| -----------|-----------|-----------|
| **标头覆盖** <br/>您可以在Content Analytics中指定标头名称和密码标头值。 此[标头覆盖配置](/help/content-analytics/config/guided.md#header-overrides)确保Content Analytics发送自定义HTTP标头以绕过任何已实施的机器人检测或关机流量技术。 |  | 2026年2月2 |
| **合并来自多个IMS组织的报表包**<br/>&#x200B;您可以使用Analytics Source Connector合并来自多个IMS组织的报表包。 此[跨IMS数据映射](/help/getting-started/aa-vs-cja/mapping-data-ims-orgs.md)功能允许组织拥有其客户数据的组合视图，即使该客户数据分布在多个IMS组织中也是如此。 <p>**注意：**&#x200B;此配置仅在向 Adobe 客户关怀团队提交请求后才可用。</p> |  | 2026年2月12日 |
| **在自由格式表中包含多个维度列**<br/>&#x200B;现在，您最多可以在自由格式表中包含5个维度列，从而允许您并排查看多个维度项目。 每一行的维度项将作为一个拼接后的单一维度项进行处理。<p>您可以对包含多个维度列的自由格式表应用筛选、排序、细分等操作，以实现更深入、更定制化的分析。</p><p>此前，自由格式表中只能包含 1 个维度列。</p><p>有关详细信息，请参阅[在自由格式表中包含多个维度列](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md)。</p> | 2026 年 1 月 28 日 | 2026年3月4日 <p>（原计划于2026年2月18日）</p> |
| **按多列对表进行排序**<br/>&#x200B;您现在可以在Analysis Workspace中按多列对自由格式表的数据进行排序，无论它们是维度还是指标。<p>当按多个列进行排序时，数据将根据您为每个列指定的优先级进行排序。优先级编号会显示在排序图标旁。</p><p>有关详细信息，请参阅[筛选和排序自由格式表](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。</p> | 2026 年 1 月 28 日 | 2026年3月4日 <p>（原计划于2026年2月18日）</p> |
| **Content Analytics：散点可视化图表缩略图和预览** <br/>[缩略图和预览](/help/content-analytics/report/report.md)可用于Content Analytics散点可视化图表中的资源和体验。 | 2026年2月17日 | 2026年3月2日 |
| **Content Analytics：条形可视化缩略图和预览** <br/>[缩略图和预览](/help/content-analytics/report/report.md)可用于Content Analytics的条形图（栈叠）和水平条形图（栈叠）可视化中的资源和体验。 | 2026年2月23日 | 2026年3月9日 |
| **数据集在连接中预览重新设计**<br/>&#x200B;当在基于人员的连接中[添加](/help/connections/create-connection.md#add-datasets)或[编辑](/help/connections/create-connection.md#edit-a-dataset)数据集时，预览数据的体验会得到改进。 对于拼接启用的数据集，有其他[拼接量度](/help/stitching/use-stitching-ui.md#stitching-metrics)和[有关错误ID](/help/stitching/use-stitching-ui.md#bad-ids)的信息可用。 | 2026年3月6日 | 待定 |
| **Report Builder：管理员可看到所有计划工作簿**<br/> Report Builder Excel加载项包含一个新的筛选器选项，该选项允许管理员查看给定组织的所有计划工作簿，而不管这些工作簿是谁计划的。 此过滤器选项仅适用于Analytics管理员。 在查看计划工作簿时，它在“工作簿”选项卡和“旧版”选项卡上均可用。<p>查看所有计划工作簿的功能在跨分布式团队迁移工作簿时特别有用，因为它允许管理员在迁移工作簿之前轻松找到所有旧工作簿。</p><p>以前，管理员只能查看他们计划的工作簿，而不能查看其他用户计划的工作簿。</br>有关详细信息，请参阅[管理计划的工作簿](/help/report-builder/manage-schedules-reportbuilder.md)。</p> | | 2026年3月10日 |
| **更新到Approximate Count Distinct函数**<br/>&#x200B;将很快更新Approximate Count Distinct函数中使用的HLL概率算法。 使用此函数得出的数字输出可能与历史数字略有不同，如下所示：<ul><li>当计算非常少量的唯一值时，将改进结果以使用精确计数，而不是使用估计值。</li><li>在计数任何更大的数字时，计数估计将保持本次更新之前的准确性（估计准确性在准确数字的5%之内，即时间的95%）。</li></ul><p>有关Approximate Count Distinct函数的更多信息，请参阅[高级函数](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct)中的[Approximate Count Distinct](/help/components/calc-metrics/cm-adv-functions.md)</p> | | 2026年3月10日 |
| **完整的表导出改进**<br/>&#x200B;完整的表导出包括以下增强功能：<p>导出创建和配置增强功能</p><ul><li>从“导出”页面创建导出。 以前，您只能通过右键单击表格来创建从Analysis Workspace的导出。</li><li>创建导出时添加新帐户或位置。</li><li>自动创建文件名并放置导出文件的文件夹。 这允许文件名是可预测的并以逻辑方式组织到文件夹中。 以前，文件名不可预测，并且被分组到单个文件夹中。</li><li>支持将数据导出为Parquet文件，以提高数据仓库兼容性。 以前，仅支持CSV和JSON。</li></ul><p>导出管理增强功能</p><ul><li>从“导出”页面续订或取消一个或多个导出。</li><li>从“日志”页面重新发送一个或多个导出。</li><li>在导出失败或即将过期时向单个用户或组发送电子邮件。</li><li>导出失败更精确的错误消息。</li></ul><p>计算指标、区段和维度增强功能</p><ul><li>支持更多计算量度函数。 以前，仅支持简单的数学函数。</li><li>创建导出时应用区段。</li><li>支持双数据类型维度以提高精度。</li></ul><p>管理增强功能</p><ul><li>管理员现在可以查看所有导出和日志，无论导出和日志是由谁创建的。</li></ul><p>有关更多信息，请参阅以下资源：<ul><li>[将全表导出到云](/help/analysis-workspace/export/export-cloud.md)</li><li>[配置云导出帐户](/help/components/exports/cloud-export-accounts.md)</li><li>[配置云导出位置](/help/components/exports/cloud-export-locations.md)</li><li>[管理导出](/help/components/exports/manage-exports.md)</li><li>[管理云导出位置和帐户](/help/components/exports/manage-export-locations.md)</li><li>[管理导出日志](/help/components/exports/manage-export-logs.md)</li></ul></p> | 2026年2月25日 | 2026年3月11日<p>（原计划于2026年3月4日）</p> |
| **Analysis Workspace实践教程**<br/>&#x200B;现在提供了新的实践教程，可指导新用户了解在Analysis Workspace中使用面板、可视化图表和组件的基础知识。 <p>（文档链接见下文。）<!--For more information, see "Learning paths" in "Customer Journey Analytics landing page".--></p> | | 2026年3月18日 |
| **支持数据镜像**<br/>&#x200B;通过为Experience Platform中的特定源连接器支持基于模型的架构和更改数据捕获(CDC)功能，Customer Journey Analytics将能够支持[、](/help/data-mirror/data-mirror.md)和[!DNL Snowflake]等数据仓库解决方案的[!DNL Azure Databricks]数据镜像[!DNL Google BigQuery]功能。<p>要访问 Beta 版本，请联系您的 Adobe 帐户团队。</p> | Beta 版：2025 年 9 月 24 日 | 2026年3月25日 |
| **Data Insights Agent与Copilot的集成** <br/> Data Insights Agent现在与Microsoft Copilot集成，允许您直接在Microsoft工具（包括Teams、Powerpoint等）中使用自然语言提示与Customer Journey Analytics数据交互。<p>（文档链接见下文。）</p> | | 2026 年 3 月 26 日 |
| **Adobe工程代理中的数据验证** <br/>Data Engineering Agent中提供了新的数据验证技能。 在Customer Journey Analytics中分析数据之前，这些技能可帮助团队直接在Adobe Experience Platform中快速评估数据质量。 <p>数据验证技能支持按需验证、字段级验证和数据集级验证，从而将统计摘要与对无效或异常值的智能检测结合起来。 </p><p>使用数据验证技能可减少手动QA工作量，并加快跨数据工程工作流的受信任数据载入和转换。</p><p>（文档链接见下文。）<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 2026年3月31日 |
| **将划分应用于面板**<br/>&#x200B;您现在可以将划分应用于面板。 在面板级别应用划分时，划分将应用于面板中所有自由格式表的所有列。 | 2026 年 3 月 | 2026 年 5 月 |
| **流媒体服务：支持计划数据** <br/>您现在可以上传过去直播流媒体内容的计划数据，以便更轻松、更准确地跟踪收视率。<p>以下是支持计划数据上传的直播内容示例：</p><ul><li>FAST（免费广告支持电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>如需了解更多信息，请参阅[上传计划数据以跟踪实时内容](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 2025 年 10 月 29 日 | 2026 年上半年<p>（原计划于 2025 年 10 月 29 日发布）</p> |
| **意大利语支持**<br/> Customer Journey Analytics中的Analysis Workspace现在支持意大利语区域设置(it-IT)。 <p>Customer Journey Analytics支持Experience Platform UI中支持的所有语言，如Experience Platform UI的[浏览器和语言支持](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-ui/browser-language-support#language-support)中所述。</p><p>您可以在Experience Platform中[更改默认语言](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language)。</p> | | 2026年4月8日 |

## Customer Journey Analytics 中的修复

**Analysis Workspace**： AN-440336、AN-440216、AN-438445、AN-438216、AN-437856、AN-437776、AN-437765、AN-437365、AN-432793、AN-432094、AN-431557、AN-431200、AN-429621、AN-429424、AN-427973、AN-426089、AN-425883、AN-424359
**组件**：
**Content Analytics**：
**引导式分析**：
**导出**： AN-432030
**数据视图**： AN-440004、AN-437154、AN-431165
**实现**：
**Report Builder**： AN-437895、AN-437083、AN-434288、AN-434209、AN-433224、AN-430622
**报告**： AN-439482、AN-439545、AN-438708、AN-431206、AN-430079、AN-428302、AN-428257、AN-425779、AN-423330
**分段**：
**计划报告**：
**共享的量度和维度**：
**Other**： AN-439795、AN-434783、AN-434233、AN-434005、AN-433368、AN-431322、AN-431165、AN-431012、AN-429983、AN-429067、AN-423285


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
