---
title: 将Google Analytics数据收录到Adobe Experience Platform
description: '解释如何利用Customer Journey Analytics(CJA)将Google Analytics和火库数据引入Adobe Experience Platform。 '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 0f1d7e0d26eefec46edabba4d0b8709c3bad6b8f
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 1%

---


# 将Google Analytics数据收录到Adobe Experience Platform

此用例重点介绍如何将Google Analytics数据作为数据集收录到Adobe Experience Platform。 我们将解释如何收集历史数据和实时数据。 完成后，您可以将两个数据集合在Customer Journey Analytics中，实现用户旅程的跨设备视图。

Experience Platform中的数据集由两部分组成：模式和数据集中的实际记录。 模式（简称“体验数据模型”或XDM）与数据集的列类似，与描述数据本身的蓝图或规则类似。 在平台内，Adobe提供2种模式:

* 开箱即用的模式，您可以将Google Analytics数据自动映射到(称为体验事件模式)
* 您可以创建并轻松地将模式Google Analytics数据映射到

Adobe数据模型最强大的方面之一是，它允许您将所有客户交互模式标准化为一个通用 — 这使得在CJA中将数据拼接在一起变得容易得多。

## 先决条件

要完成这些任务，您需要以下访问权限：

* 访问Adobe Experience Platform
* 访问通用Google Analytics(Google Analytics360版本)或Google Analytics4(免费版本或Google Analytics360版本)
* 访问Customer Journey Analytics及其[管理权限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hans#admin-access-permissions)。

如何将Google Analytics数据引入Adobe Experience Platform取决于您使用的Google Analytics版本：

| 如果您使用... | 您还需要这个许可证…… | 然后…… |
| --- | --- | --- |
| **通用分析** | Google Analytics360 | 执行下面说明步骤1 - 5 |
| **Google Analytics4** | 免费的GA版本或Google Analytics360 | 执行下面说明的步骤1和3-5。 无需步骤2。 |

## 收录历史数据

### 1.将Google Analytics数据连接到BigQuery

请注意，以下说明基于通用Google Analytics。 它们适用于历史数据。 有关实时流数据的说明，请转到[将实时流数据引入AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/ga-to-cja.html?lang=en#ingest-live-streaming-google-analytics-data)。

请参阅[这些说明](https://support.google.com/analytics/answer/3416092?hl=en)。

### 2.将Google Analytics会话转换为BigQuery中的事件

>[!IMPORTANT]
>
>此步骤仅适用于Universal Analytics客户

GA数据将每个记录作为用户会话存储在其数据中，而不是单独事件。 您需要创建SQL查询，以将Universal Analytics数据转换为符合Experience Platform规范的格式。 您将“unnest”函数应用于GA模式中的“hits”字段。 以下是您可以使用的SQL示例：

`SELECT
*,
timestamp_seconds(`` + hit.time) AS `` 
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
`visitStartTimetimestampyour_bq_table_2021_04_*`,
UNNEST(hits) AS hit 
)`

查询完成后，将完整结果保存到BigQuery表中。

请参阅[这些说明](https://support.google.com/analytics/answer/7029846?hl=en&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql)。

或视图此视频：

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3.将JSON格式的Google Analytics事件导出到Google Cloud存储，并将它们保存到存储桶

接下来，您将以JSON格式将Google Analytics事件导入Google Cloud存储。

请参阅[这些说明](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)。

### 4.将来自Google Cloud存储的数据导入Experience Platform

在Experience Platform中，选择&#x200B;**[!UICONTROL 源]**&#x200B;并找到&#x200B;**[!UICONTROL Google Cloud存储]**&#x200B;选项。 从那里，您只需要找到从“大查询”保存的数据集。

视图此视频，以获取说明：

>[!VIDEO](https://video.tv.adobe.com/v/332641)

### 5.将GCS事件导入Adobe Experience Platform并映射到XDM模式

接下来，您可以将GA事件模式映射到您之前创建的现有数据集，或使用您选择的XDM创建新数据集。 选择模式后，Experience Platform会应用机器学习，自动将Google Analytics数据中的每个字段映射到您自己的模式。

映射很容易更改，您甚至可以从Google Analytics数据创建派生或计算字段。 完成将字段映射到XDM模式后，您可以重复计划此导入，并在摄取过程中应用错误验证。 这可确保您导入的数据没有任何问题。

## 摄取实时流Google Analytics数据

您还可以将实时流事件从Google Tag Manager直接捕获到Adobe Experience Platform。

### 1.添加自定义变量

登录到Google Tag Manager帐户后，您需要添加与Adobe组织ID和数据集ID相关的自定义常量变量。 您可能已经在Google标签管理器中有要发送到Google分析的变量，如客户电子邮件、客户姓名、语言和客户登录状态。 您需要定义5个新的自定义变量：

* Adobe Experience Cloud组织ID
* DCS流端点
* Experience Platform数据集ID
* 模式参考
* 页面时间戳。

获取这些值可确保所有Google Analytics数据都被发送到正确的数据集，并具有正确的模式。 如果您不了解您的Experience Cloud组织或我们刚才提到的任何其他变量，您的Adobe客户经理可以帮助您跟踪它。

定义这些自定义变量后，我们可以设置一个触发器，将您已发送到Google Analytics的所有数据也发送到Experience Platform。

### 2.在Google标签管理器中设置触发器

在此示例中，定义了“帐户创建”触发器，其中`pageUrl equals account-creation`。 通过向此触发器中添加一些信息，您可以确保当用户成功进行身份验证并加载帐户创建页面时，数据会发送到Google Analytics和AEP。

有关说明，请视图此视频：

>[!VIDEO](https://video.tv.adobe.com/v/332668)

## 在CJA中创建到Google Analytics数据集的连接

Adobe Experience Platform开始接收实时Google Analytics数据，并且您已从BigQuery回填历史Google Analytics数据后，您就可以跳到CJA并
[创建您的第一个连接](/help/connections/create-connection.md)。 此连接将使用通用的“客户ID”将GA数据与所有其他客户数据整合在一起。

## 在Workspace中创作令人惊叹的分析

此处提供更多内容。