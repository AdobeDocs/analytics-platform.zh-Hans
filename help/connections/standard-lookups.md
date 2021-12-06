---
title: 向数据集添加标准查找
description: 使用标准查找为报表中的有用维度提供更多Customer Journey Analytics。
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
solution: Customer Journey Analytics
source-git-commit: 067502a0d69bd0b085ecb5e6cbd3ae062f33daef
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 28%

---

# 向数据集添加标准查找

>[!IMPORTANT]
>标准查找仅适用于CJA中的Analytics Data Connector数据源。 仅当使用 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) 或Experience Platform数据收集API。

标准查找(也称为Adobe提供的查找)增强了Customer Journey Analytics报告某些维度/属性的能力，这些维度/属性本身并不有用，但在与其他数据连接时很有用。 示例包括移动设备的属性、操作系统属性和浏览器维度，如浏览器版本号。“标准查找”类似于查找数据集。 标准查找适用于各个Experience Cloud组织。 它们自动应用于包含某些 XDM 架构字段（有关具体字段见下文）的所有事件数据集。对于Adobe正在分类的每个架构位置，都存在标准查找数据集。

在传统的 Adobe Analytics 中，这些维度按自已的方式显示，但在 CJA 中，您必须在创建数据视图时主动包含这些维度。在连接工作流中，您选择一个标记为具有标准查找键的数据集。 数据视图UI会自动知道包含所有可用于报表的标准查找维度。 查找文件会在所有区域和所有帐户中自动保持为最新版本和可用。这些文件将存储在与客户关联的特定于区域的组织中。

## 将标准查找与AdobeData Connector数据集结合使用

标准查找数据集会在报表时自动应用。 如果您使用Analytics Data Connector，并引入了Adobe为其提供标准查找的维度，则我们会自动应用此标准查找。 如果事件数据集包含XDM字段，我们可以对其应用标准查找。

### 可用的标准查找字段

* `browser`
   * `browser`、`group_id`、`id`
* `browser_group`
   * `browser_group`、`id`
* `os`
   * `os`、`group_id`、`id`
* `os_group`
   * `os_group`、`id`
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

## 报告标准查找维度

要报告标准查找维度，您必须在在Customer Journey Analytics中创建数据视图时添加它们：

![](assets/global-lookup.png)

然后，您便可以在工作区中查看查找数据：

![](assets/gl-reporting.png)
