---
title: Customer Journey Analytics 功能支持
description: 将 Customer Journey Analytics 功能与 Adobe Analytics 功能集进行比较。
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: ht
source-wordcount: '2034'
ht-degree: 100%

---

# Customer Journey Analytics 功能支持

下表列出了 Customer Journey Analytics 支持、部分支持或不支持 Adob&#x200B;e Analytics 中的哪些功能，以及 Adob&#x200B;e Analytics 中不支持或不提供 Customer Journey Analytics 的哪些功能。由于后续会向 Customer Journey Analytics 添加其他功能，因此这些列表会随着时间而发生变化。

## 全面支持的功能/组件 {#full-support}

| Adobe Analytics 功能 | 注释 |
| --- | --- |
| 异常检测 | 全面支持 |
| Attribution IQ | 全面支持 |
| 机器人检测 | [全面支持](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) |
| 计算量度 | 全面支持。传统 Analysis Workspace 中的任何现有计算量度都不会移植到 Customer Journey Analytics。 |
| 日程表事件 | 全面支持。日历事件在工作区中已作为[批注](/help/components/annotations/overview.md)实施。 |
| CSV 下载 | 全面支持 |
| 自定义日程表 | 全面支持 |
| 日期比较 | 全面支持 |
| 日期范围 | 支持所有日期范围功能。 |
| 维度 | 全面支持。Customer Journey Analytics 使用 XDM 并支持无限的维度。Customer Journey Analytics 不依赖于传统 Adob&#x200B;e Analytics 的自定义 eVar 或 prop。 |
| GDPR 删除 | 全面支持；请注意，现在与 [!UICONTROL Adobe Experience Platform] 一起处理 GDPR。Customer Journey Analytics 继承 [!UICONTROL Experience Platform] 对底层数据集所作的任何数据更改。 |
| 提升和置信度报告 | 通过[“试验”面板](/help/analysis-workspace/c-panels/experimentation.md)提供全面支持 |
| 列表变量/列表属性 | 全面支持。Customer Journey Analytics 使用 XDM 并支持无限的字符串数组，其使用方式与 listVars 类似。 |
| 促销 eVar | 通过[绑定维度和绑定量度](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension)提供全面支持 |
| 量度 | 全面支持；Customer Journey Analytics 利用体验数据模型 (XDM)，支持无限量的量度，并且不会与 Adobe Analytics 的自定义成功事件绑定。我们已对 Adobe Analytics 中的一些标准量度名称进行了重命名，例如：“访客”=“人员”、“访问”=“会话”、“点击”=“事件”。 |
| 将项目、筛选条件和计算量度从 Adobe Analytics 迁移到 Customer Journey Analytics | 全面支持。 |
| 移动记分卡/仪表板 | 全面支持 |
| 面板 | 全面支持空白面板、“归因”面板、“任意形状”面板和“快速分析”面板。 |
| PDF 导出 | 全面支持 |
| 项目策划 | 全面支持 |
| 项目链接 | 全面支持 |
| 报表时间处理 | 全面支持；Customer Journey Analytics 完全依赖于“报表时间处理”。 |
| 报告 API 访问 | 全面支持；通过 [Customer Journey Analytics API](https://developer.adobe.com/cja-apis/docs/) 提供。 |
| 计划报表/项目 | 全面支持 |
| 区段 | 全面支持。现在称为“筛选条件”- 请注意，传统 Analysis Workspace 中的任何现有区段都不会移植到 Customer Journey Analytics。 |
| 虚拟报表包 | 全面支持。现在称为[数据视图](/help/data-views/create-dataview.md)。 |
| 虚拟报表包组件管理 | 全面支持。现在是数据视图的一部分。 |
| 设备、浏览器、反向链接、技术维度 | 支持基于 [Analytics Source Connector ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)的数据集和 WebSDK 生成的数据集。请参阅[有关通过 ADC 支持哪些 Analytics 变量的文档](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=zh-Hans)。如果您使用 Experience Platform Web SDK 数据收集，则当前不支持基于设备查找的设备和维度。计划在以后提供支持。要将设备和浏览器查找功能添加到 Web SDK 数据流，请参阅[本文档](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html) |
| 流 Media Analytics | 使用作为 Workspace 中的“同时观看媒体的人数”面板和“媒体播放耗时”面板一部分的 Analytics Data Connector 即可获得媒体数据。 |

{style="table-layout:auto"}

## 以新方式支持 {#new-support}

| 功能 | 注释 |
| --- | --- |
| 受众发布 | 如果与 Adobe 的客户数据平台或 Journey Optimizer 产品一起获得许可即支持。[受众发布](/help/components/audiences/audiences-overview.md)将受众发送到 Experience Platform 中的 Real-time Customer Profile。 |
| 分类 | 现在称为“查找数据集”。Analytics 中使用的分类可以通过分析分类源连接器导入到 Experience Platform 和 Customer Journey Analytics。 查找数据集还可以直接上传到 Experience Platform 并在 Customer Journey Analytics 中提供。 |
| 分类规则生成器 | 支持在 Customer Journey Analytics 中使用[子字符串。](/help/data-views/component-settings/substring.md)在报告时使用字符串操作，而不使用查找数据集。 |
| 自定义会话长度 | 可通过数据视图中的[会话设置](../../data-views/create-dataview.md#session-settings)配置会话长度。有关详细信息，请参阅[会话设置](../../data-views/session-settings.md)。<br/>通过 Adobe Experience Platform Mobile SDK 支持处理移动后台事件。有关更多信息，请参阅[边缘网络的生命周期](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/)。 |
| 货币换算 | 在数据视图中[格式化量度组件](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html#currency)的过程中支持。 |
| 促销变量持久性 | 通过[绑定维度和绑定量度](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension)提供全面支持 |
| 客户属性 | 现在称为“个人资料数据集”，不自动从 Experience Cloud 导入它们，而是必须先上传到 Experience Platform，然后才能在 Customer Journey Analytics 中找到它们。 |
| 数据馈送 | 数据集的第一代数据导出可通过[ Experience Platform 数据访问 API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html)以及[ Experience Platform 目标](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html)实现。这些选项提供了事件/行级别的导出，可将收集或摄入的所有数据导出到 Experience Platform 数据湖中。后处理数据列不可用，因为后处理列是在查询时计算的。可通过报告导出帖子列。 |
| Data Warehouse 报表 | [Customer Journey Analytics 全表导出](/help/analysis-workspace/export/export-cloud.md)从 Adobe Analytics 中的 Data Warehouse 报表演化而来，具有许多当今在 Data Warehouse 中不提供但经常有人要求提供的新功能。 |
| 登录、退出和花费时间维度和量度 | 受支持（现在“进入次数”和“退出次数”称为“会话启动次数”和“会话结束次数”），但计算方式略有不同。 |
| eVar 持久性设置 | Customer Journey Analytics 中不再包括 eVar。但是，持久性设置现在是数据视图的一部分，且可用于所有维度。请记住，持久基于报告时处理，而不是数据收集处理。数据视图中的纬度集限制为 90 天最大持久性，不支持无限持久性。 |
| 归属地细分维度 | [全面支持](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hans) |
| IP 模糊处理 | 对于使用 Analytics Source Connector 将数据从 Adobe Analytics 填充到 Customer Journey Analytics 中的 Customer Journey Analytics 客户：Adobe Analytics 中应用的 IP 模糊设置会传送到您的 Customer Journey Analytics 数据。您可以根据需要在 Adobe Analytics 中控制这些设置。<p>对于使用 Experience Platform Web SDK 将数据直接填充到 Platform 和 Customer Journey Analytics 中的 Customer Journey Analytics 客户。您可以使用 Platform 中的“数据收集数据准备”功能根据您公司的要求配置混淆 IP 地址的规则。 |
| 营销渠道 | 使用 Analytics Source Connector 时，“营销渠道”数据会通过该连接器流入 Customer Journey Analytics。在传统的 Adobe Analytics 中配置营销渠道规则，其中不支持某些规则。有关更多信息，请参阅 [Customer Journey Analytics 营销渠道](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html)。<br/>对于 WebSDK 实施，通过[派生字段](../../data-views/derived-fields/derived-fields.md)支持报告时营销渠道处理规则。 |
| 量度去重 | 现在对数据视图中的量度配置此项。在人员或会话级别，而非数据集、数据视图或连接级别进行量度去重。 |
| 新会话与重复会话报告 | 以前使用“访问次数”维度实现。新会话与重复会话均支持 [13 个月的回溯时段](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html)。 |
| 处理规则、VISTA 规则、营销渠道处理规则 | 支持使用 Adobe Experience Platform 数据准备功能以及基于 WebSDK 的数据集和 Analytics Source Connector 的数据的[派生字段。](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html) |
| 产品变量 | 在 Experience Platform 中，用户可在数据集架构中使用对象数组满足此用例。在 Customer Journey Analytics 中，客户可使用任意数量的产品变量，而不像在 Adobe Analytics 中那样只能使用一个变量。 |
| 项目共享 | 仅在 Customer Journey Analytics 的用户之间支持项目共享功能 - 在 Customer Journey Analytics 与传统 Analysis Workspace 之间无项目共享。 |
| Report Builder | 通过一个新的 Office 365 Excel 插件支持此项。 |
| 用户权限/数据访问控制 | Customer Journey Analytics 区分 [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=zh-Hans) 产品管理员、产品配置文件管理员和用户。只有产品管理员可创建/更新/删除其他用户创建的连接、项目、筛选条件或计算量度，而产品管理员和产品配置文件管理员均可编辑数据视图。对于创建计算量度、筛选条件或注释等操作还有其他用户权限可用。 |
| 可视化图表 | 除地图可视化图表外，支持所有 Workspace 可视化图表。 |
| 跨设备/跨渠道拼接 | 支持直接包含标识信息的数据集（也称为“基于字段的”拼接）。尚不支持基于图形的拼接，但有计划以后支持。请参阅[拼接](../../stitching/overview.md)。 |

{style="table-layout:auto"}

## 部分支持 {#partial}

| 功能 | 注释 |
| --- | --- |
| 面板 | 全面支持空白面板、“归因”面板、“任意形状”面板和“快速分析”面板。不支持“区段比较面板”和“Analytics for Target (A4T) 面板”。 |
| Analytics for Target (A4T) | 目前处于测试阶段。通过 [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hans) 中的字段提供部分支持。有计划在 Target 活动和体验上支持适合 A4T 的名称。 |

{style="table-layout:auto"}

## 没有支持，但有计划支持 {#planned}

| 功能 | 注释 |
| --- | --- |
| 警报 | 有计划以后支持。 |
| 贡献分析 | 有计划以后支持。 |
| 通过设备图形进行 ID 拼接 | 有计划以后支持。 |
| 项目模板 | 有计划以后支持。 |
| 实时报表 | 有计划以后支持。 |
| 区段 IQ | 有计划以后支持。 |
| 交易 ID 数据源 | 有计划以后支持。 |
| 摘要级别数据源 | 有计划以后支持。 |

{style="table-layout:auto"}

## 没有支持，尚未计划提供支持 {#not-planned}

| 功能 | 注释 |
| --- | --- |
| Activity Map | 尚未计划提供支持。 |
| Advertising Cloud | 尚未计划提供支持。 |

{style="table-layout:auto"}

## 将永远不支持 {#never}

* 使用跨设备协作的人员量度

## Adobe Analytics 中不提供 Adob&#x200B;e Customer Journey Analytics 功能 {#cja-not-aa}

下表列出了 Customer Journey Analytics 中可用但 Adob&#x200B;e Analytics 不支持的功能。

| 功能 | 更多详细信息 |
| --- | --- |
| 能够组合数据集（例如 Adobe Analytics 报告包） | 通过 Customer Journey Analytics，可从多个报告包组合数据，如同它们是 Adobe Analytics 中的单个报告包一样。 |
| 适用于任何类型的数据 | Customer Journey Analytics 与 Experience Platform 保存各种数据架构和类型的能力相结合。使用[体验数据模型 (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)，可以采用统一的方式来表示和组织数据，以便进行数据合并和分析。Adobe Analytics 主要专注于 Web 和移动分析数据，并具有一些[数据导入](https://experienceleague.adobe.com/docs/analytics/import/home.html)功能。 |
| 跨设备分析 | Customer Journey Analytics 支持来自未经身份验证和经过身份验证的会话的特定于设备的数据集的无缝组合。Customer Journey Analytics 可以将历史数据回填到已知设备。在 Analytics 中，此功能仅限于单个报告包和使用设备图时。 |
| 派生字段 | 通过派生字段，可为数据转换报告时间。可即时组合、更正或创建数据，并以追溯的方式将数据应用于所有报告。 |
| 增强了安全和隐私选项 - HIPAA 就绪 | Customer Journey Analytics 符合 HIPAA 标准，并提供额外的安全选项，以确保符合相关法规。Adobe Analytics 尚未为 HIPAA 做好准备。 |
| 试验分析 | Customer Journey Analytics 可以评估来自定义为连接一部分的任何数据源的任何试验的提升度和置信度。通过此评估，您可以了解跨约任何渠道的客户互动之间的因果关系。Analytics 仅限用于通过 A4T 进行的试验分析。 |
| 预测 | 预测是一种 AI/ML 功能，包括基于 Customer Journey Analytics 中已有的历史数据对时间序列相关数据进行统计预测。预测可以出现在自由格式的表格和折线图可视化中。 |
| 引导式分析 | 引导式分析是一种报告格式，它使用户可快速地自助满足其数据需求，以使其可快速地获得高质量见解并作出更加以数据为导向的决策。引导式分析是 Customer Journey Analytics 的附加组件 Adobe Product Analytics 的一部分。 |
| 智能题注 | 智能题注使用先进的机器学习和生成式 AI 为工作区可视化提供有价值的自然语言见解。初始版本为 [Line](/help/analysis-workspace/visualizations/line.md) 可视化提供了自动生成的见解。 |
| 报表时间转换 | 通过 Customer Journey Analytics 中的数据视图，可进一步解释从某个连接获得的数据。可不更改实施即更改或删除数据、使用子字符串操纵维度、从任意值创建量度或筛选子事件。以非破坏性的方式进行所有这些转换。Adobe Analytics 通过虚拟报表包和自定义会话长度提供有限的功能。 |
| SQL 访问 | 通过使用 Data Distiller 选项，Customer Journey Analytics 可以消除 Adob&#x200B;e 后端处理中收集的数据的限制。您可以使用 SQL 修改数据、创建适合您的业务的值和数据集，并继续探索。Analytics 不支持对其数据进行任何类型的 SQL 访问。 |
| 无限量的客户维度和量度 | Customer Journey Analytics 维度是无限的；值可以是数字、文本、对象、列表或它们的组合。维度可以是嵌套的或分层的。Analytics 最多支持 75 个 prop 和 250 个 eVar。 |
| 无限量的唯一值 | Customer Journey Analytics 不限制可以在单个维度上报告的唯一值或维度项目的数量。Adobe Analytics 仅限于 500.000 个唯一值。通过支持无限的唯一值或维度，消除了大规模分析实施中当前存在的报告和分析限制。 |

{style="table-layout:auto"}
