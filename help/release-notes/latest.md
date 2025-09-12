---
title: 当前 Customer Journey Analytics 发行说明
description: 查看最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 79e120b4362fe226debaeaea94da7e6b52c7e24a
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 56%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2025 年 9 月）

**上次更新日期**：2025年9月11日


这些发行说明涵盖2025年9月至10月初的发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **使用界面的更新** | [使用界面](/help/connections/manage-connections.md#usage)现在添加了有关核心数据量和平均行大小的信息。<p>有关详细信息，请参阅[管理连接](/help/connections/manage-connections.md#usage)。</p> | | 2025 年 9 月 4 日 |
| 将项目和组件迁移到Customer Journey Analytics时的&#x200B;**改进** | 现在，将项目和组件从Adobe Analytics迁移到Customer Journey Analytics时，可使用以下改进：<ul><li>同时迁移多个项目。<br/>您一次最多可以迁移20个项目。<br/>以前，一次只能迁移一个项目。</li><li>更新已经与上一次项目迁移映射的维度和量度的映射。<br/>现在，每次迁移项目时，您都可以更新这些映射，即使以前使用以前的迁移来映射相同的维度和量度也是如此。<br/>以前，您选择的所有映射对于所有未来的项目迁移都是永久的。</li><li>提高了拥有大量项目的组织的性能。</li></ul><p>可在Adobe Analytics界面中找到此功能。 有关详细信息，请参阅[将组件和项目从Adobe Analytics迁移到Customer Journey Analytics](https://experienceleague.adobe.com/zh-hans/docs/analytics/admin/admin-tools/component-migration/component-migration)。</p> | 2025年9月15日 | 2025年9月18日 |
| **查找密钥限制提高至10亿** | 查找数据集的唯一键的最大数量现在增至10亿，具体取决于您的Customer Journey Analytics权限。 <p>以前，所有权利的最大数量为1000万。<p>有关详细信息，请参阅[护栏](/help/technotes/guardrails.md)。</p> | | 2025年9月18日 |
| **支持临时架构** | [临时架构](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/tutorials/ad-hoc)用于Experience Platform的各种数据摄取工作流，包括摄取CSV文件和创建特定类型的源连接。 <p>此功能支持在Customer Journey Analytics中使用临时架构。 作为连接定义的一部分，您现在可以选择基于临时架构的数据集，并在数据视图和工作区项目中使用这些数据。</p> <p>（文档链接见下文。）</p> |  | 2025 年 9 月 18 日（原计划于 2025 年 8 月 28 日发布） |
| **实时报告** | Customer Journey Analytics 中的实时报告功能可以实时显示并更新 Analysis Workspace 的一个或多个面板中的数据和可视化图表。<br/><br/>（文档链接随后提供。） | | 2025 年 9 月 18 日（原计划于 2025 年 8 月 15 日发布） |
| **支持数据镜像** | 通过为Experience Platform中的特定源连接器支持基于模型的架构和更改数据捕获(CDC)功能，Customer Journey Analytics将能够为Snowflake、Databricks和Google BigQuery支持Data Warehouse解决方案的数据镜像功能。 <p>请联系您的Adobe客户团队以访问测试版。</p><p>（文档链接见下文。）</p> | Beta于9月24日开始发布 | 待定 |
| **流媒体：更新了用于将流媒体数据收集到 Adobe Experience Platform 的 XDM 字段** | 将流媒体数据收集到 Adobe Experience Platform 时，不再使用流媒体参数文档中“XDM 字段路径”标题下显示的 XDM 字段路径。在 2025 年 5 月 9 日之前实施了 Analytics 源连接器以将流媒体数据收集到平台的客户，必须将其现有配置迁移到 mediaReporting 字段路径，参见流媒体参数文档中“报告 XDM 字段路径”标题下的段落。<p> 这些字段路径位于以下页面并标记为“已弃用”：[音频和视频参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/audio-video-parameters)、[广告参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/ad-parameters)、[章节参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/chapter-parameters)、[播放器状态参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/player-state-parameters)和[质量参数](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/implementation/variables/quality-parameters)。（2025 年 5 月 9 日之后实施 Analytics 源连接器，并且只使用 mediaReporting XDM 路径的客户无需采取任何行动。）</p><p>在已弃用的 XDM 字段路径上的数据摄取将继续进行，直到 2025 年 10 月底。之后，已弃用的字段路径将被完全移除，并且不再显示在 Adobe Experience Platform Schema UI 中，届时起将只使用 mediaReporting 字段路径发送数据。</p><p>有关详细信息请参阅[将 Analytics 源连接器实施迁移到更新后的 XDM 流媒体字段](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/xdm-updates/updated-xdm-fields)。</p><p>请联系您的 Adobe Consulting 服务或帐户团队以获取迁移支持。 </p> |  | 2025 年 10 月 |
| **连接中的拼接** | 简化 Customer Journey Analytics 拼接。现在不再需要复制数据集后对复制的数据集进行拼接，而是在将数据摄取到 Customer Journey Analytics 中时进行拼接，这样就无需再复制数据集和架构。 <p>此外，您现在无需再通过客户支持部门请求拼接，而是可以从更新后的 Connections UI 自行启动拼接功能。</p><p> *由于需要更多工作，之前公布的发布日期被推迟。新的发布日期与假期重叠，因此额外限制了发布。目前正计划分阶段推出，以确保稳定性，并尽量减少假期的干扰。*</p> <p>（文档链接见下文。）</p> | 2025 年 10 月底 | 2026 年 1 月底 |

## Customer Journey Analytics 中的修复

**Analysis Workspace**： AN-391719、AN-380838、AN-389402、AN-389373、AN-390851、AN-391593、AN-391404、AN-393064、AN-379337
**组件**： AN-393810
**Content Analytics**：
**引导式分析**：
**平台**：
**Report Builder**： AN-387741、AN-386777、AN-388720、AN-389343
**报告**： AN-391439、AN-391228、AN-393620、AN-393640、AN-391334、AN-393304
**分段**：
**计划报告**： AN-391150、AN-390474
**共享的量度和维度**：
**Other**： AN-387858


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
