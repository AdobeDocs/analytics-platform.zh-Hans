---
title: Data Mirror概述
description: 了解如何在Data Warehouse本机解决方案和Customer Journey Analytics之间同步数据
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta 版"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: dc3aa31c280c1a8ee8a0187edeca9bd34a2c9e2e
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# Experience Platform Data Mirror概述

{{release-limited-testing}}

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

另请参阅有关Data Mirror](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}的[Experience Platform文档。

## 适用于Customer Journey Analytics的Data Mirror

>[!NOTE]
>
>Data Mirror目前是测试版中的一项功能，它支持使用更改数据捕获(CDC)同步选定数据仓库中的数据，以便在Customer Journey Analytics中进行分析。<br/>此功能将于2026年6月18日正式在Customer Journey Analytics中提供。 请参阅适用的产品描述，以了解它如何影响未来的年度摄取限制消费。 请注意，当Data Mirror从Beta版过渡到正式发布时，贵组织将继续有权访问该功能。
>

适用于Customer Journey Analytics的Experience Platform Data Mirror适用于选定的Data Warehouse本机解决方案（[!DNL Azure Databricks]、[!DNL Google BigQuery]和[!DNL Snowflake]）。 Customer Journey Analytics版本的Experience Platform Data Mirror需要正确配置以下应用程序或组件：

* [数据仓库原生解决方案](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Data Mirror快速入门指南：镜像并使用关系数据](relational.md)
>[Data Mirror（Experience Platform文档）](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>[关系架构（Experience Platform文档）](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/schema/relational)
