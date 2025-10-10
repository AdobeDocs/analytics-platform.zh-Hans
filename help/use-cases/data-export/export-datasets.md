---
title: Customer Journey Analytics导出数据集
description: 介绍如何使用导出数据集备份您的数据。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: b861f765-b18d-4be2-b4c7-c66186d37d99
source-git-commit: 9fef1fddbb4b51efb9282e3ef13501bd498a4546
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 2%

---

# 导出数据集

本文概述如何使用[!DNL Customer Journey Analytics Export datasets]实现以下[数据导出用例](overview.md)：

- 数据备份

## 简介

使用[!DNL Experience Platform Export datasets]导出数据允许您将数据从Customer Journey Analytics数据视图导出到任何云存储目标。

![BI扩展](../assets/export-datasets.svg)

## 更多信息

您可以将原始数据集从Experience Platform中的数据湖导出到云存储目标。 此导出位于“Experience Platform目标”术语中，称为“数据集导出目标”。 有关概述，请参阅[将数据集导出到云存储目标](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/ui/activate/export-datasets)。

支持以下云存储目标：

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [数据登陆区](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google云存储](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3#changelog)
- [Azure Blob](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob#changelog)
- [SFTP](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/catalog/cloud-storage/sftp#changelog)


### EXPERIENCE PLATFORM UI

您可以通过Experience Platform UI导出和计划数据集的导出。 本节介绍所涉及的步骤。

#### 选择目标

确定要将数据集导出到的云存储目标后，[选择目标](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination)。 如果尚未为首选云存储配置目标，则必须[创建新的目标连接](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/ui/connect-destination)。

在配置目标时，您可以定义：

- 文件类型（JSON或Parquet），
- 是否应该压缩结果文件，以及
- 是否应该包含清单文件。


#### 选择数据集

选择目标后，在下一个&#x200B;**[!UICONTROL 选择数据集]**&#x200B;步骤中，您必须从数据集列表中选择数据集。 如果您创建了多个计划查询，并且希望数据集发送到同一云存储目标，则可以选择相应的数据集。 有关详细信息，请参阅[选择您的数据集](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets)。

#### 计划数据集导出

最后，要计划数据集导出作为&#x200B;**[!UICONTROL 计划]**&#x200B;步骤的一部分。 在该步骤中，您可以定义计划以及数据集导出是否应增量导出。 有关详细信息，请参阅[计划数据集导出](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling)。


#### 最后步骤

[审核](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/ui/activate/export-datasets#review)您的选择，如果正确，则开始将数据集导出到云存储目标。

首先，您必须[验证](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/ui/activate/export-datasets#verify)数据导出是否成功。 导出数据集时，Experience Platform会在目标中定义的存储位置创建一个或多个`.json`或`.parquet`文件。 根据您设置的导出计划，希望将新文件存储在您的存储位置。 Experience Platform会在您指定为选定目标一部分的存储位置中创建一个文件夹结构，用于存储导出的文件。 每次导出时都会创建一个新文件夹，其模式为： `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`。 默认文件名是随机生成的，并确保导出的文件名是唯一的。

### 流服务API

或者，您可以使用API导出和计划数据集的导出。 使用流服务API[在](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/api/export-datasets)导出数据集中记录了所涉及的步骤。

#### 快速入门

要导出数据集，请确保您具有[所需的权限](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/api/export-datasets#permissions)。 此外，还要验证要将数据集发送到的目标是否支持导出数据集。 然后，您必须[收集在API调用中使用的必需和可选标头](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/api/export-datasets#gather-values-headers)的值。 您还需要[识别要将数据集导出到的目标](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec)的连接规范和流规范ID。

#### 检索符合条件的数据集

您可以[检索符合条件的数据集列表](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets)以供导出，并使用[`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API验证您的数据集是否属于该列表。


#### 创建源连接

接下来，您必须使用要导出到云存储目标的数据集的唯一ID [为数据集](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/api/export-datasets#create-source-connection)创建源连接。 您使用[`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API。

#### 向目标进行身份验证（创建基本连接）

您现在必须[创建基本连接](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/api/export-datasets#create-base-connection)以使用[`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API进行身份验证并将凭据安全地存储到您的云存储目标。


#### 提供导出参数

接下来，您必须[再使用](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/api/export-datasets#create-target-connection) [`POST /targetConection` API创建一个目标连接，用于存储数据集的导出参数](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection)。 这些导出参数包括位置、文件格式、压缩等。

#### 设置数据流

最后，您[设置数据流](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/api/export-datasets#create-dataflow)，以确保使用[`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API将您的数据集导出到云存储目标。 在此步骤中，您可以使用`scheduleParams`参数定义导出的计划。

#### 验证数据流

要[检查数据流](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs)是否成功执行，请使用[`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API，将数据流ID指定为查询参数。 此数据流ID是您在设置数据流时返回的标识符。

[验证](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/ui/activate/export-datasets#verify)数据导出是否成功。 导出数据集时，Experience Platform会在目标中定义的存储位置创建一个或多个`.json`或`.parquet`文件。 根据您设置的导出计划，希望将新文件存储在您的存储位置。 Experience Platform会在您指定为选定目标一部分的存储位置中创建一个文件夹结构，用于存储导出的文件。 每次导出时都会创建一个新文件夹，其模式为： `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`。 默认文件名是随机生成的，并确保导出的文件名是唯一的。
