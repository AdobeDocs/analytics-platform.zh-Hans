---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新 CJA 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 8552e2e784cefc842f5105c41dcffc14192d5ceb
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 100%

---

# 当前的 Customer Journey Analytics (CJA) 发行说明（2022 年 9 月）

**上次更新日期**：2022 年 14 月 9 日

## 相关资源

* [以前的 2022 年 CJA 发行说明](/help/release-notes/2022.md)

* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)

* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)

* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)

## 主要功能

| 功能 | 描述 | [预定日期](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Analytics Source Connector 的跨区域支持** | 您现在可以接收来自任何地区（美国、英国或新加坡）的报告包。 但是，这些报告包必须映射到与创建源连接的 Experience Platform 沙盒实例相同的组织。 [了解详情](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) | 2022 年 8 月 24 日 |
| **首次会话报告** | 发现某个特定会话是否是用户的首次会话。[了解详情](/help/data-views/data-views-usecases.md) | 2022 年 8 月 24 日 |
| **CJA 试验性面板** | 该新“工作区”面板允许 CJA 用户从任何来源评估任何 A/B 试验的提升和置信度：在线、离线、Adobe 解决方案、Adobe Journey Optimizer 甚至 BYO (bring-your-own) 数据。[了解详情](/help/analysis-workspace/c-panels/experimentation.md) | [限量发行](/help/release-notes/releases.md)从 2022 年 9 月 14 日开始 |
| **Workspace 中的组合图表可视化** | 组合图表让您在 Workspace 中更轻松、更直观地比较指标。[了解详情](/help/analysis-workspace/visualizations/combo-charts.md) | 2022 年 9 月 14 日 |
| **CJA 对数据管理标签和策略的支持** | 自动化 CJA 和 Adobe Experience Platform 隐私标签和策略之间的集成。 在 Platform 使用的数据集上创建的数据标签显示在 CJA 数据视图中，用以阻止或警告从敏感字段创建亮度和/或维度的用户。 此外，从 CJA 导出数据时（通过 Workspace 或 Report Builder 报告、导出、API 等），将添加其他警告或标签，以通知用户报告包含需要以特定方式处理的敏感信息。 [了解详情](/help/data-views/data-governance.md) | 2022 年 9 月 14 日 |

{style=&quot;table-layout:auto&quot;}

## 修复

AN-298412

## CJA 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| **改进的 IP 到地理位置映射** | 2022 年 9 月 9 日 | Adobe 的 IP 查找供应商 Digital Element 正在升级到新的改进数据集 (NetAcuity Pulse)，用于 IP 到地理位置映射。Adobe Analytics 将在 **2022 年 10 月 5 日**&#x200B;采用此新数据集。新的数据库将比以前的版本更准确。 当采用新数据库时，一些 IP 到地理位置的映射将发生变化/改进。<p> 通过 Analytics Source Connector 提供的 CJA 数据也将自动利用新的映射。 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
