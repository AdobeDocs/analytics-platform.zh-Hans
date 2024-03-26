---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 20e99275a42312ed974ac4c1af28ede73180e748
workflow-type: ht
source-wordcount: '957'
ht-degree: 100%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2024 年 3 月）

**上次更新日期**：2024 年 3 月 20 日

这些发行说明涵盖 2024 年 3 月 13 日至 2024 年 4 月的发行期。Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **项目登陆页面新增一列** | 现在，在查看 **[!UICONTROL Customer Journey Analytics 登陆页面上的“项目”选项卡时，可以使用]**&#x200B;上次使用[列](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=zh-Hans)。 <p>通过显示项目上次打开的日期和时间，该信息可帮助您确定项目对组织中的用户是否有价值。以前，**[!UICONTROL 上次使用]**&#x200B;列仅在计算量度管理器、分段管理器和警报管理器中可用。</p> |  | 2024 年 3 月 13 日 |
| **使用情况量度** | [使用量度界面](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=zh-Hans)显示所有连接中摄取和可报告的行的使用情况。在此界面中可确定您的 Customer Journey Analytics 使用情况是否遵守合同条款。 |  | 2024 年 3 月 13 日 |
| **Media Analytics 报告 - 平均受众访问分钟数 (AMA)** | CJA 中现已提供“平均受众访问分钟数”面板。Media Analytics 客户使用“平均受众访问分钟数”面板可更好地了解其内容的平均使用情况。 <p>平均受众访问分钟数可对任何长度或类型的节目进行比较。此外，客户可以将此数字平均受众访问分钟数与线性电视平均访问分钟数量度进行比较或附加到其上。</p><p> 此面板可更灵活地衡量自定义时段的平均受众以及在事后更新持续时间分类的时间。</p><p>有关详细信息，请参阅[媒体平均受众访问分钟数面板](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)。</p> |  | 2024 年 3 月 12 日 |
| **个人到帐户的 B2B 架构转换** | 允许您转换数据集以更好地支持 Customer Journey Analytics B2B 报告场景中基于人员的查找。该功能适用于基于以下类的 B2B 模式数据集：<ul><li>XDM 业务帐户人员关系</li><li>XDM 业务机会人员关系</li><li>XDM 商业营销列表成员</li><li>XDM 商业营销活动成员</li></ul> | | 2024 年 3 月 26 日 |
| **Report Builder 的使用情况包含在计算量度管理器和过滤器管理器的“用于”列中** | 在计算量度管理器或过滤器管理器中查看“**用于**”列时，Report Builder 现在可提供使用情况数据。<p>以前，过滤器管理器中的使用情况数据仅适用于警报、项目、已计划项目和计算量度；而计算量度管理器中的使用情况数据仅适用于警报、项目和已计划项目。</p> |  | 三月底或四月初 |
| **Adobe Product Analytics：比较单个漏斗步骤中的事件** | 在漏斗：摩擦视图中，您现在可以比较单个漏斗步骤内的事件。当您的历程有步骤选项或正在运行 A/B 实验的步骤时，这个功能特别有用。 | 2024 年 3 月 29 日 | 2024 年 4 月 12 日 |
| **管理员可以管理其组织中的所有位置和帐户** | “位置”选项卡（在组件 > 导出页面）上的新选项允许管理员查看和管理组织中的所有位置。 <p>“位置”帐户选项卡（在组件 > 导出页面）上的新选项允许管理员查看和管理组织中的所有帐户。</p><p>以前，管理员只能查看和管理他们创建的位置和帐户。</p> | | 2024 年 4 月 |
| **受众已发布到 Experience Platform 中的新“受众”部分** | 从 Customer Journey Analytics 中发布的受众现在可以在 Experience Platform 的新“受众”部分中找到。此前，从 Customer Journey Analytics 发布的受众可在 Platform 的“细分”部分下找到。此改进具有以下优点：<ul><li>受众出现在 Platform 前不再有 1 小时的延迟；它们在发布后几秒钟即可使用。</li><li>可以使用“来源”列在 Platform 中对受众进行排序，该列显示最初发布受众的应用程序。</li><li>Platform 中的筛选和排序选项使您能够更快地找到相关受众。</li></ul>有关详细信息，请参阅[在 Experience Platform 中使用 Customer Journey Analytics 受众](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=zh-Hans#audiences-aep)部分。 |  | 2024 年 4 月 |
| **Experience Edge 机器人检测** | 通过[机器人检测](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=zh-Hans)，可将 Web SDK、Mobile SDK 和 Server API 生成的事件视为由已知的蜘蛛程序和机器人生成。 | | 2024 年 4 月 29 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-340429、AN-341544、AN-341974、AN-342176、AN-342391

## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| **更新了数据视图和连接 UI 中的链接** | 15 年 2 月 | 3 月初，Adobe 计划更新 Customer Journey Analytics 产品用户界面中的以下链接。请相应地更新您的书签。<ul><li>**数据视图页面，数据视图管理器**：[现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [新链接](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**创建新数据视图**：[现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [新链接](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**编辑数据视图**：[现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [新链接](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**连接管理器**：[现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [新链接](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**连接信息**：[现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [新链接](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**编辑连接**：[现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [新链接](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**创建新数据连接**：[现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [新链接](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |
| 添加了 Adobe API 对象成员 | 2024 年 1 月 17 日 | Adobe 可能会无通知或在版本控制中无变更地将可选的请求和响应成员（名称/值对）添加到现有的 API 对象。此类添加应为不令您的实施发生中断的更改。Adobe 建议您参考与我们的 API 集成的任何第三方工具的 API 文档，以便在处理过程中忽略不了解的此类添加。如果没有首先通过发行说明提供标准通知，Adobe 不会删除参数或添加所需参数。 |

{style="table-layout:auto"}

## 相关资源

* [之前的 2023 Customer Journey Analytics 发行说明](/help/release-notes/2023.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
