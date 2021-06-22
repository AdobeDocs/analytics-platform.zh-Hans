---
title: 将Google Analytics数据摄取到Adobe Experience Platform
description: '说明如何利用Customer Journey Analytics(CJA)将Google Analytics数据摄取到Adobe Experience Platform。 '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
source-git-commit: 316819116e9b47110763479af4e8504a2bffaff3
workflow-type: tm+mt
source-wordcount: '1178'
ht-degree: 7%

---


# 将Google Analytics数据摄取到Adobe Experience Platform

此用例重点介绍如何将Google Analytics数据作为数据集摄取到Adobe Experience Platform。 我们将介绍如何同时摄取历史和实时数据。 完成后，您可以在Customer Journey Analytics中合并这两个数据集，以便跨设备查看用户历程。

Experience Platform中的数据集由两部分组成：数据集中的架构和实际记录。 架构（我们称之为体验数据模型或XDM ，简称为体验数据模型）与数据集的列类似，也与描述数据本身的Blueprint或规则类似。 在平台中，Adobe提供了2种类型的架构：

* 现成的架构，您可以将Google Analytics数据自动映射到（称为体验事件架构）
* 自定义架构，您可以创建并轻松地将Google Analytics数据映射到

Adobe数据模型最强大的一个方面是，它允许您将所有客户交互数据标准化为一个通用架构 — 这样在CJA中将数据拼合在一起会更轻松。

## 先决条件

要完成这些任务，您需要以下访问权限和权限：

* 访问 Adobe Experience Platform
* 访问通用 Google Analytics（Google Analytics 360 版本）或 Google Analytics 4（免费版本或 Google Analytics 360 版本）
* 访问 Customer Journey Analytics 及其[管理员权限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hans#admin-access-permissions)。

将 Google Analytics 数据引入 Adobe Experience Platform 中的方式取决于您使用的是哪个 Google Analytics 版本：

| 如果您使用... | 您还需要此许可... | 并执行此操作... |
| --- | --- | --- |
| **Universal Analytics** | Google Analytics 360 | 执行下面说明的步骤1-3 |
| **Google Analytics 4** | 免费 GA 版本或 Google Analytics 360 | 执行下面说明的步骤1和步骤3。 无需步骤2。 |

## 摄取历史（回填）数据

### 1.将您的Google Analytics数据连接到BigQuery

有关详细信息，请参见[这些说明](https://support.google.com/analytics/answer/3416092?hl=en)。 请注意，这些说明基于通用Google Analytics。

### 2.将Google Analytics会话转换为BigQuery中的事件，并导出到Google云存储

>[!IMPORTANT]
>
>此步骤仅适用于Universal Analytics客户

GA数据将每个记录作为用户会话存储在其数据中，而不是作为单个事件存储。 您需要创建SQL查询，以将Universal Analytics数据转换为与Experience Platform兼容的格式。 将“取消嵌套”函数应用于GA架构中的“点击”字段。 以下是您可以使用的SQL示例：

```
SELECT
   *,
   timestamp_seconds(`visitStartTime` + hit.time) AS `timestamp` 
FROM
   (
      SELECT
         fullVisitorId,
         visitNumber,
         visitId,
         visitStartTime,
         trafficSource,
         socialEngagementType,
         channelGrouping,
         device,
         geoNetwork,
         hit 
      FROM
         `your_bq_table_2021_04_*`,
         UNNEST(hits) AS hit 
   )
```

查询完成后，将完整结果保存到BigQuery表中。

请参阅[这些说明](https://support.google.com/analytics/answer/7029846?hl=en&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql)，其中包含有关SQL查询的说明。

以下视频还介绍了下一步，该步骤将以JSON格式将Google Analytics事件导出到Google云存储。 只需单击&#x200B;**导出>导出到GCS**。 数据一旦到达，即可提取到Adobe Experience Platform。

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3.将数据从Google云存储导入Experience Platform并映射到XDM架构

在Experience Platform中，选择&#x200B;**[!UICONTROL 源]**&#x200B;并找到&#x200B;**[!UICONTROL Google云存储]**&#x200B;选项。 在此处，您只需查找从BigQuery保存的数据集即可。

请牢记这一点：

* 确保选择JSON格式。
* 您可以选择现有数据集，或创建新数据集（推荐）。
* 确保为历史Google Analytics数据和实时流Google Analytics数据选择相同的架构，即使它们位于不同的集中。 随后可以合并[CJA连接](/help/connections/combined-dataset.md)中的数据集。

有关说明，请观看此视频：

>[!VIDEO](https://video.tv.adobe.com/v/332676)

您可以将GA事件数据映射到您之前创建的现有数据集中，或使用您选择的任何XDM架构创建新数据集。 选择架构后，Experience Platform会应用机器学习，自动将Google Analytics数据中的每个字段预映射到您的[XDM架构](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en#ui)。

![](assets/schema-map.png)

映射非常容易更改，您甚至可以从Google Analytics数据创建派生或计算字段。 完成将字段映射到XDM架构后，您可以计划定期进行此导入，并在摄取过程中应用错误验证。 这可确保您导入的数据不会出现任何问题。

**“时间戳”计算字段**

对于Google Analytics数据中的`timestamp`架构字段，必须在Experience Platform架构UI中创建特殊的计算字段。 单击&#x200B;**[!UICONTROL 添加计算字段]**&#x200B;并将`timestamp`字符串包裹在`date`函数中，如下所示：

`date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

然后，您需要将此计算字段保存到架构中的时间戳数据结构：

![](assets/timestamp.png)

**“_id”计算字段**

`_id`架构字段中必须有一个值 — CJA不关心该值是什么。 您只需在字段中添加“1”即可：

![](assets/_id.png)

## 摄取实时流Google Analytics数据

您还可以直接从Google Tag Manager捕获实时流事件到Adobe Experience Platform。

### 1.添加自定义变量

登录到Google Tag Manager帐户后，您需要添加一些与Adobe相关的自定义常量变量。 您可能已在Google Tag Manager中拥有要发送到Google Analytic的变量，例如客户电子邮件、客户名称、语言和客户登录状态。 您需要定义5个新的自定义变量：

* Adobe Experience Cloud组织ID
* DCS流端点
* Experience Platform数据集ID
* 模式参考
* 页面时间戳

获取这些值可确保所有Google Analytics数据都被发送到正确的数据集，并具有正确的架构。 如果您不知道您的Experience Cloud组织或我们刚才提到的任何其他变量，您的Adobe客户经理可以帮助您跟踪。

定义这些自定义变量后，我们可以设置一个触发器，以将您已发送的所有数据发送至Google Analytics，并发送至Experience Platform。

### 2.在Google Tag Manager中设置触发器

在此示例中，已定义“帐户创建”触发器，其中`pageUrl equals account-creation`。 通过向此触发器添加一些信息，您可以确保用户成功进行身份验证并加载帐户创建页面时，数据会同时发送到Google Analytics和AEP。

您还可以参阅[数据摄取和Google Tag Manager](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module9/data-ingestion-using-google-tag-manager-and-google-analytics.html?lang=en#module9)。

有关说明，请观看此视频：

>[!VIDEO](https://video.tv.adobe.com/v/332668)

## 在CJA中创建与Google Analytics数据集的连接

Adobe Experience Platform开始接收实时Google Analytics数据，并回填来自BigQuery的历史Google Analytics数据后，您便可以跳入CJA并[创建您的第一个连接](/help/connections/create-connection.md)。 此连接将使用通用的“客户ID”将GA数据与所有其他客户数据拼合在一起。

## 后续步骤

* 根据包含Google Analytics数据的连接创建[数据视图](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#cja-dataviews)。

* 在Workspace](/help/use-cases/ga-to-cja-reporting.md)中，进行一些令人惊叹的[分析。