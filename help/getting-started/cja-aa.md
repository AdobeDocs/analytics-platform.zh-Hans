---
title: Customer Journey Analytics 功能支持
description: 将 Customer Journey Analytics 功能与 Adobe Analytics 功能集进行比较。
translation-type: tm+mt
source-git-commit: d14817f28e757e94435c3b1059765fabe7cec54b
workflow-type: tm+mt
source-wordcount: '986'
ht-degree: 87%

---


# Customer Journey Analytics 功能支持

下表列出了 Customer Journey Analytics (CJA) 完全支持、部分支持或不支持 Adobe Analytics 中的功能。由于后续会向 CJA 添加其他功能，因此这些列表会随着时间而发生变化。

## 完全支持的功能/组件

| 功能 | 注释 |
| --- | --- |
| 量度 | CJA 利用体验数据模型 (XDM) 并支持无限量的量度，同时不会与传统 Analytics 的自定义成功事件绑定。请注意，已对传统 Analytics 中的一些标准量度名称进行了重命名，例如：“访客”=“人员”、“访问”=“会话”、“点击”=“事件”。 |
| 维度 | CJA 利用 XDM 并支持无限量的维度，同时不会与传统 Analytics 的自定义成功事件绑定。 |
| 列表变量/列表 Prop | CJA 利用 XDM 并支持无限量的列表变量 |
| 日期范围 | 计划将会提供自定义日历支持。 |
| 计算量度 | 请注意，传统 Analysis Workspace 中的任何现有计算量度都不会移植到 CJA。 |
| 区段 | 现在称为“过滤器” - 请注意，传统 Analysis Workspace 中的任何现有区段都不会移植到 CJA。 |
| 异常检测 | 完全支持 |
| 归因 IQ | 完全支持 |
| 项目策划 | 完全支持 |
| 项目链接 | 完全支持 |
| 日期比较 | 完全支持 |
| 虚拟报表包 | 现在称为[数据视图](/help/data-views/create-dataview.md)。 |
| VRS 组件策划 | 现在是“数据视图”的一部分。 |
| 报表时间处理 | CJA 完全依赖于报表时间处理。 |
| 删除 GDPR | 请注意，GDPR现在与[!UICONTROL Adobe Experience Platform]协调处理- CJA继承[!UICONTROL Experience Platform]对基础数据集所做的任何数据更改。 |
| 用户权限/数据访问控制 | CJA 区分 Adobe Admin Console 产品管理员和用户。只有产品管理员才能 1) 创建/更新/删除连接或数据视图，2) 更新/删除其他用户创建的项目、过滤器或计算量度，以及 3) 将工作区项目共享给所有用户 |

## 受支持，但有注意事项

| 功能 | 注释 |
| --- | --- |
| 产品变量 | 当前可用于报表数据的产品变量符合体验报告架构（特别是使用 productListItems 的对象）。 |
| 营销渠道 | 营销渠道数据现在通过Analytics Data Connector流入CJA。 营销渠道规则仍必须在传统的Adobe Analytics中进行配置。 某些规则不受支持。 有关详细信息，请参阅[CJA营销渠道文档](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=en#cja-usecases)。 |
| 可视化图表 | 除地图可视化图表外，支持所有可视化图表。 |
| 项目共享 | 仅支持在 CJA 用户之间共享项目 - 不支持 CJA 与传统 Analysis Workspace 之间共享项目。 |
| 自定义会话流程 | 支持除移动后台点击之外的所有自定义会话流程功能。 |
| eVar 持久性设置 | eVar 不再是 CJA 的一部分。但是，持久性设置现在是数据视图的一部分，且可用于所有维度。请记住，持久基于报表时间处理，而不是数据收集处理。这意味着，所有持久性都将基于报表日期范围，而不是整个数据。 |
| 分类 | 现在称为“查找数据集”，它们不会从传统的 Analytics 中自动导入。必须先将它们上传到 AEP，然后才能在 CJA 中使用。 |
| 客户属性 | 现在称为“用户档案数据集”，它们不会从 Experience Cloud 中自动导入，必须先将其上传到 AEP，然后才能在 CJA 中使用。 |
| 设备、浏览器、技术维度 | 当AEP数据集包含特定XDM模式字段并符合XDM体验事件类时，这些维度会自动包含。 |
| 条目、退出和时间限制维度和指标 | 支持(现在“条目”和“退出”称为“会话开始”和“会话结束”)，计算方式略有不同。 |

## 部分支持

| 功能 | 注释 |
| --- | --- |
| 开箱即用的 Analysis Workspace 维度（例如，浏览器类型、反向链接类型、营销渠道、访问次数等） | CJA 本身不提供这些维度。对于使用 Analytics Data Connector (ADC) 的客户，其中部分维度可用，但不是全部维度都可用。请参阅我们的[关于通过 ADC 支持哪些 Analytics 变量的文档](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md)。 |
| 面板 | 完全支持“空白面板”、“归因面板”、“快速分析面板”。不支持“区段比较”面板、“Analytics for Target (A4T)”面板和“媒体并发查看者”面板。 |
| 促销 eVar | 除非它们严格符合相同的 XDM 架构，否则促销 eVar 将只能用于基于 ADC 的数据集，（与上述产品列表限制相似）。 |
| 机器人过滤 | 对于基于 Analytics Data Connector (ADC) 的数据集，会应用机器人过滤。[!UICONTROL Experience Platform] 或 CJA 不会对其他数据集应用常规机器人过滤逻辑。 |
| 处理规则 | 对于基于 ADC 的数据集，仍会应用处理规则。 |
| 跨设备身份拼合 | 客户只能通过查询服务对数据进行“一次性”拼合，或者，目前必须在摄取 [!UICONTROL Experience Platform] 数据之前将此逻辑应用于数据。 |

## 目前不支持，但计划将会提供支持

| 功能 | 注释 |
| --- | --- |
| 贡献分析 | 计划将会提供支持。 |
| 区段 IQ | 计划将会提供支持。 |
| 区段发布（将区段从工作区发送到 Experience Cloud） | 计划将会提供支持。 |
| CSV 下载 | 计划将会提供支持。 |
| 量度去重 | 计划将会提供支持。 |
| 自定义日历 | 计划将会提供支持。 |
| 量度去重 | 计划将会提供支持。 |
| 销售变量持久性 | 计划将会提供支持。 |
| 计划报表/项目 | 计划将会提供支持。 |
| 警报 | 计划将会提供支持。 |
| 自定义日历 | 计划将会提供支持。 |
| PDF 导出 | 计划将会提供支持。 |
| 报表 API 访问 | 计划将会提供支持 - 将仅适用于 API 2.0。 |
| 通过设备图形进行 ID 拼合 | 计划将会提供支持。 |
| Report Builder（Excel 插件） | 计划将会提供支持。 |
| 实时报告 | 计划将会提供支持。 |

## 尚未计划提供支持

| 功能 | 注释 |
| --- | --- |
| A4T | 尚未计划提供支持。 |
| Media Analytics | 尚未计划提供支持。 |
| Advertising Cloud | 尚未计划提供支持。 |
| Activity Map | 尚未计划提供支持。 |
| 分类规则生成器 | 尚未计划提供支持。 |
| 概要数据源 | 尚未计划提供支持。 |

## 将永远不支持

* 使用跨设备协作的人员量度
* Reports &amp; Analytics 功能板
* Reports &amp; Analytics 书签
* Reports &amp; Analytics 目标
* Reports &amp; Analytics 日历事件
* Ad Hoc Analysis
* Data Warehouse 报表 - [!UICONTROL Experience Platform 查询服务]将成为 CJA 中这些用例的新接口。
* Mobile Services
* 数据馈送
