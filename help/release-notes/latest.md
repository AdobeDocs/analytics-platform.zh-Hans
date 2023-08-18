---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 0160aee587c1f88e4889f26757b1962c3d59b9fa
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 92%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2023 年 8 月）

**上次更新日期**：2023 年 8 月 17 日

这些发行说明涵盖 2023 年 8 月 9 日至 9 月 13 日的发行期。Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Report Builder 增强功能** | <ul><li>您可以从“工作簿”选项卡下载计划任务，然后对其进行标题、保存和共享。 [了解详情](/help/report-builder/schedule-reportbuilder.md)</li><li>“开始日期作为维度”允许您在数据块输出中将数据块的开始日期显示为维度。 [了解详情](/help/report-builder/create-a-data-block.md) </li></ul> | 不适用 | 2023 年 8 月 17 日 |
| **货币换算** | 客户历程增加了支持多种货币的能力。您可以在数据视图设置中将一种货币转换为另一种货币。[了解详情](/help/data-views/component-settings/format.md) | 不适用 | 2023 年 8 月 31 日 |
| **Analytics Source Connector 提供对 A4T 分类的支持** | 我们正在添加关联 ID，以便轻松加入 Adob&#x200B;&#x200B;e Target 活动和体验事件的分类数据。 | 不适用 | 2023 年 8 月 31 日 |
| **报表活动管理器** | 管理员可以获得有关每个连接的报告消耗情况的详细信息，使管&#x200B;&#x200B;理员能够轻松诊断并修复报告高峰时段的容量问题。 | 不适用 | 2023 年 9 月 6 日 |
| **PowerBI 和 Tableau 访问 Customer Journey Analytics 数据视图** | 通过 Adobe Customer Journey Analytics SQL Connector，SQL 可访问您在 Customer Journey Analytics 中定义的数据视图。更熟悉 Power BI、Tableau 或其他商业智能和可视化工具的数据工程师和分析师现在可根据 Customer Journey Analytics 用户用于其 Analysis Workspace 项目的相同数据视图创建报表和仪表板。[了解详情](/help/data-views/sql-connector.md) | 不适用 | 2023 年 9 月 13 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-309141; AN-319198; AN-324576; AN-324939; AN-325138; AN-325554

## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| **Customer Journey Analytics 处理数据方式的变更** | 2023 年 6 月 22 日 | 我们最近变更了 Customer Journey Analytics 中的数据处理方式。<ul><li>任何时间戳少于 24 小时的事件数据都将流入。</li><li>任何时间戳多于 24 小时的事件数据（即使它与更新的数据属于同一批次）都将视为回填，并将以较低的优先级摄取。</li></ul> |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API、Customer Journey Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## 相关资源

* [之前的 2023 Customer Journey Analytics 发行说明](/help/release-notes/2023.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
