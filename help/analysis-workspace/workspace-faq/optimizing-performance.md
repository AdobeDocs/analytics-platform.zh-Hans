---
description: 'null'
title: 优化 Analysis Workspace 性能
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 98%

---


# 优化 Analysis Workspace 性能

>[!NOTE] 您正在查看Customer Journey Analytics中的Analysis Workspace文档。 其功能集与传统Adobe [Analytics的Analysis Workspace略有不同](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html)。 [了解更多...](/help/getting-started/cja-aa.md)

某些因素可能影响 Analysis Workspace 内的项目性能。开始构建项目之前，请务必了解这些因素的具体情况，以便您能够以最佳方式计划和构建项目。下面是一个将会影响性能的因素列表以及优化项目的最佳实践。Analysis Workspace 性能是 Adobe 最优先考虑的事项之一，也是我们每天都在持续改进的对象。

## 区段逻辑的复杂性

复杂的区段可能会对项目性能产生重大影响。增加区段复杂性的因素（按影响程度降序排列）包括：

* 运算符：“包含”、“包含任意”、“匹配”、“开始于”或“结束于”
* 连续分段，尤其是使用维度限制（之内/之后）时的连续分段
* 维度内区段中使用的唯一维度项目数（例如，在 Page = &#39;A&#39; 的情况下，页面具有 10 个唯一项目的查询速度将比页面具有 100,000 个唯一项目的查询速度更快）
* 使用的不同维度的数量（例如，Page = &#39;Home&#39; 和 Page = &#39;Search results&#39; 的查询速度将比 eVar 1 =&#39;red&#39; 和 eVar 2 =&#39;blue&#39; 更快）)
* 许多“或”运算符（而不是“和”）
* 嵌套容器的范围不同（例如，“访客”中“访问次数”内的“点击”）

**逻辑复杂性的最佳实践**

虽然某些复杂因素无法避免，但应想办法降低区段的复杂性。通常，您的区段标准越具体，其性能就越好。例如：

* 对于容器，使用区段顶部的单个容器的速度将比使用一系列嵌套容器的速度更快。
* 对于运算符，“等于”比“包含”运算速度快，“等于任意”比“包含任意”运算速度快。
* 对于许多标准，使用“和”运算符的速度将比使用一系列“或”运算符的速度更快。此外，寻找机会将许多 OR 语句简化为单个“等于任意”语句。

此外，使用[分类](https://docs.adobe.com/content/help/zh-Hans/analytics/components/classifications/c-classifications.html)可帮助将众多值整合到简洁的组中，您随后可以从这些组创建区段。与含有许多 OR 语句或“包含”标准的区段相比，按分类组划分区段可提供更佳的性能。

## 请求的数据范围

在整个项目中请求的数据范围将影响 Analysis Workspace 性能。

**数据范围的最佳实践**

请尽量不要获取超过需求的数据。

请记住，日期范围（紫色组件）会覆盖面板日期范围。因此，如果您使用不同的日期范围作为列（例如，“上月”、“上周”和“昨天”列），则面板日期范围无需跨所有的列日期范围。可以只将其设置为昨天，因为在自由格式表中使用的数据范围将覆盖面板。有关在 Analysis Workspace 中使用日期范围的更多信息，请观看[此视频](https://www.youtube.com/watch?v=ybmv6EBmhn0)。

使用[日期比较选项](/help/components/date-ranges/time-comparison.md)获取要比较的特定时间段的数据。例如，如果您需要显示上个月与去年同月份的数据比较，则不必将面板设置为最近 13 个月的数据，而只需使用比较时间段选项来显示年同比性能。

## 可视化图表数量

一个项目中包含的图形可视化图表数量将影响 Analysis Workspace 的整体响应性。

**可视化图表数量的最佳实践**

减少项目中的可视化图表数量。Analysis Workspace 对您添加的每个可视化图表都执行了大量幕后处理工作，因此请优先考虑对报表客户最为重要的可视化图表，并在需要时将支持的可视化图表划分到更加详细的单独项目中。

## 可视化图表的复杂性（区段、量度、过滤器）

自行添加到项目中的可视化图表类型（例如，流失和自由格式表）不会对项目性能有太大影响。可视化图表的复杂性会增加处理时间。导致可视化图表复杂性增加的因素包括：

* 请求的数据范围，如上所述
* 应用的区段数量；例如，用作自由格式表行的区段
* 使用复杂区段
* 自由格式表中的静态项目行或列
* 应用于自由格式表行的过滤器
* 包含的量度数量，尤其是使用区段的计算量度

**可视化图表复杂性的最佳实践**

如果您注意到项目没有按所需的速度加载，请尽量尝试将某些区段替换为 eVar 和过滤器。

如果您发现自己正在不断地将一些区段和计算量度用于对业务非常重要的数据点，请考虑改进您的实施以便更直接地捕获这些数据点。使用 Adobe Experience Platform Launch 等标记管理器和 Adobe 处理规则，可以快速地对实施进行更改并方便地进行实施。要深入了解如何简化复杂区段，请参阅上面的“区段逻辑的复杂性”。

## 面板数量

一个面板可以包含许多可视化图表，因此，面板的数量也会影响 Analysis Workspace 的整体响应性。

**面板数量的最佳实践**

请不要尝试将所有内容都添加到一个项目中，而是应创建用于特定目的或利益相关者组的不同项目。可使用标记将项目组织为关键主题，并与利益相关者组共享相关项目。

如果需要组织更多项目，请记住，可以选择[直接关联](https://www.youtube.com/watch?v=6IOEewflG2U)到您的项目。可创建项目的内部索引，以便利益相关者能够更轻松地找到所需内容。

如果一个工作区中需要许多面板，请先折叠面板，然后再进行保存和共享。加载项目时，Analysis Workspace 将只加载已展开面板的内容。折叠的面板只有等到用户展开它们后才会加载。此方法有以下两大好处：

* 折叠的面板可节省项目的整体加载时间
* 折叠的面板能够很好地以一种逻辑方式为报表客户组织项目

## 报表包大小

报表包的大小看起来像是一种驱动因素，但实际上，它因 Adobe 处理数据的方式，而只在项目性能中起到很小的作用

## 同时访问 Analysis Workspace 的人数

如果用户访问不同的报表包，则同时访问 Analysis Workspace 或特定项目的用户数量不会对 Analysis Workspace 性能产生重大影响。如果用户同时访问同一报表包，则性能将受到影响。

## Analysis Workspace 中的常见错误消息

在与 Analysis Workspace 交互时，可能会遇到错误。导致错误的原因有多种，下面列出了最常见的原因。

| 错误消息 | 为什么出现此错误？ |
|---|---|
| `The report suite is experiencing unusually heavy reporting. Please try again later.` | 您的组织针对特定报表包尝试运行的并发请求过多。导致此错误的因素包括：API 请求、计划项目、计划报表、计划警报，以及提出报表请求的并发用户数量。我们建议您将报表包的请求和计划比较均匀地分散到一整天里。 |
| `A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.` | Adobe 遇到了一个需要解决的问题。我们建议您通过“客户关怀”请求提交错误代码。 |
| `The request is too complex.` | 您的报表请求过大，无法执行。导致此错误的因素包括：因请求的大小、区段或搜索过滤器中的匹配项过多、包含的量度过多、维度与量度组合不兼容等原因而导致的各种超时。我们建议简化您的请求。 |
| `One of the segments or the search in this visualization contains a text search that returned too many results.` | 我们建议缩小搜索文本标准并再次尝试请求。 |
| `This dimension does not currently support non-default attribution models.` | 我们建议将表格中的维度替换为与[归因 IQ](../attribution/overview.md) 兼容的维度。 |
| `Your request failed as a result of too many columns or pre-configured rows.` | 我们建议移除一些列或行，或者考虑将它们拆分为单独的可视化图表。 |
