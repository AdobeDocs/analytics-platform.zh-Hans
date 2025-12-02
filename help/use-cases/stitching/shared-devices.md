---
title: 共享设备
description: 说明如何使用拼合和其他技术处理共享设备。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a7d14968-33a2-46a8-8e32-fb6716650d0a
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 6%

---

# 共享设备

本文提供有关共享设备的上下文，介绍如何使用[拼接](/help/stitching/overview.md)处理并缓解来自共享设备的数据，以及了解使用查询服务在数据中共享设备的暴露情况。

## 什么是共享设备？

共享设备是指由多个用户使用的设备。 常见的情况是平板电脑、网亭中使用的设备或由呼叫中心代理共享的计算机设备。

当两个用户使用同一设备且都进行了经过身份验证的购买时，示例事件数据可能如下所示：

| 事件 | 时间戳 | 页面名称 | 设备ID | 电子邮件 |
|--:|---|---|---|---|
| 1 | 2023-05-12 12:01 | 主页 | `1234` | |
| 2 | 2023-05-12 12:02 | 产品页面 | `1234` | |
| 3 | 2023-05-12 12:03 | 订购成功 | `1234` | `ryan@a.com` |
| 4 | 2023-05-12 12:07 | 产品页面 | `1234` | |
| 5 | 2023-05-12 12:08 | 订购成功 | `1234` | `cassidy@a.com` |

如该表所示，一旦在事件3和5上执行身份验证，设备id和人员id之间就会开始形成链接。 要了解任何营销工作对人员级别的影响，这些未经身份验证的事件需要归因到正确的人员。

<!--
The order success (purchase) events assign the data accurately to the correct email. How this assignment impacts your analysis depends on how you perform analysis:

- Device centric approach: analysis performed using the Device ID. With this approach, both authenticated and unauthenticated data are included in analysis. However, this approach does not allow for a more person based analysis. 
- Person centric approach: analysis performed using the email address or other person identifier. With this approach, only authenticated events are included in the analysis. This approach doesn't provide a complete picture of the customer journey, including acquisition

-->

## 改进以人为中心的分析

拼接过程通过将选定的人员标识符（在示例数据中为电子邮件）添加到不存在该标识符的事件来解决此归因问题。 拼接利用设备ID和人员ID之间的映射，以确保在分析中使用经过身份验证和未经身份验证的流量，同时保持以人员为中心。 有关详细信息，请参阅[拼接](/help/stitching/overview.md)。

拼接可以使用最后验证归因或设备拆分归因来归因共享设备数据。 所有将未经身份验证的事件拼合到已知用户的尝试都是不确定的。


### 最后验证归因

上次身份验证将共享设备中的所有未知活动归因于上次进行身份验证的用户。 Experience Platform Identity服务基于上次身份验证归因构建图形，因此用于基于图形的拼合。 有关详细信息，请参阅[标识图链接规则](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/features/identity-graph-linking-rules/identity-optimization-algorithm#identity-optimization-algorithm-details)。

在拼接中使用最后验证归因时，拼接ID会解析，如下表所示。

| 时间戳 | 页面名称 | 设备ID | 电子邮件 | 拼接 ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | 主页 | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:02 | 产品页面 | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:03 | 订购成功 | `1234` | `ryan@a.com` | `cassidy@a.com` |
| 2023-05-12 12:07 | 产品页面 | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:08 | 订购成功 | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | 主页 | `1234` | | `cassidy@a.com` |


### 设备拆分

设备拆分将来自共享设备的匿名活动归因于最近已知的用户，查看的是过去的记录。 设备拆分当前用于基于字段的拼合。

在拼合中使用设备拆分归因时，拼合ID会解析，如下表所示。

| 时间戳 | 页面名称 | 设备ID | 电子邮件 | 拼接 ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | 主页 | `1234` | | `ryan@a.com` |
| 2023-05-12 12:02 | 产品页面 | `1234` | | `ryan@a.com` |
| 2023-05-12 12:03 | 订购成功 | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | 产品页面 | `1234` | | `ryan@a.com` |
| 2023-05-12 12:08 | 订购成功 | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | 主页 | `1234` | | `cassidy@a.com` |


<!--

### ECID reset 

As the name implies, ECID reset implements functionality that resets the ECID on a predetermined trigger, in most cases a login or logout event. With this implementation, a single device gets a new ECID every time the predetermined trigger fires. Essentially, this reset forces the device to become a *new device* over and again from a data perspective. The ECID reset also helps to prevent shared devices from even showing up in the data. No additional algorithms are required, but you have the responsibility to implement the ECID reset signal as part of your Adobe data collection implementation.


When using ECID reset, Stitched IDs resolve as shown in the table below. 

| Timestamp | Page name | Device ID | Email | Stitched ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Home page | `1234` | | `ryan@a.com`|
| 2023-05-12 12:02 | Product page  | `1234` | |`ryan@a.com` |
| 2023-05-12 12:03 | Order success | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Product page  | 5678  | | `cassidy@a.com` |
| 2023-05-12 12:08 | Order success | 5678 |  `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Home page | 5678 | | `cassidy@a.com` |

-->

## 共享设备曝光

请考虑多个因素，以正确了解共享设备在您的组织中的普及程度。 此外，了解来自共享设备的事件的总体贡献可以帮助您了解对用于分析的总体事件数据的影响。

要了解共享设备泄露，可以考虑执行以下查询。

1. **识别共享设备**

   要了解共享的设备数量，请执行查询，以使用两个或更多关联的人员ID来计算设备ID。 这有助于识别由多个用户使用的设备。

   ```sql
   SELECT COUNT(*)
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
         COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
     FROM /* INSERT DATASET HERE */
     GROUP BY 1
   )
   WHERE transient_count > 1; 
   ```


2. **将事件归因到共享设备**

   对于已识别的共享设备，确定总计中有多少事件可归因于这些设备。 此归因将insight归因到共享设备对您的数据产生的影响以及对分析的影响。

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

3. **识别共享设备上的匿名事件**

   在归因于共享设备的事件中，确定有多少事件缺少人员ID，这表示匿名事件。 您选择的用于提高数据质量的算法（例如last-auth、device-split或ECID-reset）会影响这些匿名事件。

   ```sql
   SELECT COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) shared_persistent_ids_anon_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null))) * 100 AS shared_persistent_ids_anon_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

4. **根据事件分类错误计算曝光率**

   最后，评估每个客户因事件分类错误而可能面临的风险。 计算每个共享设备的匿名事件占事件总数的百分比。 这有助于了解对客户数据准确性的潜在影响。

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```
