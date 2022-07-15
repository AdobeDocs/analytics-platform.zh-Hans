---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新 CJA 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e0f97c42f4b1bea721825a30360f0c44b1f9f85a
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 42%

---

# 当前Customer Journey Analytics(CJA)发行说明（2022年7月）

**上次更新**:2022年7月13日

## 主要功能

| 功能 | 描述 | [预定日期](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| 首次会话与重复会话报告 | 您现在可以发现某个特定会话是否是用户的首次会话。 [了解更多 — 要遵循] | 2022年7月20日 |
| 支持数字字段作为查找键和查找值 | 如果要使用数值字段（如产品 SKU 上的 COGS 或边距）对字符串值进行分类，则此选项非常有用。允许从查找中获取量度有助于将这些数据点纳入报告。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#numeric) | 2022年7月20日 |

## 修复

AN-288455；AN-288828；AN-289323

## CJA管理员的重要注意事项

| 注意事项 | 添加或更新 | 描述 |
| --- | --- | --- |
| 改进了IP到地理位置的映射 | 2022 年 7 月 11 日 | Adobe的IP查找供应商Digital Element正在升级到用于IP到地理位置映射的新改进数据集(NetAcuity Pulse)。 Adobe Analytics将在2022年10月（时间范围）采用这个新数据集。 新数据库将比以前的版本更准确。 当采用新数据库时，某些IP到地理映射将发生更改/改进。<p> 通过Analytics源连接器提供的CJA数据还将自动利用新映射。 |

>[!MORELIKETHIS]
>[Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
