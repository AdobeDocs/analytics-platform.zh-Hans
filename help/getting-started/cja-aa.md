---
title: Customer Journey Analytics 功能支持
description: 将 Customer Journey Analytics 功能与 Adobe Analytics 功能集进行比较。
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: ab44c58a4089a5a48ad845579fb536f668d9f9f6
workflow-type: tm+mt
source-wordcount: '1440'
ht-degree: 98%

---

# Customer Journey Analytics 功能支持

下表列出了 Customer Journey Analytics (CJA) 全面支持、部分支持或不支持的 Adobe Analytics 功能。由于后续会向 CJA 添加其他功能，因此这些列表会随着时间而发生变化。

## 全面支持的功能/组件

| Adobe Analytics 功能 | 注释 |
| --- | --- |
| 异常检测 | 全面支持 |
| Attribution IQ | 全面支持 |
| 受众发布 | 全面支持. 在AA中称为区段发布(将区段从工作区发送到Experience Cloud)。 [受众发布](/help/components/audiences/audiences-overview.md) 将受众发送到experience Platform中的实时客户资料。 |
| 计算量度 | 全面支持；请注意，传统 Analysis Workspace 中的任何现有计算量度都不会移植到 CJA。 |
| 日历事件 | 全面支持. 日历事件已实施为 [批注](/help/components/annotations/overview.md) 中。 |
| 分类规则生成器 | Full support. 已调用 [子字符串](/help/data-views/component-settings/substring.md) 在CJA中。在报表时使用字符串操作，而不是查找数据集。 |
| 跨设备/跨渠道拼接 | 全面支持；请参阅[跨渠道分析](/help/connections/cca/overview.md)。 |
| CSV 下载 | 全面支持 |
| 自定义日历 | 全面支持 |
| 日期比较 | 全面支持 |
| 日期范围 | 支持所有日期范围功能。 |
| 夏令时 | 全面支持 |
| 设备、浏览器、反向链接、技术维度 | 当 AEP 数据集包含特定 XDM 架构字段并符合 XDM Experience Event 类要求时，将自动包含这些维度。请参阅我们的[关于通过 ADC 支持哪些 Analytics 变量的文档](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=zh-Hans)。<p>如果您未使用 Adobe Source Connector 将数据从 Adobe Analytics 填充到 CJA 中，而是使用 Experience Platform Web SDK 数据收集，则当前不支持基于设备查找的设备和维度。不久的将来将支持它们。 |
| 维度 | 全面支持；CJA 利用 XDM 并支持无限维度。CJA 未绑定到传统 Adobe Analytics 的自定义 eVar 或 prop。 |
| 删除 GDPR | 全面支持；请注意，GDPR 现在与 [!UICONTROL Adobe Experience Platform] 协调处理。CJA 继承 [!UICONTROL Experience Platform] 对底层数据集所作的任何数据更改。 |
| 列表变量/列表属性 | 全面支持；CJA 利用 XDM 并支持无限量的与 listVar 具有类似用法的字符串数组。 |
| 促销变量持久性 | 通过[绑定维度和绑定量度](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension)提供全面支持 |
| 促销 eVar | 通过[绑定维度和绑定量度](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension)提供全面支持 |
| 量度 | 全面支持；CJA 利用体验数据模型 (XDM)，支持无限量的量度，并且不会与传统 Analytics 的自定义成功事件绑定。请注意，已对传统 Analytics 中的一些标准量度名称进行了重命名，例如：“访客”=“人员”、“访问”=“会话”、“点击”=“事件”。 |
| 量度去重 | 全面支持 |
| 移动记分卡/仪表板 | 全面支持 |
| 面板 | 全面支持空白面板、“归因”面板、“任意形状”面板和“快速分析”面板。 |
| PDF 导出 | 全面支持 |
| 项目策划 | 全面支持 |
| 项目链接 | 全面支持 |
| Report Builder（Excel 插件） | 全面支持 |
| 报表时间处理 | 全面支持；CJA 完全依赖于报表时间处理。 |
| 报表 API 访问 | 全面支持；通过 [CJA API](https://www.adobe.io/cja-apis/docs/) 提供。 |
| 计划报表/项目 | 全面支持 |
| 区段 | 全面支持；现在称为“过滤器”- 请注意，传统 Analysis Workspace 中的任何现有区段都不会移植到 CJA。 |
| 用户权限/数据访问控制 | 全面支持；CJA 区分 [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=zh-Hans) 产品管理员和用户。仅产品管理员可以 <ul><li>创建/更新/删除连接或数据视图</li><li>更新/删除由其他用户创建的项目、过滤器或计算量度，并且</li><li>将 Workspace 项目共享给所有用户。</li></ul> |
| 虚拟报表包 | 全面支持；现在称为[数据视图](/help/data-views/create-dataview.md)。 |
| VRS 组件管理 | 全面支持；现在是数据视图的一部分。 |

{style=&quot;table-layout:auto&quot;}

## 受支持，但有注意事项

| 功能 | 注释 |
| --- | --- |
| A4T | 通过 [Adobe Analytics 源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)中的字段提供支持。 |
| 分类 | 现在称为“查找数据集”。Analytics 中使用的分类可以使用 Analytics Classifications Data Connector 导入 Experience Platform 和 CJA。查找数据集也可以直接上传到 AEP 并在 CJA 中可用。 |
| 自定义会话流程 | 支持除移动后台点击之外的所有自定义会话流程功能。 |
| 客户属性 | 现在称为“个人资料数据集”，它们不会从 Experience Cloud 自动导入，而是必须先上传到 AEP，然后才可在 CJA 中使用。 |
| [!UICONTROL 设备]、[!UICONTROL 浏览器]、[!UICONTROL 反向链接]、[!UICONTROL 技术]维度 | 当 AEP 数据集包含特定 XDM 架构字段并符合 XDM Experience Event 类要求时，将自动包含这些维度。请参阅我们的文档，[了解通过 Analytics Source Connector 哪些 Analytics 变量受支持](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html)。对于未使用 Source Connector 将数据从 Adobe Analytics 填充到 CJA 中，而是使用 AEP Web SDK 数据收集的 CJA 客户，当前不支持基于设备查找的[!UICONTROL 设备]和维度，但将在不久的将来支持。 |
| 登录、退出和花费时间维度和量度 | 受支持（现在“进入次数”和“退出次数”称为“会话启动次数”和“会话结束次数”），但计算方式略有不同。 |
| eVar 持久性设置 | eVar 不再是 CJA 的一部分。但是，持久性设置现在是数据视图的一部分，且可用于所有维度。请记住，持久基于报表时间处理，而不是数据收集处理。数据视图中的纬度集限制为 90 天最大持久性，不支持无限持久性。 |
| 地理分段维度 | 收集到 Adobe Analytics 的所有地理分段/地理位置通过 [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html) 流入 CJA。不使用 Analytics Source Connector 的实施（例如，依赖于 AEP Web SDK 进行数字数据收集的实施）不会自动执行全面的地理查找：支持国家和美国州，不支持城市和邮政编码。目前对美国以外的州/区域的支持有限或不支持。 |
| 营销渠道 | 营销渠道数据通过 Analytics Data Connector 流入 CJA。营销渠道规则仍必须在传统的 Adobe Analytics 中进行配置。某些规则不受支持。有关更多详细信息，请参阅 [CJA 营销渠道文档](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html#cja-usecases)。 |
| 产品变量 | 在该 Experience Platform 中，用户可以在数据集架构中使用“对象”类型字段的数组来满足此用例。在 CJA 内，客户能够使用任意数量的产品变量，不像在 Adobe Analytics 中一样仅限使用单个变量。 |
| 项目共享 | 仅支持在 CJA 用户之间共享项目，不支持 CJA 与传统 Analysis Workspace 之间共享项目。 |
| 可视化图表 | 除地图可视化图表外，支持所有可视化图表。 |

{style=&quot;table-layout:auto&quot;}

## 部分支持

| 功能 | 注释 |
| --- | --- |
| 机器人筛选 | 对于基于 [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html) 的数据集，将应用机器人筛选。[!UICONTROL Experience Platform] 或 CJA 不会对其他数据集应用常规机器人筛选逻辑。 |
| 面板 | 全面支持空白面板、“归因”面板、“任意形状”面板和“快速分析”面板。不支持“区段比较”面板、“Analytics for Target (A4T)”面板和“媒体并发查看者”面板。 |
| 处理规则 | 对于基于 Analytics Data Connector 的数据集，仍会应用处理规则。[Adobe Experience Platform 中的数据准备功能](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html)也可以取代处理将直接进入 Platform 的数据的规则。 |
| 流媒体分析 | 媒体数据可作为 [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html) 的一部分提供。 |

{style=&quot;table-layout:auto&quot;}

## 目前不支持，但计划将会提供支持

| 功能 | 注释 |
| --- | --- |
| 警报 | 计划将会提供支持。 |
| 贡献分析 | 计划将会提供支持。 |
| Data Warehouse 报告（100% 行导出） | 计划从 Analysis Workspace 界面提供支持。Adobe Experience Platform [[!UICONTROL 查询服务]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=zh-Hans)还为 CJA 中的这些用例提供接口。 |
| 通过设备图形进行 ID 拼合 | 计划将会提供支持。 |
| 提升和置信度报告 | 计划将会提供支持。 |
| 处理规则、VISTA 规则、营销渠道处理规则 | 计划将会提供支持，但将在查询时而不是在数据收集期间工作，以实现更灵活、可追溯和非破坏性的数据操作。 |
| 项目模板 | 计划将会提供支持。 |
| 实时报告 | 计划将会提供支持。 |
| 区段 IQ | 计划将会提供支持。 |
| 新的与重复的会话报告 | 计划将会提供支持，但有一些注意事项。 |

{style=&quot;table-layout:auto&quot;}

## 尚未计划提供支持

| 功能 | 注释 |
| --- | --- |
| Activity Map | 尚未计划提供支持。 |
| Advertising Cloud | 尚未计划提供支持。 |
| 货币换算 | 尚未计划提供支持。 |
| 数据馈送 | 尚未计划提供支持。 |
| 概要数据源 | 尚未计划提供支持。 |
| 交易 ID 数据源 | 尚未计划提供支持。 |

{style=&quot;table-layout:auto&quot;}

## 将永远不支持

* 使用跨设备协作的人员量度
* Reports &amp; Analytics 功能板
* Reports &amp; Analytics 书签
* Reports &amp; Analytics 目标
* Mobile Services
