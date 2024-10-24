---
title: Customer Journey Analytics 文档更新
description: 列出 Customer Journey Analytics 文档集自 2019 年 12 月以来的内容更新。
exl-id: 1cfb9810-e083-4a68-9c58-295e674da8d7
solution: Customer Journey Analytics
feature: Release Notes
source-git-commit: fc3aee031808d7a6c12ed2a2cbcad8f7ae6caa82
workflow-type: tm+mt
source-wordcount: '4138'
ht-degree: 69%

---

# Customer Journey Analytics - 文档更新

Customer Journey Analytics 文档自创建以来进行了以下更新。

## 2024

| 功能 | 描述 |
| --- | --- |
| **2024 年 10 月** | |
| 有关Analysis Workspace性能中的请求因素的新信息 | [优化Analysis Workspace性能](/help/technotes/optimizing-performance.md)文章中新增的[请求因子](/help/technotes/optimizing-performance.md#request-factors)部分介绍了如何处理请求以及影响处理时间的各种因素。 |
| Workspace和组件 | 刷新了有关Analysis Workspace项目（项目、可视化和面板）和组件(注释、维度、（计算）量度、过滤器、日期范围、警报、计划项目和受众)的文档。 |
| 引导式分析 | 更新了相关文档，以提供Analysis Workspace中的[引导式分析](/help/guided-analysis/overview.md)。 |
| **2024 年 9 月** | |
| 摘要数据更新 | 更新了摘要数据文章，其中包含有关如何在报告摘要数据时正确使用[查找数据](/help/data-views/summary-data.md#lookup-data)的信息。 |
| BI扩展更新 | 向BI扩展文档添加了[默认值和限制](/help/data-views/bi-extension.md#defaults-and-limitations)部分。 |
| 警报 | 添加了有关[警报](/help/components/c-intelligent-alerts/intelligent-alerts.md)功能的文档，该功能现在可在Customer Journey Analytics中使用。 |
| **2024 年 8 月** | |
| B2B 项目示例 | 添加了[用例](/help/use-cases/b2b/example.md)，以说明如何使用新的[转换数据集进行B2B查找](/help/connections/transform-datasets-b2b-lookups.md)功能，在Customer Journey Analytics中设置、配置和报告基于配置文件（人员）级别的B2B数据。 |
| 更新了数据导出用例 | 向[查询服务(Data Distiller)和导出数据集](/help/use-cases/data-export/queryservice-export-datasets.md)添加了更详细的查询示例，以说明如何使用回顾窗口跨会话正确应用归因。 |
| 摘要数据 | 添加了有关[摘要数据](/help/data-views/summary-data.md)、[摘要数据组组件设置](/help/data-views/component-settings/summary-data-group.md)和[摘要数据用例](/help/use-cases/data-views/summary-data.md)的文档。 |
| **2024 年 7 月** | |
| 添加了有关快速计算量度的信息 | 更新了 [量度](/help/components/apply-create-metrics.md) 中的信息，以阐明 [在计算量度生成器中创建的计算量度](/help/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) 与 [在单个项目内作为快速计算量度创建的计算量度之间的区别](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)。还添加了有关软管的更多详细信息，以创建快速计算的量度。<p>在计算量度生成器中创建的计算量度在组件列表中可用，并可应用于整个组织的项目，而作为快速计算量度创建的计算量度仅在创建它们的项目中可用。</p><p>还更新了 [构建量度](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) 中的信息，以做出类似的澄清。</p> |
| 派生字段重复项删除函数 | 添加了关于派生字段[deduplicate](/help/data-views/derived-fields/derived-fields.md#deduplicate)函数的文档。 |
| 已更新的常见错误消息 | 对 [常见错误消息](/help/analysis-workspace/workspace-faq/error-messages.md)做了小更新。 |
| **2024 年 6 月** | |
| 更新了涉及流媒体功能的产品名称 | 当引用收集流媒体数据并将其显示在 Analysis Workspace 中的一组流媒体功能时，将“媒体分析”和“流媒体”的实例替换为名称“流媒体收藏集附加组件”。 <p>这些更新在Customer Journey Analytics文档以及[流媒体收藏集附加组件文档](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-overview)中提供。</p> |
| 基于图形的拼接 | 通过引入基于图形的拼接，更新并重组了[拼接文档](/help/stitching/overview.md)。 |
| AI 助手 | 已在AI助手上添加[文档](../ai-assistant.md)以进行Customer Journey Analytics。 |
| 转换数据集以进行B2B查找 | 添加了有关如何使用转换B2B查找数据集支持对B2B数据](/help/connections//transform-datasets-b2b-lookups.md)（包括帐户、机会、营销列表和促销活动）进行[基于人员的查找的文档。 |
| 派生字段函数和函数模板 | 添加了关于其他派生字段函数（[Math](/help/data-views/derived-fields/derived-fields.md#math)、[Next或Previous](/help/data-views/derived-fields/derived-fields.md#next-or-previous)和[Summarize](/help/data-views/derived-fields/derived-fields.md#summarize)）和[函数模板](/help/data-views/derived-fields/derived-fields.md#function-templates)的文档。 |
| **2024 年 5 月** | |
| Target集成 | 向Adobe集成部分](/help/integrations/at.md)添加了有关如何将Target与Customer Journey Analytics集成的[篇文章。 |
| 使用组织策略限制将Customer Journey Analytics报表导出到Google Cloud Platform时需要的信息 | 已将Adobe拥有的Google Cloud Platform组织ID添加到[配置云导出位置](/help/components/exports/cloud-export-locations.md)文档，以便将Customer Journey Analytics报表导出到Google Cloud Platform。 <p>仅当组织在 Google Cloud Platform 中使用[组织策略约束](https://cloud.google.com/storage/docs/org-policy-constraints)时才需要此信息。</p> |
| 有关向项目添加组件的文档 | 添加了有关如何 [将各种类型的组件添加到 Analysis Workspace 中的项目](/help/components/use-components-in-workspace.md)的一般信息。 |
| 数据导出用例 | 一组新文章，介绍[数据导出用例](/help/use-cases/data-export/overview.md)以及如何使用Experience Platform和Customer Journey Analytics功能实施这些用例 |
| 有关从 Adobe Analytics 升级到 Customer Journey Analytics 的新文档 | 对于从 Adobe Analytics 升级到 Customer Journey Analytics 的组织，需要考虑组织当前的 Adobe Analytics 实施和长期目标，有多种升级选项和许多注意事项需要牢记。<p>现提供新的文档资产来帮助您更好地理解：</p><ul><li>现有的各种升级路径</li><li>根据组织当前的 Adobe Analytics 实施情况，有哪些升级路径可用</li><li>每种升级路径的优缺点</li><li>每种升级路径的分步指导</li><li>处理历史数据的注意事项</li><li>等等！</li></ul><p>[开始升级到 Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)。</p> |
| 更新了有关自定义日期范围的文档 | 更新了与[示例日期范围](/help/components/date-ranges/custom-date-ranges.md)相关的屏幕截图和过程，以匹配当前产品功能和设计。 |
| 有关Dimension的概述信息 | 添加了有关[维度](/help/components/dimensions/overview.md)的信息。 |
| 源连接器的示例 | 添加了在描述如何[使用源连接器](/help/data-ingestion/sources.md#use-a-source-connector)摄取数据时可用的源连接器示例。 |
| **2024 年 4 月** | |
| 预测统计技术 | 添加了描述预测服务](../analysis-workspace/c-forecast/statistics-forecasting.md)中使用的[统计技术的文章。 |
| 添加了建议对高基数维度导出完整表的信息 | 在[针对高基数维度的最佳实践](/help/components/dimensions/high-cardinality.md)中添加了项目符号，以建议使用针对高基数维度的完全表导出。 |
| 添加了关于移动记分卡中智能字幕的文档 | [智能字幕](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)可帮助非分析人员更好地理解他们的数据，而无需分析人员的帮助。 |
| 有关Adobe Product Analytics功能的新文档 | <ul><li>[功能矩阵](/help/guided-analysis/types/funnel.md)</li><li>增强的[保留](/help/guided-analysis/types/retention.md)</li><li>[漏斗中的增强型分析](/help/guided-analysis/types/funnel.md)</li><li>比较单个漏斗步骤中的事件</li></ul> |
| **2024 年 3 月** | |
| 有关“用于”列的使用情况信息仅从 2023 年 9 月开始提供。 | 阐明[项目登陆页面](/help/getting-started/landing.md)“**用于**”列的使用情况信息只能追溯到 2023 年 9 月。 |
| 添加了有关仅用于项目的Workspace组件的权限增强的文档 | 如果与其他用户共享项目，则这些用户可以编辑[快速筛选器](/help/components/filters/quick-filters.md)以及嵌入到共享项目中的其他仅用于项目的组件。 |
| **2024 年 2 月** | |
| 项目共享文档更新 | 添加了有关如何[查看与您共享的项目](/help/analysis-workspace/curate-share/share-projects.md#view-projects-shared-with-you)的信息。<p>还简化了有关[共享单个或多个项目](/help/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role)的信息。</p> |
| 添加了在配置云导出位置时将文件上传到Azure SAS和Azure RBAC的权限要求 | 添加了在[配置云导出帐户](/help/components/exports/cloud-export-accounts.md)和[配置云导出位置](/help/components/exports/cloud-export-locations.md)时将文件上传到Azure SAS和Azure RBAC的确切权限要求。 |
| 添加了在配置云导出位置时将文件上传到Amazon S3角色ARN和GCP存储桶的权限要求 | 添加了在[配置云导出位置](/help/components/exports/cloud-export-locations.md)时将文件上传到Amazon S3角色ARN和Google Cloud Platform存储桶的确切权限要求。 |
| 阐明了产品管理员始终有权导出全部表 | 进行了以下更改，以明确说明分配了产品管理员角色的用户在默认情况下有权从Analysis Workspace导出完整表： <ul><li>向[产品管理员默认权限](/help/technotes/access-control.md#product-admin-default-permissions)添加了新项目符号。</li><li>在导出完整表到云的[最低要求下添加了注释](/help/analysis-workspace/export/export-cloud.md#minimum-requirements)。</li></ul> |
| 阐明了从Adobe Analytics迁移组件期间会重新创建区段 | 在[Adobe Analytics用户用户指南](/help/getting-started/aa-to-cja-user.md)中，阐明了区段在组件迁移过程中会在Adobe Analytics中自动重新创建，无需手动重新创建。 |
| 跳过的记录详细信息 | 添加了有关“连接”中跳过的记录详细信息功能的文档。 有关详细信息，请参阅[连接详细信息](../connections/manage-connections.md#connection-details)。 |
| **2024 年 1 月** | |
| 预测 | 添加了有关[forecasting](../analysis-workspace/c-forecast/forecasting.md)的文档，该文档是新的Analysis Workspace功能，可用于对自由格式表和折线图的标准或计算量度进行预测，并具有任何受支持的时间粒度（每小时、每天、每周、每月和每年）。 |
| 更新了在导出完整表时添加帐户和位置的文档 | 更新了文档，以反映在[从Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)导出完整表时配置新帐户或位置时的细微界面更新。<p>[!UICONTROL **帐户**]&#x200B;下拉菜单中现在有新的&#x200B;[!UICONTROL **添加帐户**]&#x200B;选项可用。 以前作为&#x200B;[!UICONTROL **位置名称**]&#x200B;下拉菜单旁边的按钮提供的&#x200B;[!UICONTROL **添加位置**]&#x200B;选项现在可在菜单本身中使用。 |
| 从Adobe Analytics迁移时的新组件迁移信息 | 向[Adobe Analytics的演变](/help/getting-started/aa-to-cja.md)添加了引用《Adobe Analytics管理指南》中记录的新[组件迁移](https://experienceleague.adobe.com/cn/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)功能的信息。 |
| 阐明了仅管理员有某些信息可用 | 添加了信息来声明，[计算量度管理器](/help/components/calc-metrics/cm-workflow/cm-manager.md)和[过滤器管理器](/help/components/filters/manage-filters.md)中描述的“上次使用”和“用于”列仅适用于系统管理员。 |
| 导出数据集所需的权限 | 添加了说明[将数据集导出到云目标所需的权限](/help/technotes/access-control.md)的信息。 |
| 管理连接 | 已根据客户反馈更新[管理连接](../connections/manage-connections.md)文章。 |
| 派生字段 | 添加了函数[限制](/help/data-views/derived-fields/derived-fields.md#limitations)的摘要以及有关如何确定函数中使用的[运算符](/help/data-views/derived-fields/derived-fields.md#operators)数的说明。 |

{style="table-layout:auto"}


## 2023

| 功能 | 描述 |
| --- | --- |
| **2023 年 12 月** | |
| 数据中心 | 添加了有关Customer Journey Analytics[托管位置](../technotes/data-centers.md)的文章。 |
| 护栏 | 添加了列出Customer Journey Analytics[护栏](../technotes/guardrails.md)的文章。 |
| 货币兑换更新 | 阐明了有关如何[配置货币兑换](/help/data-views/component-settings/format.md)的文档。 |
| 对异常检测文档的更新 | 异常检测文档以前位于有关Virtual Analyst的部分中。 进行了以下更改： <ul><li>术语 Virtual Analyst 已从文档中删除。</li><li>关于[异常检测](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)的部分已直接移至 Analysis Workspace 部分下方。</li></ul> |
| **2023 年 10 月** | |
| 使用派生字段设置目标/目标 | 添加了[用例](../use-cases/goals-using-derived-fields.md)文章，说明如何使用派生字段设置目标/目标并报告这些目标/目标。 |
| 将整个表导出到云 | 添加了有关将包含数百万行Workspace的完整表导出到云目标的文档。 <p>导出全表可一次性或按计划投放在 Workspace 中设计的数据表，其中支持最多五个细分、五个量度、过滤器和计算量度，所有这些都在一个连接在一起的表中。它从 Adobe Analytics 中的 Data Warehouse 报告演化而来，具有许多当今在 Data Warehouse 中不提供但经常有人要求提供的新功能。</p><p>有关详细信息，请参阅[将 Customer Journey Analytics 报告导出到云](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html)。 |
| 报告活动管理器 | 添加了有关报告活动管理器的文档。 <p>通过报告活动管理器，可查看组织中每个连接的报告容量。它使管理员能够详细了解报告消耗，以便轻松地诊断和修复在报告高峰期出现的容量问题。</p> <p>添加了以下新文章：<ul><li>[报告活动管理器概述](/help/reporting-activity-manager/reporting-activity-overview.md)</li><li>[在报告活动管理器中查看报告活动](/help/reporting-activity-manager/reporting-activity.md)</li><li>在报告活动管理器中[取消请求](/help/reporting-activity-manager/reporting-activity-cancel-requests.md)</ul> |
| 管理页面上的新列 | 记录了[计算量度管理器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html)和[筛选器管理器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html)中现在可用的新列。 |
| 与 Adobe Analytics 进行比较 | 添加了[概述页面](../getting-started/aa-vs-cja/overview.md)作为比较和了解Customer Journey Analytics与Adobe Analytics之间差异的简介。 |
| 附加派生字段功能 | 更新了新[`Lookup`](/help/data-views/derived-fields/derived-fields.md#lookup)函数的文档。 |
| **2023 年 9 月** | |
| 更新了“媒体播放耗时”面板的文章结构 | 删除了名为“媒体播放耗时”的文件夹，并将该文件夹的内容合并为一篇文章：[“媒体播放耗时”面板](/help/analysis-workspace/c-panels/media-playback-time-spent.md)。 <p>此更改与其他面板的文档更一致。</p> |
| 附加派生字段功能 | 更新了有关新的 [`Lowercase`](/help/data-views/derived-fields/derived-fields.md#lowercase) 和 [`Trim`](/help/data-views/derived-fields/derived-fields.md#trim) 函数以及添加到 [`Classify`](/help/data-views/derived-fields/derived-fields.md#classify) 函数的附加 CSV 功能的文档。 |
| 地区数据收集 | 通过关于在使用 Customer Journey Analytics 时进行地区数据收集的信息更新了[常见问题解答](../getting-started/cja-faq.md#12-regional-data-collection)。 |
| **2023 年 8 月** | |
| “媒体播放耗时”面板 | 更新了[“媒体播放耗时”面板](/help/analysis-workspace/c-panels/media-playback-time-spent.md)的内容以提高可读性。 |
| Report Builder 增强 | 更新了[安排工作簿](/help/report-builder/schedule-reportbuilder.md)的内容以提供下载计划任务的信息。更新了[创建数据块](/help/report-builder/create-a-data-block.md)的内容以提供使用开始日期作为维度的信息。 |
| 移动了关于管理计划项目的内容 | 在《Analytics 组件指南》中创建了一篇名为[计划项目](/help/components/scheduled-projects-manager.md)的新文章。此内容以前位于《Analytics 工具指南》中的[计划项目](/help/analysis-workspace/export/t-schedule-report.md)一文中。 |
| 支持 Adobe Customer Journey Analytics 功能 | 在“Customer Journey Analytics 与 Adobe Analytics 相比”中关于会话化功能的&#x200B;*以新方式支持*&#x200B;表中添加了更多信息。[了解详情](../getting-started/aa-vs-cja/cja-aa.md#supported-in-a-new-way) |
| Adobe Analytics 的演化 | 通过引用派生字段营销渠道功能模板，更新了&#x200B;*（重新）配置营销渠道*&#x200B;部分。[了解详情](../getting-started/aa-to-cja.md#3-reconfigure-your-marketing-channels) |
| 移动应用程序和其他平台的数据摄取快速入门指南 | 添加了额外的数据摄取快速入门指南，概述了如何在 Customer Journey Analytics 中摄取和使用来自移动应用程序或其他平台（例如桌面应用程序、控制台上的游戏、机顶盒和物联网设备上的应用程序）的数据。[了解详情](../data-ingestion/data-ingestion.md) |
| **2023 年 7 月** | |
| 会话设置 | 为此数据视图设置添加了一个主题。[了解详情](/help/data-views/session-settings.md) |
| Adobe Product Analytics | Adobe Product Analytics 是一种与 Customer Journey Analytics 中的跨渠道数据和见解进行交互的新方式。这些新功能使产品团队能够通过[引导式分析](/help/guided-analysis/overview.md)工作流程自助提供有关其产品体验的数据和见解。 |
| 派生字段 | 通过[派生字段](/help/data-views/derived-fields/derived-fields.md)和可自定义的规则生成器，即可迅速定义（一般较为复杂的）数据操作。 |
| 配置文件和查找数据的扩展查找支持 | 提供将数据集添加为配置文件或查找数据集中的字段查找的功能。之前，仅支持事件数据集。[了解详情](/help/connections/create-connection.md) |
| Report Builder 增强 | <ul><li>[从单元格中筛选多个数据块](/help/report-builder/select-data-view.md)</li><li>[显示和隐藏行标题和列标题](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html#build-the-data-block)</li></ul> |
| Edge Network地理查找 | [数据流设置](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hans)如何提供统一地理数据的地理查找服务。 |
| **2023 年 6 月** | |
| 跨渠道分析和拼合 | 为了预测即将进行的更改，以支持拼合并进一步阐明如何使用拼合提升跨渠道分析，我们编辑了与跨渠道分析功能相关的文档，将[跨渠道分析](../use-cases/cross-channel/cross-channel.md)称作 Customer Journey Analytics 功能和用例，并将[拼合](../stitching/overview.md)作为实现此目的的重要功能。 |
| PowerBI 和 Tableau 访问 Customer Journey Analytics 数据视图 | Customer Journey AnalyticsBI扩展允许SQL访问您在Customer Journey Analytics中定义的数据视图。 [了解详情](/help/data-views/bi-extension.md) |
| Adobe Journey Optimizer 数据视图 | Customer Journey Analytics 管理员有权访问 Customer Journey Analytics 中某些名为“AJO 数据视图（沙盒名称）”的额外数据视图。[了解详情](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channel-report/reporting-configuration)。 |
| 货币换算 | 更新了有关[货币换算](../data-views/component-settings/format.md#currency)支持的文档。 |
| 计算量度更新 | 对计算量度文档作出了以下更新，以使其与当前的 Customer Journey Analytics 功能保持一致： <ul><li>更新了 Customer Journey Analytics 中提供的[默认计算量度](/help/components/calc-metrics/default-calcmetrics.md)的列表</li><li>更新了各种计算指标文章中的屏幕截图和过程 </li></ul> |
| **2023 年 5 月** | |
| 深层链接（移动设备应用程序）文档 | 使用户可发送记分卡的链接，而这些链接将引导用户直接进入应用程序中的记分卡项目。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html#share-scorecards-using-a-shareable-link) |
| 关于 Report Builder 中的“从单元格选择数据视图”文档 | 通过此功能，用户可从单元格选择数据块的数据视图。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) |
| 关于 Analytics 功能板应用程序（移动设备应用程序）更新的主屏幕的文档 | 通过新近更新的主屏幕，可在一个合并的记分卡列表中查看您的所有记分卡。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) |
| 优化更新 | 更新了有关[优化 Customer Journey Analytics 性能](/help/technotes/optimizing-performance.md)的文章 |
| Analysis Workspace 概述 | 更新了 [Analysis Workspace 概述](/help/analysis-workspace/home.md)，包括更多的一般概述信息和相关内容的链接。 |
| 创建项目 | 创建了一篇新文章，其中详细解释了如何在 Analysis Workspace 中[创建项目](/help/analysis-workspace/build-workspace-project/create-projects.md)。 |
| 为左边栏中的组件排序 | 添加了有关为左边栏中的组件列表排序的信息。请参阅[组件概述](/help/components/overview.md)中的“搜索、过滤组件列表和为其排序”部分。 |
| 从自由格式表中删除包含动态维度的行 | 添加了有关如何使用 x 图标快速删除包含动态维度的特定行的信息。请参阅[过滤表和为其排序](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)中的“从表中快速排除特定行”部分。 |
| 面板中添加可视化效果的按钮 | 添加了有关 Analysis Workspace 中每个面板底部的新按钮的信息，通过该按钮，可快速地添加可视化效果。请参阅[可视化概述](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)中的“将可视化效果添加到面板”部分。 |
| 智能题注文档 | 通过折线图可视化效果的[自然语言概括](/help/analysis-workspace/visualizations/intelligent-captions.md)，为用户提供更丰富多彩的叙事。 |
| 派生字段 | 添加了有关[派生字段](../data-views/derived-fields/derived-fields.md)功能的文档。 |
| **2023 年 4 月** |  |
| 关于使用过滤器作为维度的视频 | 更新了关于使用过滤器作为维度的视频。 <p>此视频链接自[创建过滤器](/help/components/filters/create-filters.md)页面。</p> <p>以下是这段视频的直接链接：[在 Analysis Workspace 中使用过滤器作为维度](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/filters/use-filters-as-dimensions.html)。</p> |
| 过滤器文档 | 添加了有关使用[过滤器生成器](/help/components/filters/filter-builder.md)的文章。 <p>简化了[创建过滤器](/help/components/filters/create-filters.md)和[过滤器概述](/help/components/filters/filters-overview.md)中的文档。</p> |
| 更新实验面板文档 | 添加了一个有关[解释非随机维度](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/experimentation.html#non-randomized)的部分。 |
| 项目过滤器（临时过滤出和快速过滤器） | 简化了有关项目过滤器的文档并删除了重复的信息。创建临时过滤器的步骤现在与[创建快速过滤器](/help/components/filters/quick-filters.md)的步骤合并在一起。 |
| **2023 年 3 月** | |
| 集成决策管理数据 | 添加了解释如何[在 Customer Journey Analytics 中集成 Adobe Journey Optimizer 决策管理数据](/help/integrations/ajo-od.md)的内容。 |
| 在移动记分卡中创建数据故事 | [数据故事](/help/mobile-app/create-scorecard.md#create-data-stories)是围绕中心主题或指标构建的辅助数据点、业务背景和相关指标的集合。 |
| 更新了功能支持 | 更新了 [Customer Journey Analytics 功能支持](/help/getting-started/aa-vs-cja/cja-aa.md)，提供一个功能表，其中是在 Customer Journey Analytics 中可用但在 AA 中不可用或不支持的功能。 |
| 默认计算量度 | 添加了解释 [Adobe 提供的默认计算量度](/help/components/calc-metrics/default-calcmetrics.md)的内容。 |
| 数据词典 | <p>添加了数据词典的新文档，包括[概述](/help/components/data-dictionary/data-dictionary-overview.md)、[查看](/help/components/data-dictionary/view-data-dictionary.md)、[编辑](/help/components/data-dictionary/edit-entries-data-dictionary.md)和[监控](/help/components/data-dictionary/monitor-data-dictionary-health.md)数据词典。</p><p>更新了[添加组件描述](/help/components/add-component-descriptions.md)中的信息以解释数据词典功能。</p> |
| 共享项目链接（无需登录） | <p>更新了现有文档以说明如何与无权访问 Analysis Workspace 的人员共享项目的只读链接。</p> <p>更新后的用户文档包括[共享项目](/help/analysis-workspace/curate-share/share-projects.md)和[创建可共享链接](/help/analysis-workspace/curate-share/shareable-links.md)。</p> <p>已将管理员的选项添加到[偏好设置](/help/analysis-workspace/user-preferences.md)。</p> |
| **2023 年 2 月** | |
| 比较 Customer Journey Analytics 和 BI 解决方案 | 新增了有关 Customer Journey Analytics 与典型 BI 解决方案的[比较](../getting-started/cja-vs-bi.md)的文档。 |
| 对 Audiences 文档的更新 | 有关[延迟注意事项](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#latency)的新章节。 |
| 对 Audiences 文档的更新 | 在您创建受众后，Adobe [为每个新的 Customer Journey Analytics 受众创建一个 Experience Platform 流式区段](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=zh-Hans#after-audience-created)。 |
| 工作区日历和日期范围 | 更新内容以描述相对日期范围、公式计算更新和日程表 UI 更改。请参阅[关于相对面板日期范围](/help/components/date-ranges/overview.md#custom-date-ranges)。 |
| 移动记分卡 | 新文档部分描述如何显示和隐藏比较日期范围。请参阅 Customer Journey Analytics 中的[显示比较日期范围](/help/mobile-app/create-scorecard.md#show-comparison-dates)。 |
| **2023 年 1 月** | |
| 排序和过滤表格 | 更新了[对表格进行筛选和排序](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)一文中的内容（包括添加过程和解释可用选项）。本文从“对表格进行分页、筛选和排序”更名而成。 |
| 数据摄取快速入门指南 | 关于如何在 Customer Journey Analytics 中[摄取和使用数据](/help/data-ingestion/data-ingestion.md)的新文档部分。 |
| Workspace 文件夹 | [文件夹管理](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)的专用页面。 |
| Workspace 用户偏好设置 | [偏好设置](/help/analysis-workspace/user-preferences.md)中现在提供了许多其他用户偏好设置。 |
| 自动保存 Workspace 项目 | 已更新内容以在[保存项目](/help/analysis-workspace/build-workspace-project/save-projects.md)中包含自动保存功能。 |
| 登陆页面 | 新的着陆页面更新[着陆页面](/help/getting-started/landing.md)。 |
| 计划工作簿 | 专用页面描述如何在 Report Builder 中[计划工作簿](/help/report-builder/schedule-reportbuilder.md)。 |
| 对象数组支持配置文件和查找数据集 | 更新了[使用对象数组](/help/use-cases/object-arrays.md)和[摄入 Adobe Experience Platform 受众](/help/use-cases/data-ingestion/ingest-aep-segments.md)以反映对配置文件和查找数据集的对象数组支持。 |

{style="table-layout:auto"}

## 2022

| 日期 | 更新描述 |
| --- | --- |
| **2022 年 12 月** |  |
| 2022 年 12 月 16 日 | 关于[测量和管理 Customer Journey Analytics 数据使用](/help/technotes/estimate-usage.md)的新主题。 |
| **2022 年 10 月** | |
| 2022 年 10 月 | 关于[计划项目密码保护](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=zh-Hans#password)的新主题。 此功能支持 [HIPAA 准备工作](https://www.adobe.com/cn/trust/compliance/hipaa-ready.html)。 |
| 2022 年 10 月 | 关于[客户管理的密钥](/help/privacy/cmk.md)新主题。 此功能支持 [HIPAA 准备工作](https://www.adobe.com/cn/trust/compliance/hipaa-ready.html)。 |
| 2022 年 10 月 | 关于 [Customer Journey Analytics 审核日志](/help/privacy/audit-log.md)的新主题。 |
| 2022 年 10 月 | 关于[关键指标摘要](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html?lang=zh-Hans)可视化的新主题。 |
| 2022 年 10 月 | 关于[数据视图中的日期和日期时间功能](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#date)的新部分 |
| 2022 年 10 月 | 移动应用程序：关于[自定义详细视图](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#view-detail-slides)的新主题。 |
| 2022 年 10 月 | 对 [Customer Journey Analytics 功能支持](/help/getting-started/aa-vs-cja/cja-aa.md)主题进行了更新。 |
| **2022 年 9 月** | |
| 2022 年 9 月 | 关于[将 Google Analytics 数据迁移到 Customer Journey Analytics](/help/use-cases/ga/overview.md) 的新用例。 |
| 2022 年 9 月 | Workspace 中[组合图表](/help/analysis-workspace/visualizations/combo-charts.md)的新主题。 |
| 2022 年 9 月 | 关于 Workspace 中[“试验”面板](/help/analysis-workspace/c-panels/experimentation.md)的新主题。 |
| **2022 年 8 月** | |
| 2022 年 8 月 | Adobe Experience Platform 有关 [Analytics Source Connector 跨区域支持](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans)的文章。 |
| 2022 年 8 月 | 关于 [Customer Journey Analytics 访问控制](/help/technotes/access-control.md)的大幅更新文章。 |
| 2022 年 8 月 | 关于 [Customer Journey Analytics 支持数据管理标签和策略](/help/data-views/data-governance.md)的新文章。 |
| 2022 年 8 月 | 关于[比较通过 Analytics Source Connector 传递的分析数据的术语](/help/getting-started/aa-vs-cja/terminology.md)的新文章。 |
| 2022 年 8 月 | 有关[将受众发布到实时客户个人资料](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=zh-Hans)的新文档。 |
| **2022 年 7 月** | |
| 2022 年 7 月 | [Media Playback 耗时面板](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html?lang=zh-Hans)文档。 |
| 2022 年 7 月 | [媒体并行查看者面板](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html?lang=zh-Hans)文档。 |
| 2022 年 7 月 | [首次会话](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html#new-repeat)报告文档。 |
| **2022 年 6 月** | |
| 2022 年 6 月 | 关于 [AAID、ECID、AACUSTOMID 和 Analytics Source Connector](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=zh-Hans) 的新文章。 |
| 2022 年 6 月 | 关于 [Adobe Analytics 处理规则、VISTA 和分类对比 Analytics Source Connector 的数据准备的新文章](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)。 |
| 2022 年 6 月 | 关于[虚拟报告环境和沙盒环境的新文章](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)。 |
| 2022 年 6 月 | 关于[跨 Adobe Analytics 和 Customer Journey Analytics 报告功能比较数据处理](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)的新文章。 |
| 2022 年 6 月 | 关于[将报告包与不同的架构](/help/use-cases/aa-data/combine-report-suites.md)组合的新文章。 |
| 2022 年 6 月 | 关于[在 Mobile 记分卡中共享批注的新文章](/help/components/annotations/mobile-annotations.md)。 |
| 2022 年 6 月 | 关于 [Customer Journey Analytics 分析实验室](/help/labs/labs.md)的新文章。 |
| 2022 年 6 月 | 有关[支持数字字段作为查找键和查找值](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hans#numeric)的新部分。 |
| 2022 年 6 月 | [流量可视化工作流](/help/analysis-workspace/visualizations/c-flow/create-flow.md)的更新。 |
| **2022 年 5 月** | |
| 2022 年 5 月 | 关于在 Customer Journey Analytics 中[创建连接](/help/connections/create-connection.md)的大幅更新文章。 |
| 2022 年 5 月 | 关于如何[在 Customer Journey Analytics Report Builder 中管理数据块](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=zh-Hans)的新文章。 |
| 2022 年 5 月 | 关于[将 Adobe Experience Platform 受众引入 Customer Journey Analytics](/help/use-cases/data-ingestion/ingest-aep-segments.md) 的新文章。 |
| **2022 年 4 月** | |
| 2022 年 4 月 | 关于[维度子字符串](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/substring.html?lang=zh-Hans)的文档。 |
| 2022 年 4 月 | 全新 [Adobe Analytics 用户的 Customer Journey Analytics 用户指南](/help/getting-started/aa-to-cja-user.md)。 |
| **2022 年 3 月** | |
| 2022 年 3 月 | 全新 [Customer Journey Analytics 批注 API 文档](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)。 |
| 2022 年 3 月 | 关于[工作区批注](/help/components/annotations/overview.md)的新文档。 |
| 2022 年 3 月 | 关于[估计连接大小](/help/getting-started/cja-faq.md)内容的大幅更新。 |
| **2022 年 2 月** | |
| 2022 年 2 月 | 面向从 Adobe Analytics 转移到 Customer Journey Analytics 的管理员的新指南：[从 Adobe Analytics 到 Customer Journey Analytics 的演化](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html?lang=zh-Hans) |
| **2022 年 1 月** | |
| 2022 年 1 月 | [在 Customer Journey Analytics 中使用绑定维度和指标](/help/use-cases/data-views/binding-dimensions-metrics.md)的新用例 |
| 2022 年 1 月 | 添加了有关[绑定维度和指标](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=zh-Hans#binding-dimension)以及新的[[!UICONTROL 第一个已知]和[!UICONTROL 最后一个已知]分配设置的新功能文档](/help/data-views/component-settings/persistence.md#allocation-settings) |
| 2022 年 1 月 | 关于[将 Adobe Analytics 数据与 Customer Journey Analytics 中的 Analytics 数据进行比较](https://experienceleague.adobe.com/docs/analytics-platform/using/troubleshooting/compare.html?lang=zh-Hans)的新文章 |

{style="table-layout:auto"}

## 2021

| 日期 | 更新描述 |
| --- | --- |
| **2021 年 11 月** | |
| 2021 年 11 月 | 更新了有关“连接详细信息”页面上[[!UICONTROL 跳过的记录数]](/help/connections/manage-connections.md)的文档。 |
| **2021 年 10 月** | |
| 2021 年 10 月 | 有关 Customer Journey Analytics 中的 [Report Builder](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/report-buider-overview.html?lang=zh-Hans#) 的文档。 |
| 2021 年 10 月 | Customer Journey Analytics [审核日志](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) API 文档 |
| 2021 年 10 月 | 记录了 [Analytics 功能板的可视化图表](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=zh-Hans#apply-visualizations) |
| 2021 年 10 月 | 有关[!UICONTROL 连接][数据保留](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=zh-Hans#set-rolling-window-for-connection-data-retention)滚动时段的文档 |
| **2021 年 9 月** | |
| 2021 年 9 月 | [指标去重](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication.html?lang=zh-Hans)文档 |
| 2021 年 9 月 | [报告中的夏令时支持](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=zh-Hans#calendar) |
| 2021 年 9 月 | [客户日历](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=zh-Hans#calendar)文档 |
| 2021 年 9 月 | [布尔字段](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/behavior.html?lang=zh-Hans)文档 |
| 2021 年 9 月 | 将数据视图中的组件设置细分为单独的文件：<ul><li>[[!UICONTROL 组件]设置概述](/help/data-views/component-settings/overview.md)</li><li>[[!UICONTROL 归因]组件设置](/help/data-views/component-settings/attribution.md)</li><li>[[!UICONTROL 行为]组件设置](/help/data-views/component-settings/behavior.md)</li><li>[[!UICONTROL 格式]组件设置](/help/data-views/component-settings/format.md)</li><li>[[!UICONTROL 包括/排除]组件设置](/help/data-views/component-settings/include-exclude-values.md)</li><li>[[!UICONTROL 指标去重]组件设置](/help/data-views/component-settings/metric-deduplication.md)</li><li>[[!UICONTROL 无值]组件设置](/help/data-views/component-settings/no-value-options.md)</li><li>[[!UICONTROL 持久性]组件设置](/help/data-views/component-settings/persistence.md)</li><li>[[!UICONTROL 值分段]组件设置](/help/data-views/component-settings/value-bucketing.md)</li></ul> |
| 2021 年 9 月 | 有关 Customer Journey Analytics 中[合并报告包后果](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hans#6。-considerations-when-merging-report-suites-in-cja)的新部分。 |
| **2021 年 8 月** | |
| 2021 年 8 月 | 关于 Customer Journey Analytics 中增强的[连接](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=zh-Hans)的新部分。 |
| 2021 年 8 月 | 有关[数据视图维度中的区分大小写](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=zh-Hans#configure-behavior-settings)的新部分。 |
| **2021 年 6 月** | |
| 2021 年 6 月 | 有关工作区中[以前的项目版本](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/build-workspace-project/save-projects.html?lang=zh-Hans#previous-version)的新文档。 |
| **2021 年 4 月** | |
| 2021 年 4 月 | 有关[持久性](/help/data-views/component-settings/persistence.md)的新主题。 |
| 2021 年 4 月 | 有关工作区中对计划项目的支持的新文档。 |
| 2021 年 4 月 | 有关[增强数据视图体验](/help/data-views/data-views.md)的新主题 |
| 2021 年 4 月 | 有关[摄取 Google Analytics 数据](/help/use-cases/ga/overview.md)和[分析该数据](/help/use-cases/ga/report.md)的新主题。 |
| 2021 年 4 月 | 增加了有关工作区中[计划报告](/help/analysis-workspace/export/t-schedule-report.md)的主题。 |
| 2021 年 4 月 | 关于 [Customer Journey Analytics 中的高基数维度](/help/components/dimensions/high-cardinality.md)的新主题。 |
| **2021 年 3 月** | |
| 2021 年 3 月 | 增加了有关对 [Analytics 功能板](/help/mobile-app/home.md)（移动应用程序）支持的主题。 |
| 2021 年 3 月 | 有关工作区中[用户首选项](/help/analysis-workspace/user-preferences.md)的新主题。 |
| **2021 年 2 月** | |
| 2021 年 2 月 | 有关在 [Adobe Experience Platform 中使用营销渠道维度](/help/use-cases/aa-data/marketing-channels.md)的新主题。 |
| 2021 年 2 月 | 已发布全新的 [Customer Journey Analytics API](https://www.adobe.io/cja-apis/docs/) 文档。 |
| **2021 年 1 月** | |
| 2021 年 1 月 | 有关[向数据集添加标准查找](/help/connections/standard-lookups.md)的新主题。 |

{style="table-layout:auto"}

## 2020

| 日期 | 更新描述 |
| --- | --- |
| 2020 年 11 月 13 日 | 有关[跨渠道分析](/help/stitching/overview.md)的新主题，它允许您重新键入数据集的人员ID，并实现多个数据集的无缝组合。 |
| 2020 年 11 月 13 日 | 添加了有关[导入呼叫中心和 Web 数据](/help/use-cases/cross-channel/call-center.md)的新用例。 |
| 2020 年 11 月 10 日 | 将有关删除数据组件后果的部分添加到[常见问题解答](/help/getting-started/cja-faq.md)中。 |
| 2020 年 11 月 2 日 | 对 [Customer Journey Analytics 功能支持](/help/getting-started/aa-vs-cja/cja-aa.md)页面进行了更新。 |
| 2020 年 11 月 | 添加了有关为连接[删除回填限制](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hans#backfill-historical-data)的内容。 |
| 2020 年 10 月 7 日 | 添加了有关[合并事件数据集](/help/connections/combined-dataset.md)的主题。 |
| 2020 年 9 月 15 日 | 添加了有关[数据摄取](/help/data-ingestion/data-ingestion.md)的主题。 |
| 2020 年 9 月 2 日 | 更新了有关[用户权限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hans)的部分。 |
| 2020 年 7 月 | 添加了有关[人员 ID 的标识映射选项](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hans)的信息。 |
| 2020 年 7 月 | 添加了有关[对象数组](/help/use-cases/object-arrays.md)或“数据层次结构”的新主题。 |
| 2020 年 4 月 14 日 | 对[创建连接](/help/connections/create-connection.md)主题中的最新 UI 进行了更新。 |
| 2020 年 2 月 27 日 | 对 [Customer Journey Analytics 功能支持](/help/getting-started/aa-vs-cja/cja-aa.md)的更新 |
| 2019 年 12 月 | Customer Journey Analytics 文档初稿 |

{style="table-layout:auto"}
