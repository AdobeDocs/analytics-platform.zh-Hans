---
title: 模拟数据馈送功能
description: 了解如何用Experience Platform中的数据模拟Adobe Analytics数据馈送。
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
role: Admin
source-git-commit: a402c4b03c9d30235f2697e1b6ad5b1b22024c66
workflow-type: tm+mt
source-wordcount: '2537'
ht-degree: 4%

---

# 模拟数据馈送功能

Adobe Analytics数据馈送是从Adobe Analytics中获取原始数据的有效方法。 此使用案例描述了如何从Experience Platform中获得相似类型的原始数据，以便您可以在Adobe之外的其他平台和工具中使用数据，具体情况由贵组织自行决定。

## 简介

模拟Adobe Analytics数据馈送的过程包括：

* 定义 **计划查询** ，它将为数据馈送生成数据作为输出数据集 ![输出数据集](assets/output-dataset.svg)，使用 **查询服务**.
* 定义 **计划的数据集导出** 用于使用以下方式将输出数据集导出到云存储目标 **数据集导出**.

![数据馈送](assets/data-feed.svg)


## 先决条件

在使用本使用案例中所述的功能之前，请确保您满足以下所有要求：

* 将数据收集到Experience Platform数据湖中的有效实施。
* 访问Data Distiller加载项，以确保您有权执行批量查询。 请参阅 [查询服务打包](https://experienceleague.adobe.com/docs/experience-platform/query/packaging.html?lang=en) 以了解更多信息。
* 访问导出数据集功能，在您购买Real-Time CDP Prime或Ultimate包、Adobe Journey Optimizer或Customer Journey Analytics后可用。 请参阅 [将数据集导出到云存储目标](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=zh-Hans) 以了解更多信息。
* 一个或多个目标(例如：Amazon S3、Google Cloud Storage)已配置为可在其中导出数据馈送的原始数据。


## 查询服务

Experience Platform查询服务允许您查询和联接Experience Platform数据湖中的任何数据集，就像它是一个数据库表一样。 然后，您可以将结果捕获为新数据集，以供进一步在报表中使用或导出。

使用查询服务 [用户界面](https://experienceleague.adobe.com/docs/experience-platform/query/ui/overview.html?lang=en)， a [通过PostgresQL协议连接的客户端](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=zh-Hans)，或 [RESTful API](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) 创建和计划收集数据馈送数据的查询。

### 创建查询

您可以使用标准ANSI SQL for SELECT语句的所有功能以及其他有限命令来创建和执行查询，以便为数据馈送生成数据。 请参阅 [SQL语法](https://experienceleague.adobe.com/docs/experience-platform/query/sql/syntax.html?lang=en) 以了解更多信息。 除了此SQL语法外，Adobe还支持：

* 预建 [Adobe定义函数(ADF)](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) 这些函数帮助对存储在Experience Platform数据湖中的事件数据执行常见的业务相关任务，包括 [会话化](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing.html?lang=zh-Hans) 和 [归因](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=zh-Hans)，
* 多个内置 [Spark SQL函数](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en)，
* [元数据PostgreSQL命令](https://experienceleague.adobe.com/docs/experience-platform/query/sql/metadata.html?lang=en)，
* [预准备语句](https://experienceleague.adobe.com/docs/experience-platform/query/sql/prepared-statements.html?lang=en).


#### 标识

在Experience Platform中，可以使用各种标识。 创建查询时，请确保正确查询了标识。

通常，您会在单独的字段组中找到身份。 在实施ECID (`ecid`)可以定义为字段组的一部分，使用 `core` 对象，它本身是 `identification` 对象(例如： `_sampleorg.identification.core.ecid`)。 ECID在架构中的组织方式可能有所不同。

或者，您可以使用 `identityMap` 以查询身份。 此对象的类型为 `Map` 并使用 [嵌套数据结构](#nested-data-structure).


#### 数据馈送列

可在查询中使用的XDM字段取决于数据集所基于的架构定义。 确保您确实了解数据集背后的架构。

要定义数据馈送列和XDM字段之间的映射，应考虑检查并可能（重新）使用 [Adobe Analytics ExperienceEvent模板](https://github.com/adobe/xdm/blob/master/extensions/adobe/experience/analytics/experienceevent-all.schema.json) 字段组。 请参阅 [数据建模的最佳实践](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/best-practices.html?lang=en) 更具体地说 [Adobe的应用程序架构字段组](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/best-practices.html?lang=en#adobe-application-schema-field-groups).

例如，如果您要使用 *页面名称* 作为数据馈送的一部分：

* 在Adobe Analytics数据馈送的UI中，您可以选择 **[!UICONTROL pagename]** 作为要添加到您的数据馈送定义的列。
* 在查询服务中，您包括 `web.webPageDetails.name` 从 `sample_event_dataset_for_website_global_v1_1` 数据集(基于 **网站(Global v1.1)的事件架构示例** 体验事件架构)。 请参阅 [Web详细信息架构字段组](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/web-details.html?lang=en) 以了解更多信息。

要了解Adobe Analytics数据馈送列与Experience事件数据集中的XDM字段和基础架构之间的映射，请参阅 [Analytics字段映射](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=zh-Hans) 和 [Adobe Analytics ExperienceEvent完整扩展架构字段组](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) 以了解更多信息。

此外， [Experience PlatformWeb SDK自动收集的信息（开箱即用）](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html?lang=en) 可能与识别查询的列相关。

#### 点击级别数据和识别

根据实施情况，传统上在Adobe Analytics中收集的点击级别数据现在作为Experience Platform中的时间戳事件数据存储。 下表摘自 [Analytics字段映射](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=en#generated-mapping-fields) 和显示了如何将特定于点击级别的Adobe Analytics数据馈送列与查询中的相应XDM字段映射的示例。 该表还显示了如何使用XDM字段识别点击、访问和访客的示例。

| 数据馈送列 | XDM字段 | 类型 | 描述 |
|---|---|---|---|
| hitid_high + hitid_low | _id | 字符串 | 用于标识点击的唯一标识符。 |
| hitid_low | _id | 字符串 | 与hitid_high一起使用，唯一标识点击。 |
| hitid_high | _id | 字符串 | 与hitid_high一起使用，唯一标识点击。 |
| hit_time_gmt | receivedTimestamp | 字符串 | 点击的时间戳，基于UNIX®时间。 |
| first_hit_time_gmt | _experience.analytics.endUser.firstTimestamp | 字符串 | 访客第一次点击的时间戳(以UNIX®时间表示)。 |
| cust_hit_time_gmt | timestamp | 字符串 | 这仅在启用了时间戳的数据集中使用。 这是随点击发送的时间戳，基于UNIX®时间。 |
| visid_high + visid_low | identityMap | 对象 | 访问的唯一标识符。 |
| visid_high + visid_low | endUserIDs._experience.aaid.id | 字符串 | 访问的唯一标识符。 |
| visid_high | endUserIDs._experience.aaid.primary | 布尔值 | 与visid_low结合使用，用来唯一标识访问。 |
| visid_high | endUserIDs._experience.aaid.namespace.code | 字符串 | 与visid_low结合使用，用来唯一标识访问。 |
| visid_low | identityMap | 对象 | 与visid_high结合使用，用来唯一标识访问。 |
| cust_visid | identityMap | 对象 | 客户访客ID |
| cust_visid | endUserIDs._experience.aacustomid.id | 对象 | 客户访客ID。 |
| cust_visid | endUserIDs._experience.aacustomid.primary | 布尔值 | 客户访客ID命名空间代码。 |
| cust_visid | endUserIDs._experience.aacustomid.namespace.code | 字符串 | 与visid_low结合使用，用来唯一标识客户访客id。 |
| 地理\_* | placeContext.geo.* | 字符串，数字 | 地理位置数据，如国家/地区、地区、城市等 |
| visit_page_num | _experience.analytics.session.depth | 数字 | 在点击深度维度中使用的变量。 对于用户生成的每次点击，此值增加1，并在每次访问后重置。 |
| event_list | commerce.purchases、commerce.productViews、commerce.productListOpens、commerce.checkouts、commerce.productListAdds、commerce.productListRemovals、commerce.productListViews、\_experience.analytics.event101to200。*， ...， \_experience.analytics.event901_1000。\* | 字符串 | 点击时触发的标准商务和自定义事件。 |
| page_event | web.webInteraction.type | 字符串 | 在图像请求中发送的点击类型（标准点击、下载链接、退出链接或单击的自定义链接）。 |
| page_event | web.webInteraction.linkClicks.value | 数字 | 在图像请求中发送的点击类型（标准点击、下载链接、退出链接或单击的自定义链接）。 |
| page_event_var_1 | web.webInteraction.URL | 字符串 | 仅在链接跟踪图像请求中使用的变量。 此变量包含下载链接、退出链接或单击的自定义链接的URL。 |
| page_event_var_2 | web.webInteraction.name | 字符串 | 仅在链接跟踪图像请求中使用的变量。 这会列出链接的自定义名称（如果已指定）。 |
| first_hit_ref_type | _experience.analytics.endUser.firstWeb.webReferrer.type | 字符串 | 数值ID，表示访客的第一个反向链接的反向链接类型。 |
| first_hit_time_gmt | _experience.analytics.endUser.firstTimestamp | 整数 | 访客第一次点击的时间戳(以UNIX®时间表示)。 |
| paid_search | search.isPaid | 布尔值 | 如果点击与付费搜索检测相匹配，则设置此标记。 |
| ref_type | web.webReferrertype | 字符串 | 表示点击的反向链接类型的数字 ID。 |

#### 发布列

Adobe Analytics数据馈送将列的概念与 `post_` 前缀，即包含处理后数据的列。 有关更多信息，请参阅[数据馈送常见问题解答](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/df-faq.html?lang=en#post)。

通过Experience Platform边缘网络(Web SDK、Mobile SDK、Server API)在数据集中所收集的数据不概念 `post_` 字段。 因此， `post_` 前缀和 *非*-`post_` 前缀的数据馈送列映射到相同的XDM字段。 例如，两者 `page_url` 和 `post_page_url` 数据馈送列映射到相同的 `web.webPageDetails.URL` XDM字段。

请参阅 [跨Adobe Analytics和Customer Journey Analytics比较数据处理](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons.html?lang=zh-Hans) 以了解有关数据处理差异的概述。

此 `post_` 前缀列类型数据在Experience Platform数据湖中收集时，但需要先进行高级转换，然后才能在数据馈送用例中成功使用。 在查询中执行这些高级转换涉及使用 [Adobe定义的函数](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) 用于会话划分、归因和重复数据删除。 请参阅 [示例](#examples) 了解如何使用这些函数。

#### 查找

若要从其他数据集查找数据，请使用标准SQL功能(`WHERE` 子句， `INNER JOIN`， `OUTER JOIN`、和其他人)。

#### 计算

要对字段（列）执行计算，请使用标准SQL函数(例如 `COUNT(*)` 或 [数学和统计运算符及函数](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#math) Spark SQL的一部分。 另外， [窗口函数](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en#window-functions) 提供对更新聚合的支持，并为有序子集中的每一行返回单个项。 请参阅 [示例](#examples) 了解如何使用这些函数。

#### 嵌套数据结构

数据集所基于的架构通常包含复杂的数据类型，包括嵌套数据结构。 先前已提及 `identityMap` 是嵌套数据结构的示例。 有关示例，请参见下文 `identityMap` 数据。

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

您可以使用 [`explode()` 或其他数组函数](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#arrays) 从Spark SQL获取嵌套数据结构中的数据，例如：

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

或者，您可以使用点表示法引用单个元素。 例如：

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

有关更多信息，请参阅[在 Query Service 中使用嵌套数据结构](https://experienceleague.adobe.com/docs/experience-platform/query/key-concepts/nested-data-structures.html?lang=en)。


#### 示例

对于使用Experience Platform数据湖中数据集的数据的查询，正在点击Adobe定义的函数和/或Spark SQL的附加功能，并且这些功能会将相似的结果提供给等效的Adobe Analytics数据馈送，请参阅

* [已放弃的浏览](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/abandoned-browse.html?lang=en)
* [归因分析](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/attribution-analysis.html?lang=en)
* [机器人过滤](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/bot-filtering.html?lang=en)
* 以及查询服务指南中的其他示例用例。


### 计划查询

您可以计划查询，以确保按首选间隔执行查询并生成结果。

#### 使用查询编辑器

您可以使用查询编辑器计划查询。 在计划查询时，您可以定义输出数据集。 请参阅 [查询计划](https://experienceleague.adobe.com/docs/experience-platform/query/ui/query-schedules.html?lang=en) 以了解更多信息。


#### 使用查询服务API

或者，您可以使用RESTful API为查询定义查询和计划。 请参阅 [查询服务API指南](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) 以了解更多信息。
确保将输出数据集定义为可选的一部分 `ctasParameters` 创建查询时的属性([创建查询](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Queries/operation/createQuery))或在为查询创建计划时([创建计划查询](https://developer.adobe.com/experience-platform-apis/references/query-service/#tag/Schedules/operation/createSchedule))。



## 数据集导出

创建并计划查询，然后验证输出数据集中的结果符合您的要求后，您可以将原始数据集导出到云存储目标。 此导出位于称为“Experience Platform导出目标”的数据集目标术语中。 请参阅 [将数据集导出到云存储目标](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=zh-Hans) 了解概述。

支持以下云存储目标：

* [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2.html?lang=en)
* [数据登陆区](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html?lang=en)
* [Google云存储](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage.html?lang=en)
* [Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3.html?lang=en#changelog)
* [Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob.html?lang=en#changelog)
* [SFTP](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/sftp.html?lang=en#changelog)


### EXPERIENCE PLATFORMUI

您可以通过Experience PlatformUI导出和计划导出输出数据集。 本节介绍所涉及的步骤。

#### 选择目标

确定要将输出数据集导出到哪个云存储目标后， [选择目标](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-destination). 如果尚未为首选云存储配置目标，您必须 [创建新的目标连接](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/connect-destination.html?lang=en).

在配置目标时，您可以定义文件类型（JSON或Parquet）、是否应压缩生成的文件，以及是否应包含清单文件。


#### 选择数据集

选择目标后，在 **[!UICONTROL 选择数据集]** 步骤您必须从数据集列表中选择输出数据集。 如果您创建了多个计划查询，并且希望将输出数据集发送到同一云存储目标，则可以选择相应的输出数据集。 请参阅 [选择您的数据集](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#select-datasets) 以了解更多信息。

#### 计划数据集导出

最后，要计划数据集导出作为 **[!UICONTROL 正在计划]** 步骤。 在该步骤中，您可以定义计划以及输出数据集导出是否应增量导出。 请参阅 [计划数据集导出](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#scheduling) 以了解更多信息。


#### 最后步骤

[审核](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#review) 您的选择以及正确后，开始将输出数据集导出到云存储目标。

您必须 [验证](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) 成功的数据导出。 导出数据集时，Experience Platform创建一个或多个数据集 `.json` 或 `.parquet` 文件位于目标中定义的存储位置。 根据您设置的导出计划，希望将新文件存储在您的存储位置。 Experience Platform会在您指定为选定目标的一部分的存储位置中创建文件夹结构，存放导出的文件。 每次导出时都会创建一个新文件夹，其模式如下： `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. 默认文件名是随机生成的，并确保导出的文件名是唯一的。

### 流服务API

或者，您可以使用API导出和计划导出输出数据集。 中记录了所涉及的步骤 [使用流服务API导出数据集](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html).

#### 开始使用

要导出数据集，请确保您具有 [所需权限](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#permissions). 此外，还要验证要将输出数据集发送到的目标是否支持导出数据集。 然后，您必须 [收集必需标题和可选标题的值](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-values-headers) 在API调用中使用的变量。 您还需要 [识别目标的连接规范和流规范ID](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-connection-spec-flow-spec) 您打算将数据集导出到。

#### 检索符合条件的数据集

您可以 [检索符合条件的数据集列表](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#retrieve-list-of-available-datasets) ，并使用，验证您的输出数据集是否属于该列表 [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API。


#### 创建源连接

接下来，您必须 [创建源连接](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-source-connection) 对于要导出到云存储目标的输出数据集（使用其唯一ID）。 您使用 [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API。

#### 向目标进行身份验证（创建基本连接）

您现在必须 [创建基本连接](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-base-connection) 要正确进行身份验证并将凭据安全地存储到您的云存储目标，请使用 [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API。


#### 提供导出参数

接下来，您必须 [创建用于存储导出参数的其他target连接](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-target-connection) 对于输出数据集，再次使用 [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API。 这些导出参数包括位置、文件格式、压缩等。

#### 设置数据流

最后，你 [设置数据流](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#create-dataflow) 要确保使用将输出数据集导出到云存储目标，请执行以下操作 [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API。 在此步骤中，您可以使用定义导出的计划 `scheduleParams` 参数。

#### 验证数据流

至 [检查数据流是否成功执行](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#get-dataflow-runs)，使用 [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API，将数据流ID指定为查询参数。 此数据流ID是您在设置数据流时返回的标识符。

[验证](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en#verify) 成功的数据导出。 导出数据集时，Experience Platform创建一个或多个数据集 `.json` 或 `.parquet` 文件位于目标中定义的存储位置。 根据您设置的导出计划，希望将新文件存储在您的存储位置。 Experience Platform会在您指定为选定目标的一部分的存储位置中创建文件夹结构，存放导出的文件。 每次导出时都会创建一个新文件夹，其模式如下： `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. 默认文件名是随机生成的，并确保导出的文件名是唯一的。

## 结论

简而言之，模拟Adobe Analytics数据馈送功能意味着使用查询服务设置计划查询，并在计划的数据集导出中使用这些查询的结果。

>[!IMPORTANT]
>
>此用例涉及两个调度程序。 要保证模拟数据馈送功能正常工作，请确保在查询服务和数据导出中配置的计划不会干预。

