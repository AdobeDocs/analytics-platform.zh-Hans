---
title: 将Google Analytics历史数据摄取到Adobe Experience Platform
description: 说明如何使用Customer Journey Analytics(CJA)将Google Analytics数据摄取到Adobe Experience Platform。
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: f65f13d696ad2045f58ccb5c9ef7fed45eb9d68c
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 9%

---


# 将Google Analytics历史数据摄取到Adobe Experience Platform

本页重点介绍如何将Google Analytics历史数据作为数据集摄取到Adobe Experience Platform中，从而允许您在Customer Journey Analytics内的“数据视图”中引用该数据集。 您可以将此页上的步骤与 [配置实时Google Analytics实施](streaming.md)，可生成循环数据集。 将此历史数据集与当前实施的数据集结合，以无缝查看与当前和回填数据Customer Journey Analytics的数据。

## 先决条件

要完成这些任务，您需要以下访问和权限：

* 访问 Adobe Experience Platform
* 对Google Analytics的访问（GA Standard或GA 360）
* [管理员访问权限](/help/getting-started/cja-access-control.md) Customer Journey Analytics

## 设置BigQuery导出

Universal Analytics属性中的数据结构与Analytics 4属性中的Google Analytics结构不同。 根据要从中导出数据的属性类型设置BigQuery导出：

* [为Universal Analytics属性设置BigQuery导出](https://support.google.com/analytics/answer/3416092)
* [为Google Analytics4属性设置BigQuery导出](https://support.google.com/analytics/answer/9823238)

### 通用分析属性的其他要求

>[!NOTE]
>
>此部分仅适用于Universal Analytics属性。 如果从GA4属性导出，则可以继续 [将数据导出到Google Cloud Platform](#export-gcp).

Universal Analytics属性将每个记录存储在其用户会话的数据中，而不是作为单个事件存储。 需要一个SQL查询，以将Universal Analytics数据转换为与Adobe Experience Platform兼容的格式。 应用 `UNNEST` 函数 `hits` 字段，并将其另存为BigQuery表。

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

## 将数据导出到Google Cloud Platform {#export-gcp}

在Google Cloud Platform中，导航到 **导出>导出到GCS**. 数据放入Google云存储后，即可将其提取到Adobe Experience Platform中。

## 将数据从Google云存储导入Experience Platform

1. 在Adobe Experience Platform中，选择 **[!UICONTROL 源]** 左边。
1. 在目录下，找到 **[!UICONTROL Google云存储]** 选项。 单击 **[!UICONTROL 添加数据]**.

>[!VIDEO](https://video.tv.adobe.com/v/332676)

>[!TIP]
>
>如果您计划导入历史流和实时流Google Analytics数据，请确保对这两个数据集使用相同的架构。 您可以使用 [组合数据集](/help/connections/combined-dataset.md).

您可以将GA事件数据映射到您之前创建的现有数据集中，或使用您选择的任何XDM架构创建数据集。 选择好架构后，Experience Platform 则应用机器学习，自动将 Google Analytics 数据中的每个字段预映射到您的 [XDM 架构](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html#ui)。

![架构映射](../assets/schema-map.png)

完成将字段映射到XDM架构后，您可以计划定期进行此导入，并在摄取过程中应用错误验证。 此验证可确保您导入的数据不会出现任何问题。

## 必需的XDM字段

Platform中的某些XDM字段需要正确的格式，才能正确处理数据。

* **`timestamp`**:在Experience Platform架构UI中创建特殊的计算字段。 单击 **[!UICONTROL 添加计算字段]** 并包裹住 `timestamp` 字符串 `date` 函数：

   `date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

   将计算字段保存到架构中的时间戳数据结构：

   ![时间戳](../assets/timestamp.png)

* **`_id`**:此字段中必须有值 — CJA不关心值的内容。 您可以向字段添加“1”：

   ![ID](../assets/_id.png)

## 后续步骤

* 如果您当前有要流入Adobe Experience Platform的数据，请参阅 [设置Google Analytics数据流](streaming.md).
* 如果要开始报告回填的数据，请参阅 [创建连接](/help/connections/create-connection.md).
