---
title: 当前 Customer Journey Analytics 发行说明
description: 查看最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f09937e6babca5549b9b78e9c90462673750a4b3
workflow-type: ht
source-wordcount: '1077'
ht-degree: 100%

---

# 当前 Adobe Customer Journey Analytics 发行说明（2025 年 8 月）

**上次更新日期**：2025 年 9 月 4 日


这些发行说明涵盖了 2025 年 8 月 13 日至 2025 年 9 月 16 日的发布期。Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **使用界面的更新** | [使用界面](/help/connections/manage-connections.md#usage)现在添加了有关核心数据量和平均行大小的信息。 | | 2025 年 9 月 4 日 |
| **地图可视化** | 地图可视化是 Analysis Workspace 中的一种可视化功能，可让您构建任何量度（包括计算量度）的可视化地图。此工具用于识别和比较不同地理区域间的量度数据。<p>以前，只有 Adobe Analytics 中提供地图可视化功能。</p><p>Customer Journey Analytics 中的地图可视化功能对 Adobe Analytics 中的地图可视化功能进行了以下改进：</p><ul><li>使用数据视图中的任何区段作为数据源。</li><li>可以配置数据视图中的维度，精确度可达一米。</li><li>使用新的选择工具，您可以在可视化图表中选择任何区域，从选定的区域创建区段、受众、趋势或细分。</li></ul><p>有关更多信息，请参阅[地图](/help/analysis-workspace/visualizations/map.md)。</p> | 2025 年 8 月 13 日 | 2025 年 8 月 25 日 |
| **B2B 模板** | 如果您获得 Customer Journey Analytics B2B Edition 的许可证，就可以从 Adobe 模板 UI 中获取以下额外的 B2B 模板： <ul><li>B2B 帐户参与度概述</li><li>B2B 机会参与度概述</li><li>B2B 购买群组活动</li></ul><p>有关详细信息，请参阅[使用模板](/help/analysis-workspace/templates/use-templates.md)中的 [B2B 模板](/help/analysis-workspace/templates/use-templates.md#b2b-templates)。</p> |  | 2025 年 8 月 15 日 |
| **以 PDF 格式下载的项目将保存到您的工作站** | 当项目以 PDF 格式下载时，文件将被保存到您工作站的下载文件夹中。 <p>此前，将项目以 PDF 格式下载时，会在新的浏览器标签页中打开该 PDF，并生成唯一的 URL。</p><p>更多信息请参阅[下载项目和数据](/help/analysis-workspace/export/download-send.md)。</p> |  | 2025 年 8 月 25 日 |
| **支持临时架构** | [临时架构](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/tutorials/ad-hoc)用于 Experience Platform 的各种数据摄取工作流，包括摄取 CSV 文件和创建某些类型的源连接。 <p>此功能支持在 Customer Journey Analytics 中使用临时架构。作为连接定义的一部分，您现在可以基于临时架构选择一个数据集，然后在数据视图和工作区项目中使用该数据。</p> <p>（文档链接见下文。）</p> |  | 2025 年 9 月 18 日（原计划于 2025 年 8 月 28 日发布） |
| **扩展查找键限制** | 您现在可以在查找数据集中最多拥有 10 亿个唯一键，具体取决于您的 Customer Journey Analytics 包。 <p>有关详细信息，请参阅 Customer Journey Analytics [护栏](/help/technotes/guardrails.md)文档中的[数据传输限制](/help/technotes/guardrails.md#data-transfer-limits)。</p> |  | 2025 年 8 月 29 日 |
| **根据平台架构中用户定义的映射字段创建量度和维度** | 您在 Experience Platform 架构中定义的用户定义映射字段现在可用于 Customer Journey Analytics。<p>您可以使用以下映射字段创建 Customer Journey Analytics 中的量度和维度：</p><ul><li>字符串到字符串</li><li>字符串到整数</li></ul><p>有关更多信息，请参阅[组件设置](/help/data-views/component-settings/overview.md)。</p><p>有关 Experience Platform 中映射字段的更多信息，请参阅[在 UI 中定义映射字段](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/ui/fields/map)。</p> |  | 2025 年 8 月底 |
| **项目一旦删除，就无法再通过 URL 访问，并立即从已计划的投放中删除** | 项目一旦删除，就会立即从已计划的投放中删除，并且无法再通过其 URL 访问。<p>以前，项目包含在已计划的投放中，在删除后 60 天内仍可通过其 URL 访问。</p><p>有关删除项目的更多信息，请参阅[项目概述](/help/analysis-workspace/build-workspace-project/freeform-overview.md)。</p> | | 2025 年 8 月底 |
| **实时报告** | Customer Journey Analytics 中的实时报告功能可以实时显示并更新 Analysis Workspace 的一个或多个面板中的数据和可视化图表。<br/><br/>（文档链接见下文。） | | 2025 年 9 月 18 日（原计划于 2025 年 8 月 15 日发布） |
| **流媒体：更新了用于将流媒体数据收集到 Adobe Experience Platform 的 XDM 字段** | 将流媒体数据收集到 Adobe Experience Platform 时，不再使用流媒体参数文档中“XDM 字段路径”标题下显示的 XDM 字段路径。在 2025 年 5 月 9 日之前实施了 Analytics 源连接器以将流媒体数据收集到平台的客户，必须将其现有配置迁移到 mediaReporting 字段路径，参见流媒体参数文档中“报告 XDM 字段路径”标题下的段落。<p> 这些字段路径位于以下页面并标记为“已弃用”：[音频和视频参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[广告参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/ad-parameters)、[章节参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/chapter-parameters)、[播放器状态参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/player-state-parameters)和[质量参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/quality-parameters)。（2025 年 5 月 9 日之后实施 Analytics 源连接器，并且只使用 mediaReporting XDM 路径的客户无需采取任何行动。）</p><p>在已弃用的 XDM 字段路径上的数据摄取将继续进行，直到 2025 年 10 月底。之后，已弃用的字段路径将被完全移除，并且不再显示在 Adobe Experience Platform Schema UI 中，届时起将只使用 mediaReporting 字段路径发送数据。</p><p>有关详细信息请参阅[将 Analytics 源连接器实施迁移到更新后的 XDM 流媒体字段](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)。</p><p>请联系您的 Adobe Consulting 服务或帐户团队以获取迁移支持。 </p> |  | 2025 年 10 月 |
| **连接中的拼接** | 简化 Customer Journey Analytics 拼接。现在不再需要复制数据集后对复制的数据集进行拼接，而是在将数据摄取到 Customer Journey Analytics 中时进行拼接，这样就无需再复制数据集和架构。 <p>此外，您现在无需再通过客户支持部门请求拼接，而是可以从更新后的 Connections UI 自行启动拼接功能。</p><p> *由于需要更多工作，之前公布的发布日期被推迟。新的发布日期与假期重叠，因此额外限制了发布。目前正计划分阶段推出，以确保稳定性，并尽量减少假期的干扰。*</p> | 2025 年 10 月底 | 2026 年 1 月底 |

## Customer Journey Analytics 中的修复

**Analysis Workspace**：AN-389683；AN-389534；AN-389207；AN-389066；AN-388687；AN-388478；AN-387089；AN-384865；AN-384560；AN-383486；AN-365768；AN-351639
**组件**：
**内容分析**：
**引导式分析**：AN-384426
**平台**：AN-384410
**Report Builder**：AN-389336; AN-382775
**报告**：
**分段**：
**共享量度和维度**：
**其他**：AN-388222；AN-384898；AN-387169


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
