---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 36badebf0710131b2f831feb645f20d8dd888b9b
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 43%

---

# 当前Adobe Customer Journey Analytics发行说明（2024年5月）

**上次更新**：2024年5月9日

这些发行说明涵盖2024年5月15日至2024年6月的发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **BI扩展** | BI扩展允许SQL访问您在Customer Journey Analytics中定义的数据视图。 [了解详情](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension) | | 2024年5月15日 |
| **Audiences 已发布到 Experience Platform 中的新“Audiences”部分** | 从 Customer Journey Analytics 中发布的受众现在可以在 Adobe Experience Platform 的新“受众”部分中找到。<p>此前，从 Customer Journey Analytics 发布的受众可在 Experience Platform 的“细分”部分下找到。</p><p>此改进具有以下优点：</p><ul><li>受众出现在 Experience Platform 前不再有 1 小时的延迟；它们在发布后几秒钟即可使用。</li><li>可以使用 Experience Platform 中“来源”列对受众进行排序，该列显示了最初发布受众的应用程序。</li><li>Experience Platform 中的筛选和排序选项使您能够更快地找到相关受众。</li></ul> [了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-components/audiences/publish) |  | 2024年5月15日 |
| **用于Customer Journey Analytics的AI助手** | 允许您在Customer Journey AnalyticsUI中询问自然语言问题，并根据Customer Journey Analytics文档获得答案。 （文档链接见下文） | | 2024年5月30日 |
| **流媒体：使用Web SDK将Web数据发送到Adobe Experience PlatformEdge Network** | 您现在可以使用Adobe Experience Platform Web SDK将流媒体Web数据发送到Adobe Experience PlatformEdge Network，从而允许您构建更个性化的促销活动并提供更个性化的内容，从而产生要报告的更多跟踪数据。<p>此增强功能为所有Platform解决方案(如Customer Journey Analytics、RT-CDP、AJO和事件转发)的Web实施提供了统一的收集方法。 以前，将流媒体Web数据发送到Edge Network的唯一方法是使用Media Edge API。 [了解详情](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge) | | 2024 年 5 月 31 日 |
| **派生字段 — 数学函数** | 允许您在数据视图中执行简单的数学运算符，以回答有关用户的问题。 例如，您可以将产品、保修和运输收入结合使用。 （文档链接见下文） | | 2024年6月5日 |
| **派生字段 — 下一个或上一个函数** | 让您查看下一个或上一个值是什么。 例如，在选定营销渠道之前，用户与之交互的上一个营销渠道是什么？ 或者，在选定页面之前或之后，用户与哪个页面进行了交互？ 在店内访问之前，最受欢迎的渠道用户与什么进行交互？  （文档链接见下文） | | 2024年6月12日 |
| **关于从Adobe Analytics升级到Customer Journey Analytics的新文档** | 对于从Adobe Analytics升级到Customer Journey Analytics的组织，根据组织当前的Adobe Analytics实施和长期目标，需要牢记有多个升级选项和许多注意事项。 现提供新的文档资源来帮助您更好地理解：<ul><li>现有的各种升级路径</li><li>根据组织当前的 Adobe Analytics 实施情况，有哪些升级路径可用</li><li>每种升级路径的优缺点</li><li>每种升级路径的分步指导</li><li>处理历史数据的注意事项</li></ul>[Customer Journey Analytics升级入门](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | 现在可用 |
| **关于的新文档 [数据导出用例](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/data-export/overview)** | 此新部分概述了数据导出用例，例如<ul><li>数据备份</li><li>数据验证</li><li>数据湖、Data Warehouse或BI工具</li><li>为AI/ML做好准备</li></ul> 以及如何使用Experience Platform和Customer Journey Analytics功能实施它们。 | | 现在可用 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-342309、AN-342312、AN-345267、AN-345909、AN-346016、AN-346049、AN-346052、AN-346287、AN-346624、AN-347919

## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 | | |

{style="table-layout:auto"}

## 相关资源

* [之前的 2024 Customer Journey Analytics 发行说明](/help/release-notes/2024.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
