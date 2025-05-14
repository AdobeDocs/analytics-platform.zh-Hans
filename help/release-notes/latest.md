---
title: 当前 Customer Journey Analytics 发行说明
description: 查看最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 50dc97017913ef7064011437e233a40c862484e6
workflow-type: tm+mt
source-wordcount: '986'
ht-degree: 31%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2025 年 5 月）

**上次更新**：2025年5月14日


这些发行说明涵盖2025年4月22日至6月18日的发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Customer Journey Analytics B2B edition** | Customer Journey Analytics B2B edition通过提供可促进收入增长的可操作客户洞察信息，帮助B2B公司整合其营销、销售和产品团队。 通过将帐户置于数据模型的中心，所有分析都将重点放在帐户历程上。 在人员和基于时间的事件上添加新的实体层（客户、机会和购买组），可以全面了解B2B营销和收入生命周期。 [了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 2025年6月18日 |
| **Data Insights Agent** | Data Insights Agent是Customer Journey Analytics人工智能助理的一部分，是一个创新型人工智能对话代理。 它使用来自您的数据视图和实际数据的组件，通过在Analysis Workspace中构建相关可视化图表，快速高效地回答以数据为中心的问题。 [了解详情](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai) |  | 2025年5月28日 |
| **在Analysis Workspace项目中添加和查看注释** | Analysis Workspace中新增的[评论功能](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects)允许您在Analysis Workspace项目的上下文中共享见解和提问。 这可以简化有关数据的讨论，使对话与正在讨论的数据保持同步。 您可以 <ul><li>评论您有权访问的任何Analysis Workspace项目</li><li>在可视化图表中的特定点添加注释或发表有关项目的一般注释</li><li>标记其他用户以通知他们您的评论</li><li>管理现有注释（编辑、固定、解析等）</li></ul>Customer Journey Analytics管理员可以[禁用组织级别](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences)的评论。 项目所有者可以[禁用项目级别](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects)的注释。 |  | 2025年5月29日 |
| **增加完整表导出限制** | Adobe将可与[完整表导出](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/export/export-cloud#comparison-of-full-table-export-in-customer-journey-analytics-to-data-warehouse-in-adobe-analytics)一起使用的列数从5个维度和5个指标增加到10个维度和10个指标。 这适用于所有Customer Journey Analytics层。 可导出的行数的权利没有变化。 |  | 2025 年 4 月 30 日 |
| **已更新用于将流媒体数据收集到 Adobe Experience Platform 的 XDM 字段** | 在将流媒体数据收集到Adobe Experience Platform时，不应再使用流媒体参数文档的“XDM字段路径”标题下方显示的XDM字段路径。 这些字段路径可在以下页面上找到并标记为“已弃用”：[音频和视频参数](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[广告参数](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/ad-parameters)、[章节参数](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/chapter-parameters)、[播放器状态参数](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/player-state-parameters)和[质量参数](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/quality-parameters)。 <p>相反，客户应迁移到`mediaReporting`字段路径，如上面引用的流媒体参数文档的“报告XDM字段路径”标题下所示。<p>在三个月的过渡期内，将继续摄取已弃用的XDM字段路径上的数据。 但是，在2025年7月底，已弃用的字段路径将完全移除并在Adobe Experience Platform架构UI中不再可见，数据将仅使用`mediaReporting`字段路径发送。<p>在2025年4月22日之前实施了Analytics Source Connector以将流媒体数据收集到Platform的客户必须迁移其现有配置以使用新的字段路径。 此迁移必须在 2025 年 7 月底之前完成。请联系您的 Adobe Consulting 服务或账户团队以获取迁移支持。在 2025 年 4 月 22 日之后实施 Analytics 源连接器的客户无需采取任何行动。</p> |  | 2025 年 4 月 22 日 |
| **拼接：从 XDM IdentityMap 检索持久和临时 ID** | 此功能支持在拼接过程中使用 XDM IdentityMap 中存储的身份标识。IdentityMap 可用于在基于字段的拼接中使用持久 ID 或临时 ID，也可用于在基于图形的拼接中使用持久 ID。您可以使用 identityMap 中的某个特定命名空间或主要身份标识。请在[此处](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/fbs#identitymap)和[此处](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/gbs#identitymap)了解详情 |  | 2025年4月28日 |
| **数据视图间共享的量度和维度** | 允许您在多个数据视图中应用维度和量度设置。对某个共享维度或量度所做的更改会应用于所有适用的数据视图中该维度或量度的所有实例。此界面允许 Customer Journey Analytics 管理员在使用许多数据视图时更轻松地管理组件。[了解详情](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | 2025 年 4 月 30 日 |
| **事件深度维度** | 新的[事件深度维度](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference#required-standard-components)已添加到数据视图所需的标准组件列表中。 |  | 2025年5月8日 |
| **Analysis Workspace左侧面板在悬停时不再打开和关闭** | Analysis Workspace中的左侧面板用于将组件、面板和可视化图表等内容添加到您的项目中。 通过将鼠标悬停在最左侧的图标之一上来临时打开左侧面板的选项不再可用。 相反，只需单击其中一个图标以保持面板打开，然后单击同一图标以将其关闭即可。 |  | 2025年5月29日 |
| **导出完整表时禁用清单文件** | 将允许您禁用在从Analysis Workspace导出完整表时默认包含的清单文件。 |  | 2025 年 5 月底 |


## Customer Journey Analytics 中的修复

**Analysis Workspace**： AN-361874； AN-371360； AN-373079； AN-374382； AN-374447； AN-375277； AN-375680
**受众**： AN-372343
**审核日志**： AN-378168
**连接**： AN-373121； AN-372996
**数据删除**： AN-375450
**派生字段**： AN-373689； AN-377852
**导出位置**： AN-374167
**历程画布**： AN-373319
**Report Builder**： AN-369786
**报告**： AN-377326； AN-378051
**报告活动管理器**： AN-377148


## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 | | |

## 相关资产

* [之前的 2025 Customer Journey Analytics 发行说明](/help/release-notes/2025.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hans)
* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
