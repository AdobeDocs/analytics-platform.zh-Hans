---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a5710e2d978661837016db5ed1bab5a53fb2d63e
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 76%

---

# 当前Adobe Customer Journey Analytics发行说明（2023年10/11月）


**上次更新日期**：2023 年 10 月 26 日

这些发行说明涵盖2023年10月16日至2023年11月底的发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **中的新功能 [!UICONTROL 使用情况] 在Adobe Product Analytics中查看** | 下列功能已添加到 [使用情况视图](/help/guided-analysis/types/usage.md)：<ul><li>**趋势线**：现在支持趋势线。 单击 [!UICONTROL 叠加] 在图表上方启用它们。</li><li>**查询划分**：您现在可以将划分应用于此视图类型。 它们作为查询边栏中的选项提供。</li></ul> | 不适用 | 2023 年 10 月 25 日 |
| **CJA数据视图API文档** | 请参阅 [数据视图API](https://developer.adobe.com/cja-apis/docs/endpoints/dataviews/) 了解如何以编程方式创建、修改或删除数据视图。 | 不适用 | 2023 年 10 月 16 日 |
| **将全表导出到云** | 通过 Customer Journey Analytics 全表导出，可将数百万个 Workspace 行导出到云目标。 <p>导出全表可一次性或按计划投放在 Workspace 中设计的数据表，其中支持最多五个细分、五个量度、过滤器和计算量度，所有这些都在一个连接在一起的表中。它从 Adobe Analytics 中的 Data Warehouse 报告演化而来，具有许多当今在 Data Warehouse 中不提供但经常有人要求提供的新功能。</p><p> 云导出选项包括：</p><ul><li>Adobe Experience Platform 数据登陆区</li><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Snowflake</li></ul>有关详细信息，请参阅[将 Customer Journey Analytics 报告导出到云](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html)。 | 2023 年 10 月 4 日 | 2023 年 10 月 19 日 |
| **报告活动管理器** | 通过报告活动管理器，可查看组织中每个连接的报告容量。通过它，管理员可详细了解报告消耗情况，从而轻松地诊断和修复在报告高峰期出现的容量问题。报告活动管理器的主要功能包括：<ul><li>取消当前的报告请求（包括从引导式分析和全表导出提出的请求）</li><li>对所定义的时段限制后续请求</li></ul>除了取消当前请求之外，管理员现在还可对所定义的时段限制请求。管理员可以按请求、项目或用户限制请求。[了解详情](/help/reporting-activity-manager/reporting-activity-overview.md) | 2023 年 10 月 17 日 | 2023 年 10 月 24 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-327661； AN-329282； AN-329383； AN-329808； AN-331030； AN-331087； AN-331105

## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 | 不适用 | 不适用 |

{style="table-layout:auto"}

## 相关资源

* [之前的 2023 Customer Journey Analytics 发行说明](/help/release-notes/2023.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
