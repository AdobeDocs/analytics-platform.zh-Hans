---
source-git-commit: f97439676c61acf1b6ba8818ef1d06542402e675
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 9%

---
# AAID、ECID、ACUSTOMID和Analytics源连接器

Adobe Analytics数据包含多个标识字段。 对3个重要的身份域给予了特殊处理 [Analytics源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans):

* **AAID** 是Adobe Analytics中的主设备标识符，并保证存在于通过Analytics源连接器传递的每个事件中。 AAID有时称为“旧版Analytics ID”或“s\_vi Cookie id”，尽管即使不存在s\_vi Cookie，也会创建AAID。 AAID由 **_post\_visid\_high/post\_visid\_low_** 列 [Adobe Analytics数据馈送](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hans#columns%2C-descriptions%2C-and-data-types). 在Analytics源连接器中，AAID将转换为 **HEX(post_visid_high)+ &quot;-&quot; + HEX(host_visid_low)**. 给定事件的AAID字段包含单个标识，该标识可能是中所述的几种不同类型之一 [Analytics ID操作顺序](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=en%5B%5D). (在整个报表包中，AAID可能包含各种事件的各种类型。 每次点击的类型在 **_[帖子\_]visid\_type_** 列。) 另请参阅： [数据列引用](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hans).
* **ECID** (Experience CloudID)(有时也称为MCID(Marketing CloudID))是一个单独的设备标识符字段，在使用实施Adobe Analytics时，该字段会填充在Adobe Analytics中 [Experience Cloud标识服务](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=zh-Hans). ECID由 **_mcvisid_** 列。 如果事件中存在ECID，则AAID可能基于ECID，具体取决于Analytics [宽限期](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=zh-Hans) 已配置。 另请参阅： [Analytics和Experience CloudID请求](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=en).
* **AACUSTOMID** 是一个单独的标识符字段，将根据在Analytics实施中使用s.VisitorID变量在Adobe Analytics中填充。 AACUSTOMID由 **_cust_visid_** 列。 如果存在AACUSTOMID，则AAID将基于AACUSTOMID。 （AACUSTOMID会覆盖上述操作顺序所定义的所有其他标识符。）

Analytics Source Connector以XDM形式将这些标识传递到AEP，如下所示：

* endUserIDs.\_experience.aaid.id
* endUserIDs.\_experience.mcid.id
* endUserIDs.\_experience.aacustomid.id

这些字段未标记为标识。 相反，相同的身份会复制到XDM的 **_identityMap_** 按键值对如下所示：

* { &quot;key&quot;:&quot;AAID&quot;、&quot;value&quot;: [ { &quot;id&quot;:&quot;**_\&lt;identity>_**&quot;, &quot;primary&quot;: **_\&lt;true or=&quot;&quot; false=&quot;&quot;>_**} ] }
* { &quot;key&quot;:&quot;ECID&quot;, &quot;value&quot;: [ { &quot;id&quot;:&quot;**_\&lt;identity>_**&quot;, &quot;primary&quot;: **_\&lt;true or=&quot;&quot; false=&quot;&quot;>_** } ] }
* { &quot;key&quot;:&quot;AACUSTOMID&quot;, &quot;value&quot;: [ { &quot;id&quot;:&quot;**_\&lt;identity>_**&quot;, &quot;primary&quot;: **false** } ] }

在identityMap中：

* 如果存在ECID，则会将其标记为事件的主标识。 请注意，在这种情况下，根据上述讨论，AAID可能基于ECID。
否则，AAID将标记为事件的主标识。
* AACUSTOMID从不被标记为事件的主ID。 但是，如果存在AACUSTOMID，则AAID将基于AACUSTOMID，如上文所述。

就CJA而言，只有最终用户决定使用主ID作为人员ID时，主ID的定义才很重要。 但是，这样做并非强制性的。 用户可以选择其他一些身份列作为人员ID。

