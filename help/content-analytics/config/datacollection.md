---
title: Content Analytics数据收集
description: 概述如何在Content Analytics中收集数据
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: feb253b20820112d5aa4b4eee31cff74d99fa186
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 1%

---

# Content Analytics数据收集

{{release-limited-testing}}

本文详细介绍Content Analytics如何收集数据


## 定义

本文上下文中使用了以下定义：

* **体验**：体验被定义为整个网页上的文本内容。 对于数据收集，Content Analytics会记录基于页面URL的Experience ID。 之后，通过检索服务捕获页面上的文本。
* **体验ID**：相关URL（基本URL加上驱动页面内容的任何参数）和[体验版本](manual.md#versioning)的唯一组合。
   * 在[配置](configuration.md)中，您指定与任何给定完整URL相关的参数。
   * 您定义要使用的[版本标识符](manual.md#versioning)，以便正确收集对体验的更改。
* **资源**：图像。 Content Analytics记录资源URL。
* **资源ID**：资源的URL。
* **相关URL**：基本URL加上驱动页面内容的任何参数。


## 功能

Content Analytics需要Experience Platform Edge Network Web SDK来收集内容事件数据。 该事件数据收集通过Experience Platform Edge Network (Web SDK，服务器API)或Analytics源连接器(例如，使用AppMeasurement)等机制，与行为事件数据的（现有）数据收集相结合。

Content Analytics库在以下情况下收集数据：

* Content Analytics包含在页面上加载的标记库中。
* 页面URL在[Content Analytics扩展](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}中配置，该扩展是包含的Tags库的一部分。



## Content Analytics事件

Content Analytics事件包括：

* 标准字段
   * 时间戳
   * 身份标识
* 体验视图（如果有，如果已配置）
* 体验点击次数（如果有，如果已配置）
* 资产视图（如果有，如果已配置）
* 资产点击次数（如果有，如果已配置）


Content Analytics事件将按顺序收集：

1. [录制视图，或单击](#recorded-view-or-click)。
1. [常规或特定（行为）事件](#regular-or-specific-behaviorial-event)。

Content Analytics确实会通过这种方式收集数据来反映该顺序，而不是收集视图或单击来代替收集紧跟在该视图或单击之后的事件。 这种收集内容分析数据的方式还减少了收集的数据量。

### 录制的视图或点击

在以下情况下会记录资源视图：

* 没有根据Content Analytics扩展配置排除该资源。
* 资产占75%。
* 尚未为此页面记录该资产。

出现以下情况时，将记录资产点击次数：

* 已查看资源。
* 没有根据Content Analytics扩展配置排除该资源。
* 直接单击资产（一个链接）以转到另一个页面。

在以下情况下，将记录体验视图：

* 体验会在Content Analytics配置中启用。

在以下情况下，将记录一次体验点击：

* 在启用了体验的页面上的链接上发生任何点击。


### 定期或特定（行为）事件

在Content Analytics上下文中触发常规或特定（行为）事件的触发程序包括：

* Web SDK或AppMeasurement发送事件。
* 可视性更改为隐藏，例如：
   * 页面卸载
   * “切换”选项卡
   * 最小化浏览器
   * 关闭浏览器
   * 锁定屏幕
* URL发生更改，从而导致相关的URL被修改。
* 记录并准备发送的资产查看次数超过了32次。


## 架构

Content Analytics数据是根据特定的Experience Platform架构在Content Analytics的数据集中收集的。 引用架构已公开可用：

* [数字资产架构](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [数字体验架构](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [体验事件内容架构](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
