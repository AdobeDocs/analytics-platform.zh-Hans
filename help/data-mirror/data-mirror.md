---
title: Data Mirror概述
description: 了解如何在Data Warehouse本机解决方案和Customer Journey Analytics之间同步数据
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
autotag-review: '2026-05-19T08:55:53.979Z'
TQID: 'https://experienceleague.adobe.com/10YCh2cnMTVriKKVOyYfzFfngvGQ2VVHOxzedE5NpWA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 2b0204c229a7d53c0a497fe448c165acf84536ad
workflow-type: tm+mt
source-wordcount: 455
ht-degree: 3%

---

# Experience Platform Data Mirror概述

Data Mirror是一项Experience Platform功能，允许使用关系架构将外部数据库中的行级更改引入数据湖。 它保留数据关系，强制唯一性，并支持版本控制，而无需上游提取、转换和加载(ETL)过程。

使用Experience Platform Data Mirror可将外部数据仓库本机解决方案（[!DNL Snowflake]、[!DNL Azure Databricks]或[!DNL Google BigQuery]）中的插入、更新和删除（可变数据）直接与Experience Platform中的数据同步。 在将数据引入Experience Platform时，Data Mirror可帮助您保持现有的数据库模型结构和数据完整性。

## 功能和优点

Data Mirror提供了以下基本数据库同步功能：

* **主键强制。** 确保数据集内的唯一性，并防止在摄取期间出现重复记录。
* **行级更改引入。** 支持粒度数据更改，包括精确控制的更新插入和删除操作。
* **架构关系。** 通过描述符启用数据集之间的外键和主键关系。
* **无序事件处理。** 使用版本和时间戳描述符处理更改事件，即使它们不按顺序到达也是如此。
* **直接仓库集成。** 与受支持的云数据仓库连接，以便实时进行更改同步。

使用Data Mirror直接从源系统中摄取更改，强制实施架构完整性，并将数据用于Analytics、Journey Orchestration和合规性工作流。 Data Mirror通过启用现有数据库模型的直接镜像，消除了复杂的上游ETL流程并加快了实施。 这种消除可以通过精确控制删除和数据卫生操作来加强数据治理。

另请参阅有关Data Mirror[&#128279;](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}的Experience Platform文档。

## 适用于Customer Journey Analytics的Data Mirror

>[!NOTE]
>
>Data Mirror是一项功能，它支持使用更改数据捕获(CDC)同步选定数据仓库中的数据，以便在Customer Journey Analytics中进行分析。<br/>请参阅适用的产品说明，以了解此功能如何影响年度摄取限制消耗。
>

>[!IMPORTANT]
>
>您在Experience Platform中为Data Mirror for Customer Journey Analytics而创建的更改数据捕获数据集不应在其他Experience Platform解决方案（如Real-Time Customer Data Platform或Journey Optimizer）中重复使用。 如果要对这些解决方案使用相同的数据，请考虑使用相同数据创建替代数据集。
>



适用于Customer Journey Analytics的Experience Platform Data Mirror适用于选定的Data Warehouse本机解决方案（[!DNL Azure Databricks]、[!DNL Google BigQuery]和[!DNL Snowflake]）。 Customer Journey Analytics版本的Experience Platform Data Mirror需要正确配置以下应用程序或组件：

* [数据仓库原生解决方案](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Data Mirror快速入门指南：镜像并使用关系数据](relational.md)
>[Data Mirror （Experience Platform文档）](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/data-mirror/overview)
>[关系架构（Experience Platform文档）](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/schema/relational)
