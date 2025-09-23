---
title: Data Mirror概述
description: 了解如何在Data Warehouse本机解决方案和Customer Journey Analytics之间同步数据
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta 版"
source-git-commit: 9bd124ad651274b48052edc56bfb72358aa2d79a
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 1%

---

# Experience Platform Data Mirror概述

{{release-limited-testing}}

Data Mirror是一项Experience Platform功能，它允许使用基于模型的架构，将外部数据库中的行级更改引入数据湖。 它保留数据关系，强制唯一性，并支持版本控制，而无需上游提取、转换、加载(ETL)过程。

使用Data Mirror将外部数据仓库本机解决方案（如[!DNL Snowflake]、[!DNL Azure Databricks]或[!DNL Google BigQuery]）的插入、更新和删除（可变数据）直接同步到Experience Platform中。 在将数据引入Experience Platform时，Data Mirror可帮助您保持现有的数据库模型结构和数据完整性。


## 功能和优点

Data Mirror提供了以下基本数据库同步功能：

* **主键强制**。 确保数据集内的唯一性，并防止在摄取期间出现重复记录。
* **行级更改引入**。 支持粒度数据更改，包括精确控制的更新插入和删除操作。
* **架构关系**。 通过描述符启用数据集之间的外键和主键关系。
* **无序事件处理**。 使用版本和时间戳描述符处理更改事件，即使它们不按顺序到达也是如此。
* **直接仓库集成**。 与受支持的云数据仓库连接，以便实时进行更改同步。

使用Data Mirror直接从源系统中摄取更改，强制实施架构完整性，并将数据用于Analytics、Journey Orchestration和合规性工作流。 Data Mirror通过启用现有数据库模型的直接镜像，消除了复杂的上游ETL流程并加快了实施。 这种消除可以通过精确控制删除和数据卫生操作来加强数据治理。

<!-- Add link when AEP docs are ready... -->

另请参阅有关Data Mirror的Experience Platform文档。


## 适用于Customer Journey Analytics的Data Mirror

>[!NOTE]
>
>适用于Customer Journey Analytics的Experience Platform Data Mirror功能在&#x200B;**公共测试版**&#x200B;中提供，有效期至2026年3月25日。 在Beta测试期间，变更数据捕获(CDC)更新限制为您的组织每月数据行的0.5%。 每月的数据行数基于您每年有权使用的数据行数除以12。 如果贵组织超过此限制，Adobe保留终止对Experience Platform Data Mirror的Beta版访问权限的权利，以便获取Customer Journey Analytics功能。
>

适用于Customer Journey Analytics的Experience Platform Data Mirror功能适用于选定的Data Warehouse本机解决方案（[!DNL Azure Databricks]、[!DNL Google BigQuery]和[!DNL Snowflake]）。 Customer Journey Analytics版本的Data Mirror功能需要正确设置和配置多个组件：

* [Data Warehouse本机解决方案](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)


>[!MORELIKETHIS]
>
>[Data Mirror快速入门指南：镜像并使用基于模型的数据](data-mirror.md)
>