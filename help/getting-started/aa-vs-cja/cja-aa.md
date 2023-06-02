---
title: Customer Journey Analytics 功能支持
description: 将 Customer Journey Analytics 功能与 Adobe Analytics 功能集进行比较。
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 683ac8b741ed73eb301364331cebf187c8c91cd2
workflow-type: tm+mt
source-wordcount: '1953'
ht-degree: 54%

---

# Customer Journey Analytics 功能支持

下表列出了Adobe Analytics (AA)中部分支持、部分支持或不支持Customer Journey Analytics (CJA)的功能，以及AA中不支持或不提供CJA的功能。 由于后续会向 CJA 添加其他功能，因此这些列表会随着时间而发生变化。

## 全面支持的功能/组件 {#full-support}

| Adobe Analytics 功能 | 注释 |
| --- | --- |
| 异常检测 | 全面支持 |
| Attribution IQ | 全面支持 |
| 计算度量 | 全面支持。传统Analysis Workspace中的任何现有计算量度都不会移植到CJA。 |
| 日历事件 | 全面支持。日历事件在工作区中已作为[批注](/help/components/annotations/overview.md)实施。 |
| CSV 下载 | 全面支持 |
| 自定义日历 | 全面支持 |
| 日期比较 | 全面支持 |
| 日期范围 | 支持所有日期范围功能。 |
| 维度 | 全面支持。CJA使用XDM并支持无限量的维度。 CJA 未绑定到传统 Adobe Analytics 的自定义 eVar 或 prop。 |
| 删除 GDPR | 全面支持；请注意，GDPR 现在与 [!UICONTROL Adobe Experience Platform] 协调处理。CJA 继承 [!UICONTROL Experience Platform] 对底层数据集所作的任何数据更改。 |
| 提升和置信度报表 | 通过[“试验”面板](/help/analysis-workspace/c-panels/experimentation.md)提供全面支持 |
| 列表变量/列表属性 | 全面支持。CJA使用XDM并支持无限量的与listVars具有类似用法的字符串数组。 |
| 促销 eVar | 通过[绑定维度和绑定度量](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=zh-Hans#binding-dimension)提供全面支持 |
| 度量 | 全面支持；CJA使用体验数据模型(XDM)，支持无限量的量度，并且不会与传统Analytics的自定义成功事件绑定。 已重命名传统Analytics中的一些标准量度：访客=人员，访问=会话，点击=事件。 |
| 移动记分卡/仪表板 | 全面支持 |
| 面板 | 全面支持空白面板、“归因”面板、“任意形状”面板和“快速分析”面板。 |
| PDF 导出 | 全面支持 |
| 项目策划 | 全面支持 |
| 项目链接 | 全面支持 |
| 报表时间处理 | 全面支持；CJA 完全依赖于报表时间处理。 |
| 报表 API 访问 | 全面支持；通过 [CJA API](https://developer.adobe.com/cja-apis/docs/) 提供。 |
| 计划报表/项目 | 全面支持 |
| 区段 | 全面支持。现在称为“过滤器” — 请注意，传统Analysis Workspace中的任何现有区段都不会移植到CJA。 |
| 虚拟报告包 | 全面支持。现在称为[数据视图](/help/data-views/create-dataview.md)。 |
| 虚拟报表包组件管理 | 全面支持。现在是“数据视图”的一部分。 |
| 流 Media Analytics | 使用作为 Workspace 中的“同时观看媒体的人数”面板和“媒体播放耗时”面板一部分的 Analytics Data Connector 即可获得媒体数据。 |

{style="table-layout:auto"}

## 以新方式支持 {#new-support}

| 功能 | 注释 |
| --- | --- |
| 受众发布（区段发布） | 如果与 Adobe 的客户数据平台或 Journey Optimizer 产品一起获得许可即支持。[受众发布](/help/components/audiences/audiences-overview.md)将受众发送到 Experience Platform 中的 Real-time Customer Profile。 |
| 分类 | 现在称为“查找数据集”。Analytics 中使用的分类可以通过分析分类源连接器导入到 Experience Platform 和 CJA。 查找数据集也可以直接上传到Experience Platform并在CJA中可用。 |
| 分类规则生成器 | 通过 CJA 中的[子字符串](/help/data-views/component-settings/substring.md)支持。在报表时使用字符串操作，而不使用查找数据集。 |
| 自定义会话流程 | 支持除移动后台事件之外的所有自定义会话流程功能。 |
| 促销变量持久性 | 通过[绑定维度和绑定度量](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=zh-Hans#binding-dimension)提供全面支持 |
| 客户属性 | 现在称为“配置文件数据集”，它们不会自动从Experience Cloud导入，但必须先上传到Experience Platform，然后才能在CJA中使用。 |
| 数据馈送 | 数据集的第一代数据导出可通过 [Experience Platform数据访问API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=en) 和至 [Experience Platform目标](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en). 这些选项提供收集或摄取到Experience Platform数据湖中的所有数据的事件/行级别导出。 后处理数据列不可用，因为后处理列是在查询时计算的。 可通过报告导出后置列。 |
| 度量去重 | 现在对数据视图中的度量配置此项。在人员或会话级别，而非数据集、数据视图或连接级别进行度量去重。 |
| 登录、退出和花费时间维度和度量 | 受支持（现在“进入次数”和“退出次数”称为“会话启动次数”和“会话结束次数”），但计算方式略有不同。 |
| eVar 持久性设置 | eVar 不再是 CJA 的一部分。但是，持久性设置现在是数据视图的一部分，且可用于所有维度。请记住，持久基于报表时间处理，而不是数据收集处理。数据视图中设置的Dimension限制为90天的最大持久性，不支持无限持久性。 |
| IP 模糊处理 | 使用 Analytics Source Connector 将数据从 Adobe Analytics 填充到 CJA 中的 CJA 客户：Adobe Analytics 中应用的 IP 混淆设置将流入您的 CJA 数据中。您可以根据需要在 Adobe Analytics 中控制这些设置。<p>适用于使用Experience PlatformWeb SDK将数据直接填充到Platform和CJA中的CJA客户。 您可以在Platform中使用数据收集的数据准备来配置规则，这些规则将根据贵公司的要求对IP地址进行模糊处理。 |
| 新会话报表与重复会话报表 | 以前使用“访问次数”维度实现。新会话与重复会话均支持 [13 个月的回溯时段](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=zh-Hans)。 |
| 产品变量 | 在该 Experience Platform 中，用户可以在数据集架构中使用“对象”类型字段的数组来满足此用例。在CJA中，客户可以使用任意数量的产品变量，而不限于Adobe Analytics中的单个变量。 |
| 项目共享 | 仅支持在 CJA 用户之间共享项目，不支持 CJA 与传统分析工作区之间共享项目。 |
| 可视化图表 | 除地图可视化图表外，支持所有可视化图表。 |
| Report Builder（Excel 插件） | 通过 Office 365 中的新 Excel 插件支持。 |
| 用户权限/数据访问控制 | CJA 区分 [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=zh-Hans) 产品管理员、产品配置文件管理员和用户。只有产品管理员可创建/更新/删除由其他用户创建的连接、项目、过滤器或计算度量，而产品管理员和产品配置文件管理员可编辑数据视图。其他用户权限可用于创建计算量度、过滤器或注释等。 |
| 处理规则、VISTA 规则、营销渠道处理规则 | 对基于WebSDK的数据集和Analytics Data Connector的数据使用Adobe Experience Platform数据准备功能时支持。 |
| 营销渠道 | 使用Analytics Source Connector时，营销渠道数据通过该连接器流入CJA。 营销渠道规则是在传统Adobe Analytics中配置的，某些规则不受支持。 有关更多详细信息，请参阅 [CJA 营销渠道文档](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html)。<br/>对于WebSDK实施，通过以下方式支持报表时间营销渠道处理规则 [派生字段](../../data-views/derived-fields/derived-fields.md). |

{style="table-layout:auto"}

## 部分支持 {#partial}

| 功能 | 注释 |
| --- | --- |
| 跨设备/跨渠道拼接 | 支持直接包含标识信息的数据集（也称为“基于字段的”拼接）。尚不支持基于图形的拼接，但已规划。请参阅[跨渠道分析](/help/cca/overview.md)。 |
| 机器人筛选 | 对于基于 [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hans) 的数据集，将应用机器人筛选。[!UICONTROL Experience Platform] 或 CJA 不会对其他数据集应用常规机器人筛选逻辑。 |
| 设备、浏览器、反向链接、技术维度 | 对于基于 [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hans) 的数据集支持。请参阅 [关于通过ADC支持哪些Analytics变量的文档](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=zh-Hans).<p>如果您使用Experience PlatformWeb SDK数据收集，则当前不支持基于设备查找的设备与维度。 有计划以后支持。 |
| 地理分段维度 | 收集到 Adobe Analytics 的所有地理分段/地理位置通过 [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hans) 流入 CJA。不使用Analytics Source Connector但依赖Experience PlatformWeb SDK进行数字数据收集的实施，可以使用 [Experience Edge地理位置查找服务](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hans). |
| 面板 | 全面支持空白面板、“归因”面板、“任意形状”面板和“快速分析”面板。不支持“区段比较面板”和“Analytics for Target (A4T) 面板”。 |
| 处理规则 | 对于基于 Analytics Source Connector 的数据集，仍会应用处理规则。[Adobe Experience Platform 中的数据准备功能](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hans)也可以取代处理将直接进入 Platform 的数据的规则。 |
| A4T | 通过 [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hans) 中的字段提供部分支持。有计划在 Target 活动和体验上支持适合 A4T 的名称。 |

{style="table-layout:auto"}

## 不支持，但已计划 {#planned}

| 功能 | 注释 |
| --- | --- |
| 警报 | 有计划要支持。 |
| 贡献分析 | 有计划要支持。 |
| Data Warehouse 报告 | 计划从分析工作区界面提供支持。Adobe Experience Platform [[!UICONTROL 查询服务]](<https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=zh-Hans>)还为 CJA 中的这些用例提供接口。 |
| 通过设备图形进行 ID 拼接 | 有计划要支持。 |
| 项目模板 | 有计划要支持。 |
| 实时报告 | 有计划要支持。 |
| 区段 IQ | 有计划要支持。 |
| 货币换算 | 有计划要支持。 |
| 交易 ID 数据源 | 有计划要支持。 |
| 将项目/过滤器/计算度量从 AA 迁移到 CJA | 有计划要支持。 |
| 摘要级别数据源 | 有计划要支持。 |

{style="table-layout:auto"}

## 无支持，尚未计划 {#not-planned}

| 功能 | 注释 |
| --- | --- |
| Activity Map | 尚未计划提供支持。 |
| Advertising Cloud | 尚未计划提供支持。 |

{style="table-layout:auto"}

## 从不支持 {#never}

* 使用跨设备协作的人员度量
* Reports &amp; Analytics 功能板
* Reports &amp; Analytics 书签
* Reports &amp; Analytics 目标

## CJA功能在Adobe Analytics中不可用 {#cja-not-aa}

下表列出了Customer Journey Analytics (CJA)中可用，但Adobe Analytics (AA)中不支持的功能。

| 功能 | 更多详细信息 |
| --- | --- |
| 为任何类型的数据提供方便 | CJA与Experience Platform保存各种数据架构和类型的能力相结合。 使用 [体验数据模型(XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hans)、可以采用统一的方式来表示和组织数据，以便进行数据合并和分析。 Adobe Analytics主要关注Web和移动分析数据，并具有以下功能： [导入数据](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=zh-Hans). |
| 无限制的客户Dimension和量度 | CJA维度无限制；值可以是数字、文本、对象、列表或所有这些的混合。 Dimension可以嵌套或分层。 Analytics最多支持75个prop和250个eVar。 |
| 无限基数/唯一值 | CJA支持可以在单个维度中报告的无限唯一值或维度项目。 AA限制为500.000个唯一值。 无限的唯一值或维度删除了大规模Analytics实施当前存在的报表和分析限制。 |
| 报表时间转换 | CJA中的报告时间转换（更名为数据视图）允许您进一步解释来自连接的数据。 您可以更改或删除数据，而无需重新实施；使用子字符串处理维度；从任何值创建量度；筛选子事件。 而转型都是非破坏性的。 Adobe Analytics通过虚拟报表包和会话流程提供有限的功能。 |
| 试验分析 | CJA可以从定义为连接一部分的任何数据源评估任何试验的提升和置信度。 通过此评估，您可以了解跨任何渠道的客户交互之间的因果关系。 Analytics仅限于通过Analytics for Target (A4T)集成进行试验分析。 |
| 跨设备分析 | CJA支持来自未经身份验证和经过身份验证的会话的设备特定数据集的无缝组合。 CJA提供将历史数据回填到已知设备的功能。 在Analytics中，此功能仅限于单个报表包以及设备图的使用。 |
| SQL访问 | 通过使用Data Distiller选项，CJA可以删除在Adobe后端处理中收集的数据的限制。 您可以使用SQL修改数据，创建特定于业务的值和数据集，并继续探索。 Analytics不支持对其数据进行任何类型的SQL访问。 |
| 增强的安全性和隐私选项 — HIPAA准备工作 | CJA已符合HIPAA要求，并为法规合规提供了其他安全选项。 Adobe Analytics未就绪。 |

{style="table-layout:auto"}
