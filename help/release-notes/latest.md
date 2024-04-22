---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: abaa747934ff2cdd0a3dab867165afb46fbc71db
workflow-type: tm+mt
source-wordcount: '945'
ht-degree: 42%

---

# 当前Adobe Customer Journey Analytics发行说明（2024年4月）

**上次更新**：2024年4月17日

这些发行说明涵盖2024年4月10日至2024年5月的发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **流媒体：将Roku数据发送到Adobe Experience Platform Edge** | 现在，当 [使用Experience PlatformEdge安装Media Analytics](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge)中，您可以使用Adobe Experience Platform Roku SDK将流媒体数据发送到Adobe Experience Platform。 |  | 2024 年 4 月 12 日 |
| **在报告活动管理器中公开每月报告** | 现在，在报表活动管理器中查看所有连接的报表活动时，均可使用显示 [月度报告/请求](https://experienceleague.adobe.com/en/docs/analytics-platform/using/reporting-activity-manager/reporting-activity#view-all-report-suites) 当前和上个月在IMS组织级别运行的日志。<p>**注意：** 提供了从2024年3月中开始的数据。 | | 2024年4月15日 |
| **移动记分卡中的智能题注** | [智能题注](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)可以帮助非分析师在没有分析师帮助的情况下更好地理解数据。这些数据现在可以在 Customer Journey Analytics 记分卡中使用。 |  | 2024 年 4 月 17 日 |
| **仅用于项目的权限增强 [!UICONTROL 工作区] 组件** | 以前，如果一个用户（用户A）与另一个用户（用户B）共享项目并授予用户B编辑项目的权限，则用户B将能够编辑项目。 但是，用户B无法编辑 [!UICONTROL 快速区段] 嵌入到项目中。 该限制现已移除 — 用户B可以编辑 [!UICONTROL 快速区段] 以及嵌入到共享项目中的其他仅用于项目的组件。 |  | 2024 年 4 月 17 日 |
| **管理员可以管理其组织中的所有位置** | 上的新选项 [“位置”页面](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) 允许管理员查看和管理组织中的所有位置。 之前，管理员只能查看和管理他们创建的位置。 |  | 2024 年 4 月 17 日 |
| **Adobe Product Analytics：功能表** | 通过了解您的核心、能力、一次性和可疑的特点来推动投资决策。 [!UICONTROL 特征矩阵] 按使用频率与%活动用户度量事件，并与中间使用率进行比较。 | 2024 年 4 月 17 日 | 2024 年 4 月 30 日 |
| **Adobe Product Analytics：漏斗中的增强见解** | 在 [摩擦](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/funnel/friction) 视图，已增强书面见解以包括类别、增量及描述，从而进一步了解图表和表格。 | 2024 年 4 月 17 日 | 2024年4月26日 |
| **Adobe Product Analytics：增强的保留视图** | 几项功能已添加到 [维系](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/retention/retention-rates) 费率视图以了解更深入且可自定义的维系率洞察：<ul><li>取消链接开始和返回事件</li><li>在单个视图中比较多个返回事件</li><li>自定义保留模型，该保留模型适用于以下设置：在设置上或之后（无限制）、在每个（有限制）和括号设置上</li><li>在图表中显示和隐藏单个同类群组行</li></ul> | 2024年4月24日 | 2024年5月8日 |
| **Adobe Product Analytics：比较单个漏斗步骤中的事件** | 您现在可以在中的单个漏斗步骤中比较事件 [摩擦](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/funnel/friction) 视图。 当您的历程有步骤选项或正在运行 A/B 实验的步骤时，这个功能特别有用。 | 2024年4月23日 | 2024年5月3日 |
| **个人到帐户的 B2B 架构转换** | 允许您转换数据集以更好地支持 Customer Journey Analytics B2B 报告场景中基于人员的查找。该功能适用于基于以下类的 B2B 模式数据集：<ul><li>XDM 业务帐户人员关系</li><li>XDM 业务机会人员关系</li><li>XDM 商业营销列表成员</li><li>XDM 商业营销活动成员</li></ul> | | 2024年5月1日 |
| **Experience Edge 机器人检测** | 通过[机器人检测](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html)，可将 Web SDK、Mobile SDK 和 Server API 生成的事件视为由已知的蜘蛛程序和机器人生成。 | | 2024年5月1日 |
| **派生字段：“下一个”或“上一个”函数** | 这些新功能让您可以将字段作为输入，然后识别n个前一个值或n个下一个值，以便更好地了解用户历程。 此功能还可以与中的其他功能结合使用 [!UICONTROL 派生字段]，例如 [!UICONTROL 拼接]，以创建新维度。 |  | 2024年5月1日 |
| **受众已发布到 Experience Platform 中的新“受众”部分** | 现在，通过Customer Journey Analytics发布的受众可在Adobe Experience Platform中新增的“受众”部分中使用。<p>以前，从Customer Journey Analytics发布的受众可在Experience Platform的“区段”部分下使用。</p><p>此改进具有以下优点：</p><ul><li>受众在出现在Experience Platform中之前不再有1小时的延迟；发布后，即可使用它们。</li><li>可以使用“来源”列按Experience Platform对受众进行排序，该列显示了最初发布受众的应用程序。</li><li>Experience Platform中的过滤和排序选项使您能够更快地找到相关受众。</li></ul> |  | 2024 年 5 月 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-319662、AN-337894、AN-338469、AN-340147、AN-340200、AN-340443、AN-341594、AN-342442、AN-342976、AN-343020、AN-343469、AN-343703、AN-343938、AN-344614、AN-344677；

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
