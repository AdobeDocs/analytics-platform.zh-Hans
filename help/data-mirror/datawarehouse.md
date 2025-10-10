---
title: 配置Data Warehouse本机解决方案
description: 了解如何为Experience Platform Data Mirror for Customer Journey Analytics配置Data Warehouse本机解决方案
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta 版"
exl-id: 92cffcc5-d7a7-47f5-869d-1fc665594bf4
source-git-commit: edf7bdac87d9bed48244ad80521bbbf83c48f7b6
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# 配置Data Warehouse本机解决方案

{{release-limited-testing}}

要支持适用于Customer Journey Analytics的Experience Platform Data Mirror，您要从三个受支持的Data Warehouse本机解决方案([[!DNL Azure Databricks]](#azure-databricks)、[[!DNL Google BigQuery]](#google-bigquery)、[[!DNL Snowflake]](#snowflake))中使用的数据需要启用更改数据捕获。


## [!DNL Azure Databricks]

在&#x200B;**表中启用**&#x200B;更改数据馈送[!DNL Azure Databricks]，以便在源连接中使用更改数据捕获。

使用以下命令在表上启用更改数据馈送：

**新表**

要将更改数据馈送应用到新表，必须在`delta.enableChangeDataFeed`命令中将表属性`TRUE`设置为`CREATE TABLE`。

```sql
CREATE TABLE student (id INT, name STRING, age INT) TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**现有表**

要将更改数据馈送应用于现有表，必须在`delta.enableChangeDataFeed`命令中将表属性`TRUE`设置为`ALTER TABLE`。

```sql
ALTER TABLE myDeltaTable SET TBLPROPERTIES (delta.enableChangeDataFeed = true)
```

**所有新表**

要将更改数据馈送应用于所有新表，必须将默认属性设置为`TRUE`。

```sql
set spark.databricks.delta.properties.defaults.enableChangeDataFeed = true;
```

有关详细信息，请阅读有关启用更改数据馈送[[!DNL Azure Databricks] 的](https://docs.databricks.com/aws/en/delta/delta-change-data-feed#enable-change-data-feed)指南。

请阅读以下文档，以了解如何为[!DNL Azure Databricks]源连接启用更改数据捕获的步骤：

* [创建 [!DNL Azure Databricks] 基本连接](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/databricks)。
* [为数据库](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection)创建源连接。

## [!DNL Google BigQuery]

要在[!DNL Google BigQuery]源连接中使用变更数据捕获，请在[!DNL Google BigQuery]控制台中导航到您的[!DNL Google Cloud]页面，并将`enable_change_history`设置为`TRUE`。 此属性启用数据表的更改历史记录。

有关详细信息，请阅读[&#x200B; [!DNL GoogleSQL]中](https://cloud.google.com/bigquery/docs/reference/standard-sql/data-definition-language#table_option_list)数据定义语言语句的指南。

请阅读以下文档，以了解如何为[!DNL Google BigQuery]源连接启用更改数据捕获的步骤：

* [创建 [!DNL Google BigQuery] 基本连接](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/bigquery)。
* [为数据库](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection)创建源连接。

## [!DNL Snowflake]

在&#x200B;**表中启用**&#x200B;更改跟踪[!DNL Snowflake]，以便在源连接中使用更改数据捕获。

在[!DNL Snowflake]中，通过使用`ALTER TABLE`并将`CHANGE_TRACKING`设置为`TRUE`来启用更改跟踪。

```sql
ALTER TABLE mytable SET CHANGE_TRACKING = TRUE
```

有关详细信息，请阅读有关使用changes子句[[!DNL Snowflake] 的](https://docs.snowflake.com/en/sql-reference/constructs/changes#usage-notes)指南。

请阅读以下文档，以了解如何为[!DNL Snowflake]源连接启用更改数据捕获的步骤：

* [创建 [!DNL Snowflake] 基本连接](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/create/databases/snowflake)。
* [为数据库](https://experienceleague.adobe.com/en/docs/experience-platform/sources/api-tutorials/collect/database-nosql#create-a-source-connection)创建源连接。


>[!MORELIKETHIS]
>
>[Data Mirror快速入门指南：镜像并使用基于模型的数据](model-based.md)
>
