---
title: Customer Journey Analytics 入门
description: Customer Journey Analytics 入门。
translation-type: ht
source-git-commit: fb2b5868db69bfff3345abcd69b0b70112fdcf3c

---


# Customer Journey Analytics 入门

要实施 Customer Journey Analytics，您需要遵循下述工作流程。一些初始任务在 Adobe Experience Platform 中执行，一些则在 Customer Journey Analytics 中执行。

| 任务 | 执行位置 | 详细信息 |
|---|---|---|
| **步骤 1：将数据导入 Adobe Experience Platform** | Adobe Experience Platform | 可通过多种方法来为流式用例和批量用例摄取数据，包括 API 和用于数据上传的图形界面。Experience Platform 可以从以下源引入数据：<ul><li>S3 存储</li><li>Azure Blob 存储</li><li>Kafka Streams</li><li>SFTP 传输</li><li>CSV 文件上传</li><li>JSON 文件上传</li></ul> |
| **步骤 2：准备数据架构** | Adobe Experience Platform | 通过 [Adobe 体验数据模型 (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) 实现客户体验数据的标准化，并界定客户体验管理架构。 |
| **步骤 3：根据架构创建数据集** | Adobe Experience Platform | Platform 中的数据由数据集组成，例如电子邮件数据集、CRM 数据集、POS 数据集、Adobe Analytics 数据集等。每个数据集都由一个架构和批量数据组成。您可以在 [Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md) 中创建一个数据集。<br>尽管可导入 Customer Journey Analytics 的数据集架构比较灵活，但必须符合一些基本规则。最好要确保数据集架构满足相应的要求，然后再将数据上传到 Platform。（请注意，架构包括量度和维度。）<br>有三种类型的数据与 Customer Journey Analytics 兼容：<ul><li>**事件数据**：表示及时事件的数据（例如 Web 访问、交互、交易、POS 数据、调查数据、广告展示数据等）。这是带有客户 ID 或 Cookie ID 和时间戳的典型点击流数据。通过事件数据，允许您使用您想要的 ID。</li><li>**查找数据**：此数据用于查找在“事件”或“用户档案”数据中找到的值或密钥。例如，您可以上传将事件数据中的数字 ID 映射到产品名称的查找数据。</li><li>**用户档案数据**：“事件”应用于数据中访客、用户或客户的数据。例如，允许您上传有关客户的 CRM 数据。</li></ul> |
| **步骤 4：在 Platform 数据集与 Customer Journey Analytics 之间创建连接** | Customer Journey Analytics | 请参阅[创建连接](/help/connections/create-connection.md)。 |
| **步骤 5：创建数据视图** | Customer Journey Analytics | 请参阅[创建数据视图](/help/data-views/create-dataview.md)。 |
| **步骤 6：在 Workspace 中报告跨渠道数据** | Customer Journey Analytics | 请参阅[执行基本分析](/help/projects/perform-basic-analysis.md)和[执行高级分析](/help/projects/perform-adv-analysis.md)。 |

## 先决条件

Customer Journey Analytics 适用以下客户：

* Adobe Analytics [Select、Prime 或 Ultimate](https://www.adobe.com/cn/analytics/compare-adobe-analytics-packages.html) 客户，以及
* 已配置 [Adobe Experience Platform](https://www.adobe.com/cn/experience-platform.html) 的客户，以及
* 已购买 Customer Journey Analytics SKU 的客户

## 准备数据架构

[使用架构编辑器创建架构](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)

## 步骤 1：将数据导入 Adobe Experience Platform

您必须将数据导入 Platform，然后才能在 CJA 中利用 Experience Platform 数据。可通过多种方法来执行此操作：

* 如果要导入现有 Adobe Analytics 数据，请使用 Adobe Analytics Platform Connector。
* 要摄取其他数据，请使用以下格式：S3 存储、Azure Blob 存储、Kafka Streams、SFTP 传输、CSV 文件上传、JSON 文件上传

### 步骤 1a：将现有 Analytics 数据导入 Adobe Experience Platform

使用开箱即用的 Adobe Analytics Platform Connector 将传统 Adobe Analytics 中的数据导入 Platform。您可以为每个报表包创建一个源连接。请参阅 Adobe Experience Platform 文档中的[创建与 Adobe Analytics 的源连接](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md)。

创建连接后，将自动创建目标架构和数据集，以包含传入数据。此外，还会进行数据回填，并摄取至多 13 个月的历史数据。完成初始摄取后，您可以继续执行 `Step 4` 以便在此 Analytics 数据集与 Customer Journey Analytics 之间创建连接。

### 步骤 1b：摄取其他数据类型

[批量摄取](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md)让您可以将数据作为批处理文件导入到 Experience Platform 中。批量是由一个或多个要作为单个单位摄取的文件组成的数据单位。摄取后，批量会提供元数据以描述已成功摄取的记录数量，以及任何失败记录和关联的错误消息。如果使用这种方法，则必须摄取手动上传的数据文件(例如映射到 XDM 模式的 .CSV 文件)和 Parquet Dataframe。

[流式摄取](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md)让您可以实时将数据从客户端和服务器端设备发送到 Experience Platform。

[其他源连接器](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md)让您可以从外部源摄取数据，同时让你能够通过 Platform 服务来构建、标记和增强传入数据。您可以从各种源摄取数据，例如 Adobe 应用程序（Adobe Analytics、Audience Manager、Experience Platform Launch、Target）、基于云的存储（Azure Blob、Amazon S3、FTP/SFTP、Google Cloud Storage）、第三方软件，以及您的 CRM（Microsoft Dynamics 365、Salesforce）。

## 步骤 2：准备数据架构

bnbnbnbn
