---
title: Customer Journey Analytics 功能支持
description: 了解 Customer Journey Analytics 的功能，并与 Adobe Analytics 的功能集进行对比。
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 7f44c7497a48e8377ca26cb194f828c3c8836f98
workflow-type: tm+mt
source-wordcount: '2709'
ht-degree: 100%

---

# Customer Journey Analytics 功能支持

下表列出了 Customer Journey Analytics 所独有的功能，以及 Customer Journey Analytics 中支持、部分支持或不支持的 Adobe Analytics 功能。由于后续会向 Customer Journey Analytics 添加其他功能，因此这些列表会随着时间而发生变化。

## Adobe Customer Journey Analytics 独有的功能 {#cja-not-aa}

下表列出了 Customer Journey Analytics 中可用但 Adob&#x200B;e Analytics 不支持的功能。

| 功能 | 更多详细信息 |
| --- | --- |
| **能够组合数据集（例如 Adobe Analytics 报告包）** | 通过 Customer Journey Analytics，可从多个报告包[组合数据](/help/connections/combined-dataset.md)，如同它们是 Adobe Analytics 中的单个报告包一样。 |
| **适用于任何类型的数据** | Customer Journey Analytics 与 Experience Platform 保存各种数据架构和类型的能力相结合。使用[体验数据模型 (XDM)](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/home)，可以采用统一的方式来表示和组织数据，以便进行数据合并和分析。Adobe Analytics 主要专注于 Web 和移动分析数据，并具有一些[数据导入](https://experienceleague.adobe.com/zh-hans/docs/analytics/import/home)功能。 |
| **B2B Edition** | [Customer Journey Analytics B2B Edition](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition?lang=cn) 通过提供可付诸行动的账户洞察，助力 B2B 企业协同其市场、销售与产品团队，推动营收增长。帐户是数据模型的中心，因此所有分析都集中在帐户历程上。在基于人员及时间的事件之上添加一层新实体（帐户、机会和购买群组），可以创建 B2B 营销活动和收入生命周期的完整图景。 |
| **BI 扩展** | 通过 [BI 扩展功能](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-usecases/data-export/bi-extension)，您可以将 Customer Journey Analytics 直接连接至主流 BI 可视化工具，例如 Power BI 或 Tableau。使用此扩展功能，您可以确保 BI 报表与 Analysis Workspace 及其他 Customer Journey Analytics 报表界面中的数据精准一致。该扩展功能为 Customer Journey Analytics 提供了一种更为简便的 BI 报表获取方式，无需从原始数据重新构建报表或量度。 |
| **Workspace 项目中的备注** | 您可以通过备注在 [Analysis Workspace 项目](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects?lang=cn)的上下文中分享见解并提出问题。这可以简化有关数据的讨论，使对话保持在正在讨论的数据范围内。 |
| **Content Analytics** | [Content Analytics](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/content-analytics/content-analytics) 帮助营销人员了解内容如何影响企业定义的关键绩效指标。除了行为数据之外，Content Analytics 还收集关于内容如何被消费以及内容如何产生影响的数据。 |
| **跨设备分析** | Customer Journey Analytics 支持来自未经身份验证和经过身份验证的会话的特定于设备的数据集的无缝组合。Customer Journey Analytics 可以将历史数据回填到已知设备。在 Adobe Analytics 中，此功能仅限于单个报告包和使用设备图时。 |
| **Data Insights 代理** | [Data Insights 代理](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai?lang=cn)是 Customer Journey Analytics 中 AI 助手的一部分，是一款生成式 AI 对话代理。它使用来自数据视图和实际数据的组件，通过在 Analysis Workspace 中构建相关的可视化图表来快速有效地回答以数据为中心的问题。 |
| **维度增强功能** | Customer Journey Analytics 为使用维度提供了更大的灵活性： <ul><li>**自定义基于数值的维度**：[在数据视图中创建您自己的基于数值的维度](/help/data-views/create-dataview.md#components)。</li><li>**对基于字符串的维度进行排序**：[在自由格式表中按字母顺序对基于字符串的维度进行排序。](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#sort-tables) </li></ul><p>在 Adobe Analytics 中，只有少数内置数值维度可用，并且无法按基于字符串的维度进行排序。</p> |
| **派生字段** | [派生字段](/help/data-views/derived-fields/derived-fields.md)可为数据转换报告时间。可即时组合、更正或创建数据，并且这些转换可追溯地应用于所有报告。 |
| **增强了安全和隐私选项** - HIPAA 就绪 | Customer Journey Analytics 符合 HIPAA 标准，并提供[附加安全选项](/help/privacy/cmk.md)，以确保符合相关法规。Adobe Analytics 尚未为 HIPAA 做好准备。 |
| **试验分析** | Customer Journey Analytics 可以[评估来自定义为连接一部分的任何数据源的任何试验](/help/analysis-workspace/c-panels/experimentation.md)的提升度和置信度。通过此评估，您可以了解跨任何渠道的客户互动之间的因果关系。Analytics 仅限用于通过 A4T 进行的试验分析。 |
| **预测** | [预测](/help/analysis-workspace/c-forecast/forecasting.md)是一种 AI/ML 功能，包括基于 Customer Journey Analytics 中已有的历史数据对时间序列相关数据进行统计预测。预测可以出现在自由格式的表格和线形图可视化中。 |
| **引导式分析** | [引导式分析](/help/guided-analysis/overview.md)使用户能够通过基于 Customer Journey Analytics 的跨渠道数据的引导式工作流，自助提供有关客户历程的高质量数据和洞察。 |
| **智能题注** | [智能题注](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/visualizations/intelligent-captions)使用先进的机器学习和生成式 AI 为 Workspace 可视化提供有价值的自然语言见解。支持以下可视化图表的智能题注：线形图、多行、条形图、水平条形图、圆环图、面积图、流量和流失图。 |
| **历程画布** | [历程画布](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/visualizations/journey-canvas/journey-canvas?lang=cn)是 Analysis Workspace 中的一种可视化工具，可用于分析用户如何在既定历程中前进或流失。 |
| **产品使用情况** | [产品使用情况](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/tools/product-usage/usage-overview)向您展示贵组织如何使用 Customer Journey Analytics。 |
| **报告时转换** | Customer Journey Analytics 中的[数据视图](/help/data-views/data-views.md)可用于解释来自某个连接的数据。您可以在不更改实施方式的前提下修改或移除数据。使用子字符串操作维度。可根据任意数值创建量度，或筛选子事件。以非破坏性的方式进行所有这些转换。Adobe Analytics 通过虚拟报告包和自定义会话长度提供有限的功能。 |
| **数据视图间共享的量度和维度** | 共享的量度和维度可让您[在多个数据视图中统一应用维度和量度设置](/help/data-views/shared-metrics-dimensions/smd-overview.md)。对某个共享维度或量度所做的更改会应用于所有适用的数据视图中该维度或量度的所有实例。 |
| **SQL 访问** | 通过使用数据蒸馏器选项，Customer Journey Analytics 可以消除 Adob&#x200B;e 后端处理中收集的数据的限制。您可以使用 SQL 修改数据、创建适合您的业务的值和数据集，并继续探索。Analytics 不支持对其数据进行任何类型的 SQL 访问。 |
| **拼合** | [拼合](/help/stitching/overview.md)是一项强大的功能，可以提升事件数据集进行跨渠道分析的适用性。跨渠道分析是 Customer Journey Analytics 能够支持的主要使用场景之一。跨渠道分析可让您基于共同标识符（如人员 ID），将来自不同渠道的多个数据集无缝整合并运行报表。 |
| **Adobe Journey Optimizer 中的模板** | 在 Adobe Journey Optimizer 中自定义新的报告界面：在 Customer Journey Analytics 中创建或编辑[模板](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/templates/create-templates?lang=cn)，然后保存该模板，将其在 Journey Optimizer 的报告页面中使用。 |
| **无限量的客户维度和量度** | Customer Journey Analytics 维度是无限的；值可以是数字、文本、对象、列表或它们的组合。维度可以是嵌套的或分层的。<br/>根据对比度，Adobe Analytics 最多支持 75 个 prop 和 250 个 eVar。 |
| **无限量的唯一值** | Customer Journey Analytics 不限制可以在单个维度上报告的唯一值或维度项目的数量。<p> [维度上没有基数限制](/help/components/dimensions/high-cardinality.md)，允许任何唯一值出现并被计算。</p><p>这种方法消除了大规模 Adobe Analytics 实施中可能存在的报告和分析限制，从而产生 [!UICONTROL 低流量] 标签。</p><p>在 Customer Journey Analytics 中，可能会看到[!UICONTROL 已超出唯一值限制]的标签，但此类标签出现的频率远低于以往，并可通过对数据应用区段来加以缓解。</p> |

## 完全支持 Adobe Analytics 功能/组件 {#full-support}

| Adobe Analytics 功能 | Customer Journey Analytics 支持说明 |
| --- | --- |
| **异常检测** | 全面支持 |
| **资产转移** | 全面支持 |
| **归因功能** | 全面支持 |
| **机器人检测** | [全面支持](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/bot-detection) |
| **计算量度** | 全面支持。传统 Analysis Workspace 中的任何现有计算量度都不会移植到 Customer Journey Analytics。 |
| **日程表事件** | 全面支持。日程表事件在 Workspace 中已作为[注释](/help/components/annotations/overview.md)实施。 |
| **CSV 下载** | 全面支持 |
| **自定义日程表** | 全面支持 |
| **日期比较** | 全面支持 |
| **日期范围** | 支持所有日期范围功能。 |
| **维度** | 全面支持。Customer Journey Analytics 使用 XDM 并支持无限的维度。Customer Journey Analytics 不依赖于传统 Adob&#x200B;e Analytics 的自定义 eVar 或 prop。 |
| **GDPR 删除** | 全面支持；请注意，现在与 [!UICONTROL Adobe Experience Platform] 一起处理 GDPR。Customer Journey Analytics 继承 [!UICONTROL Experience Platform] 对底层数据集所作的任何数据更改。 |
| **提升和置信度报告** | 通过[“试验”面板](/help/analysis-workspace/c-panels/experimentation.md)提供全面支持 |
| **列表变量/列表属性** | 全面支持。Customer Journey Analytics 使用 XDM 并支持无限的字符串数组，其使用方式与 listVars 类似。 |
| **促销 eVar** | 通过[绑定维度和绑定量度](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/component-settings/persistence)实现全面支持 |
| **量度** | 全面支持；Customer Journey Analytics 利用体验数据模型 (XDM)，支持无限量的量度，并且不会与 Adobe Analytics 的自定义成功事件绑定。我们已对 Adobe Analytics 中的一些标准量度名称进行了重命名，例如：“访客”=“人员”、“访问”=“会话”、“点击”=“事件”。 |
| **将项目、区段和计算量度从 Adobe Analytics 迁移到 Customer Journey Analytics** | 全面支持。 |
| **移动记分卡/仪表板** | 全面支持 |
| **面板** | 完全支持以下面板：空白面板、属性、自由形式、快速洞察以及下一个或上一个项目。 |
| **PDF 导出** | 全面支持 |
| **项目策划** | 全面支持 |
| **项目链接** | 全面支持 |
| **产品模板** | 包括[预建模板](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/templates/use-templates)和[公司模板](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/templates/create-templates#access-a-company-template)。 |
| **报告时处理** | 全面支持；Customer Journey Analytics 完全依赖于报告时处理。 |
| **报告 API 访问** | 全面支持；通过 [Customer Journey Analytics API](https://developer.adobe.com/cja-apis/docs/) 提供。 |
| **计划报告/项目** | 全面支持 |
| **区段** | 全面支持。在 Customer Journey Analytics 中，区段此前被称为&#x200B;*过滤器*。 |
| **流媒体收藏集** | 使用作为 Workspace 中的“同时观看媒体的人数”面板和“媒体播放耗时”面板一部分的 Analytics Source Connector 即可获取流媒体数据。 |
| **汇总级数据源** | 全面支持 |
| **虚拟报告包** | 全面支持。[数据视图](/help/data-views/create-dataview.md)是 Customer Journey Analytics 中对应于 Adobe Analytics 中报表包的概念。 |
| **虚拟报表包组件管理** | 全面支持。组件管理是数据视图功能的一部分。 |
| **设备、浏览器、反向链接、技术维度** | 支持基于 [Analytics Source Connector ](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/connectors/adobe-applications/analytics)的数据集和 WebSDK 生成的数据集。请参阅[关于通过 ADC 支持哪些 Analytics 变量的文档。](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics)如果您使用 Experience Platform Web SDK 数据收藏集，则当前不支持基于设备查找的设备和维度。计划在以后提供支持。要将设备和浏览器查找功能添加到 Web SDK 数据流，请参阅[本文档](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/configure) |

## 以新方式支持 {#new-support}

| 功能 | 注释 |
| --- | --- |
| **Advertising Cloud** | 您可以[收集 AMO ID 和 EF ID 的历史数据以用于 Customer Journey Analytics](https://experienceleague.adobe.com/zh-hans/docs/advertising/integrations/analytics/planning/rvars-to-evars)。 |
| **警报** | 在 Customer Journey Analytics 中[使用警报的过程](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)与在 Adobe Analytics 中使用警报的过程几乎相同。 <p>但是，由于 Customer Journey Analytics 中数据收集的时间，无法提供每小时警报。在 Customer Journey Analytics 中，可以将警报配置为每日、每周或每月。</p> |
| **Analytics for Target (A4T)** | [Adobe Customer Journey Analytics 和 Target 进行集成](https://experienceleague.adobe.com/zh-hans/docs/target/using/integrate/cja/target-reporting-in-cja)，为优化项目提供强大而又节省时间的分析工具。 |
| **受众发布** | 如果与 Adobe 的客户数据平台或 Journey Optimizer 产品一起获得许可即支持。[受众发布](/help/components/audiences/audiences-overview.md)将受众发送到 Experience Platform 中的 Real-time Customer Profile。 |
| **分类** | 查找数据集相当于 Adobe Analytics 中的分类功能。Analytics 中使用的分类可以通过分析分类源连接器导入到 Experience Platform 和 Customer Journey Analytics。查找数据集还可以直接上传到 Experience Platform 并在 Customer Journey Analytics 中提供。 |
| **分类规则生成器** | 支持在 Customer Journey Analytics 中使用[子字符串。](/help/data-views/component-settings/substring.md)在报告时使用字符串操作，而不使用查找数据集。 |
| **自定义会话长度** | 可通过数据视图中的[会话设置](../../data-views/create-dataview.md#session-settings)配置会话长度。有关详细信息，请参阅[会话设置](../../data-views/session-settings.md)。<br/>通过 Adobe Experience Platform Mobile SDK 支持处理移动后台事件。有关更多信息，请参阅[边缘网络的生命周期](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/)。 |
| **货币换算** | 在数据视图中[格式化量度组件](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/component-settings/format)的过程中支持。 |
| **客户属性** | 轮廓数据集相当于客户归因功能。轮廓数据集不会自动从 Experience Cloud 导入，必须先上传至 Experience Platform，才可在 Customer Journey Analytics 中使用。 |
| **数据馈送** | 数据集的第一代数据导出可通过[ Experience Platform 数据访问 API](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/data-access/api)以及[ Experience Platform 目标](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/ui/activate/export-datasets)实现。这些选项提供了事件/行级别的导出，可将收集或摄入的所有数据导出到 Experience Platform 数据湖中。后处理数据列不可用，因为后处理列是在查询时计算的。可通过报告导出帖子列。 |
| **Data Warehouse 报告** | [Customer Journey Analytics 全表导出](/help/analysis-workspace/export/export-cloud.md)从 Adobe Analytics 中的 Data Warehouse 报告演化而来，具有许多当今在 Data Warehouse 中不提供但经常有人要求提供的新功能。 |
| **登录、退出和花费时间维度和量度** | 受支持（现在“进入次数”和“退出次数”称为“会话启动次数”和“会话结束次数”），但计算方式略有不同。 |
| **eVar 持久性设置** | Customer Journey Analytics 中不再包括 eVar。但是，持久性设置现在是数据视图的一部分，且可用于所有维度。请记住，持久基于报告时处理，而不是数据收集处理。数据视图中的纬度集限制为 90 天最大持久性，不支持无限持久性。 |
| **地理分段维度** | [全面支持](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/configure) |
| **基于图形的拼合** | 通过 [基于图形的拼合](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/stitching/overview#graph-based-stitching)，您可以利用 [Adobe Experience Platform 身份标识服务](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/home) 中身份图的强大功能将数据集提升到其首选身份。 |
| **警报** | 在 Customer Journey Analytics 中使用[警报](/help/components/c-intelligent-alerts/intelligent-alerts.md)的过程与在 Adobe Analytics 中使用警报的过程几乎相同。但是，有一些[重要的不同之处](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-components/alerts/alerts-feature-comparison)。 |
| **IP 模糊处理** | 对于 Customer Journey Analytics 用户，在使用 Analytics 源连接器将 Adobe Analytics 数据导入 Customer Journey Analytics 时，Adobe Analytics 中应用的 IP 混淆设置会传递至 Customer Journey Analytics 数据中。您可以根据需要在 Adobe Analytics 中控制这些设置。<p>对于使用 Experience Platform Web SDK 将数据直接填充到 Platform 和 Customer Journey Analytics 中的 Customer Journey Analytics 客户。您可以使用 Platform 中的“数据收集数据准备”功能根据您公司的要求配置混淆 IP 地址的规则。 |
| **营销渠道** | 使用 Analytics Source Connector 时，“营销渠道”数据会通过该连接器流入 Customer Journey Analytics。在传统的 Adobe Analytics 中配置营销渠道规则，其中不支持某些规则。有关更多信息，请参阅 [Customer Journey Analytics 营销渠道](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels)。<br/>对于 WebSDK 实施，通过[派生字段](../../data-views/derived-fields/derived-fields.md)支持报告时营销渠道处理规则。 |
| **促销变量持久性** | 通过[绑定维度和绑定量度](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/component-settings/persistence)实现全面支持 |
| **量度去重** | 在数据视图中的量度上进行配置。量度去重是在人员级别或会话级别执行的，而非在数据集、数据视图或连接级别。 |
| **新会话与重复会话报表分析** | 此前是通过使用“访问次数”维度实现的。新会话与重复会话分析支持[最长 13 个月的回溯窗口](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases)。 |
| **处理规则、VISTA 规则、营销渠道处理规则** | 支持使用 Adobe Experience Platform 数据准备功能以及基于 WebSDK 的数据集和 Analytics Source Connector 的数据的[派生字段。](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/derived-fields) |
| **Products 变量** | 在 Experience Platform 中，用户可在数据集架构中使用对象数组满足此用例。在 Customer Journey Analytics 中，客户可使用任意数量的产品变量，而不像在 Adobe Analytics 中那样只能使用一个变量。 |
| **项目共享** | 仅在 Customer Journey Analytics 的用户之间支持项目共享功能 - 在 Customer Journey Analytics 与传统 Analysis Workspace 之间无项目共享。 |
| **实时报告** | Customer Journey Analytics 中的实时报告功能可以实时显示并更新 Analysis Workspace 的一个或多个面板中的数据和可视化图表。 |
| **Report Builder** | 通过一个新的 Office 365 Microsoft Excel 插件支持此功能。 |
| **用户权限/数据访问控制** | Customer Journey Analytics 区分 [Adobe Admin Console](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/administration/admin-tool-experience-cloud) 产品管理员、产品配置文件管理员和用户。只有产品管理员可以创建、更新和删除其他用户所创建的连接、项目、区段或计算量度。产品管理员和产品轮廓管理员均可编辑数据视图。对于创建计算量度、区段或注释等操作还有其他用户权限可用。 |
| **可视化图表** | 支持所有 Workspace 可视化。 |
| **跨设备/跨渠道拼合** | 支持包含身份标识信息的事件数据集。请参阅[拼合](../../stitching/overview.md)。 |

## 部分支持 {#partial}

| 功能 | 注释 |
| --- | --- |
| **Workspace 面板** | 全面支持空白面板、“归因”面板、“任意形状”面板和“快速洞察”面板。不支持“区段比较面板”和“Analytics for Target (A4T) 面板”。 |

## 没有支持，但有计划支持 {#planned}

| 功能 | 注释 |
| --- | --- |
| **交易 ID 数据源** | 有计划以后支持。 |

## 没有支持，尚未计划提供支持 {#not-planned}

| 功能 | 注释 |
| --- | --- |
| **Activity Map** | 尚未计划提供支持。 |
| **贡献分析** | 尚未计划提供支持。 |

## 永不支持 {#never}

* 使用跨设备合作的人员量度
* 触发因素
