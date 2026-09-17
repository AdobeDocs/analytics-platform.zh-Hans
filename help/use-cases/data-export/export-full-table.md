---
title: Customer Journey Analytics导出完整表
description: 描述如何使用导出完整表功能验证您的数据或将数据用于AI/ML。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: ee004948-3025-434b-a90b-8aa185800820
autotag-review: '2026-05-19T09:39:35.989Z'
TQID: 'https://experienceleague.adobe.com/5lP3PKpCpxkeyH34327gieZ48KFkEai4DF2SC0H4E2U'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
  - id: f24857a4-4b64-4b25-b237-d43026362144
    internal-label: BI extension
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 4%
---
# 导出整个表

本文概述如何使用[!DNL Export full table]功能实现以下[数据导出用例](overview.md)：

* 数据验证
* 为AI/ML做好准备

## 简介

使用[!DNL Customer Journey Analytics Full Table Export]导出数据允许您从Customer Journey Analytics Analysis Workspace中的自由格式表中导出数据。

![BI扩展](../assets/export-full-table.png)

## 更多信息

要将您在Analysis Workspace中创建的任何自由格式表的完整内容直接导出到指定的云目标，请使用导出完整表功能。

导出完整表格每个报表最多支持10个维度和10个量度，包括计算量度和分段。 根据您的许可证层，每次导出可导出300万、3000万、1.5亿或3亿行，这超过了其他导出方法50000行的限制。 支持的目标包括Adobe Experience Platform Data Landing Zone、Google Cloud Platform、Microsoft Azure、Amazon S3和Snowflake。 有关详细信息，请参阅[完全表导出的优点](/help/analysis-workspace/export/export-cloud.md#advantages)。

有关详细信息，请参阅有关[将Customer Journey Analytics报表导出到云](/help/analysis-workspace/export/export-cloud.md)的详细文档。
