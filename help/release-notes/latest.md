---
title: 当前 Customer Journey Analytics 发行说明
description: 查看最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4d0ad58193217ebcff8dcf15b3d5a65f0977133f
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 72%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2025 年 4 月）

**上次更新时间**：2025年4月30日

这些发行说明涵盖 2025 年 3 月 27 日至 5 月 15 日的发行期。Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **增加完整表导出限制** | 我们将增加客户可以通过完整表格导出使用的列数（从5个维度和5个指标导出为10个维度和10个指标）。 这适用于所有Customer Journey Analytics层。 可导出的行数的权利没有变化。 |  | 2025 年 4 月 30 日 |
| **数值维度的“无值”行项目的更新** | 对于数值维度，此更新可让您<ul><li>在区段中使用“无值”维度项。</li><li>在报告中对“无值”行项目进行细分。</li></ul> [了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/component-settings/no-value-options#numeric) | | 2025 年 3 月 27 日 |
| **Adobe Content Analytics** | Adobe Content Analytics 可让您快速轻松地调查大量内容数据，以了解趋势、发现异常、识别内容疲劳并从内容曝光中获取见解。<p>开箱即用，您可以使用预建的报告模板和资产检查器等新功能节省时间。此功能不仅可以让您根据数据直观地查看资产，还可以打开每个资产以获取汇总的详细信息，包括绩效、投放环境、属性等。<p>您可以在完整的客户历程背景中调查这组新的内容数据，以回答重要的业务问题、评估内容绩效、增强分段、识别优化机会并定义新的待激活的受众。<p>内容分析是 Customer Journey Analytics 的附加功能。[了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/content-analytics/content-analytics) |  | 2025 年 3 月 27 日 |
| **媒体收集：Adobe Source Connector 更新了新的媒体报告 XDM** | Analytics 源连接器会自动将 Adobe Analytics 中的流媒体数据映射到 Web SDK 使用的相同字段。以前，数据被映射到旧位置和新位置，但未来只使用新位置。[了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/aep-edge/xdm-var-mapping) |  | 2025 年 3 月 31 日 |
| **已更新用于将流媒体数据收集到 Adobe Experience Platform 的 XDM 字段** | 在将流媒体数据收集到Adobe Experience Platform时，不应再使用流媒体参数文档的“XDM字段路径”标题下方显示的XDM字段路径。 这些字段路径可在以下页面上找到并标记为“已弃用”：[音频和视频参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[广告参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/ad-parameters)、[章节参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/chapter-parameters)、[播放器状态参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/player-state-parameters)和[质量参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/quality-parameters)。 <p>相反，客户应迁移到`mediaReporting`字段路径，如上面引用的流媒体参数文档的“报告XDM字段路径”标题下所示。<p>在三个月的过渡期内，将继续摄取已弃用的XDM字段路径上的数据。 但是，在2025年7月底，已弃用的字段路径将完全移除并在Adobe Experience Platform架构UI中不再可见，数据将仅使用`mediaReporting`字段路径发送。<p>在2025年4月22日之前实施了Analytics Source Connector以将流媒体数据收集到Platform的客户必须迁移其现有配置以使用新的字段路径。 此迁移必须在 2025 年 7 月底之前完成。请联系您的 Adobe Consulting 服务或账户团队以获取迁移支持。在 2025 年 4 月 22 日之后实施 Analytics 源连接器的客户无需采取任何行动。</p> |  | 2025 年 4 月 22 日 |
| **术语更改：将“过滤器”改为“区段”** | 此前，Adobe Customer Journey Analytics 将区段称为“过滤器”。该术语现已与 Adobe Analytics 保持一致。“过滤器”现在改称为“区段”。（显然，搜索筛选器仍称为“筛选器”。）用户界面和文档已更新。 | | 2025 年 4 月 16 日 |
| **拼接：从 XDM IdentityMap 检索持久和临时 ID** | 此功能支持在拼接过程中使用 XDM IdentityMap 中存储的身份标识。IdentityMap 可用于在基于字段的拼接中使用持久 ID 或临时 ID，也可用于在基于图形的拼接中使用持久 ID。您可以使用 identityMap 中的某个特定命名空间或主要身份标识。请在[此处](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/stitching/fbs#identitymap)和[此处](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/stitching/gbs#identitymap)了解详情 |  | 2025年4月28日 |
| **数据视图间共享的量度和维度** | 允许您在多个数据视图中应用维度和量度设置。对某个共享维度或量度所做的更改会应用于所有适用的数据视图中该维度或量度的所有实例。此界面允许 Customer Journey Analytics 管理员在使用许多数据视图时更轻松地管理组件。[了解详情](/help/data-views/shared-metrics-dimensions/smd-overview.md) |  | 2025 年 4 月 30 日 |


## Customer Journey Analytics 中的修复

**Admin Console**：AN-370228
**Analysis Workspace**：AN-371933；AN-371933；AN-371979
**受众**：AN-373032
**组件设置**：AN-367400
**派生字段**：AN-370614；AN-370959
**导出位置**：AN-371670
**完整表导出**：AN-360492；AN-369204；AN-370755；AN-372294；AN-372363；AN-372754；AN-373040；AN-373081；AN-373168
**历程画布**: AN-373294
**移动应用程序**: AN-363169；AN-368496；AN-371766
**产品使用情况**: AN-369501
**报告**: AN-369085；AN-371094；AN-372580


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
