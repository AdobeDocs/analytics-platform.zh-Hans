---
title: AAID、ECID、AACUSTOMID 和 Analytics Source Connector
description: 了解 Analytics Source Connector 如何处理 Adobe Analytics 标识字段。
exl-id: c983cf50-0b6c-4daf-86a8-bcd6c01628f7
feature: Basics
source-git-commit: ff71d21235bd37da73c0b6c628c395da6cda7659
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 91%

---

# AAID、ECID、AACUSTOMID 和 Analytics Source Connector

Adobe Analytics 数据包含多个标识字段。[Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans) 对三个重要的标识字段进行了特殊处理：AAID、ECID、AACUSTOMID。

## AAID

Adobe Analytics ID (AAID) 是 Adobe Analytics 中的主要设备标识符，并且必定存在于通过 Analytics Source Connector 传递的每个事件中。AAID 有时称作“旧版 Analytics ID”或 `s_vi` Cookie Id。不过，即使 `s_vi` Cookie不存在，也会创建 AAID。在 [Adobe Analytics 数据馈送](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hans#columns%2C-descriptions%2C-and-data-types)中，AAID 由 `post_visid_high/post_visid_low` 列表示。

在 Analytics Source Connector 中，AAID 将转换为 `HEX(post_visid_high) + "-" + HEX(post_visid_low)`。给定事件的 AAID 字段包含单个标识，它可能是 [Analytics ID 操作顺序](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=zh-Hans%5B%5D)中所述的几种不同类型之一。（在整个报告包中，AAID 可能包含各种事件的类型组合。每个事件的类型均指示在 `post_visid_type` 列。) 另请参阅：[数据列引用](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hans)。

## ECID

ECID (Experience Cloud ID) 有时也称作 MCID (Marketing Cloud ID)，它是一个单独的设备标识符字段，在使用 [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=zh-Hans) 实施 Analytics 时，会在 Adobe Analytics 中填充该字段。在 Adobe Analytics 数据馈送中，ECID 由 `mcvisid` 列表示。

如果事件中存在 ECID，则 AAID 可能基于 ECID，具体取决于是否配置了 Analytics [宽限期](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=zh-Hans)。另请参阅：[Analytics 和 Experience Cloud ID 请求](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=zh-Hans)。

## AACUSTOMID

AACUSTOMID 是一个单独的标识符字段，将根据 Analytics 实施中对 `s.VisitorID` 变量的使用，在 Adobe Analytics 中填充该字段。在 Adobe Analytics 数据馈送中，AACUSTOMID 由 `cust_visid` 列表示。如果存在 AACUSTOMID，则 AAID 将基于 AACUSTOMID。（AACUSTOMID 优于上述操作的顺序所定义的所有其他标识符。）

## Analytics Source Connector 如何处理这些标识

Analytics Source Connector 将这些标识以 XDM 形式传递到 Adobe Experience Platform，如下所示：

* `endUserIDs._experience.aaid.id`
* `endUserIDs._experience.mcid.id`
* `endUserIDs._experience.aacustomid.id`

这些字段未标记为标识。相反，相同的标识将以键值对的形式复制到 XDM 的 **_identityMap_**，如下所示：

* `{ "key": "AAID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "ECID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "AACUSTOMID", "value": [ { "id": "<identity>", "primary": false } ] }`

&lt;> 括号中的项目表示实际值出现的位置。

在 identityMap 中：

* 如果存在 ECID，则会将它标记为事件的主标识。请注意，在此情况下，AAID 可能基于 ECID，如上面的讨论中所述。否则，会将 AAID 标记为事件的主标识。
* 绝不会将 AACUSTOMID 标记为事件的主 ID。不过，如果存在 AACUSTOMID，则 AAID 将基于 AACUSTOMID，如上面的讨论中所述。

## Customer Journey Analytics和主ID

就Customer Journey Analytics而言，只有在您决定使用主ID作为人员ID时，主ID的定义才重要。 但这样做并不是强制性的。您可以选择其他某个标识列作为人员 ID。
