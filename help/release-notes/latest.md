---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7b368f81c4036a3992fdfc34b983f344a61dc2fb
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 40%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2024 年 9 月）

**上次更新日期**：2024年9月11日

这些发行说明涵盖2024年9月11日到10月初的发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **计算指标管理器和筛选器管理器的“用于”列中的其他信息** | 计算量度管理器和过滤器管理器中的“用于”列包含以下新报表区域：<ul><li>**Report Builder**：显示Report Builder中使用的计算量度或筛选器数。</li><li>**临时组件**：显示项目中使用的临时计算量度或临时过滤器数。 这些临时计算量度和过滤器（也称为“快速计算量度”和“快速过滤器”）只能在创建它们的项目中使用，因此它们会与“用于”列中的“项目”报表区域分开报告。</li></ul>有关详细信息，请参阅[计算量度管理器](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager)和[筛选器管理器](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-filters/manage-filters)。 |  | 2024年9月11日 |
| **智能警报** | Customer Journey Analytics 中的智能警报允许您在数据中出现异常事件时立即收到通知。<p>您可以设置根据异常阈值、变化的百分比或特定数据点触发的警报。警报提供与异常检测集成的细粒度控制，在您最需要时触发。</p><p>在 Customer Journey Analytics 中使用智能警报的过程与在 Adobe Analytics 中使用智能警报的过程几乎相同。一个主要的区别是 Customer Journey Analytics 不提供每小时警报。此差异在于可摄取的各种事件数据的数据摄取仅在延迟后才能完成，延迟时间通常比数据事件时间晚3到9个小时。 [了解详情](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/c-intelligent-alerts/intellligent-alerts) |  | 2024年9月中旬 |
| **Adobe Analytics源连接器的更新** | 数据集活动页面不显示有关批次的信息，因为Analytics Source Connector完全由Adobe管理。 您可以通过查看所摄取记录的相关量度来监控数据流动。 有关详细信息，请阅读有关[为Analytics数据创建源连接](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)的指南。 |  | 现在可用 |
| **使用情况分析** | 了解您的组织如何使用Customer Journey Analytics。 启用此功能可在Adobe Experience Platform中创建数据集，以便在贵组织中的任何人使用Analysis Workspace时收集数据。 系统还会自动创建连接和数据视图，以便您访问项目中最热门的类型、最活跃的用户以及在项目中使用的最受欢迎的组件等维度。 （文档链接见下文） |  | 2024 年 9 月 18 日 |
| **引导式分析：嵌入到Workspace** | 在Analysis Workspace中将多个引导式分析合并到单个视图中。 （文档链接见下文） | 2024年9月22日 | 2024年10月2 |


## Customer Journey Analytics 中的修复

AN-352461； AN-355446： AN-355665

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
