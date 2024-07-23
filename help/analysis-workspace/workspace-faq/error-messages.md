---
description: 了解 Adobe Analysis Workspace 及其相关组件中的错误消息
title: Analysis Workspace 中的常见错误消息
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
source-git-commit: fe089afb2022d8c4b50346bb81d6ba4ad6404014
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 66%

---

# 常见错误消息

当您与 Analysis Workspace 交互时，可能会遇到错误，这也会影响性能。下面列出了最常见的错误类型、发生原因以及优化方案。

| 错误消息 | 为什么出现此错误？ | 优化 |
| --- | --- | --- |
| [!UICONTROL 数据视图正在经历异常繁重的报告。请稍后重试。] | 您的组织针对特定数据视图尝试运行的并发请求过多。 导致此错误的因素包括：API 请求、计划项目、计划报告、计划警报，以及提出报告请求的并发用户数量。 | 在一天中更均匀地分布数据视图的请求和计划。<p>管理员可以使用[报告活动管理器识别并取消占用报告容量的请求](/help/reporting-activity-manager/reporting-activity-overview.md)。</p> |
| [!UICONTROL 这份报告太复杂了。请查看构建 Analysis Workspace 报告的最佳实践。] | 您的报告请求过大，无法执行。导致此错误的因素是由于请求的复杂性而导致的超时。 | 通过缩短日期范围、简化筛选条件或删除表中的某些列或行来简化请求。 或者，考虑将表拆分为单独的请求。 |
| [!UICONTROL 数据视图目前已超出其报告容量。请简化请求或稍后重试。] | 您的组织针对特定数据视图尝试运行的并发请求过多。 导致此错误的因素包括：API请求、计划项目，以及提出报表请求的并发用户。 | 在一天中更均匀地分布数据视图的请求和计划。 |
| [!UICONTROL 发生系统错误。请在&#x200B;**[!UICONTROL 帮助 > 提交支持票证]**&#x200B;下记录一条客户关怀团队请求，并将您的错误代码包含在内。] | Adobe 遇到了一个需要解决的问题。 | 将错误代码提交给客户关怀团队。 |
| [!UICONTROL 错误 500：无法加载页面] | 本地网络的问题（如公司[防火墙设置](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=zh-hans)），是引发该错误的一个因素。此外，Adobe 可能遇到了需要解决的问题。 | 请在几分钟后再次尝试登录。如果问题仍然存在，请向客户关怀团队提交 EIM 实例 ID 代码。 |
| [!UICONTROL 由于列或预配置行过多，导致请求失败。] | 表格中自由格式单元格（行数乘以列数）过多。 | 移除表格中的列或行，或考虑将表格拆分为单独的请求。 |
