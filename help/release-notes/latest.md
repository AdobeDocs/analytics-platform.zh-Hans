---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 57124124254f5ca9eb2a9f63a7478cd288c19b0e
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 100%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2023 年 10 月）

**上次更新日期**：2023 年 10 月 13 日

这些发行说明涵盖 2023 年 10 月 4 日至 2023 年 10 月 24 日的发行期。Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **将全表导出到云** | 通过 Customer Journey Analytics 全表导出，可将数百万个 Workspace 行导出到云目标。 <p>导出全表可一次性或按计划投放在 Workspace 中设计的数据表，其中支持最多五个细分、五个量度、过滤器和计算量度，所有这些都在一个连接在一起的表中。它从 Adobe Analytics 中的 Data Warehouse 报告演化而来，具有许多当今在 Data Warehouse 中不提供但经常有人要求提供的新功能。</p><p> 云导出选项包括：</p><ul><li>Adobe Experience Platform 数据登陆区</li><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Snowflake</li></ul>有关详细信息，请参阅[将 Customer Journey Analytics 报告导出到云](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html)。 | 2023 年 10 月 4 日 | 2023 年 10 月 19 日 |
| **管理组件时可用的新列** | 在管理组件时，现在可在[计算量度管理器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html)和[过滤器管理器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html)中找到以下新列：<ul><li>用在</li><li>上次使用时间</li></ul>此信息可帮助您确定某个组件是否对组织中的用户有用、在何处使用该组件以及是否需要删除或修改该组件。可使用数据词典配合此信息帮助您跟踪并更好地了解如何在您的组织中使用组件。 | 2023 年 9 月 23 日 | 2023 年 10 月 4 日 |
| **将 Adobe Analytics 项目和其中包括的任何组件迁移到 Customer Journey Analytics** | 现在可将 Adobe Analytics 项目迁移到 Customer Journey Analytics。此过程简化了从 Adobe Analytics 到 Customer Journey Analytics 的过渡。 <p>将项目迁移到 Customer Journey Analytics 时，资源将从 Adobe Analytics 报表包映射到 Customer Journey Analytics 数据视图。</p> <p>从 Adobe Analytics 界面将项目迁移到 Customer Journey Analytics。[了解详情](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)</p> | 不适用 | 2023 年 10 月 9 日 |
| **Adobe Product Analytics：显示/隐藏系列** | 单击图表图例或表行以控制可视化图表中各个系列的可见性。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/overview.html?lang=zh-Hans) | 不适用 | 2023 年 10 月 4 日 |
| **Adobe Product Analytics 中的注释** | 引导式分析现在支持查看在 Customer Journey Analytics 中创建的注释的功能。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/annotations/overview.html?lang=zh-Hans) | 不适用 | 2023 年 10 月 4 日 |
| **报告活动管理器** | 通过报告活动管理器，可查看组织中每个连接的报告容量。通过它，管理员可详细了解报告消耗情况，从而轻松地诊断和修复在报告高峰期出现的容量问题。报告活动管理器的主要功能包括：<ul><li>取消当前的报告请求（包括从引导式分析和全表导出提出的请求）</li><li>对所定义的时段限制后续请求</li></ul>除了取消当前请求之外，管理员现在还可对所定义的时段限制请求。管理员可以按请求、项目或用户限制请求。[了解详情](/help/reporting-activity-manager/reporting-activity-overview.md) | 2023 年 10 月 17 日 | 2023 年 10 月 23 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-325940、AN-326468、AN-328301、AN-328640、AN-329370

## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 | 不适用 | 不适用 |

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
