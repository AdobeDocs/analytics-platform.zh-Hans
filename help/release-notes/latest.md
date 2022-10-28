---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新 CJA 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 07842c9f1e2f4708d0881dec75c067d93611626c
workflow-type: ht
source-wordcount: '590'
ht-degree: 100%

---

# Customer Journey Analytics (CJA) 发行说明（2022 年 10 月/11 月）

**上次更新时间**：2022 年 10 月 25 日

Customer Journey Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 主要功能及更新

| 功能 | 描述 | [开始推出](/help/release-notes/releases.md) | [正式发布](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **[!UICONTROL 关键指标摘要]可视化** | 通过[!UICONTROL 关键指标摘要]可视化，可了解某个重要的指标在单个时间范围内的趋势如何。通过它，还可比较指标在两个时间范围内的表现。[了解详情](/help/analysis-workspace/visualizations/key-metric.md) | 2022 年 10 月 5 日 | 2022 年 10 月 19 日 |
| **不区分大小写的多值变量** | 对于不区分大小写的多值变量，存储在 `mvvar1` 至 `mvvar3` 中的值将不再自动变为小写。而是通过 Analytics Source Connector 传递到 Adobe Experience Platform 和 CJA 的数据将反映从页面传入的原有大小写形式。 | 不适用 | 2022 年 10 月 24 日 |
| **CJA 审核日志** | Customer Journey Analytics (CJA) 允许您通过“审核日志”的形式审核各种服务和功能的用户活动。这些日志形成审核记录，可以帮助解决问题，并帮助您的企业有效遵守公司数据管理政策和监管要求，例如“健康保险流通与责任法案”(HIPAA)。这些日志以前只能通过审核日志 API 获得。[了解详情](/help/privacy/audit-log.md) | 不适用 | 2022 年 10 月 26 日 |
| **HIPAA 准备就绪** | Adobe 现在仅支持 Healthcare Shield 客户在 Customer Journey Analytics 和其他基于 Experience Platform 的应用程序中接收、使用、维护或传输受保护的健康信息。Healthcare Shield 仅适用于美国的受保实体或业务伙伴的医疗保健客户。[了解详情](https://www.adobe.com/trust/compliance/hipaa-ready.html) | 不适用 | 2022 年 11 月 7 日 |
| **计划项目的密码保护** | 此功能是 HIPAA 就绪的一部分，仅适用于 Healthcare Shield 客户。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html#password) | 不适用/ | 2022 年 11 月 7 日。 |

{style=&quot;table-layout:auto&quot;}

## 修复

* 修复了最近的 MacOS 版本被错误地命名为“Macintosh”的问题。通过此修复，操作系统维度将开始使用“MacOS”版本编号（从 MacOS 11 开始）。(AN-301834)

### 其他修复

AN-302367；AN-302562；AN-304036

## CJA 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| **默认登陆页面** | 2023 年 9 月 29 日 | 今年早些时候引入的[新登陆页面](/help/getting-started/landing.md)在 **2023 年 1 月**&#x200B;将成为所有用户的默认体验。当前页面将被弃用，每个人都将必须使用新体验。 |
| **改进了 IP 到地理位置的映射** | 2022 年 9 月 29 日 | Adobe 的 IP 查找供应商 Digital Element 正在升级到经过改进的新数据集 (NetAcuity Pulse) 以进行 IP 到地理位置映射。Adobe Analytics 已推迟到 **2023 年 1 月**&#x200B;采用此新数据集。新的数据库将比以前的版本更准确。 当采用新数据库时，一些 IP 到地理位置的映射将发生变化/改进。<p> 通过 [!UICONTROL Analytics Source Connector] 提供的 CJA 数据也将自动利用新映射。 |
| **[!UICONTROL 异常检测]自动运行条件** | 2022 年 9 月 29 日 | 现在对时间序列自由格式表的所有列都自动运行[!UICONTROL 异常检测]。为了确保有数据可用于分析并加快项目加载，Adobe 将更改[!UICONTROL 异常检测]自动运行的方式。从 **2022 年 10 月 26 日**&#x200B;起，将对表中的第一个指标列自动运行异常检测。如果需要，可配置列设置以对其他列运行[!UICONTROL 异常检测]。 |

{style=&quot;table-layout:auto&quot;}


## 相关资源

* [以前的 2022 年 CJA 发行说明](/help/release-notes/2022.md)

* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)

* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)

* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)

* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
