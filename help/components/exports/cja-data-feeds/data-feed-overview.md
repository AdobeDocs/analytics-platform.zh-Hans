---
description: 了解如何使用数据馈送从Customer Journey Analytics导出原始事件级数据，查看先决条件，并查找开始使用所需的文章。
keywords: 点击流;数据馈送;数据馈送;数据馈送
title: Customer Journey Analytics数据馈送概述
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
autotag-review: '2026-05-19T08:45:11.428Z'
TQID: 'https://experienceleague.adobe.com/TO8lEW8-GE-sIGj3vmm0X1zCgpg-0VpS1wjs0-HQjg8'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 34959e37a7040bcd861a506968895ad6f051b686
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 1%
---
# 数据馈送概述

{{release-limited-testing}}

数据馈送可将原始事件级数据从Customer Journey Analytics导出到云目标。 您可以在Adobe以外的其他平台（如Data Warehouse）中使用此数据。

数据馈送是从数据视图中的组件构建的。 您包括的每个维度和量度都会成为数据馈送中的一列，并且数据视图设置（如持久性、派生字段和区段）会应用于数据。 文件以Parquet格式传送。

您可以创建以下类型的数据馈送：

* **实时馈送**：每小时或每天导出当前和未来的数据。 每次投放都会在小时或天结束并且处理延迟已过期后发送。

* **回填馈送**：导出过去日期范围的历史数据。

有关数据馈送与其他Customer Journey Analytics导出方法（如完全表导出）的比较，请参阅[Analytics产品比较](/help/getting-started/analytics-product-comparison.md)。

## 先决条件

在使用数据馈送之前，请确保您满足以下所有要求：

* 数据正在被摄取到Customer Journey Analytics，并且已配置连接和[数据视图](/help/data-views/create-dataview.md)。<!-- For more information, see Data ingestion overview - add link -->

* 您的帐户是Customer Journey Analytics产品管理员，或属于对您要使用的数据视图具有&#x200B;[!UICONTROL **数据馈送**]&#x200B;权限（在&#x200B;[!UICONTROL **数据视图工具**]&#x200B;类别中）的产品配置文件。 有关详细信息，请参阅[访问控制](/help/technotes/access-control.md)。<!--Add a Data Feeds row to the Data View Tools permissions table in access-control.md.-->

* 已为[!DNL Amazon S3]、[!DNL Google Cloud Platform]、[!DNL Azure RBAC]或[!DNL Azure SAS]配置云导出帐户和位置。 有关详细信息，请参阅[配置云导出帐户](/help/components/exports/cloud-export-accounts.md)和[配置云导出位置](/help/components/exports/cloud-export-locations.md)。

>[!TIP]
>
>由于对数据视图中的组件所做的更改会影响使用它的每个数据馈送，因此请考虑创建仅用于数据馈送的数据视图。
>
>* **优势**：降低Analysis Workspace报表更改意外更改数据馈送输出的风险。
>
>* **缺点**：您必须与其他数据视图一起维护其他数据视图。

## 快速入门

使用以下文章来规划、迁移和创建数据馈送。

### 规划您的数据馈送

* [在Customer Journey Analytics和Adobe Analytics中比较数据馈送](/help/components/exports/cja-data-feeds/df-comparison.md)：如果您以前使用的是Adobe Analytics数据馈送，请了解功能和概念上的差异。

* [了解数据馈送与Analysis Workspace之间的数据差异](/help/components/exports/cja-data-feeds/df-comparison-workspace.md)：了解为什么数据馈送输出可能与Analysis Workspace中的报表不匹配。

* [数据馈送中的组件可用性](/help/components/exports/cja-data-feeds/df-components.md)：了解数据馈送中需要、不支持或限制哪些维度和量度。

### 从Adobe Analytics数据馈送迁移

1. [准备映射数据馈送列](/help/components/exports/cja-data-feeds/df-column-mapping-prep.md)：了解影响Adobe Analytics列如何映射到Customer Journey Analytics的因素。

1. [将Adobe Analytics数据馈送列映射到Customer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)：查找要保留的每个Adobe Analytics列的Customer Journey Analytics等效项。

### 创建和配置数据馈送

* [创建数据馈送](/help/components/exports/cja-data-feeds/create-feed.md)：选择组件、配置计划并设置投放。

* [数据馈送中的分段](/help/components/exports/cja-data-feeds/df-segmentation.md)：应用区段以过滤数据馈送中的数据。

* [应用数据转换](/help/components/exports/cja-data-feeds/df-data-transformations.md)：使用组件设置、派生字段或SQL转换数据。

* [数据馈送中的子事件组件](/help/components/exports/cja-data-feeds/df-sub-event.md)：了解如何导出数组和映射中的组件以及如何查询它们。

