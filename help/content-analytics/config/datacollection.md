---
title: Content Analytics数据收集
description: 了解如何在Content Analytics中收集数据。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
TQID: https://experienceleague.adobe.com/B2j6BrXAHMu-3LKI61LbK01i-UdpMlELsqYSfAWYDCo
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad5685a0-8296-4a0c-814c-658c10b4af12
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: d9715c3da9893e1c47b702acb4daef5e666bedd7
workflow-type: tm+mt
source-wordcount: 1093
ht-degree: 52%

---


# Content Analytics 数据收集

本文详细介绍了 Content Analytics 如何收集数据

## 定义

本文中使用以下定义：

* **体验**：
   * 对于&#x200B;**Web**&#x200B;渠道，体验被定义为整个网页上的文本内容。 对于数据收集，Content Analytics会记录基于页面URL的Experience ID。 然后通过检索服务捕捉页面上的文本。
   * 对于&#x200B;**移动设备**&#x200B;渠道，使用适用于Adobe Experience Platform Mobile SDK的Content Analytics扩展在移动设备应用程序中定义和跟踪体验。
* **体验ID**：
   * 对于Web渠道，体验ID是相关URL（基本URL加上驱动页面内容的任何参数）和[体验版本](manual.md#versioning)的唯一组合。
      * 作为[配置](configuration.md)的一部分，您指定哪些参数与任何给定的完整 URL 相关。
      * 您定义一个可使用的[版本标识符](manual.md#versioning)，这样就可以正确收集有关体验的变化。
   * 对于&#x200B;**移动设备**&#x200B;渠道，体验ID是使用`registerExperience` API调用的返回值。
* **资产**：一个图像。 Content Analytics 会记录资产 URL。
* **资产 ID**：资产的 URL。
* **相关 URL**：基本 URL 加上驱动页面内容的任何参数。


## 功能

Content Analytics需要Experience Platform Edge Network Web SDK（适用于Web渠道）和Experience Platform Edge Network Mobile SDK（适用于移动渠道）来收集内容事件数据。 此事件数据与使用Experience Platform Edge Network（Web SDK、Mobile SDK或服务器API）或Analytics源连接器（如Adobe AppMeasurement）的现有行为数据相结合。

在以下情况下 Content Analytics 库会收集数据：

* Content Analytics包含在页面上加载或在移动设备应用程序中使用的标记库中。
* 页面URL和资产URL在[Content Analytics Web扩展](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}中配置，该扩展是包含的标记库的一部分。
* [Content Analytics移动扩展](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/)中未排除资源URL、资源位置或体验位置。


## Content Analytics 事件

本节详细介绍Web Content Analytics事件的细节。 有关Content Analytics移动事件的详细信息，请参阅[体验跟踪](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/experience-tracking/)。
Content Analytics 事件由以下各项组成：

* 标准字段
   * 时间戳
   * 身份标识
* 体验访问数（如有且已配置）
* 体验点击数（如有且已配置）
* 资产访问数（如有且已配置）
* 资产点击数（如有且已配置）

Content Analytics 事件收集为以下顺序：

1. [录制的视图或单击](#recorded-view-or-click)。
1. 用于发送Content Analytics事件](#trigger-to-send-a-content-analytics-event)的[触发器。

Content Analytics 实际上以这种方式收集数据来反映该序列，而不是将收集某次访问或点击与收集该访问或点击之后立即发生的事件两者分开。 这种收集 Content Analytics 数据的方式也减少了所收集的数据量。

### 记录的访问或点击

在以下情况下会记录资产访问：

* 该资产尚未通过 Content Analytics 扩展配置被排除。
* 该资产的 75% 被访问。
* 该资产尚未为此页面被记录。

在以下情况下会记录资产点击：

* 该资产已被访问。
* 该资产尚未通过 Content Analytics 扩展配置被排除。
* 直接单击资产（一个链接）会指向另一个页面。

在以下情况下会记录体验访问：

* 在 Content Analytics 配置中启用了体验。

在以下情况下会记录体验点击：

* 单击任何启用的链接都会触发体验。


### 用于发送 Content Analytics 事件的触发器

为了减少从页面发送的网络请求数，Content Analytics会收集信息，但不立即发送该信息。 内容交互信息会先被收集，只有当以下触发器之一发生时，才会发送包含这些信息的事件：

* Web SDK或Adobe AppMeasurement发送事件。
* 可见性变为隐藏，例如：
   * 页面卸载
   * 切换选项卡
   * 将浏览器最小化
   * 关闭浏览器
   * 锁定屏幕
* URL 发生变化，导致相关 URL 改变。
* 记录并准备发送的资产查看次数超过32次。

>[!NOTE]
>
>额外的 Content Analytics 事件很可能会影响任何基于会话或页面事件数量的跳出率定义。
>

## 身份标识

本节介绍Content Analytics如何处理身份。

### Web

Content Analytics通过以下方式处理Web渠道的身份：

* ECID 会自动填充到 Content Analytics 架构中的 `identityMap` 部分。
* 如果您需要在 `identityMap` 中包含其他身份标识值，则必须在 Web SDK 扩展的 `onBeforeEventSend` 回调中设置这些值。
* 由于该架构由系统所有，因此不支持基于字段的拼接。 因此，您无法向架构中添加其他字段来支持基于字段的拼接。


要确保在字段级别正确拼接Content Analytics标识数据和Web SDK数据标识数据，请在事件发送](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/configure/onbeforeeventsend){target="_blank"}回调之前修改Web SDK [。

1. 导航至包含 Adobe Experience Platform Web SDK 扩展和 Adobe Content Analytics 扩展的&#x200B;**[!UICONTROL 标记]**&#x200B;属性。
1. 选择![插件](/help/assets/icons/Plug.svg)**[!UICONTROL 扩展]**。
1. 选择 **[!UICONTROL Adobe Experience Platform Web SDK]** 扩展。
1. 选择&#x200B;**[!UICONTROL 配置]**。
1. 在 **[!UICONTROL SDK 实例]**&#x200B;部分，向下滚动至&#x200B;**[!UICONTROL 数据收集]** - **[!UICONTROL 在事件发送回调之前]**。

   ![在事件发送回调之前](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. 选择 **[!UICONTROL &lt;/> 提供在事件发送回调之前代码]**。
1. 添加以下代码：

   ```JavaScript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![在事件发送回调之前](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存代码。
1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存扩展。
1. [发布](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/publish/overview)对标记属性的更新。


### 移动

有关如何使用移动应用程序中的标识的更多信息，请参阅[Experience Cloud ID服务扩展的标识](https://developer.adobe.com/client-sdks/home/base/mobile-core/identity/)和[Edge Network移动扩展的标识](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/)。

一旦移动应用中的标识发生更改，当前的Content Analytics数据[批次](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/#batching-settings)即会重置，以便为新标识开始新的Content Analytics数据收集。

## 架构

Experience Platform根据特定的Content Analytics架构在数据集中收集Content Analytics数据。 参考架构公开可用：

* [数字资产架构](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [数字体验架构](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [体验事件内容架构](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
