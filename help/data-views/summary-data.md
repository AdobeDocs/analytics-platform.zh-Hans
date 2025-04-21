---
title: 摘要数据
description: 有关如何使用和配置数据视图中的摘要数据的详细信息。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: 417443ae-a1ab-483b-a8fd-cff5ee8b6263
source-git-commit: e2e04432682f94b18bf9ed25d15f906c05bfd59d
workflow-type: tm+mt
source-wordcount: '1146'
ht-degree: 99%

---

# 摘要数据

摘要数据是与个人 ID 无关的时间序列数据。摘要数据代表不同聚合级别的聚合数据，例如活动。您可以在 Customer Journey Analytics 中使用这些数据来支持各种用例。例如，包含日期和单个量度值的数据，或者包含多个维度和量度的数据。

然后可以使用这些摘要数据来呈现高级绩效量度或进行分析。例如，摘要数据可以是广告展示次数、电子邮件打开次数、广告支出、销售商品成本、标准普尔指数等。您还可以使用摘要数据按小时或按天上传目标。

>[!NOTE]
>
>摘要数据是来自摘要数据集的时间序列数据。该摘要数据集基于一个以 XDM 摘要量度类别为基础类别的架构。
>仅支持基于小时或每日的时间序列数据。

>[!TIP]
>
>您可以配置一个连接、数据视图并随后&#x200B;**仅对**&#x200B;摘要数据进行报告。您的配置中不需要有额外的事件、轮廓或查找数据。


## 示例

使用摘要数据的一个例子是将汇总的广告活动数据与网站上点击流数据结合起来进行报告。

### 摘要数据

您的摘要数据包含以下广告活动数据。

| 营销活动代码 | 展示次数 | 成本 |
|---|---:|---:|
| abc123 | 1,250 | $1,500 |
| def456 | 775 | $650 |
| ghi789 | 500 | $500 |


### 事件数据

您的网站点击流数据包含以下事件。

| 跟踪代码 | 点进次数 | 收入 |
|---|---:|---:|
| abc123 | 1,250 | $7,200 |
| def456 | 775 | $1,250 |
| ghi789 | 500 | $750 |

### 综合数据

正如在[组合事件数据集](/help/connections/combined-dataset.md)中解释的那样，在定义一个连接时，Customer Journey Analytics 会创建一个整体的组合事件数据集。当您为源自摘要数据集的维度配置数据视图时，可以对维度进行分组和隐藏，以为在工作区中进行报告做准备。具体来说，对于摘要数据，根据[摘要数据组的组件](component-settings/summary-data-group.md)配置，将摘要数据与事件数据组合在一起。

| 跟踪代码 | 营销活动代码 | 展示次数 | 成本 | 点进次数 | 收入 |
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1,250 | $1,500 | 1,250 | $7,200 |
| def456 | def123 | 775 | $650 | 775 | $1,250 |
| ghi789 | ghi789 | 500 | $500 | 500 | $750 |



### 报告

结合汇总的事件数据和网站点击流数据，您可以在工作区中报告广告支出回报率 (ROAS)。

| 跟踪代码 | 展示次数 | 成本 | 点进次数 | 收入 | ROAS |
|---|--:|--:|--:|--:|:--|
| abc123 | 1,250 | $1,500 | 1,250 | $7,200 | 4.80 |
| def456 | 775 | $650 | 775 | $1,250 | 1.92 |
| ghi789 | 500 | $500 | 500 | $750 | 1.50 |


### 查找数据

如果您想使用在附加的查找数据集中定义的维度（例如，营销活动名称）进行报告，则必须遵循以下附加步骤：

1. 创建一个新的派生字段，该字段使用 [Lookup](/help/data-views/derived-fields/derived-fields.md#lookup) 函数从查找数据集中查找该营销活动的名称。在 [Lookup](/help/data-views/derived-fields/derived-fields.md#lookup) 函数的定义中，使用营销活动代码和跟踪代码之间的匹配项来查找营销活动名称。
1. 将新创建的派生字段作为维度组件添加到数据视图中。
1. 配置营销活动名称维度组件（来自查找数据集），以使用新创建的派生字段对摘要数据进行分组。

请参阅[摄取和报告摘要数据](/help/use-cases/data-views/summary-data.md)用例，了解有关如何使用、报告和分析 Customer Journey Analytics 中的摘要数据的详细文章。


## 先决条件

要在报告和分析中正确使用摘要数据，需要满足一些先决条件。以下部分详细介绍了这些先决条件。

### 粒度和时区

在 Customer Journey Analytics 中配置包含摘要数据的数据集时，您会注意到粒度是从数据中自动得出的。**[!UICONTROL 时间戳]**&#x200B;和&#x200B;**[!UICONTROL 时区]**&#x200B;下拉菜单选项被禁用，因为它们均源自架构定义。

#### 粒度

您不能使用一个摘要数据架构在一个数据集（或不同的数据集）中混合和匹配每小时和每日粒度的摘要数据。例如，如果您有广告活动数据的每日和每小时粒度摘要数据，则需要两种架构：一种用于每日摘要数据，一种用于每小时摘要数据。然后将相关的细粒度数据上传到与相应架构相关联的数据集中（例如，将每小时数据上传到与每小时摘要数据架构相关联的数据集中）。

#### 时区

摘要数据的时区在 Experience Platform 中的摘要架构级别定义。时区仅适用于每小时粒度的数据。

- 对于每日粒度，除非时间戳中包含时区偏移量，否则 Experience Platform 将采用 UTC。添加包含每日摘要数据的摘要数据集时，Customer Journey Analytics 会忽略架构上设置的时区定义，并遵循与数据集中数据的时间戳相关联的日期。
- 对于每小时粒度，Customer Journey Analytics 在解释时间戳时会遵循 Experience Platform 中摘要数据架构上配置的时区。下表提供了该解释的一些示例。

  | 时间戳<br/>源数据 | 时区<br/>架构 | 时间戳<br/>Experience<br/>Platform | 时区<br/>数据<br/>视图 | 时间戳<br/>Customer<br/>Journey<br>Analytics |
  |---|---|---|:---|---|
  | 2024-07-29T01:00:00 | *默认 GMT* | 2024-07-29T01:00:00 | GMT | 2024-07-29T01:00:00 |
  | 2024-07-29T01:00:00 | *默认 GMT* | 2024-07-29T01:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | *默认 GMT* | 2024-07-30T06:00:00 | GMT | 2024-07-30T06:00:00 |
  | 2024-07-30T01:00:00-05:00 | *默认 GMT* | 2024-07-30T06:00:00 | PST | 2024-07-29T23:00:00 |
  | 2024-08-02 | *默认 GMT* | 2024-08-02T00:00:00 | IST | 2024-08-02T05:00:00 |
  | 2024-07-29T01:00:00 | `America/`<br/>`Los_Angeles` | 2024-07-28T18:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | `Australia/`<br/>`Sydney` | 2024-07-30T17:00:00 | CET | 2024-07-30T08:00:00 |

  对于具有 30 分钟偏移量的时区（例如 IST，印度标准时间），报告摘要数据时会忽略这 30 分钟的偏移量。例如：12:30 会报告为 12:00。


为确保您的每小时粒度摘要数据使用正确的时区，您必须确保用于摘要数据的架构配置了正确的时区。

要为您的摘要数据架构配置粒度和时区，您必须使用以下 API 调用，因为没有可用的等效用户界面。

```shell
curl -X POST \
https://platform.adobe.io/data/foundation/schemaregistry/tenant/descriptors \
 -H "Authorization: Bearer {$ACCESS_TOKEN}" \
 -H 'Content-Type: application/json' \
 -H 'x-api-key: {$API_KEY}' \
 -H 'x-gw-ims-org-id: {$ORG_ID}' \
 -H 'x-sandbox-name: {$SANDBOX_NAME}' \
 -d '{  
    "@type": "xdm:descriptorTimeSeriesGranularity",
    "xdm:sourceSchema": "{$SCHEMA_ID}",
    "xdm:sourceVersion": 1,
    "xdm:granularity": "{$GRANULARITY}",
    "xdm:ianaTimezone": "{$TIMEZONE}" 
 }'
```

| 变量 | 值 |
|---|---|
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | 有关如何为这些变量指定值的更多信息，请参阅[验证和访问 Experience Platform API](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/landing/platform-apis/api-authentication)。 |
| `$SCHEMA_ID` | 您可以在 Experience Platform UI 中找到架构的 ID。从架构列表中选择您的摘要架构，然后在右侧面板中找到 **[!UICONTROL API 用法]** > **[!UICONTROL 架构 ID]**。使用该 ID 作为值。 |
| `$GRANULARITY` | 指定 `hour` 或 `day` 为值。 |
| `$TIMEZONE` | 从 [tz 数据库时区列表](https://zh.wikipedia.org/wiki/List_of_tz_database_time_zones)的 TZ 身份标识符列中指定正确的时区身份标识符值。例如：`America/Los_Angeles`。 |

## 组件设置

确保摘要数据组的组件设置相同。请参阅[摘要数据组的组件设置](component-settings/summary-data-group.md#same-component-settings)，以了解更多详细信息。

>[!MORELIKETHIS]
>
>- 请参阅[使用摘要数据](/help/use-cases/data-views/summary-data.md)一文，了解有关如何使用和报告摘要数据的详细用例示例。
>- 博客： [摘要数据如何增强Adobe Customer Journey Analytics数据集](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/how-summary-data-enhances-adobe-customer-journey-analytics/ba-p/704635)

