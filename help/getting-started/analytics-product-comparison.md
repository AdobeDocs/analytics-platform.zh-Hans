---
title: Customer Journey Analytics产品比较
description: 比较历程 Analytics报告和导出工具的客户属性，例如Analysis Workspace、Report Builder、完整表格导出、数据馈送、API和MCP。
keywords: 点击流；数据馈送；数据馈送；产品比较；Analysis Workspace；Report Builder；完整表导出
feature: Components
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: e686fca2c77a8f9739298ece01ccf0fa2fe87b3b
workflow-type: tm+mt
source-wordcount: 464
ht-degree: 44%

---


# Analytics产品比较

使用此页面可比较关键属性上的Customer Journey Analytics报告和导出工具，以帮助您根据分析或数据导出需求选择适当的工具。

| 产品名称和帮助链接 | [Analysis Workspace](/help/analysis-workspace/home.md) | [Report Builder](/help/report-builder/rb-overview.md) | [完整表格导出](/help/analysis-workspace/export/export-cloud.md) | [数据源](/help/components/exports/cja-data-feeds/data-feed-overview.md) | [API](https://developer.adobe.com/cja-apis/docs/) | MCP | BI 扩展 | 同事 |
|---|---|---|---|---|---|---|---|---|
| **访问方法** | 浏览器 | Microsoft Excel | 浏览器 | 通过浏览器进行设置 | RESTful API工具 | 与MCP兼容的工具 | BI 工具 | 与MCP兼容的工具 |
| **数据粒度** | 汇总 | 汇总 | 汇总 | 事件 | 汇总 | 汇总 | 汇总 | 汇总 |
| **Experience Cloud ID (ECID) 可用** | 否 | 否 | 否 | 是 | 否 | 否 | 否 | 否 |
| **时间戳可用** | 否 | 否 | 否 | 是 | 否 | 否 | 否 | 否 |
| **处理级别** | 完全处理 | 完全处理，具有单独的实时报表 | 完全处理 | 完全处理 | 完全处理 | 完全处理 | 完全处理 | 完全处理 |
| **应用机器人过滤的位置** | 在[数据流](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/bot-detection)内和/或[CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection)内 | 在[数据流](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/bot-detection)内和/或[CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection)内 | 在[数据流](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/bot-detection)内和/或[CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection)内 | 在[数据流](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/bot-detection)内和/或[CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection)内 |  |  | 在[数据流](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/bot-detection)内和/或[CJA](/help/data-views/derived-fields/derived-fields.md#simple-bot-detection)内 | |
| **可见的行限制（分页前）** | 400 | 50,000 | 限额为 300 万、3000 万、1.5 亿或 3 亿，具体取决于等级 | 依赖层 | 50,000 | 50,000 | 50,000 | 50,000 |
| **多个数据视图** | 是，一个项目可以包含来自多个数据视图的数据 | 是，一个项目可以包含来自多个数据视图的数据 | 否，导出只能包含一个数据视图中的数据 | 否，导出只能包含一个数据视图中的数据 | 否，每个查询只能引用一个数据视图 | 否，每个查询只能引用一个数据视图 | 否，每个查询只能引用一个数据视图 | 是，如果用户提示 |
| **维度列数** | 最多5个 | ? | 最多10 | 无限制 | 最多5个 | ? | ? | ? |
| **量度列数** | ? | ? | 最多10 | 无限制 | ? | ? | ? | ? |
| **区段划分** <br> [了解详情](/help/components/segments/seg-overview.md) | 是 | 是 | 是 | 是，具有[限制](/help/components/exports/cja-data-feeds/df-segmentation.md) | 是 | 是 | 是 | 是 |
| **计算指标** <br> [了解详情](/help/components/calc-metrics/calc-metr-overview.md) | 是 | 是 | 是，具有[限制](/help/analysis-workspace/export/export-cloud.md#calculated-metric-functions-support) | 否 | 是 | 是 | 是 | 是 |
| **派生字段** <br> [了解详情](/help/data-views/derived-fields/derived-fields.md) | 是 | 是 | 是 | 是 | 是 | 是 | 是 | 是 |
| **归因** <br> [了解详情](/help/analysis-workspace/attribution/overview.md) | 是 | 有限制 | 是，具有[限制](/help/analysis-workspace/export/export-cloud.md#attribution-behavior) | 否 | 是 | 是 | 是 | 是 |
| **计划提交** | 是 | 是 | 是 | 是 | — | — | — | — |
| **提交目标** | 电子邮件 | 电子邮件 | Amazon S3、Azure RBAC、Azure SAS、GCP | Amazon S3、Azure RBAC、Azure SAS、GCP | — | — | — | — |

{style="table-layout:auto"}
