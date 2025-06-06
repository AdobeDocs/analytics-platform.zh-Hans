---
title: 当前 Customer Journey Analytics 发行说明
description: 查看最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: df8a10c674ed64d0341209fbe0a700a5c94b3b75
workflow-type: ht
source-wordcount: '1093'
ht-degree: 100%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2025 年 5 月）

**上次更新日期**：2025 年 5 月 22 日


这些发行说明涵盖 2025 年 4 月 22 日至 6 月 18 日的发行期。Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **已更新用于将流媒体数据收集到 Adobe Experience Platform 的 XDM 字段** | 将流媒体数据收集到 Adobe Experience Platform 时，不再使用流媒体参数文档中“XDM 字段路径”标题下显示的 XDM 字段路径。这些字段路径位于以下页面并标记为“已弃用”：[音频和视频参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[广告参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/ad-parameters)、[章节参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/chapter-parameters)、[播放器状态参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/player-state-parameters)和[质量参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/quality-parameters)。 <p>客户应改迁移到 `mediaReporting` 字段路径，如上面引用的流媒体参数文档中“报告 XDM 字段路径”标题下显示的那样。<p>在三个月的过渡期内，已弃用的 XDM 字段路径的数据摄取将继续进行。但是从 2025 年 7 月末起，已弃用的字段路径将被完全移除，并且不再显示在 Adobe Experience Platform Schema UI 中，从那时起只能使用 `mediaReporting` 字段路径发送数据。<p>在 2025 年 4 月 22 日之前实施了 Analytics 源连接器以将流媒体数据收集到 Platform 的客户，必须迁移其现有的配置，才能使用新字段路径发送数据。此迁移必须在 2025 年 7 月底之前完成。请联系您的 Adobe Consulting 服务或帐户团队以获取迁移支持。在 2025 年 4 月 22 日之后实施 Analytics 源连接器的客户无需采取任何行动。</p> |  | 2025 年 4 月 22 日 |
| **拼合：从 XDM IdentityMap 检索持久和临时 ID** | 此功能支持在拼合过程中使用 XDM IdentityMap 中存储的身份标识。IdentityMap 可用于在基于字段的拼合中使用持久 ID 或临时 ID，也可用于在基于图形的拼合中使用持久 ID。您可以使用 identityMap 中的某个特定命名空间或主要身份标识。请在[此处](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/stitching/fbs#identitymap)和[此处](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/stitching/gbs#identitymap)了解详情 |  | 2025 年 4 月 28 日 |
| **数据视图间共享的量度和维度** | 允许您在多个数据视图中应用维度和量度设置。对某个共享维度或量度所做的更改会应用于所有适用的数据视图中该维度或量度的所有实例。此界面允许 Customer Journey Analytics 管理员在使用许多数据视图时更轻松地管理组件。[了解详情](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | 2025 年 4 月 30 日 |
| **增加完整表格导出的限制** | Adobe 将[完整表格导出](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/export/export-cloud#comparison-of-full-table-export-in-customer-journey-analytics-to-data-warehouse-in-adobe-analytics)时可用的列数从 5 个维度和 5 个量度增加到 10 个维度和 10 个量度。这适用于所有 Customer Journey Analytics 层。可导出行数的权利保持不变。 |  | 2025 年 4 月 30 日 |
| **事件深度维度** | 数据视图所需标准组件列表中添加了新的[事件深度维度](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/component-reference#required-standard-components)。 |  | 2025 年 5 月 8 日 |
| **导出完整表格时禁用清单文件** | 将允许您禁用从 Analysis Workspace 导出完整表格时默认包含的清单文件。[了解详情](/help/analysis-workspace/export/export-cloud.md) |  | 2025 年 5 月 20 日 |
| **Data Insights 代理** | Data Insights 代理是 Customer Journey Analytics 中 AI 助手的一部分，是一个生成式 AI 对话代理。它使用来自数据视图和实际数据的组件，通过在 Analysis Workspace 中构建相关的可视化图表来快速有效地回答以数据为中心的问题。[了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai) |  | 2025 年 5 月 28 日 |
| **Double 类型维度的维度格式默认为 2** | 对于具有 Double 数据类型的架构，维度格式现在默认为小数点后 2 位。您可以将此数字更改为小数点后 0 到 5 位。<p>以前，该格式默认为小数点后 0 位。</p><p>这意味着如果您在 Analysis Workspace 报告中使用双精度浮点数维度类型，则在默认情况下不显示小数位。这些相同的报告现在将显示小数点后 2 位。</p><p>有关如何更新双精度浮点数维度类型显示的小数位数的更多信息，请参阅 [格式组件设置](/help/data-views/component-settings/format.md)。</p> | | 2025 年 5 月 29 日 |
| **Analysis Workspace 左侧面板不再在鼠标悬停时打开和关闭** | Analysis Workspace 中的左侧面板用于将组件、面板和可视化图表等元素添加到您的项目中。将鼠标悬停在最左侧的一个图标上以临时打开左侧面板，这个选项不再可用。现在，只需单击其中一个图标即可保持面板打开，然后单击相同的图标可将其关闭。 |  | 2025 年 6 月 2 日 <p>（原计划于 2025 年 5 月 29 日发布）</p> |
| **Customer Journey Analytics B2B Edition** | Customer Journey Analytics B2B Edition 提供有助于推动收入增长的可操作的帐户洞察，帮助 B2B 公司协调其营销活动、销售和产品团队。帐户是数据模型的中心，因此所有分析都集中在帐户历程上。在基于人员及时间的事件之上添加一层新实体（帐户、机会和购买群组），可以创建 B2B 营销活动和收入生命周期的完整图景。[了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 2025 年 6 月 18 日 |
| **在 Analysis Workspace 项目中添加和查看评论** | Analysis Workspace 中新增的[评论功能](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects)可让您在 Analysis Workspace 项目的上下文中分享见解和提出问题。这可以简化有关数据的讨论，使对话保持在正在讨论的数据范围内。您可以 <ul><li>对任何您有权访问的 Analysis Workspace 项目进行评论</li><li>对可视化图表中的特定点进行评论，也可以对项目进行一般性评论</li><li>标记其他用户，将您的评论告知他们</li><li>管理现有评论（编辑、固定、解决等）</li></ul>Customer Journey Analytics 管理员可以[在组织级别禁用评论功能](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences)。项目所有者可以[在项目级别禁用评论功能](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects)。 |  | 2025 年 6 月 25 日 <p>（原计划于 2025 年 5 月 29 日发布）</p> |

## Customer Journey Analytics 中的修复

**Analysis Workspace**：AN-361874；AN-371360；AN-373079；AN-374382；AN-374447；AN-375277；AN-375680
**受众**：AN-372343
**审核日志**：AN-378168
**连接**：AN-373121；AN-372996
**数据删除**：AN-375450
**派生字段**：AN-373689；AN-377852
**导出位置**：AN-374167
**历程画布**：AN-373319
**Report Builder**：AN-369786
**报告**：AN-377326；AN-378051
**报告活动管理器**：AN-377148


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
