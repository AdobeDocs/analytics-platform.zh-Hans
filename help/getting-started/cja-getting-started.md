---
title: 客户旅程分析入门
description: 客户旅程分析入门。
translation-type: tm+mt
source-git-commit: fb2b5868db69bfff3345abcd69b0b70112fdcf3c

---


# 客户旅程分析入门

要实施客户旅程分析，您需要遵循此工作流。 一些初始任务在Adobe Experience Platform中执行，一些在客户旅程分析中执行。

| 任务 | 执行情况 | 详细信息 |
|---|---|---|
| **第1步：将数据导入Adobe Experience Platform** | Adobe Experience Platform | 有多种方法可以为流和批量使用案例获取数据，包括API和用于数据上传的图形界面。 Experience Platform可以从以下方面导入数据：<ul><li>S3存储</li><li>Azure Blob存储</li><li>卡夫卡流</li><li>SFTP传输</li><li>CSV文件上传</li><li>JSON文件上传</li></ul> |
| **第2步：准备数据模式** | Adobe Experience Platform | 使用 [Adobe Experience Data Model(XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) ，标准化客户体验数据并定义客户体验管理的模式。 |
| **第3步：根据模式创建数据集** | Adobe Experience Platform | 平台中的数据由数据集组成，如电子邮件数据集、CRM数据集、POS数据集、Adobe Analytics数据集等。 每个数据集都由模式和批量数据组成。 您可以在Experience Platform中创 [建数据集](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)。<br>尽管可导入客户旅程分析的数据集的模式是灵活的，但它必须符合一些基本规则。 最好在将数据上传到平台之前，先确保数据满足这些要求。 (请注意，模式包括指标和维度。)<br>有三种类型的数据与客户旅程分析兼容：<ul><li>**事件数据**:表示及时事件的数据(例如，Web访问、交互、交易、POS数据、调查数据、广告印象数据等)。 这是典型的点击流数据，带有客户ID或cookie ID，以及时间戳。 利用事件数据，我们允许您使用您需要的ID。</li><li>**查找数据**:此数据用于查找在事件或用户档案数据中找到的值或键。 例如，您可以上传将事件数据中的数字ID映射到产品名称的查找数据。</li><li>**用户档案数据**:应用于访客、用户或客户的事件数据。 例如，允许您上传有关客户的CRM数据。</li></ul> |
| **第4步：在平台数据集和客户旅程分析之间建立联系** | 客户历程分析 | See [Create a connection](/help/connections/create-connection.md). |
| **第5步：创建数据视图** | 客户历程分析 | See [Create a data view](/help/data-views/create-dataview.md). |
| **第6步：在Workspace中报告跨渠道数据** | 客户历程分析 | 请参 [阅执行基本分析](/help/projects/perform-basic-analysis.md) , [执行高级分析](/help/projects/perform-adv-analysis.md)。 |

## 先决条件

客户旅程分析适用于

* Adobe Analytics [Select、Prime或Ultimate客户](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) ，以及
* 为 [Adobe Experience Platform提供](https://www.adobe.com/experience-platform.html)，并且
* 已购买客户旅程分析SKU

## 准备数据模式

[使用模式编辑器创建模式](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)

## 第1步：将数据导入Adobe Experience Platform

在CJA中利用Experience Platform数据之前，您必须将该数据引入Platform。 可通过以下几种方式执行此操作：

* 如果要导入现有Adobe Analytics数据，请使用Adobe Analytics Platform Connector。
* 要获取其他数据，请使用以下格式：S3存储、Azure Blob存储、Kafka流、SFTP传输、CSV文件上传、JSON文件上传

### 第1a步：将现有Analytics数据导入Adobe Experience Platform

使用现成的Adobe Analytics Platform Connector将传统的Adobe Analytics数据引入Platform。 您可以为每个报表包创建一个源连接。 请参 [阅Adobe Experience Platform文档中的](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) “使用Adobe Analytics创建源连接”。

创建连接后，将自动创建目标模式和数据集以包含传入的数据。 此外，还会进行数据回填，并收集长达13个月的历史数据。 初始摄取完成后，您可以继续在此 `Step 4` Analytics数据集和客户旅程分析之间建立连接。

### 第1b步：摄取其他数据类型

[批处理提取](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md) ，允许您将数据作为批处理文件导入到Experience Platform中。 批量是由一个或多个要作为单个单位摄取的文件组成的数据单位。 摄取后，批处理将提供描述成功摄取的记录数以及任何失败记录和关联的错误消息的元数据。 必须使用此方法摄取手动上传的数据文件，如平面。CSV文件(映射到XDM模式)和Parce数据帧。

[流摄取](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md) ，让您能够将数据从客户端和服务器端设备实时发送到Experience Platform。

[其他源连接器](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md) ，允许您从外部源中摄取数据，同时提供使用平台服务构建、标记和增强传入数据的能力。 您可以从各种来源收集数据，如Adobe应用程序(Adobe Analytics、受众管理器、Experience Platform Launch、目标)、基于云的存储(Azure Blob、Amazon S3、FTP/SFTP、Google Cloud存储)、第三方软件和您的CRM(Microsoft Dynamics 365、Salesforce)。

## 第2步：准备数据模式

bnbnbnbn
