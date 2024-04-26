---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 284c73374ca3fdfc4afbc2824209bebdc764fb64
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 96%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2024 年 4 月）

**上次更新时间**：2024 年 4 月 17 日

这些发行说明涵盖 2024 年 4 月 10 日至 2024 年 5 月的发行期。Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **流媒体：将 Roku 数据发送到 Adobe Experience Platform Edge** | 现在，当 [使用 Experience Platform Edge 安装 Media Analytics ](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge)时，您可以使用 Adobe Experience Platform Roku SDK 将流媒体数据发送到 Adobe Experience Platform。 |  | 2024 年 4 月 12 日 |
| **在 Reporting Activity Manager 中显示每月报告** | 在 Reporting Activity Manager 中查看所有连接的报告活动时，现在可以提供一个图表，其中显示在 IMS Org 级别运行的当前月份和上个月的 [月度报告/请求](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/reporting-activity-manager/reporting-activity#view-all-report-suites)。<p>**注意：** 数据从 2024 年 3 月中旬开始提供。 | | 2024 年 4 月 15 日 |
| **移动记分卡中的智能题注** | [智能题注](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)可以帮助非分析师在没有分析师帮助的情况下更好地理解数据。这些数据现在可以在 Customer Journey Analytics 记分卡中使用。 |  | 2024 年 4 月 17 日 |
| **仅限项目 [!UICONTROL Workspace] 组件的权限增强** | 以前，如果一个用户（用户 A）与另一个用户（用户 B）共享一个项目，并授予用户 B 编辑该项目的访问权限，则用户 B 将能够编辑该项目。但是，用户B无法编辑 [!UICONTROL 快速过滤器] 嵌入到项目中。 该限制现已移除 — 用户B可以编辑 [快速过滤器](/help/components/filters/quick-filters.md) 以及嵌入到共享项目中的其他仅用于项目的组件。 |  | 2024 年 4 月 17 日 |
| **管理员可以管理其组织中的所有位置** | [位置页面](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/locations/locations-manager) 上的新选项允许管理员查看和管理组织中的所有位置。之前，管理员只能查看和管理他们创建的位置。 |  | 2024 年 4 月 |
| **Adobe Product Analytics：特征矩阵** | 通过了解您的核心、力量、一次性和可疑特征来推动投资决策。[!UICONTROL 特征矩阵] 通过使用频率与活跃用户百分比来衡量事件，并与中位使用率进行比较。 | 2024 年 4 月 17 日 | 2024 年 4 月 30 日 |
| **Adobe Product Analytics：增强漏斗洞察** | 在 [Friction](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/guided-analysis/funnel/friction) 视图中，书面见解已得到增强，包括类别、增量和描述，以进一步提高图表和表格的可理解性。 | 2024 年 4 月 17 日 | 2024 年 4 月 26 日 |
| **Adobe Product Analytics：增强的保留视图** | [留存](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/guided-analysis/retention/retention-rates) 率视图中添加了多项功能，以便获得更深入、可定制的留存洞察：<ul><li>取消链接开始和返回事件</li><li>在单个视图中比较多个返回事件</li><li>自定义应用的保留模型，在或之后（无限制）、在每个（有限制）和括号内设置</li><li>显示和隐藏图表中的各个群组行</li></ul> | 2024 年 4 月 24 日 | 2024 年 5 月 8 日 |
| **Adobe Product Analytics：比较单个漏斗步骤中的事件** | 您现在可以在 [Friction](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/guided-analysis/funnel/friction) 视图中比较单个漏斗步骤中的事件。当您的历程有步骤选项或正在运行 A/B 实验的步骤时，这个功能特别有用。 | 2024 年 4 月 23 日 | 2024 年 5 月 3 日 |
| **个人到帐户的 B2B 架构转换** | 允许您转换数据集以更好地支持 Customer Journey Analytics B2B 报告场景中基于人员的查找。该功能适用于基于以下类的 B2B 模式数据集：<ul><li>XDM 业务帐户人员关系</li><li>XDM 业务机会人员关系</li><li>XDM 商业营销列表成员</li><li>XDM 商业营销活动成员</li></ul> | | 2024 年 5 月 1 日 |
| **Experience Edge 机器人检测** | 通过[机器人检测](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html)，可将 Web SDK、Mobile SDK 和 Server API 生成的事件视为由已知的蜘蛛程序和机器人生成。 | | 2024 年 5 月 1 日 |
| **派生字段：下一个或上一个函数** | 这些新功能让您可以将字段作为输入，然后识别前 n 个或后 n 个值，以更好地查看用户历程。此功能还可与 [!UICONTROL Derived Fields]中的其他功能（如 [!UICONTROL 连接]）相结合，以创建新的维度。 |  | 2024 年 5 月 1 日 |
| **Audiences 已发布到 Experience Platform 中的新“Audiences”部分** | 从 Customer Journey Analytics 中发布的受众现在可以在 Adobe Experience Platform 的新“受众”部分中找到。<p>此前，从 Customer Journey Analytics 发布的受众可在 Experience Platform 的“细分”部分下找到。</p><p>此改进具有以下优点：</p><ul><li>受众出现在 Experience Platform 前不再有 1 小时的延迟；它们在发布后几秒钟即可使用。</li><li>可以使用 Experience Platform 中“来源”列对受众进行排序，该列显示了最初发布受众的应用程序。</li><li>Experience Platform 中的筛选和排序选项使您能够更快地找到相关受众。</li></ul> |  | 2024 年 5 月 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-319662；AN-337894；AN-338469；AN-340147；AN-340200；AN-340443；AN-341594；AN-342442；AN-342976；AN-343020；AN-343469；AN-343703；AN-343938；AN-344614；AN-344677；

## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| **更新了数据视图和连接 UI 中的链接** | 15 年 2 月 | 3 月初，Adobe 计划更新 Customer Journey Analytics 产品用户界面中的以下链接。请相应地更新您的书签。<ul><li>**数据视图页面，数据视图管理器**：[现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [新链接](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**创建新数据视图**：[现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [新链接](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**编辑数据视图**：[现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [新链接](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**连接管理器**：[现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [新链接](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**连接信息**：[现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [新链接](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**编辑连接**：[现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [新链接](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**创建新数据连接**：[现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [新链接](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |

{style="table-layout:auto"}

## 相关资源

* [之前的 2024 Customer Journey Analytics 发行说明](/help/release-notes/2024.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
