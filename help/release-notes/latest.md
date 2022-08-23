---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新 CJA 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e7ff0bfae0f7d041a8131cecbf362cf71aca9740
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 100%

---

# 当前的 Customer Journey Analytics (CJA) 发行说明（2022 年 8 月）

**上次更新日期**：2022 年 8 月 23 日

## 主要功能

| 功能 | 描述 | [预定日期](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **“媒体并行查看者”面板** | 了解同时观看的人数在哪里达到峰值或在哪里发生下降。获得关于内容质量和观众参与情况的宝贵洞察，并帮助进行故障排除或规划数量和规模。 [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | 2022 年 8 月 9 日 |
| **“Media Playback 耗时”面板** | Media Playback 耗时提供有关查看者参与情况的宝贵洞察，并使媒体组织能够通过具备时段分割功能的高级耗时分析，利用以分钟计的用户参与获得更深入、更精细的洞察。 您可以观察在特定时间点查看媒体流的耗时。您可以按不同的粒度分割播放时长，包括新的 5 分钟、15 分钟和 30 分钟粒度。 [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | 2022 年 8 月 9 日 |
| **将受众发布到实时客户个人资料** | 允许您将在 CJA 中发现的受众发布到 Adobe Experience Platform/实时客户个人资料，以实现客户定位和个性化。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/audiences-overview.html?lang=zh-Hans) | 2022 年 8 月 17 日 |
| **CJA 对数据管理标签和策略的支持** | 自动化 CJA 和 Adobe Experience Platform 隐私标签和策略之间的集成。 在 Platform 使用的数据集上创建的数据标签显示在 CJA 数据视图中，用以阻止或警告从敏感字段创建亮度和/或维度的用户。 此外，从 CJA 导出数据时（通过 Workspace 或 Report Builder 报告、导出、API 等），将添加其他警告或标签，以通知用户报告包含需要以特定方式处理的敏感信息。 [了解详情](/help/data-views/data-governance.md) | 2022 年 8 月 17 日 |
| **CJA 中的日期字段支持** | 允许 CJA 报告日期和日期时间字段。 [了解详情](/help/data-views/data-views-usecases.md#date) | 2022 年 8 月 17 日 |
| **Analytics Source Connector 的跨区域支持** | 您现在可以接收来自任何地区（美国、英国或新加坡）的报告包。 但是，这些报告包必须映射到与创建源连接的 Experience Platform 沙盒实例相同的组织。 [了解详情](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans) | 2022 年 8 月 24 日 |
| **首次与重复会话报告** | 现在，您可以发现某个特定会话是否是用户的首次会话。 [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=zh-Hans#new-repeat) | 2022 年 8 月 24 日 |

{style=&quot;table-layout:auto&quot;}

## 修复

AN-297141

## CJA 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| **改进的 IP 到地理位置映射** | 2022 年 7 月 11 日 | Adobe 的 IP 查找供应商 Digital Element 正在升级到新的改进数据集 (NetAcuity Pulse)，用于 IP 到地理位置映射。 Adobe Analytics 将在 **2022 年 10 月**&#x200B;采用此新数据集。 新的数据库将比以前的版本更准确。 当采用新数据库时，一些 IP 到地理位置的映射将发生变化/改进。<p> 通过 Analytics Source Connector 提供的 CJA 数据也将自动利用新的映射。 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
