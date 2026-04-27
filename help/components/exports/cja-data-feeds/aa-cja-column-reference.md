---
title: 将Adobe Analytics数据馈送列映射到Customer Journey Analytics
description: 确定如何获取给定的Adobe Analytics数据馈送列，并确定其在您的Customer Journey Analytics实施中的大致等效项。
feature: Components
hide: true
exl-id: 81d6e79e-8324-4726-9a48-10177b0a91b1
source-git-commit: d79c6d883f436d97925e007f453879e20b4fcc04
workflow-type: tm+mt
source-wordcount: '3912'
ht-degree: 48%

---

# 将Adobe Analytics数据馈送列映射到Customer Journey Analytics

无法在Adobe Analytics和Customer Journey Analytics数据馈送列之间进行1:1映射。 这两种产品存在根本性差异，并且每个组织的实施也可能存在显着差异。

此参考可帮助数据工程师评估Adobe Analytics数据馈送列，并确定其工作流中与Customer Journey Analytics最接近的等效项。

>[!NOTE]
>
>此引用仅包括Adobe根据[Analytics数据馈送列引用](https://experienceleague.adobe.com/zh-hans/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference)视为当前的列。 如果您的Analytics数据馈送列未在此表格中列出，且您积极使用，请查阅贵组织的解决方案设计文档，以确定其在Customer Journey Analytics中的最佳等效项。

+++**`accept_language`**

列出所有已接受的语言，如图像请求中的 Accept-Language HTTP 标头所示。

+++

+++**`adload`**

媒体广告加载

{{cja-df-post}}

+++

+++**`aemassetid`**

一个多值变量与一组 Adobe Experience Manager Assets 的资产 ID (GUID) 相对应。 可增加展示事件的计数。

{{cja-df-post}}

+++

+++**`aemassetsource`**

标识资产事件的来源。 在 Adobe Experience Manager 中使用。

{{cja-df-post}}
+++

+++**`aemclickedassetid`**

Adobe Experience Manager 资产的资产 ID。 增加点击事件的数量。

{{cja-df-post}}

+++

+++**`amo_cid`**

AMO ID维度，用于Adobe Advertising集成。

{{cja-df-post}}

+++

+++**`amo_ef_id`**

AMO EF ID维度，用于Adobe Advertising集成。

{{cja-df-post}}

+++

+++**`browser`**

表示浏览器的数值 ID。

{{cja-df-lookup}}

+++

+++**`browser_height`**

“浏览器高度”维度。

{{cja-df-post}}

+++

+++**`browser_width`**

浏览器宽度

{{cja-df-post}}

+++

+++**`campaign`**

“跟踪代码”维度。

{{cja-df-post}}

+++

+++**`carrier`**

指定移动运营商。

{{cja-df-lookup}}

{{cja-df-ua}}

+++

+++**`channel`**

网站区域维度。

{{cja-df-post}}

+++

+++**`ch_hdr`**

通过 HTTP 请求头收集的客户端提示。

在Adobe Analytics中，客户端提示作为连接字符串包含在此列中。 与`user_agent`列相比，这种方法被认为是一种更现代的方法。

{{cja-df-ua}}

+++

+++**`ch_js`**

通过用户代理客户端提示 JavaScript API 收集的客户端提示。

在Adobe Analytics中，客户端提示作为连接字符串包含在此列中。 与`user_agent`列相比，这种方法被认为是一种更现代的方法。

配置Web SDK时，您可以使用[`highEntropyUserAgentHints`](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/js/commands/configure/context)上下文字符串收集此数据。 填充多个XDM字段而不是一个长连接字符串：

* **操作系统版本**： `xdm.environment.browserDetails.userAgentClientHints.platformVersion`
* **架构**： `xdm.environment.browserDetails.userAgentClientHints.architecture`
* **设备型号**： `xdm.environment.browserDetails.userAgentClientHints.model`
* **位**： `xdm.environment.browserDetails.userAgentClientHints.bitness`
* **浏览器供应商**： `xdm.environment.browserDetails.userAgentClientHints.vendor`
* **浏览器名称**： `xdm.environment.browserDetails.userAgentClientHints.brand`
* **浏览器版本**： `xdm.environment.browserDetails.userAgentClientHints.version`

有关详细信息，请参阅[用户代理客户端提示](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/use-cases/client-hints)。

{{cja-df-ua}}

+++

+++**`clickmaplink`**

Activity Map链接维度。

{{cja-df-post}}

{{cja-df-na}}

此列不适用，因为Customer Journey Analytics尚不支持Activity Map。

+++

+++**`clickmaplinkbyregion`**

Activity Map链接（按地区）维度。

{{cja-df-post}}

{{cja-df-na}}

此列不适用，因为Customer Journey Analytics尚不支持Activity Map。

+++

+++**`clickmappage`**

Activity Map页面维度。

{{cja-df-post}}

{{cja-df-na}}

此列不适用，因为Customer Journey Analytics尚不支持Activity Map。

+++

+++**`clickmapregion`**

Activity Map区域维度。

{{cja-df-post}}

{{cja-df-na}}

此列不适用，因为Customer Journey Analytics尚不支持Activity Map。

+++

+++**`code_ver`**

用于编译和发送图像请求的 API 或客户端 SDK 版本。

+++

+++**`color`**

颜色深度 ID，它基于 `c_color` 列的值。

{{cja-df-lookup}}

+++

+++**`connection_type`**

表示连接类型维度的数值ID。

{{cja-df-lookup}}

+++

+++**`cookies`**

Cookie支持维度。<br>Y：已启用<br>N：已禁用<br>U：未知

{{cja-df-post}}

+++

+++**`country`**

表示访客所在国家/地区的数值 ID。 引用 `country.tsv` 查找表。

{{cja-df-lookup}}

+++

+++**`currency`**

交易过程中使用的货币代码。 用 `currencyCode` 设置。

`xdm.commerce.order.currencyCode`

{{cja-df-post}}

+++

+++**`ct_connect_type`**

与 `connection_type` 列相关。 最常见的值为 LAN/Wifi、Mobile Carrier 和 Modem。

+++

+++**`curr_factor`**

确定货币的小数位。 用于货币换算。 例如，美元使用两个小数位，因此该列的值为 `2`。

+++

+++**`curr_rate`**

交易时的汇率。 Adobe 与 XE 合作，以确定当天的汇率。

+++

+++**`customer_perspective`**

决定点击是否为移动后台点击。

{{cja-df-post}}

{{cja-df-na}}

Customer Journey Analytics没有事件类型的本机概念，在该概念中，它会根据点击的上下文自动包含或排除点击。 您可以使用`xdm.eventType`帮助确定大多数报告中应包含和排除哪些事件。

+++

+++**`cust_hit_time_gmt`**

仅限启用了时间戳的报表包。 随点击发送的时间戳（基于 UNIX® 时间）。

Customer Journey Analytics没有时间戳与非时间戳报表包的概念。 请改用`xdm.timestamp`，并根据需要调整组件设置。

{{cja-df-post}}

+++

+++**`cust_visid`**

在用 `visitorID` 设置情况下的自定义访客 ID。

Customer Journey Analytics支持使用[`identityMap`](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/field-groups/profile/identitymap)的任意数量的标识。 如果您的组织使用自定义身份，则它很可能位于身份映射中。

{{cja-df-post}}

+++

+++**`c_color`**

调色板的位深度。 在计算颜色深度维度时用到。 AppMeasurement 使用 JavaScript 函数 `screen.colorDepth()`。

+++

+++**`daily_visitor`**

用于确定点击是否为新的每日访客的标记。

+++

+++**`dataprivacyconsentoptin`**

同意管理选择加入维度。 每次点击可以出现多个值，各个值之间用竖线 (`\|`) 隔开。 有效值包括 `DMP` 和 `SELL`。

如果您的组织具有数据管理平台，则该平台可能会填充此维度的所需XDM字段。

+++

+++**`dataprivacyconsentoptout`**

同意管理选择退出维度。 每次点击可以出现多个值，各个值之间用竖线 (`\|`) 隔开。 有效值包括 `SSF`, `DMP` 和 `SELL`。

如果您的组织具有数据管理平台，则该平台可能会填充此维度的所需XDM字段。

+++

+++**`date_time`**

以可读格式表示的点击时间（基于报表包所在时区）。

您可以使用`xdm.timestamp`并应用&#x200B;**[!UICONTROL 日期]**&#x200B;或&#x200B;**[!UICONTROL 日期时间]** [格式](/help/data-views/component-settings/format.md)组件设置。

+++

+++**`domain`**

域维度。 基于访客的网络接入点。

在[配置数据流](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/configure)时启用&#x200B;**[!UICONTROL 网络查找]**。 如果XDM字段包含在您的架构中，则该字段为`xdm.environment.domain`。

+++

+++**`duplicated_from`**

仅在包含点击复制 VISTA 规则的报表包中使用。 指示从中复制点击的报表包。

{{cja-df-na}}

此列不适用，因为Customer Journey Analytics不具有VISTA规则的概念。

+++

+++**`duplicate_events`**

列出每一个算作重复的事件。

{{cja-df-na}}

Customer Journey Analytics没有充当所有量度重复标志的单个字段。 相反，每个指标都包含其自己的[指标去重组件设置](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication)。 因此，Customer Journey Analytics中没有与此Adobe Analytics数据馈送列等效的字段。

+++

+++**`duplicate_purchase`**

确定此次点击对应的购买事件是重复事件因而被忽略的标记。

虽然无法直接翻译为此Analytics数据馈送列，但其删除重复购买操作的功能仍然存在。 如果使用[[!UICONTROL Commerce详细信息]](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/field-groups/event/commerce-details)字段组，则可以设置[指标去重组件设置](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication)，其中&#x200B;**[!UICONTROL 去重ID]**&#x200B;为`xdm.commerce.purchases.id`。

如果需要在需要标记重复购买的位置进行直接翻译，则可以使用规则集中的&#x200B;**Deduplicate**&#x200B;函数的[Derived字段](/help/data-views/derived-fields/derived-fields.md)。

+++

+++**`ef_id`**

EF ID，用于Adobe Advertising集成。

{{cja-df-post}}

+++

+++**`evar1 - evar250`**

自定义变量 1 至 250。 在eVar维度中使用。 每个公司使用 eVar 的方式有所不同。 要了解有关贵组织如何填充各个eVar的更多信息，最好的地方是特定于贵组织的解决方案设计文档。

{{cja-df-post}}

+++

+++**`event_list`**

以逗号分隔的数值 ID 列表，各 ID 表示点击时所触发的事件。 包括商务事件和自定义事件1-1,000。 使用 `event.tsv` 查找。

此列可能会映射到数十个不同的量度，具体取决于您的实施。 Adobe建议执行以下流程，将Customer Journey Analytics中的每个相应指标映射到其在此Analytics数据馈送列中表示的数字值：

1. 使用`event.tsv`查找将每个数值映射到其度量名称。
1. 使用您的解决方案设计文档将每个Analytics事件名称映射到Customer Journey Analytics中相应的量度名称。
1. 在数据视图UI中选择映射的组件并记下其组件ID。 如果组件ID太笨重，您可以填充数据馈送别名ID字段并使用它。
1. 对您的组织使用的每个指标重复执行上述操作。

{{cja-df-post}}

如果您的架构使用[[!UICONTROL Commerce详细信息]](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/field-groups/event/commerce-details)字段组，则某些量度可能会直接映射到以下XDM字段：

* **结帐**： `xdm.commerce.checkouts.value`
* **购物车添加次数**： `xdm.commerce.productListAdds.value`
* **购物车打开**： `xdm.commerce.productListOpens.value`
* **购物车移除**： `xdm.commerce.productListRemovals.value`
* **购物车查看次数**： `xdm.commerce.productListViews.value`
* **产品查看次数**： `xdm.commerce.productViews.value`
* **订单**： `xdm.commerce.purchases.value`

某些量度可能使用事件序列化，这是Adobe Analytics允许完全控制重复数据删除的方式。 您可以使用[指标去重](/help/data-views/component-settings/metric-deduplication.md)组件设置来实现去重奇偶校验。

* 如果您的指标在Adobe Analytics中按访问删除了重复项，则您可以在该指标的组件设置中将重复项删除范围设置为会话。
* 如果您的量度在Adobe Analytics中按事件ID进行了重复数据删除，则该量度的XDM对象可能同时包含`value`和`id`字段。 如果您的架构使用[[!UICONTROL Commerce详细信息]](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/field-groups/event/commerce-details)字段组，则这些量度可能驻留在这些XDM字段中，您可以在量度的组件设置中设置&#x200B;**[!UICONTROL 重复数据删除ID]**&#x200B;字段：

   * **结帐**： `xdm.commerce.checkouts.id`
   * **购物车添加次数**： `xdm.commerce.productListAdds.id`
   * **购物车打开**： `xdm.commerce.productListOpens.id`
   * **购物车移除**： `xdm.commerce.productListRemovals.id`
   * **购物车查看次数**： `xdm.commerce.productListViews.id`
   * **产品查看次数**： `xdm.commerce.productViews.id`

如果要删除重复的订单量度，请参阅`duplicate_purchase`。

+++

+++**`exclude_hit`**

确定报告中是否包含此点击的标记。 对于被排除的点击，`visit_num` 列不递增。

Customer Journey Analytics不接受开箱即用的“排除的点击”。 但是，如果您具有标记要排除的特定点击的XDM字段，则可以重新创建此功能：

1. 确保将标记已排除点击的XDM字段作为一个组件（维度或量度，具体取决于您如何设置此标记）包含在内。 在报告[&#128279;](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/component-settings/overview)中选择隐藏组件可能对此字段有益。
1. 在[数据视图设置](/help/data-views/session-settings.md)中，选择&#x200B;**[!UICONTROL 添加区段]**&#x200B;下拉菜单，然后选择&#x200B;**[!UICONTROL 创建区段]**。
1. 创建一个区段，以排除存在排除点击组件的所有事件或包含要排除的值。
1. 在区段和数据视图上选择&#x200B;**[!UICONTROL 保存]**。

现在，Customer Journey Analytics报表中不存在排除的点击，但在数据馈送导出中仍然可用。

+++

+++**`first_hit_pagename`**

原始登入页面维度。 访客访问的原始登入页面的名称。

+++

+++**`first_hit_page_url`**

访客访问的第一个 URL。

+++

+++**`first_hit_referrer`**

访客访问的第一个反向链接 URL。

+++

+++**`first_hit_ref_domain`**

原始反向链接域维度。 基于 `first_hit_referrer`。 访客首次访问的反向链接域。

+++

+++**`first_hit_ref_type`**

表示访客使用的第一个反向链接的反向链接类型的数值 ID。

{{cja-df-lookup}}

+++

+++**`first_hit_time_gmt`**

访客第一次点击的时间戳（基于 UNIX® 时间）。

+++

+++**`geo_city`**

根据 IP 地址判断的点击来源城市的名称。 在城市维度中用到。

+++

+++**`geo_country`**

根据 IP 地址判断的点击来源国家/地区的缩写。 在国家/地区维度中用到。

+++

+++**`geo_dma`**

根据 IP 地址判断的点击来源人口统计区的数值 ID。 在美国DMA维度中用到。

+++

+++**`geo_region`**

根据 IP 地址判断的点击来源省/市/自治区或区域的名称。 在地区维度中使用。

+++

+++**`geo_zip`**

根据 IP 地址判断的点击来源的邮政编码。 帮助填充邮政编码维度。 另请参阅 `zip`。

+++

+++**`hitid_high`**

与 `hitid_low` 配合使用可标识某次点击。

+++

+++**`hitid_low`**

与 `hitid_high` 配合使用可标识某次点击。

+++

+++**`hit_source`**

点击的来源。 点击源1和2将计费。 <br>1：不带时间戳的标准图像请求<br>2：带有时间戳的标准图像请求<br>3：带有时间戳的实时数据源上载<br>4：未使用<br>5：通用数据源上载<br>6：不再使用；完全处理数据源上载<br>7：TransactionID数据源上载<br>8：不再使用；Adobe Advertising数据源的以前版本<br>9：不再使用；Adobe Social概要量度<br>10：使用了Audience Manager服务器端转发

+++

+++**`hit_time_gmt`**

Adobe 数据收集服务器接收到点击的时间戳（基于 UNIX® 时间）。

+++

+++**`hourly_visitor`**

用于确定点击是否为新小时访客的标记。

+++

+++**`ip`**

IPv4 地址，基于图像请求的 HTTP 标头。 与 `ipv6` 互斥；如果此列包含未进行模糊处理的 IP 地址，则 `ipv6` 为空白。

+++

+++**`ipv6`**

压缩的 IPv6 地址（如果有）。 与 `ip` 互斥；如果此列包含未进行模糊处理的 IP 地址，则 `ip` 为空白。

+++

+++**`javascript`**

基于 `j_jscript` 的 JavaScript 版本的查找 ID。

{{cja-df-lookup}}

+++

+++**`java_enabled`**

启用Java的维度。 <br>Y：启用<br>N：禁用<br>U：未知

{{cja-df-post}}

+++

+++**`j_jscript`**

浏览器支持的 JavaScript 版本。

+++

+++**`language`**

表示访客语言的数值 ID。

{{cja-df-lookup}}

+++

+++**`last_hit_time_gmt`**

上次点击的时间戳（以 UNIX® 时间表示）。 用于计算上次访问后天数维度。

+++

+++**`last_purchase_num`**

客户忠诚度维度。 访客以前购买的次数。 <br>0：之前没有购买（不是客户）<br>1：1 次先前购买（新客户）<br>2：2 次先前购买（退货客户）<br>3：3 次或更多先前购买（忠诚客户）

+++

+++**`last_purchase_time_gmt`**

在上次购买后天数维度中用到。 上次购买的时间戳（以 UNIX® 时间表示）。 对于首次购买和以前未购买过的访客，此值为 `0`。

+++

+++**`latlon1`**

位置（精确到 10 千米）

+++

+++**`latlon23`**

位置（精确到 100 米）

+++

+++**`latlon45`**

位置（精确到 1 米）

+++

+++**`mcvisid`**

Experience Cloud 访客 ID。 一个 128 位的数字（由两个 64 位的数字拼接而成），共占据了 19 位数。

+++

+++**`mc_audiences`**

列出访客所属的 Audience Manager 区段 ID。 `post_mc_audiences` 列将分隔符更改为 `--**--`。

{{cja-df-post}}

+++

+++**`mobileaction`**

移动设备操作。 在移动实施中调用 `trackAction` 时会自动收集。 应用程序支持自动的操作路径。

{{cja-df-post}}

+++

+++**`mobileappid`**

移动应用程序 ID。 采用以下格式存储应用程序名称和版本：`[AppName] [BundleVersion]`

`xdm.application.name` + `xdm.application.version`

{{cja-df-post}}

+++

+++**`mobileappperformanceappid`**

用于 Apteligent Data Connector。 Apteligent 中使用的应用程序 ID。

+++

+++**`mobileappperformancecrashid`**

用于 Apteligent Data Connector。 Apteligent 中使用的崩溃 ID。

+++

+++**`mobileappstoreobjectid`**

用在 [!DNL Appfigures] 数据连接器中。 应用程序商店对象 ID。

+++

+++**`mobilebeaconmajor`**

Mobile Services 信标主要

+++

+++**`mobilebeaconminor`**

Mobile Services 信标次要

+++

+++**`mobilebeaconproximity`**

Mobile Services 信标邻近性

+++

+++**`mobilebeaconuuid`**

Mobile Services 信标 UUID

+++

+++**`mobilecampaigncontent`**

显示链接的内容名称或 ID。 由移动设备应用程序客户获取填充。

{{cja-df-post}}

+++

+++**`mobilecampaignmedium`**

营销媒介，例如横幅或电子邮件。 由移动设备应用程序客户获取填充。

{{cja-df-post}}

+++

+++**`mobilecampaignname`**

营销活动的名称，也存储在营销活动变量中。 由移动设备应用程序客户获取填充。

{{cja-df-post}}

+++

+++**`mobilecampaignsource`**

原始反向链接，例如商务通讯或社交媒体网络。 由移动设备应用程序客户获取填充。

{{cja-df-post}}

+++

+++**`mobilecampaignterm`**

要在此客户获取中跟踪的付费关键字或其他搜索词。 由移动设备应用程序客户获取填充。

{{cja-df-post}}

+++

+++**`mobiledayofweek`**

应用程序启动的时间（星期几）。

{{cja-df-post}}

+++

+++**`mobiledayssincefirstuse`**

距应用程序首次运行的间隔天数。

{{cja-df-post}}

+++

+++**`mobiledayssincelastuse`**

距应用程序上次运行的间隔天数。

{{cja-df-post}}

+++

+++**`mobiledeeplinkid`**

从上下文数据变量 `a.deeplink.id` 收集。 在客户获取报表中用作移动客户获取链接的标识符。

+++

+++**`mobiledevice`**

移动设备名称。 在 iOS 上，该变量存储为用逗号分隔的 2 位数的字符串。 第一个数字表示设备是第几代的，而另一个数字则表示设备所属的系列。

{{cja-df-post}}

+++

+++**`mobilehourofday`**

确定应用程序启动的具体时间。 采用 24 小时数字格式。

{{cja-df-post}}

+++

+++**`mobileinstalldate`**

移动设备安装日期。 提供用户首次打开移动应用程序的日期。

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilelaunchnumber`**

应用程序每启动一次，该变量值便会递增。

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilemessagebuttonname`**

从上下文数据变量 `a.message.button.id` 收集。 用于应用程序内消息传递，以标识关闭消息的按钮。

{{cja-df-post}}

+++

+++**`mobilemessageid`**

应用程序内消息 ID

{{cja-df-post}}

+++

+++**`mobilemessageonline`**

应用程序内消息在线

{{cja-df-post}}

+++

+++**`mobilemessagepushoptin`**

从上下文数据变量 `a.push.optin` 收集。 当用户选择启用推送消息时，设置为“true”；否则，将该值设为“false”。

{{cja-df-post}}

+++

+++**`mobilemessagepushpayloadid`**

从上下文数据变量 `a.push.payloadid` 收集。 在推送消息中用作有效负载标识符。

{{cja-df-post}}

+++

+++**`mobileosversion`**

Mobile Services 操作系统版本

{{cja-df-post}}

+++

+++**`mobileplaceaccuracy`**

从上下文数据变量 `a.loc.acc` 收集。 指示收集时 GPS 的精度（以米为单位）。

+++

+++**`mobileplacecategory`**

从上下文数据变量 `a.loc.category` 收集。 描述特定位置的类别。

+++

+++**`mobileplaceid`**

从上下文数据变量 `a.loc.id` 收集。 给定目标点的标识符。

+++

+++**`mobilepushoptin`**

Mobile Services Push 选择启用

{{cja-df-post}}

+++

+++**`mobilepushpayloadid`**

Mobile Services Push 负载 ID

{{cja-df-post}}

+++

+++**`mobilerelaunchcampaigncontent`**

Mobile Services 启动内容

+++

+++**`mobilerelaunchcampaignmedium`**

Mobile Services 启动媒介

+++

+++**`mobilerelaunchcampaignsource`**

Mobile Services 启动来源

+++

+++**`mobilerelaunchcampaignterm`**

Mobile Services 启动搜索词

+++

+++**`mobilerelaunchcampaigntrackingcode`**

从上下文数据变量 `a.launch.campaign.trackingcode` 收集。 在客户获取中用作启动促销活动的跟踪代码。

+++

+++**`mobileresolution`**

移动设备的分辨率。 `[Width] x [Height]` 以像素为单位。

{{cja-df-post}}

+++

+++**`mobile_id`**
如果用户使用了移动设备，则为移动设备的数字 ID。

{{cja-df-lookup}}

+++

+++**`monthly_visitor`**

确定访客是否在当月首次出现的标记。

+++

+++**`mvvar1`** - **`mvvar3`**

列出变量值。 包含分隔的自定义值列表（取决于实施）。 `post_mvvar1` - `post_mvvar3` 列将原始分隔符替换为 `--**--`。

{{cja-df-post}}

+++

+++**`mvvar1_instances`** - **`mvvar3_instances`**

在当前点击上设置的列表变量值。 将原始分隔符替换为 `--**--`。 `post` 列通常不包含数据。

{{cja-df-post}}

+++

+++**`new_visit`**

确定当前点击是否为新访问的标记。 在不活跃的访问状态持续 30 分钟后，由 Adobe 设置。

+++

+++**`os`**

表示访客的操作系统的数值 ID。 基于 `user_agent` 列。

{{cja-df-lookup}}

当[配置数据流](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/configure)时，您可以启用&#x200B;**[!UICONTROL 设备查找]**。 如果启用，请选中&#x200B;**[!UICONTROL 操作系统]**&#x200B;复选框。 如果您在架构中包含以下XDM字段，则这样做会自动填充这些字段：

* **OS供应商**： `xdm.environment.operatingSystemVendor`
* **OS名称**： `xdm.environment.operatingSystem`
* **OS版本**： `xdm.environment.operatingSystemVersion`

{{cja-df-ua}}

+++

+++**`pagename`**

页面维度。 如果 `pagename` 变量为空，则 Analytics 改用 `page_url`。

{{cja-df-post}}

+++

+++**`pagename_no_url`**

与 `pagename` 类似，但它不会回退到 `page_url`。 仅 `post` 列可用。

{{cja-df-post}}

+++

+++**`page_event`**

在图像请求中发送的点击类型（标准点击、下载链接、自定义链接、退出链接）。

{{cja-df-post}}

{{cja-df-lookup}}

+++

+++**`page_event_var1`**

仅用于链接跟踪图像请求。 所点击的下载链接、退出链接或自定义链接的 URL。

{{cja-df-post}}

+++

+++**`page_event_var2`**

仅用于链接跟踪图像请求。 链接的自定义名称（如果已指定）。 根据`page_event`中的值设置自定义链接、下载链接或退出链接。

{{cja-df-post}}

+++

+++**`page_type`**

未找到页面维度，通常用于404页面。

{{cja-df-post}}

+++

+++**`page_url`**

**`page_url`**：点击的URL。 使用文本的数据类型。<br>**`post_page_url`**：已剥离链接跟踪图像请求(`tl()`)。

{{cja-df-post}}

+++

+++**`paid_search`**

确定点击是否与付费搜索检测相匹配的标记。

+++

+++**`persistent_cookie`**

在永久性Cookie支持维度中使用。 表示访客是否支持每次点击后不丢弃的 Cookie。

{{cja-df-post}}

+++

+++**`pointofinterest`**

Mobile Services 目标点名称

{{cja-df-post}}

+++

+++**`pointofinterestdistance`**

Mobile Services 与目标点中心的距离

{{cja-df-post}}

+++

+++**`product_list`**

`products` 页面变量。 有助于填充多个维度和量度，包括类别、产品、件数和收入。

{{cja-df-post}}

+++

+++**`prop1`** - **`prop75`**

自定义流量变量 1 至 75。 在Prop维度中使用。

{{cja-df-post}}

+++

+++**`purchaseid`**

某次购买的唯一标识符，使用 `purchaseID` 变量设置它。 供 `duplicate_purchase` 列使用。

`xdm.commerce.order.purchaseID`

{{cja-df-post}}

+++

+++**`quarterly_visitor`**

确定此点击是否为新季度访客的标记。

+++

+++**`referrer`**

反向链接维度。 请注意，在 `referrer` 使用数据类型 varchar(255) 时，`post_referrer` 使用数据类型 varchar(244)。

{{cja-df-post}}

+++

+++**`ref_domain`**

反向链接域维度。 基于 `referrer` 列。

+++

+++**`ref_type`**


表示此点击的反向链接类型的数值 ID。 在反向链接类型维度中使用。<br>1：网站内部<br>2：其他网站<br>3：搜索引擎<br>4：硬盘<br>5：未发送<br>6：已输入/添加书签（无反向链接）<br>7：电子邮件<br>8：无JavaScript<br>9：社交网络<br>10：对话式AI工具

+++

+++**`resolution`**

表示显示器分辨率的数值 ID。 在显示器分辨率维度中使用。

{{cja-df-lookup}}

+++

+++**`search_engine`**

表示将访客引向您的网站的搜索引擎的数值 ID。 在搜索引擎维度中使用。

{{cja-df-post}}

{{cja-df-lookup}}

+++

+++**`search_page_num`**

供所有搜索页面排名维度使用。 指示用户在点进您的网站之前您的网站出现在搜索结果的第几页上。

+++

+++**`secondary_hit`**

确定此点击是否为辅助点击的标记。 此标记通常源自多包标记和复制点击的 VISTA 规则。

+++

+++**`sourceid`**

源 ID

+++

+++**`stats_server`**

没有用处。 处理点击的 Adobe 内部服务器。

+++

+++**`s_kwcid`**

Adobe Advertising 集成中使用的关键词 ID。

{{cja-df-post}}

+++

+++**`s_resolution`**

原始屏幕分辨率值。 使用 JavaScript 函数 `screen.width x screen.height` 收集而得。

+++

+++**`tnt`**

在 Adobe Target 集成中使用。 表示所有当前符合条件的测试。 格式为：`TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`。

{{cja-df-post}}

+++

+++**`tnt_action`**

在 Adobe Target 集成中使用。 表示点击符合条件的所有测试。

{{cja-df-post}}

+++

+++**`tnt_instances`**

在 Adobe Target 集成中使用。 Target 实例变量。

+++

+++**`transactionid`**

稍后可通过数据源上传各种数据点的唯一标识符。 使用 `transactionID` 变量收集而得。

`xdm.commerce.order.payments[0].transactionID`

{{cja-df-post}}

+++

+++**`truncated_hit`**

表示图像请求被截断（收到部分点击）的标记。 <br>Y：点击被截断；接收到部分点击<br>N：点击未被截断；收到完整点击

+++

+++**`t_time_info`**

访客的当地时间。 格式为：`M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)`

{{cja-df-post}}

+++

+++**`userid`**

没有用处。 报告包 ID 的数值 ID。 请改用 `username`。

+++

+++**`username`**

点击的报表包 ID。

+++

+++**`user_agent`**

在图像请求的 HTTP 标头中发送的用户代理字符串。

+++

+++**`user_hash`**

没有用处。 报告包 ID 的哈希值。 请改用 `username`。

+++

+++**`user_server`**

在服务器维度中使用。

{{cja-df-post}}

+++

+++**`va_closer_detail`**

最近联系详细信息维度。

+++

+++**`va_closer_id`**

标识上次接触渠道维度的数值ID。

{{cja-df-lookup}}

+++

+++**`va_finder_detail`**

首次接触渠道详细信息维度。

+++

+++**`va_finder_id`**

标识首次接触渠道维度的数值ID。

{{cja-df-lookup}}

+++

+++**`va_instance_event`**

标识营销渠道实例的标志。

+++

+++**`va_new_engagement`**

标识营销渠道新参与的标志。

+++

+++**`video`**

内容流媒体服务维度。

{{cja-df-post}}

+++

+++**`videoad`**

广告流媒体服务维度。

{{cja-df-post}}

+++

+++**`videoadinpod`**

面板中的广告位置流媒体服务维度。

{{cja-df-post}}

+++

+++**`videoadlength`**

广告时长（变量）流媒体服务维度。

{{cja-df-post}}

+++

+++**`videoadname`**

广告名称（变量）流媒体服务维度。

{{cja-df-post}}

+++

+++**`videoadplayername`**

广告播放器名称流媒体服务维度。

{{cja-df-post}}

+++

+++**`videoadpod`**

广告Pod流媒体服务维度。

{{cja-df-post}}

+++

+++**`videoadvertiser`**

广告商流媒体服务维度。

{{cja-df-post}}

+++

+++**`videoaudioalbum`**

相册流媒体服务维度。

+++

+++**`videoaudioartist`**

艺人流媒体服务维度。

+++

+++**`videoaudioauthor`**

创作流媒体服务维度。

+++

+++**`videoaudiolabel`**

为流媒体服务添加标签维度。

+++

+++**`videoaudiopublisher`**

Publisher流媒体服务维度。

+++

+++**`videoaudiostation`**

Station流媒体服务维度。

+++

+++**`videocampaign`**

促销活动ID流媒体服务维度。

{{cja-df-post}}

+++

+++**`videochannel`**

内容渠道流媒体服务维度。

{{cja-df-post}}

+++

+++**`videochapter`**

章节流媒体服务维度。

{{cja-df-post}}

+++

+++**`videocontenttype`**

内容类型流媒体服务维度。

{{cja-df-post}}

+++

+++**`videodaypart`**

日部分流媒体服务维度。

{{cja-df-post}}

+++

+++**`videoepisode`**

剧集流媒体服务维度。

{{cja-df-post}}

+++

+++**`videofeedtype`**

媒体馈送类型流媒体服务维度。

{{cja-df-post}}

+++

+++**`videogenre`**

流媒体服务类型维度。 此维度允许在同一次点击中有多个值，值之间用逗号分隔。

{{cja-df-post}}

+++

+++**`videolength`**

内容时长（变量）流媒体服务维度。

{{cja-df-post}}

+++

+++**`videomvpd`**

MVPD流媒体服务维度。

{{cja-df-post}}

+++

+++**`videoname`**

内容名称（变量）流媒体服务维度。

{{cja-df-post}}

+++

+++**`videonetwork`**

网络流媒体服务维度。

{{cja-df-post}}

+++

+++**`videopath`**

媒体路径流媒体服务维度。

{{cja-df-post}}

+++

+++**`videoplayername`**

内容播放器名称流媒体服务维度。

{{cja-df-post}}

+++

+++**`videoqoebitrateaverageevar`**

平均比特率流媒体服务维度。

{{cja-df-post}}

+++

+++**`videoqoebitratechangecountevar`**

比特率会更改流媒体服务维度。

{{cja-df-post}}

+++

+++**`videoqoebuffercountevar`**

缓冲事件流媒体服务维度。

{{cja-df-post}}

+++

+++**`videoqoebuffertimeevar`**

流媒体服务总缓冲时间维度。

{{cja-df-post}}

+++

+++**`videoqoedroppedframecountevar`**

丢帧流媒体服务维度。

{{cja-df-post}}

+++

+++**`videoqoeerrorcountevar`**

错误流媒体服务维度。

+++
{{cja-df-post}}


+++**`videoqoeextneralerrors`**

外部错误ID流媒体服务维度。 此维度允许在同一次点击中有多个值。

+++

+++**`videoqoeplayersdkerrors`**

播放器SDK错误ID流媒体服务维度。 此维度允许在同一次点击中有多个值。

{{cja-df-post}}

+++

+++**`videoqoetimetostartevar`**

开始流媒体服务的时间维度。

{{cja-df-post}}

+++

+++**`videoseason`**

季流媒体服务维度。

{{cja-df-post}}

+++

+++**`videosegment`**

流媒体服务维度内容区段。

{{cja-df-post}}

+++

+++**`videosessionid`**

媒体会话ID流媒体服务维度。

{{cja-df-post}}

+++

+++**`videoshow`**

显示流媒体服务维度。

{{cja-df-post}}

+++

+++**`videoshowtype`**

显示类型流媒体服务维度。

{{cja-df-post}}

+++

+++**`videostreamtype`**

流类型流媒体服务维度。

+++

+++**`visid_high`**

与 `visid_low` 配合使用可唯一地标识某位访客。

{{cja-df-post}}

+++

+++**`visid_low`**

与 `visid_high` 配合使用可唯一地标识某位访客。

{{cja-df-post}}

+++

+++**`visid_new`**

确定此点击是否包含新生成访客 ID 的标记。

+++

+++**`visid_timestamp`**

如果新生成了访客 ID，就会在生成时提供 UNIX® 时间戳。

+++

+++**`visid_type`**

不能用于外部用途；Adobe 内部用于处理优化。 数字ID，表示用于识别访客的方法。<br>`0`：自定义访客ID或未知/不适用<br>`1`： IP和用户代理回退<br>`2`： HTTP移动订阅者标头<br>`3`：旧版Cookie值(`s_vi`) <br>`4`：回退Cookie值(`s_fid`) <br>`5`：身份服务

{{cja-df-post}}

+++

+++**`visit_keywords`**

搜索关键词维度。 此列使用 varchar(244) 的非标准字符限制容纳 Adobe 使用的后端逻辑。 后处理列是`**post_keywords**`，而不是`**post_visit_keywords**`。

{{cja-df-post}}

+++

+++**`visit_num`**

访问数量维度。 起始值为 1，每当每个访客开始新的访问时，此项就会递增。

+++

+++**`visit_page_num`**

点击深度维度。 访客每产生一次点击，此值就增加 1。 重置每一个访问。

+++

+++**`visit_referrer`**

此访问的第一个反向链接。

+++

+++**`visit_ref_domain`**

基于 `visit_referrer` 列。 此访问的第一个反向链接域。

+++

+++**`visit_ref_type`**

表示此访问的第一个反向链接的反向链接类型的数值 ID。

{{cja-df-lookup}}

+++

+++**`visit_search_engine`**

表示此访问的第一个搜索引擎的数值 ID。

{{cja-df-lookup}}

+++

+++**`visit_start_pagename`**

访问中首次点击的页面。

+++

+++**`visit_start_page_url`**

访问中首次点击的URL。

+++

+++**`visit_start_time_gmt`**

访问中首次点击的时间戳（基于 UNIX® 时间）。

+++

+++**`weekly_visitor`**

用于确定此点击是新每周访客的标记。

+++

+++**`yearly_visitor`**

用于确定此点击是新每年访客的标记。

+++

+++**`zip`**

帮助填充邮政编码维度。 另请参阅 `geo_zip`。

{{cja-df-post}}

+++
