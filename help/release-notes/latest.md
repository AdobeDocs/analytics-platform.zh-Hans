---
title: 当前 Customer Journey Analytics 发行说明
description: 查看最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: b2cb99696145efe59507831d066382648741f479
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 18%

---

# 当前 Adobe Customer Journey Analytics 发行说明（2025 年 8 月）

**上次更新日期**：2025年8月14日


这些发行说明涵盖2025年8月13日至9月16日的发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **地图可视化图表** | 地图可视化是Analysis Workspace中的一个可视化图表，允许您构建任何量度（包括计算量度）的可视地图。 它有助于识别和比较不同地理区域之间的量度数据。<p>以前，地图可视化仅在Adobe Analytics中可用。</p><p>Customer Journey Analytics中的地图可视化图表包含对Adobe Analytics中的地图可视化图表的以下改进：</p><ul><li>使用数据视图中的任何区段作为数据源。</li><li>通过在数据视图中配置维度，精确到单表。</li><li>新的选择工具允许您根据在可视化图表中选择的任何区域创建区段、受众、趋势或划分。</li></ul><p>有关详细信息，请参阅[映射](/help/analysis-workspace/visualizations/map.md)。</p> | 2025年8月13日 | 2025 年 8 月 25 日 |
| **实时报告** | Customer Journey Analytics中的实时报表可实时显示和更新Analysis Workspace中一个或多个面板的数据和可视化图表。 | | 2025年9月15日（原计划于2025年8月15日发布） |
| **B2B模板** | 如果您许可Customer Journey Analytics B2B edition，则现在可以从Adobe模板UI中获得以下附加的B2B模板： <ul><li>B2B 帐户参与度概述</li><li>B2B 机会参与概述</li><li>B2B 购买群组活动</li></ul><p>（文档链接见下文。）</p> |  | 2025年8月15日 |
| **以 PDF 格式下载的项目将保存到您的工作站** | 将项目下载为PDF时，PDF将下载到您工作站上的下载文件夹中。 <p>以前，将项目下载为PDF会在新的浏览器选项卡中启动一个具有唯一URL的PDF。</p><p>有关详细信息，请参阅[下载项目和数据](/help/analysis-workspace/export/download-send.md)。</p> |  | 2025 年 8 月 25 日 |
| **支持临时架构** | [临时架构](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/tutorials/ad-hoc)用于Experience Platform的各种数据摄取工作流，包括摄取CSV文件和创建特定类型的源连接。 <p>此功能支持在Customer Journey Analytics中使用临时架构。 作为连接定义的一部分，您现在可以选择基于临时架构的数据集，并在数据视图和工作区项目中使用这些数据。</p> <p>（文档链接见下文。）</p> |  | 2025年8月28日 |
| **连接中的拼接** | 简化了Customer Journey Analytics拼合。 现在，可以在将数据摄取到Customer Journey Analytics时进行拼合，而不是复制数据集并对复制的数据集应用拼合，这样便不再需要使用重复的数据集和架构。 <p>此外，您现在可以从更新的连接UI启动拼接，而不必通过客户支持请求拼接。</p><p> *由于需要进行额外的工作，将推送以前通知的发布日期。 新的发布日期与假日季节重叠，这会引入其他发布限制。 现在计划分阶段推出，以确保稳定性并在假日期间将中断降至最低。*</p> | 2025年10月底 | 2026年1月底 |
| **正在扩展查找键限制** | 根据您的Customer Journey Analytics包，查找数据集中现在最多可以有10亿个唯一密钥。 <p>有关详细信息，请参阅Customer Journey Analytics [护栏](/help/technotes/guardrails.md#data-transfer-limits)文档中的[数据传输限制](/help/technotes/guardrails.md)。</p> |  | 2025年8月29日 |
| **根据Platform架构中的用户定义的映射字段创建量度和维度** | 您在Experience Platform架构中定义的用户定义映射字段现在可以在Customer Journey Analytics中使用。<p>在Customer Journey Analytics中创建量度和维度时，可以使用以下映射字段：</p><ul><li>String to String</li><li>String to Integer</li></ul><p>（文档链接见下文。）</p><p>有关Experience Platform中映射字段的更多信息，请参阅[在UI中定义映射字段](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/ui/fields/map)。</p> |  | 2025年8月底 |
| **删除的项目将通过URL立即不可用，并且将从计划的投放中删除** | 已删除的项目会立即从计划投放中删除，并且不再可通过其URL访问。<p>以前，项目包含在计划交付中，可在删除项目后60天内通过其URL进行访问。</p><p>有关删除项目的详细信息，请参阅[项目概述](/help/analysis-workspace/build-workspace-project/freeform-overview.md)。</p> | | 2025年8月底 |
| **流媒体：更新了用于将流媒体数据收集到Adobe Experience Platform的XDM字段** | 将流媒体数据收集到 Adobe Experience Platform 时，不再使用流媒体参数文档中“XDM 字段路径”标题下显示的 XDM 字段路径。相反，如果在2025年5月9日之前实施了Analytics Source Connector以将流媒体数据收集到Platform，则客户必须将其现有配置迁移到mediaReporting字段路径，如流媒体参数文档的“报告XDM字段路径”标题下所示。<p> 这些字段路径可在以下页面上找到并标记为“已弃用”：[音频和视频参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[广告参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/ad-parameters)、[章节参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/chapter-parameters)、[播放器状态参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/player-state-parameters)和[质量参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/quality-parameters)。 （对于在2025年5月9日后实施Analytics源连接器并且已经在仅使用mediaReporting XDM路径的客户，无需执行任何操作。）</p><p>已弃用的XDM字段路径上的数据摄取将持续到2025年10月底。 之后，已弃用的字段路径将完全删除，并且在Adobe Experience Platform架构UI中将不再可见，数据将仅使用mediaReporting字段路径发送。</p><p>有关详细信息，请参阅[将Analytics Source Connector实施迁移到更新的XDM流媒体字段](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)。</p><p>有关迁移支持，请联系您的Adobe Consulting服务或帐户团队。 </p> |  | 10 月 2025 日 |

## Customer Journey Analytics 中的修复

**Analysis Workspace**： AN-389683、AN-389534、AN-389207、AN-389066、AN-388687、AN-388478、AN-387089、AN-384865、AN-384560、AN-383486、AN-365768、AN-351639
**组件**：
**Content Analytics**：
**引导式分析**： AN-384426
**平台**： AN-384410
**Report Builder**： AN-389336； AN-382775
**报告**：
**分段**：
**共享的量度和维度**：
**Other**： AN-388222； AN-384898； AN-387169


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
