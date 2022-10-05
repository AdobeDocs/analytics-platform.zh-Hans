---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新 CJA 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: fc1a5b1b0f01ace6207820e2421d1770f68c3583
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Customer Journey Analytics(CJA)发行说明（2022年10月）

**上次更新**:2022年10月5日

Customer Journey Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 相关资源

* [以前的 2022 年 CJA 发行说明](/help/release-notes/2022.md)

* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)

* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)

* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)

## 主要功能

| 功能 | 描述 | [预定日期](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **实验面板** | 该新”工作区“面板允许 CJA 用户从任何来源评估任何 A/B 试验的提升和置信度：在线、离线、Adobe 解决方案、Adobe Journey Optimizer 甚至 BYO 数据。 [了解详情](/help/analysis-workspace/c-panels/experimentation.md) | 2022 年 10 月 5 日 |
| **[!UICONTROL 关键量度摘要] 可视化** | 的 [!UICONTROL 关键量度摘要] 通过可视化图表，您可以了解重要量度在单个时间范围内的趋势。 它还允许您在两个时间范围内比较量度表现。 了解详情 | 从2022年10月5日开始分阶段推出 |
| **CJA 中的日期字段支持** | 允许 CJA 报告日期和日期时间字段。 [了解详情](/help/data-views/data-views-usecases.md#date) | 2022 年 10 月 5 日 |
| **移动设备应用程序：自定义详细信息视图** | 通过自定义详细信息视图，您可以更加有针对性地了解您与受众共享的哪些信息，具体方法是让受众重点关注最重要的内容。 您可以更改与每个记分卡图块关联的详细信息视图的布局，并可以添加文本以更好地说明最终用户在数据中可能看到的内容。 [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=zh-Hans) | 2022 年 10 月 5 日 |

{style=&quot;table-layout:auto&quot;}

## CJA 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| **默认登陆页面** | 2023年9月29日 | 的 [新登陆页面](/help/getting-started/landing.md) 今年早些时候引入的体验将成为 **2023年1月**. 当前页面将被弃用，每个人都需要使用新体验。 |
| **改进的 IP 到地理位置映射** | 2022 年 9 月 29 日 | Adobe 的 IP 查找供应商 Digital Element 正在升级到新的改进数据集 (NetAcuity Pulse)，用于 IP 到地理位置映射。Adobe Analytics已将此新数据集的采用推迟到 **2023年1月**. 新的数据库将比以前的版本更准确。 当采用新数据库时，一些 IP 到地理位置的映射将发生变化/改进。<p> 通过 [!UICONTROL Analytics源连接器] 还将自动利用新映射。 |
| **[!UICONTROL 异常检测] 自动运行条件** | 2022 年 9 月 29 日 | 今天， [!UICONTROL 异常检测] 自动在时间序列自由格式表的所有列上运行。 为确保数据能够更快地用于分析和项目加载，Adobe将更改 [!UICONTROL 异常检测] 自动运行。 开始 **2022年10月26日**，异常检测将仅在表中的第一个量度列上自动运行。 您可以配置要运行的列设置 [!UICONTROL 异常检测] （如果需要）。 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
