---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新 CJA 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: f961bf0a615199de931a98f14d8b640890df7a2b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 当前Customer Journey Analytics(CJA)发行说明（2022年9月）

**上次更新日期**：2022 年 9 月 9 日

>[!NOTE]
>
>本页包含预发行内容，可能会发生更改。

## 相关资源

* [2022版CJA以前的发行说明](/help/release-notes/2022.md)

* [年 Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)

* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)

* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)

## 主要功能

| 功能 | 描述 | [预定日期](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **Analytics Source Connector 的跨区域支持** | 您现在可以接收来自任何地区（美国、英国或新加坡）的报告包。 但是，这些报告包必须映射到与创建源连接的 Experience Platform 沙盒实例相同的组织。 [了解详情](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans) | 2022 年 8 月 24 日 |
| **首次会话报告** | 了解特定会话是否是用户的首次会话。 [了解详情](/help/data-views/data-views-usecases.md) | 2022 年 8 月 24 日 |
| **CJA实验面板** | 此新的工作区面板允许CJA用户评估任何来源(在线、离线、Adobe解决方案、Adobe Journey Optimizer甚至BYO（自带）数据)的A/B实验的提升度和置信度。 [了解详情](/help/analysis-workspace/c-panels/experimentation.md) | [有限版本](/help/release-notes/releases.md) 自2022年9月14日起 |
| **工作区中的组合图可视化图表** | 通过组合图，您可以在工作区中更轻松、更直观地比较量度。 [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/visualizations/combo-charts.html?lang=en) | 2022 年 9 月 14 日 |

{style=&quot;table-layout:auto&quot;}

## 修复

AN-298412

## CJA 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| **改进的 IP 到地理位置映射** | 2022 年 9 月 9 日 | Adobe 的 IP 查找供应商 Digital Element 正在升级到新的改进数据集 (NetAcuity Pulse)，用于 IP 到地理位置映射。 Adobe Analytics将采用此新数据集 **2022年10月5日**. 新的数据库将比以前的版本更准确。 当采用新数据库时，一些 IP 到地理位置的映射将发生变化/改进。<p> 通过 Analytics Source Connector 提供的 CJA 数据也将自动利用新的映射。 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
