---
title: 共享设备
description: 说明如何使用拼合和其他技术处理共享设备。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hide-from-toc: true
role: Admin
source-git-commit: f17d2ebdf9a45ebb3a4e923a34c4b9b3d629f038
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 6%

---

# 共享设备

本文提供了有关共享设备的上下文，介绍如何使用拼合处理和缓解共享设备中的数据，以及了解使用查询服务在数据中暴露的共享设备。

## 什么是共享设备？

共享设备是指由多个用户使用的设备。 常见的情况是平板电脑、网亭中使用的设备或由呼叫中心代理共享的计算机设备。

当两个用户使用同一设备且都进行购买时，示例事件数据可能如下所示：

| 时间戳 | 页面名称 | 设备ID | 电子邮件 |
|---|---|---|---|
| 2023-05-12 12:01 | 主页 | 1234 | |
| 2023-05-12 12:02 | 产品页 | 1234 | |
| 2023-05-12 12:03 | 订购成功 | 1234 | <ryan@a.com> |
| 2023-05-12 12:07 | 产品页 | 1234 | |
| 2023-05-12 12:08 | 订购成功 | 1234 | <cassidy@a.com> |

订单成功（购买）事件将数据准确地分配给正确的电子邮件。 此分配如何影响您的分析取决于您执行分析的方式：

- 以设备为中心的方法：使用设备ID执行的分析。 使用此方法时，分析中会同时包含经过身份验证的数据和未经过身份验证的数据。 但是，这种方法无法进行更多基于人员的分析。
- 以人员为中心的方法：使用电子邮件地址或其他人员标识符执行的分析。 使用此方法时，分析中仅包含经过身份验证的事件。 此方法无法提供客户历程（包括客户获取）的完整信息

## 改进以人为中心的分析

为了改进对共享设备进行以人为中心的分析，您有两个选择：您可以使用拼接，或者实施ECID重置功能。 下面各节将更详细地讨论这两种方法。

### 拼合

拼接过程解决了以人为中心方法的缺点。 拼接可将选定的人员标识符（在示例数据中，即电子邮件）添加到不存在该标识符的事件。 拼接利用设备ID和人员ID之间的映射，以确保在分析中使用经过身份验证和未经身份验证的流量，同时保持以人员为中心。 有关详细信息，请参阅[拼接](/help/stitching/overview.md)。

拼接可以使用最后验证归因或设备拆分归因来归因共享设备数据。 但是，通过ECID重置来更改实施也可能会寻址共享设备。


#### 最后验证归因

上次身份验证将共享设备中的所有未知活动归因于上次进行身份验证的用户。 最后验证用于Audience Manager，是实时客户数据配置文件用例的首选方法。 Experience PlatformIdentity服务基于最后验证归因构建图形，因此用于基于图形的拼合。 有关详细信息，请参阅[身份图链接规则概述](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/overview)。

在拼接中使用最后验证归因时，拼接ID会解析，如下表所示。

| 时间戳 | 页面名称 | 设备ID | 电子邮件 | 拼接 ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | 主页 | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:02 | 产品页 | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:03 | 订购成功 | 1234 | <ryan@a.com> | <cassidy@a.com> |
| 2023-05-12 12:07 | 产品页 | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:08 | 订购成功 | 1234 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | 主页 | 1234 | | <cassidy@a.com> |


#### 设备拆分

设备拆分将来自共享设备的匿名活动归因于最接近匿名活动的用户。 设备拆分当前用于基于字段的拼合。 设备拆分是分析用例的首选方法，因为设备拆分将未经身份验证和经过身份验证的活动的点数都授予最接近的已知人员。 设备拆分当前用于基于字段的拼合。

在拼接中使用设备拆分归因时，拼接ID会解析，如下表所示。

| 时间戳 | 页面名称 | 设备ID | 电子邮件 | 拼接 ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | 主页 | 1234 | | <ryan@a.com> |
| 2023-05-12 12:02 | 产品页 | 1234 | | <ryan@a.com> |
| 2023-05-12 12:03 | 订购成功 | 1234 | <ryan@a.com> | <ryan@a.com> |
| 2023-05-12 12:07 | 产品页 | 1234 | | <ryan@a.com> |
| 2023-05-12 12:08 | 订购成功 | 1234 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | 主页 | 1234 | | <cassidy@a.com> |


### ECID重置

顾名思义，ECID reset实施了在预定触发器（大多数情况下是登录或注销事件）上重置ECID的功能。 使用此实施，每当触发预定义的触发器时，单个设备都会获取新的ECID。 实际上，此重置强制设备从数据角度反复成为&#x200B;*新设备*。 ECID重置还有助于防止共享设备甚至显示在数据中。 您无需使用其他算法，但是在Adobe数据收集实施过程中，您有责任实施ECID重置信号。


使用ECID重置时，拼合ID会得到解析，如下表所示。

| 时间戳 | 页面名称 | 设备ID | 电子邮件 | 拼接 ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | 主页 | 1234 | | <ryan@a.com> |
| 2023-05-12 12:02 | 产品页 | 1234 | | <ryan@a.com> |
| 2023-05-12 12:03 | 订购成功 | 1234 | <ryan@a.com> | <ryan@a.com> |
| 2023-05-12 12:07 | 产品页 | 5678 | | <cassidy@a.com> |
| 2023-05-12 12:08 | 订购成功 | 5678 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | 主页 | 5678 | | <cassidy@a.com> |

## 共享设备曝光

请考虑多个因素，以正确了解共享设备在您的组织中的普及程度。 此外，了解来自共享设备的事件的总体贡献可以帮助您了解对用于分析的总体事件数据的影响。

要了解共享设备泄露，可以考虑执行以下查询。

1. 了解共享的设备数量。 您可以使用查询来计数具有两个或多个与设备ID关联的人员ID的设备ID。 示例查询可能如下所示：

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


2. 对于首次查询产生的共享设备，您需要了解可以将总事件中的多少个事件归因到这些共享设备。 此归因使您能够更好地了解共享设备对数据的影响以及执行分析时的影响。 示例查询可能如下所示：

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

3. 对于归因于共享设备的事件（第二次查询的结果），您需要了解其中有多少事件没有人员ID。 否则，将说明有多少共享设备事件是匿名事件。 最终，您选择的用于提高数据质量的算法(last-auth、device-split、ECID-reset)确实会影响这些匿名共享设备事件。 示例查询可能如下所示：

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

4. 最后，您要了解由于事件分类错误导致每个客户面临的风险。 要获得此公开信息，您需要为每个共享设备计算与事件总数相关的匿名事件百分比。 示例查询可能如下所示：

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


