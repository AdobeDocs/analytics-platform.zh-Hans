---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: b02a3954e7b531caabfbea1f7df4e322eb4af741
workflow-type: ht
source-wordcount: '712'
ht-degree: 100%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2024 年 5 月）

**上次更新日期**：2024 年 5 月 21 日

这些发行说明涵盖 2024 年 5 月 15 日至 2024 年 6 月的发行期。Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **BI 扩展** | BI 扩展允许 SQL 访问您在 Customer Journey Analytics 中定义的数据视图。[了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/bi-extension) | | 2024 年 5 月 15 日 |
| **Audiences 已发布到 Experience Platform 中的新“Audiences”部分** | 从 Customer Journey Analytics 中发布的受众现在可以在 Adobe Experience Platform 的新“受众”部分中找到。<p>此前，从 Customer Journey Analytics 发布的受众可在 Experience Platform 的“细分”部分下找到。</p><p>此改进具有以下优点：</p><ul><li>受众出现在 Experience Platform 前不再有 1 小时的延迟；它们在发布后几秒钟即可使用。</li><li>可以使用 Experience Platform 中“来源”列对受众进行排序，该列显示了最初发布受众的应用程序。</li><li>Experience Platform 中的筛选和排序选项使您能够更快地找到相关受众。</li></ul> <p>（更新文档链接见下文）</p> |  | 2024 年 5 月下旬至 6 月上旬 |
| **Customer Journey Analytics 的 AI 助手** | 允许您在 Customer Journey Analytics UI 中提出自然语言问题，并根据 Customer Journey Analytics 文档获取答案。 <p>（更新文档链接见下文）</p> | | 2024 年 5 月 30 日 |
| **流媒体：使用 web SDK 将 web 数据发送到 Adobe Experience Platform Edge Network** | 您现在可以使用 Adobe Experience Platform Web SDK 将流媒体 Web 数据发送到 Adobe Experience Platform Edge Network，从而可以构建更加个性化的营销活动并提供更加个性化的内容，从而生成更多可供报告的跟踪数据。<p>此增强功能为所有平台解决方案（例如 Customer Journey Analytics、RT-CDP、AJO 和事件转发）的 Web 实现提供了统一的收集方法。以前，将流媒体网络数据发送到 Edge Network 的唯一方法是使用 Edge Network API。 <p>（更新文档链接见下文）</p> | | 2024 年 5 月 31 日 |
| **派生字段 - 数学函数** | 允许您在数据视图中执行简单的数学运算符来回答有关用户的问题。例如，您可以将产品、保修和运输收入结合起来。 <p>（更新文档链接见下文）</p> | | 2024 年 6 月 5 日 |
| **共享用于导出和导入的账户和位置** | 用户现在可以将他们创建的帐户和位置提供给其组织内的所有用户。只有帐户和位置所有者以及系统管理员可以编辑和删除帐户和位置。<p>以前，帐户和位置只能由创建它们的用户使用。</p><p>当用户配置云导出帐户以及配置云导出位置时，这些设置适用。</p> <p>（更新文档链接见下文）</p> | 2024 年 6 月 12 日 | 2024 年 6 月 30 日 |
| **有关从 Adobe Analytics 升级到 Customer Journey Analytics 的新文档** | 对于从 Adobe Analytics 升级到 Customer Journey Analytics 的组织，需要考虑组织当前的 Adobe Analytics 实施和长期目标，有多种升级选项和许多注意事项需要牢记。现提供新的文档资源来帮助您更好地理解：<ul><li>现有的各种升级路径</li><li>根据组织当前的 Adobe Analytics 实施情况，有哪些升级路径可用</li><li>每种升级路径的优缺点</li><li>每种升级路径的分步指导</li><li>处理历史数据的注意事项</li></ul>[开始升级到 Customer Journey Analytics](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-getstarted) | | 现在可用 |
| **有关 [数据导出用例的新文档](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-usecases/data-export/overview)** | 此新部分概述了数据导出用例，例如<ul><li>数据备份</li><li>数据验证</li><li>数据湖、数据仓库或 BI 工具</li><li>为 AI/ML 做好准备</li></ul> 以及如何使用 Experience Platform 和 Customer Journey Analytics 功能实现它们。 | | 现在可用 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-342309；AN-342312；AN-345267；AN-345909；AN-346016；AN-346049；AN-346052；AN-346287；AN-346624；AN-347919

## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 | | |

{style="table-layout:auto"}

## 相关资源

* [之前的 2024 Customer Journey Analytics 发行说明](/help/release-notes/2024.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
