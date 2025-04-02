---
title: Content Analytics数据收集
description: 概述如何在Content Analytics中收集数据
solution: Customer Journey Analytics
feature: Content Analytics
hide: true
hidefromtoc: true
role: Admin
source-git-commit: d835411beba3d40f67d2f93ee76aa5eda6f45041
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 1%

---


# Content Analytics数据收集

本文详细介绍了Content Analytics如何收集数据


## 定义

本文上下文中使用了以下定义：

* **体验**：体验被定义为整个网页上的文本内容。 对于数据收集，Content Analytics会记录该体验ID。 Content Analytics不会在页面上记录文本。
* **资源**：图像。 Content Analytics记录资源URL。
* **相关URL**：基本URL加上驱动页面内容的任何参数。
* **体验ID**：相关URL和体验版本的唯一组合。
   * 在[配置](configuration.md)中，您指定与任何给定完整URL相关的参数。
   * 您可以定义使用的[版本标识符](manual.md#versioning)。 对于数据收集，不考虑版本。 仅收集相关的URL。

## 功能

Content Analytics库在以下情况下收集数据：

* Content Analytics包含在页面上加载的标记库中。
* 页面URL在[Content Analytics扩展](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}中配置，该扩展是包含的标记库的一部分。


### Content Analytics事件

Content Analytics事件包括：

* 标准字段
   * 时间戳
   * 身份标识
* 体验视图（如果有，如果已配置）
* 体验点击次数（如果有，如果已配置）
* 资产视图（如果有，如果已配置）
* 资产点击次数（如果有，如果已配置）

#### 记录的查看次数或点击次数

在以下情况下会记录资源视图：

* 没有根据ACA扩展配置排除该资源。
* 资产占75%。
* 尚未为此页面记录该资产。

出现以下情况时，将记录资产点击次数：

* 已查看资源。
* 没有根据ACA扩展配置排除该资源。
* 直接单击资产（一个链接）以转到另一个页面。

在以下情况下，将记录体验视图：

* 体验会在Content Analytics配置中启用。

在以下情况下，将记录一次体验点击：

* 在启用了体验的页面上的链接上发生任何点击。


#### 事件已发送

当出现以下两种情况时，将发送Content Analytics事件：

* 发送内容，发生条件：

   * 将记录资源视图或点击。
   * 将记录一次体验视图或点击。

* 会触发一个用于发送事件的触发器，此触发器发生于：

   * Web SDK或AppMeasurement发送事件。
   * 可视性更改为隐藏，例如：
      * 页面卸载
      * “切换”选项卡
      * 最小化浏览器
      * 关闭浏览器
      * 锁定屏幕
   * URL发生更改，从而导致相关的URL被修改。
   * 资产查看次数超过了32次的批量限制。


## 架构

Content Analytics数据是根据特定的Experience Platform架构在Content Analytics的数据集中收集的。 引用架构是公开可用的，用于Content Analytics的默认实施。

* [数字资产架构](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [数字体验架构](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [体验事件内容架构](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
