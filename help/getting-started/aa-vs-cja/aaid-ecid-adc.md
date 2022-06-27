---
title: AAID、ECID、ACUSTOMID和Analytics源连接器
description: 了解Analytics源连接器如何处理Adobe Analytics标识字段。
source-git-commit: 348f4e8596146f7ff4234535fa76a54f7be33171
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 9%

---


# AAID、ECID、ACUSTOMID和Analytics源连接器

Adobe Analytics数据包含多个标识字段。 对3个重要的身份域给予了特殊处理 [Analytics源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans):AAID、ECID、AACUSTOMID。

## AAID

Adobe Analytics ID(AAID)是Adobe Analytics中的主要设备标识符，可保证存在于通过Analytics源连接器的每个事件中。 AAID有时称为“旧版Analytics ID”或 `s\_vi cookie id`. 但是，即使 `s\_vi` cookie不存在。 AAID由 `_post\_visid\_high/post\_visid\_low_` 列 [Adobe Analytics数据馈送](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hans#columns%2C-descriptions%2C-and-data-types).

在Analytics源连接器中，AAID将转换为 `HEX(post_visid_high) + "-" + HEX(host_visid_low)`. 给定事件的AAID字段包含单个标识，该标识可能是中所述的几种不同类型之一 [Analytics ID操作顺序](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=en%5B%5D). (在整个报表包中，AAID可能包含各种事件的各种类型。 每次点击的类型在 `_[post\_]visid\_type_` 列。) 另请参阅： [数据列引用](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hans).

## ECID

ECID(Experience CloudID)有时也称为MCID(Marketing CloudID)，是一个单独的设备标识符字段，在使用实施Analytics时，该字段会填充在Adobe Analytics中 [Experience Cloud标识服务](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=zh-Hans). ECID由 `_mcvisid_` 列。

如果事件中存在ECID，则AAID可能基于ECID，具体取决于Analytics [宽限期](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=zh-Hans) 已配置。 另请参阅： [Analytics和Experience CloudID请求](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=en).

## AACUSTOMID

AACUSTOMID是一个单独的标识符字段，它根据使用 `s.VisitorID` 变量。 AACUSTOMID由 `_cust_visid_` 列。 如果存在AACUSTOMID，则AAID将基于AACUSTOMID。 （AACUSTOMID会覆盖上述操作顺序所定义的所有其他标识符。）

## Analytics源连接器如何处理这些标识

Analytics源连接器将以XDM形式将这些身份传递到Adobe Experience Platform，如下所示：

* `endUserIDs.\_experience.aaid.id`
* `endUserIDs.\_experience.mcid.id`
* `endUserIDs.\_experience.aacustomid.id`

这些字段未标记为标识。 相反，相同的身份会复制到XDM的 **_identityMap_** 按键值对如下所示：

* `{ “key”: “AAID”, “value”: [ { “id”: “_\<identity\>_”, “primary”: **_\<true or false\>_**} ] }`
* `{ “key”: “ECID”, “value”: [ { “id”: “_\<identity\>_”, “primary”: **_\<true or false\>_** } ] }`
* `{ “key”: “AACUSTOMID”, “value”: [ { “id”: “_\<identity\>_”, “primary”: **false** } ] }`

在identityMap中：

* 如果存在ECID，则会将其标记为事件的主标识。 请注意，在这种情况下，根据上述讨论，AAID可能基于ECID。
否则，AAID将标记为事件的主标识。
* AACUSTOMID从不被标记为事件的主ID。 但是，如果存在AACUSTOMID，则AAID将基于AACUSTOMID，如上文所述。

就CJA而言，只有最终用户决定使用主ID作为人员ID时，主ID的定义才很重要。 但是，这样做并非强制性的。 用户可以选择其他一些身份列作为人员ID。

