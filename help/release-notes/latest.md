---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新 CJA 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 45e4a60b6bbf38e33f307dbbbf68ab3124dd6a33
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 90%

---

# Customer Journey Analytics (CJA) 发行说明（2022 年 10 月）

**上次更新时间**：2022 年 10 月 13 日

Customer Journey Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 相关资源

* [以前的 2022 年 CJA 发行说明](/help/release-notes/2022.md)

* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)

* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)

* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)

## 主要功能和更新

| 功能 | 描述 | [预定日期](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| **“试验”面板** | 通过这个新的“工作区”面板，CJA 用户可从在线、离线、从 Adobe 解决方案、Adobe Journey Optimizer 甚至 BYO 数据等任何来源评估任何 A/B 试验的提升和置信度。[了解详情](/help/analysis-workspace/c-panels/experimentation.md) | 2022 年 10 月 5 日 |
| **[!UICONTROL 关键指标摘要]可视化** | 通过[!UICONTROL 关键指标摘要]可视化，可了解某个重要的指标在单个时间范围内的趋势如何。通过它，还可比较指标在两个时间范围内的表现。了解详情 | 已从 2022 年 10 月 5 日开始分阶段推出 |
| **CJA 中的日期字段支持** | 允许 CJA 报告日期和日期时间字段。 [了解详情](/help/data-views/data-views-usecases.md#date) | 2022 年 10 月 5 日 |
| **移动应用程序：自定义详细信息视图** | 通过自定义详细信息视图，可通过让受众关注最重要的内容而使与受众共享的信息更有针对性。可更改与每个记分卡图块关联的详细视图的布局，并可添加文本以更好地解释最终用户可能在数据中看到的内容。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=zh-Hans) | 2022 年 10 月 5 日 |
| **不区分大小写的多值变量** | 对于不区分大小写的多值变量，存储在mvvar1 - mvvar3中的值将不再自动转换为小写。 相反，通过Analytics源连接器传递到Adobe Experience Platform和CJA的数据将反映从页面传入的原始大小写。 | 2022 年 10 月 24 日 |

{style=&quot;table-layout:auto&quot;}

## CJA 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| **默认登陆页面** | 2023 年 9 月 29 日 | 今年早些时候引入的[新登陆页面](/help/getting-started/landing.md)在 **2023 年 1 月**&#x200B;将成为所有用户的默认体验。当前页面将被弃用，每个人都将必须使用新体验。 |
| **改进了 IP 到地理位置的映射** | 2022 年 9 月 29 日 | Adobe 的 IP 查找供应商 Digital Element 正在升级到经过改进的新数据集 (NetAcuity Pulse) 以进行 IP 到地理位置映射。Adobe Analytics 已推迟到 **2023 年 1 月**&#x200B;采用此新数据集。新的数据库将比以前的版本更准确。 当采用新数据库时，一些 IP 到地理位置的映射将发生变化/改进。<p> 通过 [!UICONTROL Analytics Source Connector] 提供的 CJA 数据也将自动利用新映射。 |
| **[!UICONTROL 异常检测]自动运行条件** | 2022 年 9 月 29 日 | 现在对时间序列自由格式表的所有列都自动运行[!UICONTROL 异常检测]。为了确保有数据可用于分析并加快项目加载，Adobe 将更改[!UICONTROL 异常检测]自动运行的方式。从 **2022 年 10 月 26 日**&#x200B;起，将对表中的第一个指标列自动运行异常检测。如果需要，可配置列设置以对其他列运行[!UICONTROL 异常检测]。 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
