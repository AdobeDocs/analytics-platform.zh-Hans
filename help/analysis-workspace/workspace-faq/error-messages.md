---
description: Analysis Workspace及其相关组件中错误消息的列表
title: 错误消息
translation-type: tm+mt
source-git-commit: a991dce6abaf90cbca06de75606a2517cb5b6484
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 35%

---


# 错误消息

您在与Analysis Workspace交互时可能会遇到错误，这也会影响性能。 下面列出了最常见的错误类型、发生原因以及可进行的优化。

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html) 略有不同。[了解更多...](/help/getting-started/cja-aa.md)

| 错误消息 | 为什么出现此错误？ | 优化 |
| --- | --- | --- |
| [!UICONTROL 发生系统错误。 请在 **[!UICONTROL “帮助”>“提交支持票证”]** 并包含错误代码。] | Adobe 遇到了一个需要解决的问题。 | 将错误代码提交给客户关怀。 |
| [!UICONTROL 错误500:无法加载页面] | 本地网络的问题，如公司 [防火墙设置](https://docs.adobe.com/content/help/en/analytics/technotes/ip-addresses.html)，是导致此错误的一个因素。 此外，Adobe可能遇到需要解决的问题。 | 几分钟后再次尝试登录。 如果问题仍然存在，请向客户关怀部门提交EIM实例ID代码。 |
| [!UICONTROL 此可视化中的一个区段或搜索包含返回过多结果的文本搜索。] | 您的细分条件或报表筛选器过于宽泛。 | 缩小搜索文本条件并重试请求。 |
| [!UICONTROL 报表包的报告过于繁重。请稍后重试。] | 您的组织针对特定报表包尝试运行的并发请求过多。导致此错误的因素包括：API 请求、计划项目、计划报表、计划警报，以及提出报表请求的并发用户数量。 | 将您的报表包请求和计划分布在一天中更均匀。 |
| [!UICONTROL 请求太复杂。] | 您的报表请求过大，无法执行。导致此错误的因素包括：因请求的大小、区段或搜索过滤器中的匹配项过多、包含的量度过多、维度与量度组合不兼容等原因而导致的各种超时。 | 通过删除表中的某些列或行来简化请求，或考虑将表拆分为单独的请求。 |
| [!UICONTROL 此维度当前不支持非默认归因模型。] | 您所使用的维不支持非默认属性。 | 用与 [Attribution IQ](/help/analysis-workspace/attribution/overview.md). |
| [!UICONTROL 由于列或预配置行过多，您的请求失败。] | 表中的自由格式单元格太多（行*列）。 | 删除表中的列或行，或考虑将表拆分为单独的请求。 |