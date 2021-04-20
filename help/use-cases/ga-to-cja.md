---
title: 将Google Analytics数据收录到Adobe Experience Platform
description: '解释如何利用Customer Journey Analytics(CJA)将Google Analytics和火库数据引入Adobe Experience Platform。 '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 1dcc566f286b0399e5ebd1e06e9d42a9522a1684
workflow-type: tm+mt
source-wordcount: '1222'
ht-degree: 7%

---


# 将Google Analytics数据收录到Adobe Experience Platform

此用例重点介绍如何将Google Analytics数据作为数据集收录到Adobe Experience Platform。 我们解释了如何收集历史数据和实时数据。 完成后，您可以将两个数据集合在Customer Journey Analytics中，实现用户旅程的跨设备视图。

Experience Platform中的数据集由两部分组成：模式和数据集中的实际记录。 模式（简称“体验数据模型”或XDM）与数据集的列类似，与描述数据本身的蓝图或规则类似。 在平台内，Adobe提供2种模式:

* 开箱即用的模式，您可以将Google Analytics数据自动映射到(称为体验事件模式)
* 您可以创建并轻松地将模式Google Analytics数据映射到

Adobe数据模型最强大的方面之一是，它允许您将所有客户交互模式标准化为一个通用 — 这使得在CJA中将数据拼接在一起变得容易得多。

## 先决条件

要完成这些任务，您需要以下访问权限：

* 访问 Adobe Experience Platform
* 访问通用 Google Analytics（Google Analytics 360 版本）或 Google Analytics 4（免费版本或 Google Analytics 360 版本）
* 访问 Customer Journey Analytics 及其[管理权限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hans#admin-access-permissions)。

将 Google Analytics 数据引入 Adobe Experience Platform 中的方式取决于您使用的是哪个 Google Analytics 版本：

| 如果您使用... | 您还需要此许可... | 并执行此操作... |
| --- | --- | --- |
| **通用分析** | Google Analytics 360 | 执行下面说明的步骤1-3 |
| **Google Analytics 4** | 免费 GA 版本或 Google Analytics 360 | 执行下面说明的步骤1和3。 无需步骤2。 |

## 收录历史（回填）数据

### 1.将Google Analytics数据连接到BigQuery

有关详细信息，请参阅[这些说明](https://support.google.com/analytics/answer/3416092?hl=en)。 请注意，这些说明基于通用Google Analytics。

### 2.将Google Analytics会话转换为BigQuery中的事件并导出到Google Cloud 存储

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

请参阅[这些说明](https://support.google.com/analytics/answer/7029846?hl=en&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql)，其中包含有关SQL查询的说明。

以下视频还介绍了下一步，即将Google Analytics事件以JSON格式导出到Google Cloud存储。 只需单击&#x200B;**“导出”>“导出到GCS**”。 数据一旦到达，即可导入Adobe Experience Platform。

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3.将数据从Google Cloud存储导入Experience Platform并映射到XDM模式

在Experience Platform中，选择&#x200B;**[!UICONTROL 源]**&#x200B;并找到&#x200B;**[!UICONTROL Google Cloud存储]**&#x200B;选项。 从那里，您只需要找到从BigQuery保存的数据集。

请牢记这一点：

* 确保选择JSON格式。
* 您可以选择现有数据集或创建新数据集（推荐）。
* 确保为历史Google Analytics数据和实时流Google Analytics数据选择相同的模式，即使它们位于不同的数据集中。 您随后可以合并[CJA连接](/help/connections/combined-dataset.md)中的数据集。

有关说明，请视图此视频：

>[!VIDEO](https://video.tv.adobe.com/v/332676)

您可以将GA事件模式映射到您之前创建的现有数据集，或使用您选择的XDM创建新数据集。 选择模式后，Experience Platform会应用机器学习，自动将Google Analytics数据中的每个字段预映射到您的[ XDM模式](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en#ui)。

![](assets/schema-map.png)

映射很容易更改，您甚至可以从Google Analytics数据创建派生或计算字段。 完成将字段映射到XDM模式后，您可以重复计划此导入，并在摄取过程中应用错误验证。 这可确保您导入的数据没有任何问题。

视图此视频，以获取说明：

>[!VIDEO](https://video.tv.adobe.com/v/332641)

**“时间戳”计算字段**

对于Google Analytics数据中的`timestamp`模式字段，您必须在Experience Platform模式UI中创建一个特殊的计算字段。 单击&#x200B;**[!UICONTROL 添加计算字段]**&#x200B;并将`timestamp`字符串放入`date`函数中，如下所示：

`date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

然后，您需要将此计算字段保存到模式中的时间戳数据结构：

![](assets/timestamp.png)

**“_id”计算字段**

`_id`模式字段中必须有一个值 — CJA不在乎该值是什么。 您只需向字段中添加“1”即可：

![](assets/_id.png)

## 摄取实时流Google Analytics数据

您还可以将实时流事件从Google Tag Manager直接捕获到Adobe Experience Platform。

### 1.添加自定义变量

登录到Google标签管理器帐户后，您需要添加一些与Adobe相关的自定义常量变量。 您可能已经在Google标签管理器中有要发送到Google分析的变量，如客户电子邮件、客户姓名、语言和客户登录状态。 您需要定义5个新的自定义变量：

* Adobe Experience Cloud组织ID
* DCS流端点
* Experience Platform数据集ID
* 模式参考
* 页面时间戳

获取这些值可确保所有Google Analytics数据都被发送到正确的数据集，并具有正确的模式。 如果您不了解您的Experience Cloud组织或我们刚才提到的任何其他变量，您的Adobe客户经理可以帮助您跟踪它。

定义这些自定义变量后，我们可以设置一个触发器，将您已发送到Google Analytics的所有数据也发送到Experience Platform。

### 2.在Google标签管理器中设置触发器

在此示例中，定义了“帐户创建”触发器，其中`pageUrl equals account-creation`。 通过向此触发器中添加一些信息，您可以确保当用户成功进行身份验证并加载帐户创建页面时，数据会发送到Google Analytics和AEP。

您还可以引用[数据摄取和Google标签管理器](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module9/data-ingestion-using-google-tag-manager-and-google-analytics.html?lang=en#module9)。

有关说明，请视图此视频：

>[!VIDEO](https://video.tv.adobe.com/v/332668)

## 在CJA中创建到Google Analytics数据集的连接

在Adobe Experience Platform开始接收实时Google Analytics数据并回填来自BigQuery的历史Google Analytics数据后，您就可以跳入CJA并[创建您的第一个连接](/help/connections/create-connection.md)。 此连接将使用通用的“客户ID”将GA数据与所有其他客户数据整合在一起。

## 后续步骤

* 根据Google Analytics数据创建视图
接下来，您将根据包含视图数据的连接在CJA中[创建Google Analytics数据](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#cja-dataviews)。

* 在[Workspace](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/home.html?lang=en#cja-workspace)中执行一些令人惊叹的分析。 稍后查看某些报告用例。