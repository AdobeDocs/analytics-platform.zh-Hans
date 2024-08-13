---
title: 摘要数据
description: 有关如何在数据视图中使用和配置摘要数据的详细信息和信息。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: cba5904191b0602557903b5b9f32a2b793c8207d
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 4%

---


# 摘要数据

摘要数据是与个人ID无关的时间系列数据。 摘要数据表示不同聚合级别的聚合数据，例如促销活动。 您可以在Customer Journey Analytics中使用此数据来支持各种用例。 例如，包含日期和单个量度值的数据，或者包含多个维度和量度的数据。

然后，可使用此概要数据来呈现高级别性能指标或执行分析。 概要数据的示例包括广告展示次数、电子邮件打开次数、广告支出、已售商品成本、标准普尔(S&amp;P)指数等。 您还可以使用概要数据每小时或每天上传目标或目标。

>[!NOTE]
>
>摘要数据是摘要数据集中的时间序列数据。 该摘要数据集基于一个使用XDM摘要量度类作为其基类的架构。
>仅支持基于每小时或每天的时间系列数据。

>[!TIP]
>
>您可以配置连接、数据视图，然后仅报告&#x200B;**个**&#x200B;摘要数据。 您的配置中不需要包含其他事件、配置文件或查找数据。


## 示例

使用摘要数据的示例如下：将汇总的广告促销活动数据与网站上的点击流数据相结合，以便进行报告。

### 摘要数据

您的摘要数据包含以下广告促销活动数据。

| 营销活动代码 | 展示次数 | 成本 |
|---|---:|---:|
| abc123 | 1,250 | 1,500美元 |
| def456 | 775 | 650美元 |
| ghi789 | 500 | 500美元 |


### 事件数据

您的网站点击流数据包含以下事件。

| 跟踪代码 | 点进次数 | 收入 |
|---|---:|---:|
| abc123 | 1,250 | 7,200美元 |
| def456 | 775 | 1,250美元 |
| ghi789 | 500 | 750美元 |

### 组合数据

如[组合事件数据集](/help/connections/combined-dataset.md)中所述，在定义连接时，Customer Journey Analytics会创建一个整体的组合事件数据集。 为源自摘要数据集的维度配置数据视图时，可使用选项对维度进行分组和隐藏，以备在Workspace中生成报表。 专门针对摘要数据，摘要数据会根据[摘要数据组组件](component-settings/summary-data-group.md)配置与事件数据相结合。

| 跟踪代码 | 营销活动代码 | 展示次数 | 成本 | 点进次数 | 收入 |
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1,250 | 1,500美元 | 1,250 | 7,200美元 |
| def456 | def123 | 775 | 650美元 | 775 | 1,250美元 |
| ghi789 | ghi789 | 500 | 500美元 | 500 | 750美元 |



### 报告

通过将汇总的事件数据和现场点击流数据相结合，您可以在Workspace中报告广告支出回报率(ROAS)。

| 跟踪代码 | 展示次数 | 成本 | 点进次数 | 收入 | ROAS |
|---|--:|--:|--:|--:|:--|
| abc123 | 1,250 | 1,500美元 | 1,250 | 7,200美元 | 4.80 |
| def456 | 775 | 650美元 | 775 | 1,250美元 | 1.92 |
| ghi789 | 500 | 500美元 | 500 | 750美元 | 1.50 |


有关如何在Customer Journey Analytics中使用、报告和分析摘要数据的详细文章，请参阅[摘要数据的摄取和报告](/help/use-cases/data-views/summary-data.md)用例。


## 先决条件

要在报表和分析中正确使用摘要数据，需要满足许多先决条件。 以下部分详细介绍了这些先决条件。

### 粒度和时区

在配置包含Customer Journey Analytics中摘要数据的数据集时，您会注意到粒度是自动从数据派生的。 已禁用&#x200B;**[!UICONTROL 时间戳]**&#x200B;和&#x200B;**[!UICONTROL 时区]**&#x200B;下拉列表的选择，因为两者都派生自架构定义。

#### 粒度

您不能在一个数据集（或在不同数据集）中，使用一个摘要数据架构，将每小时和每天的摘要数据粒度混合和匹配。 例如，如果您的广告促销活动数据确有每天和每小时粒度摘要数据，则需要两个架构：一个用于每天，另一个用于每小时摘要数据。 然后，将相关的粒度数据上传到与正确架构关联的数据集中（例如，将每小时数据上传到与每小时摘要数据架构关联的数据集中）。

#### 时区

摘要数据的时区在Experience Platform的摘要架构级别定义。 时区仅适用于每小时粒度数据。

- 对于每日粒度，除非时间戳中包含时区偏移，否则Experience Platform采用UTC时间。 添加包含每日摘要数据的摘要数据集时，Customer Journey Analytics会忽略架构上设置的时区定义，并遵循数据集中与时间戳关联的日期。
- 对于每小时粒度，Customer Journey Analytics在解释时间戳时遵循在Experience Platform的摘要数据架构上配置的时区。 下表提供了这种解释的一些例子。

  | 时间戳<br/>源数据 | 时区<br/>架构 | 时间戳<br/>Experience<br/>平台 | 时区<br/>数据<br/>视图 | 时间戳<br/>客户<br/>历程<br>分析 |
  |---|---|---|:---|---|
  | 2024-07-29T01:00:00 | *默认GMT* | 2024-07-29T01:00:00 | GMT | 2024-07-29T01:00:00 |
  | 2024-07-29T01:00:00 | *默认GMT* | 2024-07-29T01:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | *默认GMT* | 2024-07-30T06:00:00 | GMT | 2024-07-30T06:00:00 |
  | 2024-07-30T01:00:00-05:00 | *默认GMT* | 2024-07-30T06:00:00 | PST | 2024-07-29T23:00:00 |
  | 2024-08-02 | *默认GMT* | 2024-08-02T00:00:00 | IST | 2024-08-02T05:00:00 |
  | 2024-07-29T01:00:00 | `America/`<br/>`Los_Angeles` | 2024-07-28T18:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | `Australia/`<br/>`Sydney` | 2024-07-30T17:00:00 | CET | 2024-07-30T08:00:00 |

  对于具有30分钟偏移量的时区（例如IST、印度标准时间），在报告摘要数据时将删除30分钟偏移量。 例如：12:30报告为12:00。


要确保，对于每小时粒度的摘要数据使用适当的时区，您必须确保用于摘要数据的架构配置适当的时区。

要为摘要数据架构配置粒度和时区，您必须使用以下API调用，因为没有等效的用户界面可用。

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
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | 有关如何为这些Experience Platform指定值的详细信息，请参阅[验证和访问变量API](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-authentication)。 |
| `$SCHEMA_ID` | 您可以在Experience PlatformUI中找到架构的ID。 从架构列表中选择您的摘要架构，然后在右侧面板中找到&#x200B;**[!UICONTROL API使用情况]** > **[!UICONTROL 架构ID]**。 使用该id作为值。 |
| `$GRANULARITY` | 指定`hour`或`day`作为值。 |
| `$TIMEZONE` | 从tz数据库时区](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)的[List的TZ标识符列中指定适当的时区标识符值。 例如：`America/Los_Angeles`。 |

## 组件设置

确保摘要数据组的组件设置相同。 有关更多详细信息，请参阅[摘要数据组组件设置](component-settings/summary-data-group.md#same-component-settings)。

>[!MORELIKETHIS]
>
>有关如何使用和报告摘要数据的详细用例示例，请参阅[摄取和使用摘要数据](/help/use-cases/data-views/summary-data.md)文章。
