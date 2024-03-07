---
title: Customer Journey Analytics护栏
description: 了解用于Customer Journey Analytics的护栏
solution: Customer Journey Analytics
feature: Administration
role: Admin
exl-id: f093ac54-7d31-449b-a441-a65856a1d535
source-git-commit: d6837178bccc1a80130ec3fc282d2b44858d06b1
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 8%

---

# Customer Journey Analytics护栏

本文档对Customer Journey Analytics的各个组件进行了限制。 有关护栏、范围参数和权限，请参阅 [Customer Journey Analytics的产品描述](https://helpx.adobe.com/cn/legal/product-descriptions/customer-journey-analytics.html) 或 [Adobe Analytics加载项的产品描述：Customer Journey Analytics](https://helpx.adobe.com/cn/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html).

## 限制类型

此文档有两种类型的默认限制：

| 护栏类型 | 描述 |
|----------|---------|
| **性能护栏（软限制）** | Performance Guardrails是与用例范围相关的使用限制。 当超出性能护栏时，您可能会遇到性能下降和延迟问题。 Adobe不对此类性能下降负责。 始终超过性能护栏的客户可以选择许可额外的容量，以避免性能下降。 |
| **系统强制的护栏（硬限制）** | Customer Journey AnalyticsUI或API强制实施系统强制的护栏。 这些限制不得超过，因为UI和API会阻止您这样做或返回错误。 |

{style="table-layout:auto"}

某些功能及其关联限制值取决于您有权访问的Customer Journey Analytics包。

>[!NOTE]
>
>根据产品中的不断改进，本文档中概述的值可能会发生更改。 请定期查看以获取最新信息。 如果您有兴趣了解自定义限制，请联系您的客户关怀代表。

## 临时SQL查询

| 名称 | 值 | 限制类型 | 描述 |
|---|--:|---|---|
| 重试超时 | 90 | 系统强制的护栏 | 报告引擎作出响应时，如果请求返回结果所花费的时间过长（可能由于其他同时进行的请求），则返回结果所耗的最大秒数；可以再次请求。 |
| 不要重试超时 | 600 | 系统强制的护栏 | 临时SQL查询超时前的最大秒数。 否则，报告引擎报告请求返回结果所花费的时间过长，不应重试之前的最大秒数。 由于后台进程中的问题，请求很可能从不返回结果。 |
| 量度 | 150 | 系统强制的护栏 | 请求中的最大量度数。 |
| 交互式查询输出行 | 50,000 | 系统强制的护栏 | 除非另有指定，否则返回的默认行数。 |

{style="table-layout:auto"}

## Analysis Workspace项目

| 名称 | 值 | 限制类型 | 描述 |
|---|--:|---|---|
| 每个表的可见行数 | 400 | 系统强制的护栏 | Analysis Workspace项目中任何自由格式表中的最大可见行数。 |
| 每个表的可导出行数 | 50,000 | 系统强制的护栏 | 每个维度可导出的最大行数。 |
| 每个项目的面板数 | 15 | 系统强制的护栏 | 最大数量 [面板](../analysis-workspace/home.md#panels) 每个项目。 |
| 每个面板的可视化图表 | 25 | 系统强制的护栏 | 最大数量 [可视化图表](../analysis-workspace/home.md#visualizations) 每个面板。 |
| 每个自由格式表的派生字段 | 5 | 系统强制的护栏 | 单个自由格式表中不同派生字段的最大数量。 |

{style="table-layout:auto"}

<!--
## Attribution AI

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Attribution AI models | 35 | Maximum number of Attribution AI Model per year to analyze the impact of up to an average of 60 independent touchpoints on a specified conversion event.  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Region based iterations | 10 | Maximum number of region-based iterations of each Attribution AI model. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  | 
| Export Insights batches | 12 | Maximum number of export batches times the number of authorized Attribution AI Insights per year. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) | 

{style="table-layout:auto"}
-->

## 受众

| 名称 | 值 | 限制类型 | 描述 |
|---|--:|---|---|
| 受众筛选器 | 20 | 系统强制的护栏 | 最大数量 [过滤器](../components/filters/filters-overview.md) 每个受众。 |
| 受众标识数量 | 2000万 | 系统强制的护栏 | 每个受众的最大身份数。 |
| 受众刷新频率 | 4 | 系统强制的护栏 | 最大频率（小时an） [受众](../components/audiences/audiences-overview.md) 可能更新。 |
| 受众刷新回顾窗口 | 90 | 系统强制的护栏 | 刷新回顾时间范围的最大天数。 |
| 刷新受众过期日期 | 13 | 系统强制的护栏 | 受众从创建日期起停止刷新的最大月数。 客户可以将其延长13个月。 |
| 刷新受众的数量 | 75， 100 | 系统强制的护栏 | 刷新受众的最大数量，该值因包而异（请参阅产品描述）。 |

{style="table-layout:auto"}

另请参阅Experience Platform [Real-time Customer Data Platform护栏](https://experienceleague.adobe.com/docs/experience-platform/profile/guardrails.html?lang=en).


## 自动数据集过期

| 名称 | 值 | 限制类型 | 描述 |
|---|--:|---|:---:|
| 工作单 | 20 | 系统强制的护栏 | 每月自动数据集到期工作单的最大数量。 |

{style="table-layout:auto"}



## 连接、数据视图、项目

| 名称 | 值 | 限制类型 | 描述 |
|---|--:|---|---|
| 项目 | 2,000 | 系统强制的护栏 | 组织的最大项目数。 |
| 数据视图 | 2,000 | 系统强制的护栏 | 最大数量 [数据视图](../data-views/data-views.md) 对于组织。 |
| 数据视图 | 50 | 系统强制的护栏 | 连接的最大数据视图数 |
| 数据集 | 100 | 系统强制的护栏 | 最大数量 [数据集](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=en) 每个连接。 |
| 连接 | 1000 | 系统强制的护栏 | 最大数量 [连接](../connections/overview.md) 对于组织。 |
| 连接标题 | 500 | 系统强制的护栏 | 连接标题的最大字符数。 |
| 量度 | 5,000 | 系统强制的护栏 | 数据视图中的最大量度数。 |
| 维度 | 5,000 | 系统强制的护栏 | 数据视图中的最大维度数。 |
| 批注标题 | 100 | 系统强制的护栏 | 批注标题的最大字符数。 |
| 注释描述 | 250 | 系统强制的护栏 | 注释描述的最大字符数。 |
| 架构字段 | 10 | 系统强制的护栏 | 为定义规则时架构字段的最大数量（不包括标准字段） [派生字段](../data-views/derived-fields/derived-fields.md). |
| 查找/配置文件字段 | 3 | 系统强制的护栏 | 定义派生字段的规则时，架构字段（不包括标准字段）最大数量内的查找或配置文件架构字段的最大数量。 |
| 派生字段 | 100 | 系统强制的护栏 | 每个连接的最大派生字段数。 |

{style="table-layout:auto"}


## 数据传输限制

| 名称 | 值 | 限制类型 | 描述 |
|---|--:|---|---|
| 字段 | 10,000 | 系统强制的护栏 | 数据集中每行属性或字段的最大数量。 |
| 唯一字符串 | 1000万 | 系统强制的护栏 | 每个查找数据集的最大唯一键数。 |
| 行 | 100万 | 系统强制的护栏 | 连接中每个唯一人员ID的最大行数。 |
| 行大小 | 2 | 性能护栏/系统强制的护栏 | 引入Customer Journey Analytics的每行数据的平均大小（以KB为单位）（软限制）。 行大小的静态限制由Experience Platform中用于数据摄取的护栏决定。 |

{style="table-layout:auto"}

另请参阅Experience Platform [数据引入的护栏](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html?lang=en).


## 数据登陆区

| 名称 | 值 | 限制类型 | 描述 |
|---|--:|---|---|
| 每个沙盒的数据登陆区 | 1 | 系统强制的护栏 | 每个沙盒的最大数据登陆区域数。 |
| 数据存储 | 7 | 系统强制的护栏 | 数据在被删除之前存储在数据登陆区的最大天数。 |

{style="table-layout:auto"}


## 基于字段的拼合

| 名称 | 值 | 限制类型 | 描述 |
|---|--:|---|---|
| 拼接数据集 | 10 | 系统强制的护栏 | 每位客户的最大拼接数据集数，该值因适用的Customer Journey Analytics包而异（请参阅适用的产品描述）。 |
| 回填数据 | 60 | 系统强制的护栏 | 回填数据的最大天数。 |

{style="table-layout:auto"}


## 过滤器和计算量度

| 名称 | 值 | 限制类型 | 描述 |
|---|--:|---|---|
| 每个过滤器的容器 | 50 | 系统强制的护栏 | 每个过滤器的最大容器数。 |
| 每个计算量度的量度 | 25 | 系统强制的护栏 | 每个计算量度的最大量度数。 |
| 每个过滤器的量度和Dimension | 25 | 系统强制的护栏 | 每个过滤器的唯一量度和维度的最大数量。 |
| 每个过滤器的嵌套容器 | 10 | 系统强制的护栏 | 每个过滤器的嵌套容器的最大数量。 |
| 每个过滤器的规则 | 100 | 系统强制的护栏 | 每个过滤器的最大规则数。 |
| 每个过滤器每个Dimension的字符串比较数 | 100 | 系统强制的护栏 | 每个过滤器每个维度的最大字符串比较数。 |
| 计算量度 | 6,000 | 系统强制的护栏 | 组织的最大计算量度数。 |
| 过滤器 | 50,000 | 系统强制的护栏 | 可为组织定义的最大过滤器数。 |
| API 调用 | 120 | 系统强制的护栏 | 每分钟API请求数（每6秒12个请求）。 |

{style="table-layout:auto"}


## 移动应用程序

| 名称 | 值 | 限制类型 | 描述 |
|---|--:|---|---|
| 磁贴 | 16 | 系统强制的护栏 | 每个记分卡的最大磁贴数。 |
| 过滤器 | 10 | 系统强制的护栏 | 每个记分卡的最大过滤器数。 |
| 维度 | 10 | 系统强制的护栏 | 每个记分卡的最大维度数。 |

{style="table-layout:auto"}

## Report Builder

| 名称 | 值 | 限制类型 | 描述 |
|---|--:|---|---|
| 工作簿文件大小 | 5 | 系统强制的护栏 | 计划工作簿的最大文件大小（以MB为单位）。 |
| 数据块 | 1000 | 系统强制的护栏 | 最大数量 [个数据块](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html?lang=en) 每个工作簿。 |
| 量度 | 20 | 系统强制的护栏 | 每个数据块的最大量度数。 |
| 日期范围 | 13 | 系统强制的护栏 | 日期范围可跨每个数据块的最大月数。 |
| 行 | 50,000 | 系统强制的护栏 | 每个数据块的最大行数。 |

{style="table-layout:auto"}


## 整个表导出

| 名称 | 值 | 限制类型 | 描述 |
|---|--:|---|---|
| 每个报告的行数 | 300万 — 3亿 | 系统强制的护栏 | 每个报表的最大报表行数；该值因适用的Customer Journey Analytics包而异（请参阅适用的产品描述）。 |
| 每个表的细分 | 5 | 系统强制的护栏 | 每个表的最大划分数。 |
| 每个表的量度 | 5 | 系统强制的护栏 | 每个表的最大量度数。 |
| 计划频率 | 1 | 系统强制的护栏 | 导出可以安排在一天中执行一次(1)，也可以安排更长的导出时间（例如：每2天执行一次，或每周执行一次）。 |

{style="table-layout:auto"}

## 延迟

>[!NOTE]
>
>以下处理时间是护栏，而不是合同服务级别协议(SLA)。 滞后时间因客户配置、数据卷和使用者应用程序而异。 实际处理时间通常更快。 请参阅您的Customer Journey Analytics合同，以了解具体的合同条款和SLA。 请参阅Experience Platform [数据引入的护栏](https://experienceleague.adobe.com/docs/experience-platform/ingestion/Guardrails.html?lang=en) 以了解更多信息。

| 数据流 | 预期延迟 |
|---|---|
| Adobe Analytics到Adobe Analytics源连接器（已启用A4T） | &lt; 30分钟 |
| Adobe Analytics Source Connector to Real-time Customer Profile（未启用A4T） | &lt; 2分钟 |
| Adobe Analytics Source Connector到Real-time Customer Profile（启用A4T） | &lt; 30分钟 |
| 数据从Edge Network引入数据湖或流式引入 | &lt; 60分钟 |
| 从Adobe Analytics Source Connector将数据摄取到数据湖 | &lt; 2.25小时 |
| 数据从数据湖摄取到Customer Journey Analytics | &lt; 90分钟 |
| 拼合(可选功能，请参阅 [拼接概述](../stitching/overview.md) 了解更多信息) | &lt; 3.25小时 |
| 少于100亿个事件的Adobe Analytics源连接器回填（最多13个月的历史数据） | &lt; 4周 |
| 将受众发布到实时客户个人资料，包括自动创建流区段，并允许区段准备好接收数据。 | ≈ 60分钟 |
| 刷新受众的频率 | 一次性刷新：少于5分钟的延迟。<br/>每4小时、每天、每周、每月刷新一次（延迟与刷新率密切相关）。 |

{style="table-layout:auto"}
