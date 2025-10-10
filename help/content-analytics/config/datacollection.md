---
title: Content Analytics 数据收集
description: Content Analytics 中数据收集方式概述
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: e8cba64e706a456861fd8392ce9260b7a1c4636b
workflow-type: ht
source-wordcount: '622'
ht-degree: 100%

---

# Content Analytics 数据收集

本文详细介绍了 Content Analytics 如何收集数据

## 定义

本文中使用以下定义：

* **体验**：体验定义为整个网页上的文本内容。Content Analytics 会为数据收集记录基于页面 URL 的体验 ID。然后通过检索服务捕捉页面上的文本。
* **体验 ID**：相关 URL 的唯一组合（基本 URL 加上驱动页面内容的任何参数）和[体验版本](manual.md#versioning)。
   * 作为[配置](configuration.md)的一部分，您指定哪些参数与任何给定的完整 URL 相关。
   * 您定义一个可使用的[版本标识符](manual.md#versioning)，这样就可以正确收集有关体验的变化。
* **资产**：一个图像。Content Analytics 会记录资产 URL。
* **资产 ID**：资产的 URL。
* **相关 URL**：基本 URL 加上驱动页面内容的任何参数。


## 功能

Content Analytics 需要 Experience Platform Edge Network Web SDK 来收集内容事件数据。该事件数据收集通过 Experience Platform Edge Network（Web SDK、服务器 API）或 Analytics 源连接器（例如，使用 AppMeasurement）等机制与行为事件数据的（现有）数据收集相结合。

在以下情况下 Content Analytics 库会收集数据：

* Content Analytics 包含在页面上加载的标记库中。
* 页面 URL 在 [Content Analytics 扩展](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}中配置，是所包含的标记库的一部分。


## Content Analytics 事件

Content Analytics 事件由以下各项组成：

* 标准字段
   * 时间戳
   * 身份标识
* 体验访问数（如有且已配置）
* 体验点击数（如有且已配置）
* 资产访问数（如有且已配置）
* 资产点击数（如有且已配置）

Content Analytics 事件收集为以下顺序：

1. [记录的访问或点击](#recorded-view-or-click)。
1. [用于发送 Content Analytics 事件的触发器](#trigger-to-send-a-content-analytics-event)。

Content Analytics 实际上以这种方式收集数据来反映该序列，而不是将收集某次访问或点击与收集该访问或点击之后立即发生的事件两者分开。这种收集 Content Analytics 数据的方式也减少了所收集的数据量。

### 记录的访问或点击

在以下情况下会记录资产访问：

* 该资产尚未通过 Content Analytics 扩展配置被排除。
* 该资产的 75% 被访问。
* 该资产尚未为此页面被记录。

在以下情况下会记录资产点击：

* 该资产已被访问。
* 该资产尚未通过 Content Analytics 扩展配置被排除。
* 直接点击该资产（即链接）后转到另一个页面。

在以下情况下会记录体验访问：

* 在 Content Analytics 配置中启用了体验。

在以下情况下会记录体验点击：

* 对启用了体验的页面中某个链接的任何点击。


### 用于发送 Content Analytics 事件的触发器

为减少从页面发出的调用次数，Content Analytics 会收集信息，但不会立即发送。内容交互信息会先被收集，只有当以下触发器之一发生时，才会发送包含这些信息的事件：

* Web SDK 或 AppMeasurements 发送事件。
* 可见性变为隐藏，例如：
   * 页面卸载
   * 切换选项卡
   * 将浏览器最小化
   * 关闭浏览器
   * 锁定屏幕
* URL 发生变化，导致相关 URL 改变。
* 已记录并准备发送的资产访问数超过 32。

>[!NOTE]
>
>额外的 Content Analytics 事件很可能会影响任何基于会话或页面事件数量的跳出率定义。
>


## 架构

Content Analytics 数据根据特定的 Content Analytics 架构收集在 Experience Platform 的数据集中。参考架构公开可用：

* [数字资产架构](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [数字体验架构](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [体验事件内容架构](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
