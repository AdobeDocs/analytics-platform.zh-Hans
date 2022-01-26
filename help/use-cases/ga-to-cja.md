---
title: 将 Google Analytics 数据摄取到 Adobe Experience Platform
description: '阐述如何利用 Customer Journey Analytics (CJA) 将您的 Google Analytics 数据摄取到 Adobe Experience Platform。 '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
source-git-commit: 445317efa636024dbaf0ac34b6a74b52b92b9000
workflow-type: tm+mt
source-wordcount: '1178'
ht-degree: 97%

---


# 将 Google Analytics 数据摄取到 Adobe Experience Platform

此用例侧重于如何将 Google Analytics 数据作为数据集摄取到 Adobe Experience Platform。我们解释了如何同时摄取历史和实时数据。完成后，您可以在 Customer Journey Analytics 中合并两个数据集，以实现用户历程的跨设备视图。

Experience Platform 中的数据集由两部分组成：架构和数据集中的实际记录。架构（我们简称其为 Experience Data Model 或 XDM）类似于数据集的列，也类似于描述数据本身的蓝图或规则。在该 Platform 内，Adobe 提供 2 种类型的架构：

* 开箱即用的架构，称为 Experience Event 架构，可自动将您的 Google Analytics 数据映射到其中
* 您可以创建并轻松将 Google Analytics 数据映射到其中的自定义架构

Adobe 数据模型最强大的地方之一是，它允许您将所有客户互动数据标准化为一个公共架构 - 这使得在 CJA 中将数据拼合在一起很容易。

## 先决条件

要完成这些任务，您需要以下访问和权限：

* 访问 Adobe Experience Platform
* 访问通用 Google Analytics（Google Analytics 360 版本）或 Google Analytics 4（免费版本或 Google Analytics 360 版本）
* 访问 Customer Journey Analytics以及它的[管理员权限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hans#admin-access-permissions)。

将 Google Analytics 数据引入 Adobe Experience Platform 中的方式取决于您使用的是哪个 Google Analytics 版本：

| 如果您使用... | 您还需要此许可... | 并执行此操作... |
| --- | --- | --- |
| **Universal Analytics** | Google Analytics 360 | 执行以下说明中的第 1-3 步 |
| **Google Analytics 4** | 免费 GA 版本或 Google Analytics 360 | 执行以下说明中的第 1 和第 3 步。无需第 2 步。 |

## 摄取历史（回填）数据

### 1. 将您的 Google Analytics 数据连接到 BigQuery

有关更多信息，请参阅[这些说明](https://support.google.com/analytics/answer/3416092?hl=en)。请注意，这些说明基于通用 Google Analytics。

### 2. 将 Google Analytics 会话转换为 BigQuery 中的事件并导出到 Google 云存储

>[!IMPORTANT]
>
>此步骤仅适用于 Universal Analytics 客户

GA 数据将数据中的每个记录存储为用户会话，而不是单个事件。您需要创建 SQL 查询，以便将 Universal Analytics 数据转换为符合 Experience-Platform 的格式。将“unnest”函数应用于 GA 架构中的“点击数”字段。以下是您可以使用的 SQL 示例：

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

查询完成后，将完整结果保存到 BigQuery 表中。

请参考[这些说明](https://support.google.com/analytics/answer/7029846?hl=en&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql)，其中包括有关 SQL 查询的说明。

以下视频也解释了此后续步骤，即以 JSON 格式将 Google Analytics 事件导出到 Google 云存储。只需单击&#x200B;**“导出”>“导出到 GCS”**。到了这一步，数据就已准备好被拉入 Adobe Experience Platform 了。

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3. 将 Google 云存储的数据导入 Experience Platform 并映射到 XDM 架构

在 Experience Platform 中，选择&#x200B;**[!UICONTROL 源]**&#x200B;并查找 **[!UICONTROL Google 云存储]**&#x200B;选项。从那里，您只需要从 BigQuery 找到保存的数据集。

请牢记这一点：

* 确保选择 JSON 格式。
* 您可以选择现有数据集，也可以创建新的数据集（推荐）。
* 务必为历史 Google Analytics 数据和实时流式传输 Google Analytics 数据选择同样的架构，即使它们位于分开的数据集中。然后，您可以在 [CJA 连接](/help/connections/combined-dataset.md)中合并数据集。

有关说明，请观看此视频：

>[!VIDEO](https://video.tv.adobe.com/v/332676)

您可以将 GA 事件数据映射到以前创建的现有数据集，或者使用所选择的任何 XDM 架构创建新的数据集。选择好架构后，Experience Platform 则应用机器学习，自动将 Google Analytics 数据中的每个字段预映射到您的 [XDM 架构](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hans#ui)。

![](assets/schema-map.png)

映射很容易更改，您甚至可以根据 Google Analytics 数据创建派生或计算字段。完成将字段映射到 XDM 架构中后，您可以定期计划此导入，并在摄取过程中应用错误验证。这可以确保您导入的数据没有任何问题。

**“时间戳”计算字段**

对于 Google Analytics 数据中的 `timestamp` 架构字段，您必须在 Experience Platform 架构 UI 中创建特殊计算字段。单击&#x200B;**[!UICONTROL 添加计算字段]**&#x200B;并将`timestamp`字符串包裹在`date`函数中，如下所示：

`date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

然后，您需要将此计算字段保存到架构中的时间戳数据结构：

![](assets/timestamp.png)

**“_id”计算字段**

`_id` 架构字段中必须具有值 - CJA 不管这个值是什么。您可以只在该字段中添加“1”：

![](assets/_id.png)

## 摄取实时流式传输 Google Analytics 数据

您还可以直接将 Google Tag Manager 的实时流式传输事件捕获到 Adobe Experience Platform。

### 1. 添加自定义变量

登录 Google Tag Manager 帐户后，您需要添加一些与 Adobe 相关的自定义常量变量。您可能已在Google标签管理器中拥有要发送到Google Analytics的变量，例如客户电子邮件、客户名称、语言和客户登录状态。 您需要定义 5 个新的自定义变量：

* Adobe Experience Cloud 组织 ID
* DCS 流式传输端点
* Experience Platform 数据集 ID
* 架构参考
* 页面时间戳

获取这些值可以确保所有 Google Analytics 数据都发送到正确的数据集并具有正确的架构。如果您不知道您的 Experience Cloud 组织或我们刚才提到的任何其他变量，那么您的 Adobe 客户经理可以帮助您追踪到它们。

当您定义了这些自定义变量后，我们可以设置一个触发器，将您发送到 Google Analytics 的所有数据也发送到 Experience Platform。

### 2. 在 Google Tag Manager 中设置触发器

在此示例中，已定义“客户创建”触发器，其中 `pageUrl equals account-creation`。通过在此触发器中添加一些信息，您可以确保当用户验证成功并且客户创建页面加载时，数据将同时发送到 Google Analytics 和 AEP。

您还可以参考[数据摄取和 Google Tag Manager](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module9/data-ingestion-using-google-tag-manager-and-google-analytics.html?lang=zh-Hans#module9)。

有关说明，请观看此视频：

>[!VIDEO](https://video.tv.adobe.com/v/332668)

## 在 CJA 中创建与 Google Analytics 数据集的连接

当 Adobe Experience Platform 开始接收实时 Google Analytics 数据，并且您已回填了来自 BigQuery 的历史 Google Analytics 数据时，就可以跳转到 CJA 并[创建您的第一个连接](/help/connections/create-connection.md)了。该连接将使用公共“客户 ID”将 GA 数据与所有其他客户数据拼合在一起。

## 后续步骤

* 根据包含 Google Analytics 数据的连接创建[数据视图](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=zh-Hans#cja-dataviews)。

* 在Workspace](/help/use-cases/ga-to-cja-reporting.md)中，进行一些令人惊叹的[分析。