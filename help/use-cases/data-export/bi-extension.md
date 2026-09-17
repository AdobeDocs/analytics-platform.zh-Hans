---
title: Customer Journey Analytics BI 扩展
description: 描述如何使用BI扩展将数字数据引入您自己的BI工具或数据湖以与其他数据集一起使用。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 669a1305-3e37-4ca2-8178-a89a27958e5d
autotag-review: '2026-05-19T08:00:39.048Z'
TQID: 'https://experienceleague.adobe.com/BgO7hQlR2J3o-nD38ZIg2ILUTwDKGfSXu-i-bEo5SJs'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: f24857a4-4b64-4b25-b237-d43026362144
    internal-label: BI extension
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 25%
---
# BI 扩展

本文概述如何使用[!DNL Customer Journey Analytics BI extension]实现以下[数据导出用例](overview.md)：

* Data Lake、Data Warehouse或BI工具

## 简介

使用[!DNL Customer Journey Analytics BI extension]导出数据允许您从Customer Journey Analytics数据视图中导出数据。

![BI扩展](../assets/bi-extension.png)

## 更多信息

通过 [!DNL Customer Journey Analytics BI extension]，SQL 可访问您在 Customer Journey Analytics 中定义的[数据视图](/help/data-views/data-views.md)。 您的数据工程师和分析人员更熟悉Power BI、Tableau或其他业务智能和可视化工具（进一步称为BI工具）。 他们现在可以基于 Customer Journey Analytics 用户在创建 Analysis Workspace 项目时使用的相同数据视图来创建报告和仪表板。

BI扩展会返回聚合的数据，而不是原始事件级别的行。 默认情况下，每个查询在30天的日期范围内返回50行，但您可以将行限制覆盖为最多50,000行，并将日期范围覆盖为您自己的自定义范围。 有关详细信息，请参阅[默认值和限制](../../data-views/bi-extension.md#defaults-and-limitations)。

有关详细信息，请参阅有关[BI扩展](../../data-views/bi-extension.md)的详细文档。
