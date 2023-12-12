---
title: 模拟数据馈送功能
description: 了解如何用Experience Platform中的数据模拟Adobe Analytics数据馈送。
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: d5719dddfb4cefda761370951973d55b3904032f
workflow-type: tm+mt
source-wordcount: '2107'
ht-degree: 1%

---

# 模拟数据馈送功能

Adobe Analytics数据馈送是从Adobe Analytics中获取原始数据的有效方法。 此使用案例描述了如何从Experience Platform中获取相似类型的原始数据，以便在Adobe之外的其他平台中使用并根据贵组织的意愿使用。

## 先决条件

在使用本使用案例中所述的功能之前，请确保您满足以下所有要求：

* 将在线和离线数据发送到Experience Platform数据湖的有效实施。
* 访问查询服务，该服务将打包为基于平台的应用程序或Data Distiller加载项的一部分。 请参阅 [查询服务打包](https://experienceleague.adobe.com/docs/experience-platform/query/packaging.html?lang=en) 以了解更多信息。
* 访问导出数据集功能，已购买Real-Time CDP Prime或Ultimate包、Adobe Journey Optimizer或Customer Journey Analytics的客户可以使用此功能。 请参阅 [将数据集导出到云存储目标](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=zh-Hans) 以了解更多信息。
* 一个或多个目标(例如：Amazon S3、Google Cloud Storage)已配置为可在其中导出数据馈送的原始数据。

## 简介

模拟Adobe Analytics数据馈送的过程包括：

* 定义 **计划查询** ，使用为您的数据馈送生成数据作为输出数据集 **查询服务**.
* 定义 **计划的数据集导出** 用于使用以下方式将输出数据集导出到云存储目标 **数据集导出**.


![数据馈送](assets/data-feed.svg)


## 查询服务

Experience Platform查询服务允许您查询和联接Experience Platform数据湖中的任何数据集，就像它是一个数据库表一样。 然后，您可以将结果捕获为新数据集，以供进一步在报表中使用或导出。

使用查询服务 [用户界面](https://experienceleague.adobe.com/docs/experience-platform/query/ui/overview.html?lang=en)， a [客户端通过PostgresSQL协议连接](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=zh-Hans)，或 [RESTful API](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en) 创建和计划收集数据馈送数据的查询。

### 创建查询

您可以使用标准ANSI SQL for SELECT语句的所有功能以及其他有限命令来创建和执行为数据馈送生成数据的查询。 请参阅 [SQL语法](https://experienceleague.adobe.com/docs/experience-platform/query/sql/syntax.html?lang=en) 以了解更多信息。 除了此SQL语法外，Adobe还支持：

* 预建 [Adobe定义函数(ADF)](https://experienceleague.adobe.com/docs/experience-platform/query/sql/adobe-defined-functions.html?lang=en) 帮助执行有关存储在Experience Platform数据湖中的事件数据的常见业务相关任务，包括 [会话化](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-mobile-visit-processing.html?lang=zh-Hans) 和 [归因](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=zh-Hans)，
* 多个内置 [Spark SQL函数](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en)，
* [元数据PostgreSQL命令](https://experienceleague.adobe.com/docs/experience-platform/query/sql/metadata.html?lang=en)，
* [预准备语句](https://experienceleague.adobe.com/docs/experience-platform/query/sql/prepared-statements.html?lang=en).


#### 示例

下面列出了为数据馈送收集数据的一些查询示例。 这些示例使用 `demo_system_event_dataset_for_website_global_v1_1` 作为示例体验事件数据集，其中包含从与网站交互的客户那里收集的数据。

+++五大产品

*在网站上查看的五大产品是什么？*

```sql
select productListItems.name, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType = 'commerce.productViews'
group  by productListItems.name
order  by 2 desc
limit 5;
```

+++

+++产品交互漏斗

*网站中的各种产品交互是什么？*

```sql
select eventType, count(*)
from   demo_system_event_dataset_for_website_global_v1_1
where  eventType is not null
and    eventType <> ''
group  by eventType;
```

+++

+++人们做什么

*在作为会话的第三个页面访问“取消服务”页面之前，人们在网站上做什么？*

此查询使用Adobe定义的函数 `SESS_TIMEOUT` 和 `NEXT`.

* 此 `SESS_TIMEOUT()` 重现使用Adobe Analytics找到的访问分组。 它执行类似的基于时间的分组，但带有可自定义的参数。
* `NEXT()` 和 `PREVIOUS()` 帮助您了解客户如何在您的站点中导航。

```sql
SELECT
  webPage,
  webPage_2,
  webPage_3,
  webPage_4,
  count(*) journeys
FROM
  (
      SELECT
        webPage,
        NEXT(webPage, 1, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_2,
        NEXT(webPage, 2, true)
          OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_3,
        NEXT(webPage, 3, true)
           OVER(PARTITION BY ecid, session.num
                ORDER BY timestamp
                ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING).value
          AS webPage_4,
        session.depth AS SessionPageDepth
      FROM (
            select a._sampleorg.identification.core.ecid as ecid,
                   a.timestamp,
                   web.webPageDetails.name as webPage,
                    SESS_TIMEOUT(timestamp, 60 * 30)
                       OVER (PARTITION BY a._sampleorg.identification.core.ecid
                             ORDER BY timestamp
                             ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW)
                  AS session
            from   demo_system_event_dataset_for_website_global_v1_1 a
            where  a._sampleorg.identification.core.ecid in (
                select b._sampleorg.identification.core.ecid
                from   demo_system_event_dataset_for_website_global_v1_1 b
                where  b.web.webPageDetails.name = 'Cancel Service'
            )
        )
)
WHERE SessionPageDepth=1
and   webpage_3 = 'Cancel Service'
GROUP BY webPage, webPage_2, webPage_3, webPage_4
ORDER BY journeys DESC
LIMIT 10;
```

+++

+++多少时间

*访问“取消服务”页面后，访客需要多长时间才能致电呼叫中心？*

要回答此类查询，请使用 `TIME_BETWEEN_NEXT_MATCH()` Adobe定义的函数。 上一个匹配或下一个匹配之间的时间函数提供了一个新维度，该维度测量自特定事件以来经过的时间。

```sql
select * from (
       select _sampleorg.identification.core.ecid as ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
where r.webPage = 'Cancel Service'
limit 15;
```

+++

+++结果如何

*客户致电呼叫中心会有什么结果？*

对于此查询， `demo_system_event_dataset_for_website_global_v1_1` 数据集使用示例连接 `demo_system_event_dataset_for_call_center_global_v1_1` 包含呼叫中心交互的数据集。

```sql
select distinct r.*,
       c._sampleorg.interactionDetails.core.callCenterAgent.callFeeling,
       c._sampleorg.interactionDetails.core.callCenterAgent.callTopic,
       c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled
from (
       select _sampleorg.identification.core.ecid ecid,
              web.webPageDetails.name as webPage,
              TIME_BETWEEN_NEXT_MATCH(timestamp, web.webPageDetails.name='Call Start', 'seconds')
              OVER(PARTITION BY _sampleorg.identification.core.ecid
                  ORDER BY timestamp
                  ROWS BETWEEN CURRENT ROW AND UNBOUNDED FOLLOWING)
              AS contact_callcenter_after_seconds
       from   demo_system_event_dataset_for_website_global_v1_1
       where  web.webPageDetails.name in ('Cancel Service', 'Call Start')
) r
, demo_system_event_dataset_for_call_center_global_v1_1 c
where r.ecid = c._sampleorg.identification.core.ecid
and r.webPage = 'Cancel Service'
and c._sampleorg.interactionDetails.core.callCenterAgent.callContractCancelled IN (true,false)
and c._sampleorg.interactionDetails.core.callCenterAgent.callTopic IN ('contract', 'invoice','complaint','wifi')
limit 15;
```

+++

+++营销渠道参与(Adobe Analytics数据)

*对于以意大利语为主的Web流量，各个营销渠道的参与情况如何？*

例如，此示例使用由Adobe Analytics源连接器自动创建的数据集 `demo_data_sample_org_midvalues`.

```sql
select 
    channel.typeAtSource, count(*) 
from 
    demo_data_sample_org_midvalues 
where 
    (channel.typeAtSource IS NOT NULL
and
    web.webPageDetails.URL LIKE '%/it/it/%')
group by 
    channel.typeAtSource
order by 2 desc;
```

+++

有关更多（高级）示例查询，请参阅 [已放弃的浏览](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/abandoned-browse.html?lang=en)， [归因分析](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/attribution-analysis.html?lang=en)， [机器人过滤](https://experienceleague.adobe.com/docs/experience-platform/query/use-cases/bot-filtering.html?lang=en)以及查询服务指南中的其他示例。


#### 标识

在Experience Platform中，可以使用各种标识。 确保正确查询标识。 在上述示例中，ECID被定义为核心对象的一部分，而核心对象本身又是标识对象的一部分，这两种对象都使用体验事件核心字段组添加到架构中(例如： `_sampleorg.identification.core.ecid`)。 ECID在架构中的组织方式可能有所不同。

或者，您可以使用 `identityMap` 以查询身份。 此对象的类型为 `Map` 并使用 [嵌套数据结构](#nested-data-structure).

对于使用Adobe Analytics源连接器摄取的数据，可能有多个标识可用。 主要标识符取决于ECID或AAID是否存在。 请参阅 [Adobe Analytics数据中的主标识符](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en#how-the-analytics-source-treats-identities) 和 [AAID、ECID、AACUSTOMID和Analytics源连接器](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=zh-Hans) 了解更多信息

#### 数据馈送列

可在查询中使用的字段（列）取决于数据集所基于的架构定义。 确保您确实了解数据集背后的架构。

例如，在一些 [示例查询](#examples) 您已查询 *页面名称*.

* 在Adobe Analytics数据馈送的UI中，您可以选择 **[!UICONTROL pagename]** 作为要添加到您的数据馈送定义的列。
* 在查询服务中，您包括 `web.webPageDetails.name` 从 `demo_system_event_dataset_for_website_global_v1_1` 数据集(基于 **演示系统 — 网站的事件架构(Gobal v1.1)** 体验事件架构)。 请参阅 [Web详细信息架构字段组](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/web-details.html?lang=en) 以了解更多信息。

要了解体验事件数据集中的前Adobe Analytics数据列和XDM字段与底层架构之间的映射，请参阅 [Analytics字段映射](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=zh-Hans) 和 [Adobe Analytics ExperienceEvent完整扩展架构字段组](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) 以了解更多信息。

此外，Experience PlatformWeb SDK自动收集的信息（即装即用）可能与识别查询列相关。 请参阅 [自动收集的信息](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/automatic-information.html?lang=en) 以了解更多信息。


#### 查找

要从其他数据集查找数据，请使用标准SQL功能（WHERE子句、INNER JOIN、OUTER JOIN等）。 请参阅 [结果如何](#examples) 示例中的查询。

#### 计算

要对字段（列）执行计算，只需使用标准SQL函数(例如 `COUNT(*)` 在 [产品交互漏斗](#examples) 查询)或 [数学和统计运算符及函数](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#math) Spark SQL的一部分。

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

您可以使用 [`explode()` 或其他数组函数](https://experienceleague.adobe.com/docs/experience-platform/query/sql/spark-sql-functions.html?lang=en#arrays) 从Spark SQL获取嵌套数据结构中的数据。

例如：

```sql
select explode(identityMap) from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

或者，您可以使用点表示法引用单个元素。 例如：

```sql
select identityMap.ecid from demosys_cja_ee_v1_website_global_v1_1 limit 15;
```

有关更多信息，请参阅[在 Query Service 中使用嵌套数据结构](https://experienceleague.adobe.com/docs/experience-platform/query/key-concepts/nested-data-structures.html?lang=en)。

### 计划查询

您可以计划查询，以确保按首选间隔执行查询并生成结果。 在计划查询时，您可以定义输出数据集。

#### 使用查询编辑器

您可以使用查询编辑器计划查询。 定义查询的计划时，您可以定义输出数据集。 请参阅 [查询计划](https://experienceleague.adobe.com/docs/experience-platform/query/ui/query-schedules.html?lang=en) 以了解更多信息。


#### 使用查询服务API

或者，您可以使用RESTful API为查询定义查询和计划。 请参阅 [查询服务API指南](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=en_) 以了解更多信息。
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

确保您拥有 [所需权限](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#permissions) 要导出数据集，并且要将输出数据集发送到的目标支持导出数据集。 然后，您必须 [收集必需标题和可选标题的值](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-values-headers) 您可以在API调用中使用以及 [识别目标的连接规范和流规范ID](https://experienceleague.adobe.com/docs/experience-platform/destinations/api/export-datasets.html#gather-connection-spec-flow-spec) 您打算将数据集导出到。

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

