---
title: Experience Platform查询服务(数据Distiller)和导出数据集
description: 介绍如何使用查询服务(数据Distiller)和数据集导出来导出数据。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 14a90758-91eb-4610-8802-1edfdb8b9689
source-git-commit: 9fef1fddbb4b51efb9282e3ef13501bd498a4546
workflow-type: tm+mt
source-wordcount: '2475'
ht-degree: 3%

---

# 查询服务(数据Distiller)和导出数据集

本文概述如何使用Experience Platform查询服务(Data Distiller)和数据集导出的组合实现以下[数据导出用例](overview.md)：

- 数据验证
- Data Lake，BI工具Data Warehouse
- 为人工智能和机器学习做好准备。


Adobe Analytics可以使用其[数据馈送](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview)功能实施这些用例。 数据馈送是从 Adobe Analytics 中获取原始数据的有效方法。本文介绍了如何从Experience Platform中获得相似类型的原始数据，以便您实施上述用例。 在适用的情况下，将本文中描述的功能与Adobe Analytics数据馈送进行比较，以阐明数据和流程中的差异。

## 简介

使用查询服务(数据Distiller)导出数据以及数据集导出包含以下内容：

- 定义一个&#x200B;**计划查询**，该查询使用&#x200B;**查询服务**&#x200B;将您的数据馈送的数据生成为输出数据集![输出数据集](../assets/output-dataset.svg)。
- 定义使用&#x200B;**数据集导出**&#x200B;将输出数据集导出到云存储目标的&#x200B;**计划数据集导出**。

![数据馈送](../assets/queryservice-export-datasets.svg)


## 先决条件

在使用本使用案例中所述的功能之前，请确保您满足以下所有要求：

- 将数据收集到Experience Platform数据湖中的有效实施。
- 访问Data Distiller加载项，以确保您有权执行批量查询。 有关详细信息，请参阅[查询服务打包](https://experienceleague.adobe.com/en/docs/experience-platform/query/packaging)。
- 访问导出数据集功能，在您购买Real-Time CDP Prime或Ultimate包、Adobe Journey Optimizer或Customer Journey Analytics后可用。 有关详细信息，请参阅[将数据集导出到云存储目标](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets)。
- 将一个或多个已配置目标(例如：Amazon S3、Google Cloud Storage)导出到的数据馈送原始数据。


## 查询服务

Experience Platform查询服务允许您查询和联接Experience Platform数据湖中的任何数据集，就像它是一个数据库表一样。 然后，您可以将结果捕获为新数据集，以供进一步在报表中使用或导出。

您可以使用查询服务[用户界面](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/overview)、通过PostgresQL协议](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview)连接的[客户端或[RESTful API](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started)创建和计划收集数据馈送数据的查询。

### 创建查询

您可以使用标准ANSI SQL for SELECT语句的所有功能以及其他有限命令来创建和执行查询，以便为数据馈送生成数据。 有关详细信息，请参阅[SQL语法](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/syntax)。 除了此SQL语法外，Adobe还支持：

- 预建[Adobe定义函数(ADF)](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions)，这些函数帮助对存储在Experience Platform数据湖中的事件数据执行常见的业务相关任务，包括[Sessionization](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing)和[Attribution](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/attribution/overview)的函数，
- 多个内置[Spark SQL函数](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions)，
- [元数据PostgreSQL命令](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/metadata)，
- [准备的语句](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/prepared-statements)。

#### 数据馈送列

可在查询中使用的XDM字段取决于数据集所基于的架构定义。 确保您确实了解数据集背后的架构。 请参阅[数据集UI指南](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/user-guide)以了解更多信息。

为了帮助您定义数据馈送列和XDM字段之间的映射，请参阅[Analytics字段映射](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics)。 另请参阅[架构UI概述](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/overview#defining-xdm-fields)，了解有关如何管理XDM资源（包括架构、类、字段组和数据类型）的更多信息。

例如，如果要使用&#x200B;*页面名称*&#x200B;作为数据馈送的一部分，请执行以下操作：

- 在Adobe Analytics数据馈送的UI中，您可以选择&#x200B;**[!UICONTROL pagename]**&#x200B;作为要添加到数据馈送定义的列。
- 在查询服务中，您在查询中包含来自`sample_event_dataset_for_website_global_v1_1`数据集的`web.webPageDetails.name`(基于网站的&#x200B;**示例事件架构（全局v1.1）**&#x200B;体验事件架构)。 有关详细信息，请参阅[Web详细信息架构字段组](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/web-details)。


#### 标识

在Experience Platform中，可以使用各种标识。 创建查询时，请确保正确查询了标识。


通常，您会在单独的字段组中找到身份。 在实现中，ECID (`ecid`)可以定义为具有`core`对象的字段组的一部分，该对象本身是`identification`对象的一部分（例如： `_sampleorg.identification.core.ecid`）。 ECID在架构中的组织方式可能有所不同。

或者，您可以使用`identityMap`查询身份。 `identityMap`的类型为`Map`，并使用[嵌套数据结构](#nested-data-structure)。

有关如何在Experience Platform中定义标识字段的更多信息，请参阅[在UI中定义标识字段](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/ui/fields/identity)。

请参阅[Analytics数据中的主要标识符](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics#primary-identifiers-in-analytics-data)，了解在使用Analytics源连接器时，Adobe Analytics标识如何映射到Experience Platform标识。 此映射可用作设置标识的指导，即使未使用Analytics Source Connector也是如此。


#### 点击级别数据和识别

根据实施情况，传统上在Adobe Analytics中收集的点击级别数据现在作为Experience Platform中的时间戳事件数据存储。 下表是从[Analytics字段映射](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics#generated-mapping-fields)中提取的，并显示了如何将特定于点击级别的Adobe Analytics数据馈送列与查询中的相应XDM字段进行映射的示例。 该表还显示了如何使用XDM字段识别点击、访问和访客的示例。

| 数据馈送列 | XDM字段 | 类型 | 描述 |
|---|---|---|---|
| `hitid_high` + `hitid_low` | `_id` | 字符串 | 用于标识点击的唯一标识符。 |
| `hitid_low` | `_id` | 字符串 | 与`hitid_high`一起使用以唯一标识点击。 |
| `hitid_high` | `_id` | 字符串 | 与`hitid_high`一起使用以唯一标识点击。 |
| `hit_time_gmt` | `receivedTimestamp` | 字符串 | 点击的时间戳，基于UNIX®时间。 |
| `cust_hit_time_gmt` | `timestamp` | 字符串 | 此时间戳仅在启用了时间戳的数据集中使用。 此时间戳基于UNIX®时间，随点击一起发送。 |
| `visid_high` + `visid_low` | `identityMap` | 对象 | 访问的唯一标识符。 |
| `visid_high` + `visid_low` | `endUserIDs._experience.aaid.id` | 字符串 | 访问的唯一标识符。 |
| `visid_high` | `endUserIDs._experience.aaid.primary` | 布尔值 | 与`visid_low`一起使用以唯一标识访问。 |
| `visid_high` | `endUserIDs._experience.aaid.namespace.code` | 字符串 | 与`visid_low`一起使用以唯一标识访问。 |
| `visid_low` | `identityMap` | 对象 | 与`visid_high`一起使用以唯一标识访问。 |
| `cust_visid` | `identityMap` | 对象 | 客户访客ID。 |
| `cust_visid` | `endUserIDs._experience.aacustomid.id` | 对象 | 客户访客ID。 |
| `cust_visid` | `endUserIDs._experience.aacustomid.primary` | 布尔值 | 客户访客ID命名空间代码。 |
| `cust_visid` | `endUserIDs._experience.aacustomid.namespace.code` | 字符串 | 与`visid_low`一起使用以唯一地标识客户访客ID。 |
| `geo\_*` | `placeContext.geo.* ` | 字符串，数字 | 地理位置数据，如国家/地区、地区、城市等 |
| `event_list` | `commerce.purchases`、`commerce.productViews`、`commerce.productListOpens`、`commerce.checkouts`、`commerce.productListAdds`、`commerce.productListRemovals`、`commerce.productListViews`、`_experience.analytics.event101to200.*`、...、`_experience.analytics.event901_1000.*` | 字符串 | 点击时触发的标准商务和自定义事件。 |
| `page_event` | `web.webInteraction.type` | 字符串 | 在图像请求中发送的点击类型（标准点击、下载链接、退出链接或单击的自定义链接）。 |
| `page_event` | `web.webInteraction.linkClicks.value` | 数字 | 在图像请求中发送的点击类型（标准点击、下载链接、退出链接或单击的自定义链接）。 |
| `page_event_var_1` | `web.webInteraction.URL` | 字符串 | 仅在链接跟踪图像请求中使用的变量。 此变量包含下载链接、退出链接或单击的自定义链接的URL。 |
| `page_event_var_2` | `web.webInteraction.name` | 字符串 | 仅在链接跟踪图像请求中使用的变量。 这会列出链接的自定义名称（如果已指定）。 |
| `paid_search` | `search.isPaid` | 布尔值 | 如果点击与付费搜索检测相匹配，则设置此标记。 |
| `ref_type` | `web.webReferrertype` | 字符串 | 表示点击的反向链接类型的数字 ID。 |

#### 发布列

Adobe Analytics数据馈送使用带有`post_`前缀的列的概念，这些列是包含处理之后的数据的列。 有关更多信息，请参阅[数据馈送常见问题解答](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/df-faq#post)。

通过Experience PlatformEdge Network（Web SDK、Mobile SDK、服务器API）在数据集中所收集的数据不包含`post_`字段的概念。 因此，`post_`个带有前缀和&#x200B;*非*-`post_`个带有前缀的数据馈送列映射到相同的XDM字段。 例如，`page_url`和`post_page_url`数据馈送列都映射到相同的`web.webPageDetails.URL` XDM字段。

请参阅[跨Adobe Analytics和Customer Journey Analytics比较数据处理](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons)，以了解数据处理差异的概述。

在Experience Platform数据湖中收集的`post_`前缀列类型的数据确实需要高级转换，然后才能成功地用于数据馈送用例。 在查询中执行这些高级转换涉及使用[Adobe定义的函数](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions)进行会话化、归因和重复数据删除。 请参阅有关如何使用这些函数的[示例](#examples)。

#### 查找

若要从其他数据集查找数据，请使用标准SQL功能（`WHERE`子句、`INNER JOIN`、`OUTER JOIN`等）。

#### 计算

要对字段（列）执行计算，请使用标准SQL函数（例如`COUNT(*)`），或Spark SQL的[数学和统计运算符及函数](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#math)部分。 此外，[窗口函数](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/adobe-defined-functions#window-functions)支持更新聚合并为有序子集中的每一行返回单个项。 请参阅有关如何使用这些函数的[示例](#examples)。

#### 嵌套数据结构

数据集所基于的架构通常包含复杂的数据类型，包括嵌套的数据结构。 前面提到的`identityMap`是嵌套数据结构的示例。 有关`identityMap`数据的示例，请参见下文。

```json
{
   "identityMap":{
      "FPID":[
         {
            "id":"55613368189701342632255821452918751312",
            "authenticatedState":"ambiguous"
         }
      ],
      "CRM":[
         {
            "id":"2394509340-30453470347",
            "authenticatedState":"authenticated"
         }
      ]
   }
}
```

您可以使用Spark SQL中的[`explode()`或其他Arrays函数](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/spark-sql-functions#arrays)来获取嵌套数据结构中的数据，例如：

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

或者，您可以使用点表示法引用单个元素。 例如：

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

有关更多信息，请参阅[在 Query Service 中使用嵌套数据结构](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/nested-data-structures)。


#### 示例

对于查询：

- 那些使用来自Experience Platform数据湖中数据集的数据，
- 正在点击Adobe定义的函数和/或Spark SQL的附加功能，并且
- 会将类似的结果交付给等效的Adobe Analytics数据馈送，

请参阅：

- [放弃的浏览](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/abandoned-browse)
- [归因分析](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/attribution-analysis)
- [机器人筛选](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/bot-filtering)
- 和查询服务指南](https://experienceleague.adobe.com/en/docs/experience-platform/query/use-cases/overview)中其他[支持的用例。


### 计划查询

您可以计划查询，以确保按首选间隔执行查询并生成结果。

#### 使用查询编辑器

您可以使用查询编辑器计划查询。 在计划查询时，您可以定义输出数据集。 有关详细信息，请参阅[查询计划](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/query-schedules)。


#### 使用查询服务API

或者，您可以使用RESTful API为查询定义查询和计划。 有关详细信息，请参阅[查询服务API指南](https://experienceleague.adobe.com/en/docs/experience-platform/query/api/getting-started)。
在创建查询（[创建查询](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery)）或为查询创建计划时（[创建计划查询](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule)），请确保将输出数据集定义为可选`ctasParameters`属性的一部分。



## 导出数据集

创建并计划查询并验证结果后，您可以将原始数据集导出到云存储目标。 此导出位于称为“Experience Platform导出目标”的数据集目标术语中。 有关概述，请参阅[将数据集导出到云存储目标](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets)。

支持以下云存储目标：

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [数据登陆区](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google云存储](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp)


### EXPERIENCE PLATFORMUI

您可以通过Experience PlatformUI导出和计划导出输出数据集。 本节介绍所涉及的步骤。

#### 选择目标

确定要将输出数据集导出到的云存储目标后，[选择目标](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination)。 如果尚未为首选云存储配置目标，则必须[创建新的目标连接](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination)。

在配置目标时，您可以

- 定义文件类型（JSON或Parquet），
- 是否应该压缩结果文件，以及
- 是否应该包含清单文件。


#### 选择数据集

选择目标后，在下一个&#x200B;**[!UICONTROL 选择数据集]**&#x200B;步骤中，您必须从数据集列表中选择输出数据集。 如果您创建了多个计划查询，并且希望将输出数据集发送到同一云存储目标，则可以选择相应的输出数据集。 有关详细信息，请参阅[选择您的数据集](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets)。

#### 计划数据集导出

最后，要计划数据集导出作为&#x200B;**[!UICONTROL 计划]**&#x200B;步骤的一部分。 在该步骤中，您可以定义计划以及输出数据集导出是否应增量导出。 有关详细信息，请参阅[计划数据集导出](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling)。


#### 最后步骤

[查看](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review)您的选择，如果正确，开始将输出数据集导出到云存储目标。

您必须[验证](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify)数据导出是否成功。 导出数据集时，Experience Platform会在目标中定义的存储位置创建一个或多个`.json`或`.parquet`文件。 根据您设置的导出计划，希望将新文件存储在您的存储位置。 Experience Platform会在您指定为选定目标的一部分的存储位置中创建文件夹结构，存放导出的文件。 每次导出时都会创建一个新文件夹，其模式为： `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`。 默认文件名是随机生成的，并确保导出的文件名是唯一的。

### 流服务API

或者，您可以使用API导出和计划导出输出数据集。 使用流服务API](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets)在[导出数据集中记录了所涉及的步骤。

#### 快速入门

要导出数据集，请确保您具有[所需的权限](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions)。 此外，还要验证要将输出数据集发送到的目标是否支持导出数据集。 然后，您必须[收集在API调用中使用的必需和可选标头](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers)的值。 您还需要[识别要将数据集导出到的目标](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec)的连接规范和流规范ID。

#### 检索符合条件的数据集

您可以[检索符合条件的数据集列表](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets)以供导出，并使用[`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API验证您的输出数据集是否属于该列表。


#### 创建源连接

接下来，您必须使用要导出到云存储目标的输出数据集的唯一ID [创建源连接](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection)。 您使用[`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API。

#### 向目标进行身份验证（创建基本连接）

您现在必须[创建基本连接](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection)以使用[`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API进行身份验证并将凭据安全地存储到您的云存储目标。


#### 提供导出参数

接下来，您必须[再使用[`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API创建一个目标连接，用于存储输出数据集的导出参数](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection)。 这些导出参数包括位置、文件格式、压缩等。

#### 设置数据流

最后，您[设置数据流](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow)，以确保使用[`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API将输出数据集导出到云存储目标。 在此步骤中，您可以使用`scheduleParams`参数定义导出的计划。

#### 验证数据流

要[检查数据流](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs)是否成功执行，请使用[`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API，将数据流ID指定为查询参数。 此数据流ID是您在设置数据流时返回的标识符。

[验证](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify)数据导出是否成功。 导出数据集时，Experience Platform会在目标中定义的存储位置创建一个或多个`.json`或`.parquet`文件。 根据您设置的导出计划，希望将新文件存储在您的存储位置。 Experience Platform会在您指定为选定目标的一部分的存储位置中创建文件夹结构，存放导出的文件。 每次导出时都会创建一个新文件夹，其模式为： `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`。 默认文件名是随机生成的，并确保导出的文件名是唯一的。

## 结论

简而言之，模拟Adobe Analytics数据馈送功能意味着使用查询服务设置计划查询，并在计划的数据集导出中使用这些查询的结果。

>[!IMPORTANT]
>
>此用例涉及两个调度程序。 要保证模拟数据馈送功能正常工作，请确保在查询服务和数据导出中配置的计划不会干预。
