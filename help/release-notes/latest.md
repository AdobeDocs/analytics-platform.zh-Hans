---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新 CJA 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 3b2a6225d6f94b158e217df4963611cb6d55580e
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 51%

---

# 当前Customer Journey Analytics(CJA)发行说明（2022年7月）

**上次更新日期**：2022 年 7 月 28 日

## 主要功能

| 功能 | 描述 | [预定日期](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| 支持数字字段作为查找键和查找值 | 如果要使用数值字段（如产品 SKU 上的 COGS 或边距）对字符串值进行分类，则此选项非常有用。允许从查找中获取量度有助于将这些数据点纳入报告。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#numeric) | 2022 年 7 月 20 日 |
| 首次会话与重复会话报告 | 您现在可以发现某个特定会话是否是用户的首次会话。 [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat) | 2022 年 8 月 17 日 |
| “媒体并行查看者”面板 | 了解同时观看的人数在哪里达到峰值或在哪里发生下降。获得关于内容质量和观众参与情况的宝贵见解，并帮助进行故障排除或规划数量和规模。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-concurrent-viewers.html) | 2022 年 8 月 31 日 |
| “媒体播放耗时”面板 | 媒体播放逗留时间对查看者参与度提供了有价值的分析，并且通过使用时段划分功能进行高级逗留时间分析，使媒体组织能够通过每分钟的用户参与度获得更深入、更精细的洞察。 您可以观察在特定时间点查看媒体流的耗时。您可以按不同的粒度分割播放时长，包括新的 5 分钟、15 分钟和 30 分钟粒度。 [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/media-playback-timespent/media-playback-time-spent.html) | 2022 年 8 月 31 日 |

{style=&quot;table-layout:auto&quot;}

## 修复

AN-288455；AN-288828；AN-289323

## CJA管理员的重要注意事项

| 注意事项 | 添加或更新的通知 | 描述 |
| --- | --- | --- |
| **改进了IP到地理位置的映射** | 2022 年 7 月 11 日 | Adobe的IP查找供应商Digital Element正在升级到用于IP到地理位置映射的新改进数据集(NetAcuity Pulse)。 Adobe Analytics将在 **2022年10月**、时间范围。 新数据库将比以前的版本更准确。 当采用新数据库时，某些IP到地理映射将发生更改/改进。<p> 通过Analytics源连接器提供的CJA数据还将自动利用新映射。 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
