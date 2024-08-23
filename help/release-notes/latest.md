---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 3b5877ff515147964c2d4fbd6eaa43a8a99f0fe0
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 100%

---

# 当前 Adobe Customer Journey Analytics 发行说明（2024 年 8 月）

**最后更新**: 2024 年 8 月 14 日

这些发行说明涵盖了 2024 年 8 月 14 日至 2024 年 9 月的发布期。Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **摘要级别数据源** | 允许您引入没有人员 ID 的时间序列数据。该时间序列数据可用于支持各种用例，例如：<ul><li>将高级性能指标作为事件级数据的一部分或在其旁边呈现。这可以包括诸如日期和单个指标值之类的简单内容，也可以包括多个维度和指标，例如广告展示、电子邮件打开、广告支出、销售成本等。</li><li>以小时或每天的频率上传目标或目的,然后将这些目标或目的与事件级量度进行对比。这有助于可视化指标相对于组织目标的趋势。</li></ul><p>欲了解更多信息，请参阅[汇总数据](/help/data-views/summary-data.md).</p> | 2024 年 8 月 13 日 | 2024 年 8 月 21 日 |
| **Audiences 已发布到 Experience Platform 中的新“Audiences”部分** | 从 Customer Journey Analytics 中发布的受众现在可以在 Adobe Experience Platform 的新“受众”部分中找到。<p>此前，从 Customer Journey Analytics 发布的受众可在 Experience Platform 的“细分”部分下找到。</p><p>此改进具有以下优点：</p><ul><li>受众出现在 Experience Platform 前不再有 1 小时的延迟；它们在发布后几秒钟即可使用。</li><li>可以使用 Experience Platform 中“来源”列对受众进行排序，该列显示了最初发布受众的应用程序。</li><li>Experience Platform 中的筛选条件和排序选项使您能够更快地找到相关受众。</li></ul> <p>有关详细信息，请参阅文章[“创建和发布受众”](/help/components/audiences/publish.md)中的[“在 Experience Platform 中使用 Customer Journey Analytics 受众”](/help/components/audiences/publish.md#use-customer-journey-analytics-audiences-in-experience-platform)。</p> | 2024 年 9 月 | 2024 年 9 月 |
| **智能警报** | Customer Journey Analytics 中的智能警报允许您在数据中出现异常事件时立即收到通知。<p>您可以设置根据异常阈值、变化的百分比或特定数据点触发的警报。警报提供与异常检测集成的细粒度控制，在您最需要时触发。</p><p>在 Customer Journey Analytics 中使用智能警报的过程与在 Adobe Analytics 中使用智能警报的过程几乎相同。一个主要的区别是 Customer Journey Analytics 不提供每小时警报。这种差异是因为，各种事件数据摄取只能在延迟之后才能完成，通常是数据事件时间之后的 3 到 9 个小时。</p><p>（已更新的文档链接见下文）</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | 待定 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-354359; AN-351646; AN-346873; AN-352504; AN-353755; AN-354199; AN-354268; AN-354791; AN-354598; AN-354462; AN-354547;

## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 | | |

{style="table-layout:auto"}

## 相关资源

* [之前的 2024 Customer Journey Analytics 发行说明](/help/release-notes/2024.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)
* [流媒体收藏集附加组件发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
