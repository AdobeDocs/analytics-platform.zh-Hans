---
title: 将 Google Analytics 历史数据提取到 Adobe Experience Platform
description: 介绍如何使用Adobe Customer Journey Analytics将Google Analytics数据摄取到Adobe Experience Platform。
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 91%

---


# 将 Google Analytics 历史数据提取到 Adobe Experience Platform

本页面重点介绍如何将您的 Google Analytics 历史数据作为数据集提取到 Adobe Experience Platform 中，允许您在 Customer Journey Analytics 的数据视图中引用该数据集。您可以将此页面上的步骤与[配置实时 Google Analytics 实施](streaming.md)结合使用，这会生成一个循环数据集。将此历史数据集与您当前实施的数据集结合起来，以无缝查看 Customer Journey Analytics 中的数据以及当前和回填数据。

## 先决条件

要完成这些任务，您需要以下访问和权限：

* 访问 Adobe Experience Platform
* 访问 Google Analytics（GA 标准版或 GA 360）
* [管理员访问](/help/admin/cja-access-control.md) Customer Journey Analytics

## 设置 BigQuery 导出

Universal Analytics 属性中的数据结构与 Google Analytics 4 属性中的数据结构不同。根据您要从中导出数据的属性类型设置 BigQuery Export：

* [为 Universal Analytics 属性设置 BigQuery 导出](https://support.google.com/analytics/answer/3416092)
* [为 Google Analytics 4 属性设置 BigQuery 导出](https://support.google.com/analytics/answer/9823238)

### Universal Analytics 属性的其他要求

>[!NOTE]
>
>本部分仅适用于 Universal Analytics 属性。如果您要从 GA4 属性导出，您可以继续[将数据导出到 Google Cloud Platform](#export-gcp)。

Universal Analytics 属性将每条记录作为用户会话而不是单个事件存储在其数据中。需要使用 SQL 查询将 Universal Analytics 数据转换为与 Adobe Experience Platform 兼容的格式。将 `UNNEST` 函数应用于 GA 架构中的 `hits` 字段，并将其保存为 BigQuery 表。

>[!VIDEO](https://video.tv.adobe.com/v/332634)

```sql
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
         `example_bq_table_*`,
         UNNEST(hits) AS hit 
   )
```

## 将数据导出到 Google Cloud Platform {#export-gcp}

在 Google Cloud Platform 中，导航至 **导出 > 导出到 GCS**。数据存储在 Google Cloud Storage 中后，即可将其拉入 Adobe Experience Platform。

## 将 Google Cloud Storage 中的数据导入 Experience Platform

1. 在 Adobe Experience Platform 中，选择左侧的&#x200B;**[!UICONTROL 源]**。
1. 在目录下，找到 **[!UICONTROL Google Cloud Storage]** 选项。单击&#x200B;**[!UICONTROL “添加数据”]**。

>[!VIDEO](https://video.tv.adobe.com/v/332676)

>[!TIP]
>
>如果您计划同时导入历史和实时流式 Google Analytics 数据，请确保对两个数据集使用相同的架构。您可以使用合并Customer Journey Analytics中的数据集 [组合的数据集](/help/connections/combined-dataset.md).

您可以将 GA 事件数据映射到以前创建的现有数据集，或者使用所选择的任何 XDM 架构创建数据集。选择好架构后，Experience Platform 则应用机器学习，自动将 Google Analytics 数据中的每个字段预映射到您的 [XDM 架构](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html#ui)。

![架构图](../assets/schema-map.png)

完成将字段映射到 XDM 架构中后，您可以定期计划此导入并在摄取过程中应用错误验证。此验证可确保您导入的数据没有任何问题。

## 所需 XDM 字段

Platform 中的某些 XDM 字段需要正确的格式才能正确处理数据。

* **`timestamp`**：在 Experience Platform 架构 UI 中创建一个特殊的计算字段。单击&#x200B;**[!UICONTROL 添加计算字段]**，并在 `date` 函数中包含 `timestamp` 字符串：

  `date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

  将计算的字段保存到架构中的时间戳数据结构中：

  ![时间戳](../assets/timestamp.png)

* **`_id`**：此字段必须具有值 — Customer Journey Analytics不管该值是什么。 您可以在字段中添加“1”：

  ![ID](../assets/_id.png)

## 后续步骤

* 如果您想要将当前数据流式传输到 Adobe Experience Platform，请参阅[为 Google Analytics 数据设置流式传输](streaming.md)。
* 如果您想开始报告回填数据，请参阅[创建连接](/help/connections/create-connection.md)。
