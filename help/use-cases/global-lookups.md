---
title: 向数据集添加全局查找
description: 使用全局查找功能以报告中有用的维度来增强Customer Journey Analytics。
translation-type: tm+mt
source-git-commit: b3c9757421537d2d84a78a4d37e9bfc362438d40
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 0%

---


# 向数据集添加全局查找

全局查找增强了Customer Journey Analytics报告某些维度／属性的能力，这些维度／属性本身并不有用，但在与其他数据结合时非常有用。 示例包括移动设备的属性以及操作系统和浏览器尺寸的属性，如浏览器版本号。 “全局查找”与查找数据集(在传统Adobe Analytics被称为分类)非常相似。 但是，全局查找功能适用于Experience Cloud组织。 全局查找会自动应用于包含某些XDM事件字段的所有模式数据集（有关特定字段，请参见下文）。
对于模式要分类的每个Adobe位置，都存在全局查找数据集。 您可以将全局查找数据集与Analytics Source Connector一起使用，也可以将其与其他可接受的自定义数据集一起使用。

在传统的Adobe Analytics，这些维度是自行显示的，而在CJA中，创建数据视图时，您必须主动包含这些维度。 当用户在连接工作流中选择标记为具有全局查找密钥的数据集时，数据视图UI将知道包含所有全局查找维（如果可用）。 数据视图工作流知道包括这些全局查找维，如果数据视图可用。 查找文件会在所有区域和所有帐户中自动保持最新并可用。 它们存储在与客户关联的特定于地区的组织中。

## 对Adobe数据连接器数据集使用全局查找

全局查找数据集在报告时自动应用。 如果您使用[Analytics数据连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en#connectors)，并且您引入了Adobe提供全局查找的维，我们会自动应用此全局查找。 如果事件数据集包含[XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en)字段，我们可以对其应用全局查找。

## 对自定义数据集使用全局查找

事件集中需要有一个与全局查找数据集兼容的键。 只要通过添加一些我们的标准[Adobe Experience Platform模式混合](https://experienceleague.adobe.com/docs/experience-platform/xdm/mixins/event/environment-details.html?lang=en#mixins)来填充正确的XDM字段，您就可以使自定义数据集与全局查找结合使用。

## 可用的全局查找字段

* `browser`
   * `browser`, `group_id`, `id`
* `browser_group`
   * `browser_group`,  `id`
* `os`
   * `os`,  `group_id`  `id`
* `os_group`
   * `os_group`,  `id`
* `mobile_audio_support - multi`
* `mobile_color_depth`
* `mobile_cookie_support`
* `mobile_device_name`
* `mobile_device_number_transmit`
* `mobile_device_type`
* `mobile_drm - multi`
* `mobile_image_support - multi`
* `mobile_information_services`
* `mobile_java_vm - multi`
* `mobile_mail_decoration`
* `mobile_manufacturer`
* `mobile_max_bookmark_url_length`
* `mobile_max_browser_url_length`
* `mobile_max_mail_url_length`
* `mobile_net_protocols - multi`
* `mobile_os`
* `mobile_push_to_talk`
* `mobile_screen_height`
* `mobile_screen_size`
* `mobile_screen_width`
* `mobile_video_support - multi`

## 全局查找维度报告

要报告全局查找维，您必须在Customer Journey Analytics中创建数据视图时添加这些维：

![](assets/global-lookup.png)

然后，您可以在Workspace中查看查找数据：

![](assets/gl-reporting.png)

