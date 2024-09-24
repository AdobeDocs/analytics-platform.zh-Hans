---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a07823d3671c683ec30cf1be4efc542b2b1b29d9
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 100%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2024 年 9 月）

**上次更新日期**：2024 年 9 月 11 日

这些发行说明涵盖 2024 年 9 月 11 日至 2024 年 10 月初的发行期。Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **计算量度管理器和过滤管理器中“用于”列中的附加信息** | 计算量度管理器和过滤管理器中的“用于”列包含以下新的报告区域：<ul><li>**Report Builder：**&#x200B;显示 Report Builder 中正在使用的计算量度或过滤器的数量。</li><li>**临时组件：**&#x200B;显示项目中使用的临时计算量度或临时过滤器的数量。这些临时的计算量度和过滤器（也称为“快速计算量度”和“快速过滤器”）只能在创建它们的项目中使用，因此它们在“用于”列中的“项目”报告区域中是分开报告的。</li></ul>有关更多信息，请参阅 [计算量度管理器](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager) 和 [过滤器管理器](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-components/cja-filters/manage-filters)。 |  | 2024 年 9 月 11 日 |
| **警报** | Customer Journey Analytics 中的警报允许您根据变化的百分比或特定数据点收到通知。<p>根据您的 Customer Journey Analytics 包，您还可以使用基于异常阈值触发的警报。这些警报（也称为“智能警报”）提供与异常检测集成的细粒度控制，在您最需要时触发。</p><p>在 Customer Journey Analytics 中使用警报的过程与在 Adobe Analytics 中使用警报的过程几乎相同。一个主要的区别是 Customer Journey Analytics 不提供每小时警报。这种差异是因为，各种事件数据摄取只能在延迟之后才能完成，通常是数据事件时间之后的 3 到 9 个小时。</p><p>有关使用 Adobe Analytics 的 Customer Journey Analytics 中的警报时的差异的更多信息，请参阅 [警报功能比较](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)。</p><p>要了解有关警报的更多信息，请参阅[警报概述](/help/components/c-intelligent-alerts/intelligent-alerts.md)。 |  | 2024 年 9 月 13 日 |
| **Adobe Analytics Source Connector 的更新** | 由于 Analytics Source Connector 完全由 Adobe 管理，因此数据集活动页面不会显示有关批次的信息。您可以通过查看与引入的记录相关的量度来监控数据流动的情况。请阅读有关 [创建 Analytics 数据的源连接](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)的指南以了解更多信息。 |  | 现在可用 |
| **引导分析：嵌入工作区** | 将多个引导分析合并到 Analysis Workspace 中的单个视图中。（文档链接见下文） | 2024 年 9 月 22 日 | 2024 年 10 月 2 日 |

## Customer Journey Analytics 中的修复

AN-352461、AN-355446：AN-355665

## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 | | |

{style="table-layout:auto"}

## 相关资源

* [之前的 2024 Customer Journey Analytics 发行说明](/help/release-notes/2024.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hans)
* [流媒体收藏集附加组件发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
