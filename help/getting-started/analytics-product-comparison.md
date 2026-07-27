---
title: Customer Journey Analytics产品比较
description: 比较历程 Analytics报告和导出工具的客户属性，例如Analysis Workspace、Report Builder、完整表格导出、数据馈送、API和MCP。
keywords: 点击流；数据馈送；数据馈送；产品比较；Analysis Workspace；Report Builder；完整表导出
feature: Components
hold: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: d5ecbbc28bc3892a2114de2c73df3287f22cf1a0
workflow-type: tm+mt
source-wordcount: 345
ht-degree: 59%

---


# Analytics产品比较

使用此页面可比较关键属性上的Customer Journey Analytics报告和导出工具，以帮助您根据分析或数据导出需求选择适当的工具。

| 产品名称和帮助链接 | [Analysis Workspace](/help/analysis-workspace/home.md) | [Report Builder](/help/report-builder/rb-overview.md) | [完整表格导出](/help/analysis-workspace/export/export-cloud.md) | [数据源](/help/components/exports/cja-data-feeds/data-feed-overview.md) | [API](https://developer.adobe.com/cja-apis/docs/) | MCP |
|---|---|---|---|---|---|---|
| **访问方法** | 浏览器 | Microsoft Excel | 浏览器 | 通过浏览器进行设置 | RESTful API工具 | 与MCP兼容的工具 |
| **数据粒度** | 汇总 | 汇总 | 汇总 | 事件 | 汇总 | 汇总 |
| **Experience Cloud ID (ECID) 可用** | 否 | 否 | 是 | 是 | 否 | 否 |
| **时间戳可用** | 否 | 否 | 否 | 是 | 否 | 否 |
| **处理级别** | 完全处理 | 完全处理 | 完全处理 | 完全处理 | 完全处理 | 完全处理 |
| **包含机器人筛选器数据** | 否 | 否 | 否 | 否 | 否 | 否 |
| **显示低流量（超出唯一值）**<br> [了解详情](/help/components/dimensions/high-cardinality.md) | 是 | 是 | 否 | 否 | 是 | 是 |
| **可见的行限制（分页前）** | 400 | 50,000 | 无限制 | 无限制 | 50,000 | 50,000 |
| **多个数据视图** | 是 | 是 | 否 | 否 | 是 | 是 |
| **划分数** | 无限制 | 最高 2 | 无限制 | 无限制 | 无限制，跨多个查询运行 | 无限制 |
| **区段划分** <br> [了解详情](/help/components/segments/seg-overview.md) | 是 | 是 | 是 | 是，具有[限制](/help/components/exports/cja-data-feeds/df-segmentation.md) | 是 | 是 |
| **计算指标** <br> [了解详情](/help/components/calc-metrics/calc-metr-overview.md) | 是，具有[归因](/help/analysis-workspace/attribution/overview.md) | 是，具有归因 | 否 | 否 | 是，具有归因 | 是，具有归因 |
| **派生字段** <br> [了解详情](/help/data-views/derived-fields/derived-fields.md) | 是 | 是 | 是 | 是 | 是 | 是 |
| **同类群组分析** | [是](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | 否 | 否 | 否 | 否 | 否 |
| **归因** <br> [了解详情](/help/analysis-workspace/attribution/overview.md) | 是 | 有限制 | 否 | 否 | 是 | 是 |
| **策划**<br> [了解详情](/help/analysis-workspace/curate-share/curate.md) | 是，在项目和数据视图中可用 | 否 | 否 | 是，在数据视图中 | 是，在数据视图中 | 是，在数据视图中 |
| **项目共享**<br> [了解详情](/help/analysis-workspace/curate-share/share-projects.md) | 是，具有项目角色 | 否 | 否 | 否 | 否 | 否 |
| **计划提交** | 是 | 是 | 是 | 是 | 否 | 否 |
| **提交目标** | 电子邮件 | 电子邮件 | Amazon S3、Azure RBAC、Azure SAS、GCP | Amazon S3、Azure RBAC、Azure SAS、GCP | — | — |
| **数据视图报告时间处理** <br> [了解详情](/help/data-views/data-views.md) | 是 | 是 | 否 | 否 | 是 | 是 |

{style="table-layout:auto"}
