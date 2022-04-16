---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新 CJA 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 56f62d8af96e64a6867e38a9701219bcefc62a6a
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 15%

---

# 当前Customer Journey Analytics(CJA)发行说明（2022年4月）

>[!NOTE]
>
>本页包含可能发生更改的预发行信息。

**上次更新**:2022年4月13日

## 主要功能

| 功能 | 描述 | [预定日期](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Dimension子字符串 | 提供多种方法来提取字符串的所需部分，以用作维度项目。 此功能还允许您在字符串包含分隔值时将字符串维度视为数组。 [了解详情](../data-views/component-settings/substring.md) | 2022 年 4 月 20 日 |
| Analytics Source Connector的数据准备 | 的 [Analytics源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans) 现已与集成 [数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) 功能。Adobe Experience Platform Adobe Real-time Customer Data Platform(RTCDP)、CJA和Adobe Journey Optimizer(AJO)客户现在可以通过其他字段组扩展Analytics字段组。 他们还可以利用100多个数据准备操作员，在将数据摄取到Adobe Experience Platform(AEP)期间扩充Analytics数据。 RTCDP客户现在可以为配置文件启用多个支持数据准备的报表包。<p>现在，通过Analytics源连接器摄取多个报表包的CJA客户可以在报表包之间取消对列差异的冲突。 例如，如果“搜索词”存储在 `eVar1` 在一个报表包中 `eVar2` 在另一个报表包中，使用数据准备，您可以通过合并两个eVar中的值的新列来扩展Analytics字段组。 | 2022 年 4 月 25 日 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
