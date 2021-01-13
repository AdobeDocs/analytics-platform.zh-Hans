---
description: Adobe Analysis Workspace 及其相关组件中的错误消息列表
title: Analysis Workspace 中的常见错误消息
translation-type: tm+mt
source-git-commit: 7f6afbb7c0376791c286021d9ffe4ac670ed7bd7
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 100%

---


# 常见错误消息

当您与 Analysis Workspace 交互时，可能会遇到错误，这也会影响性能。下面列出了最常见的错误类型、发生原因以及优化方案。

| 错误消息 | 为什么出现此错误？ | 优化 |
| --- | --- | --- |
| [!UICONTROL 发生系统错误。请在&#x200B;**[!UICONTROL 帮助 > 提交支持票证]**&#x200B;下记录一条客户关怀团队请求，并将您的错误代码包含在内。] | Adobe 遇到了一个需要解决的问题。 | 将错误代码提交给客户关怀团队。 |
| [!UICONTROL 错误 500：无法加载页面] | 本地网络的问题（如公司[防火墙设置](https://docs.adobe.com/content/help/zh-Hans/analytics/technotes/ip-addresses.html)），是引发该错误的一个因素。此外，Adobe 可能遇到了需要解决的问题。 | 请在几分钟后再次尝试登录。如果问题仍然存在，请向客户关怀团队提交 EIM 实例 ID 代码。 |
| [!UICONTROL 此可视化图表中的一个区段或搜索，包含返回了大量结果的文本搜索。] | 您设定的区段标准或报表过滤器过于宽泛。 | 应缩小搜索文本标准，然后重试请求。 |
| [!UICONTROL 报表包的报告过于繁重。请稍后重试。] | 您的组织针对特定报表包尝试运行的并发请求过多。导致此错误的因素包括：API 请求、计划项目、计划报表、计划警报，以及提出报表请求的并发用户数量。 | 将报表包的请求和计划较为均匀地分布在一天当中。 |
| [!UICONTROL 请求过于复杂。] | 您的报表请求过大，无法执行。导致此错误的因素包括：因请求的大小、区段或搜索过滤器中的匹配项过多、包含的量度过多、维度与量度组合不兼容等原因而导致的各种超时。 | 通过删除表中的某些列或行来简化请求，或者考虑将表拆分为单独的请求。 |
| [!UICONTROL 此维度当前不支持非默认归因模型。] | 您使用的维度不支持非默认归因。 | 将表格中的维度替换为[归因 IQ](/help/analysis-workspace/attribution/overview.md) 兼容的维度。 |
| [!UICONTROL 由于列或预配置行过多，导致请求失败。] | 表格中自由格式单元格（行数乘以列数）过多。 | 移除表格中的列或行，或考虑将表格拆分为单独的请求。 |

