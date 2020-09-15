---
title: Customer Journey Analytics的数据获取选项
description: 了解将数据收录到Customer Journey Analytics的不同方式
translation-type: tm+mt
source-git-commit: 4ea06ca1f13255c570ccc9f69cb328d57bf975b2
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 27%

---


# Customer Journey Analytics的数据获取选项

在将数据引入Customer Journey Analytics方面，您有许多选择。 他们中有些人认为你想转移传统的Adobe Analytics数据，有些人认为你直接从Adobe Experience Platform收集数据。 本参考提供了要遵循的高级步骤，其中提供了指向更详细信息的链接。

## 从传统Adobe Analytics采集数据

此工作流利用Adobe Analytics数据连接器，并因您使用DTM还是Launch作为标签管理器而有所不同。

### 通过动态标签管理(DTM)

1. [创建数据层](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html)，如果您还没有。 数据层是网站上 JavaScript 对象的框架，其中包含实施中使用的所有变量值。它让您可以在实施中拥有更大的控制力且更便于维护。
1. 使用 [DTM](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/other/dtm/dtm-implementation-overview.html) 在您的站点上实施代码以收集数据（如果尚未）。 动态标签管理可提供一个用于从多个数据源提取数据的单一数据层。
1. 创建 [Adobe Analytics源连接器](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) adobe experience platform。 此源连接器将将Analytics数据引入一个称为 [体验数据模型(XDM)系统](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/home.html).
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/zh-Hans/analytics-platform/using/cja-overview/cja-getting-started.html) 创建一个或多个连接和视图，以通知您的跨渠道报告。

### 通过启动

1. [创建数据层](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html)，如果您还没有。 数据层是网站上 JavaScript 对象的框架，其中包含实施中使用的所有变量值。它让您可以在实施中拥有更大的控制力且更便于维护。
1. 使用 [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/analytics/implementation/launch/overview.html) 在您的站点上实施代码以收集数据（如果尚未）。 Launch 是一款标签管理解决方案，可让您在满足其他标记要求的同时部署 Analytics 代码。启动优惠与其他解决方案和产品集成，并让您部署自定义代码。 所有这些任务都可以完成，无需依赖组织中的任何开发团队更新站点上的代码。
1. 创建 [Adobe Analytics源连接器](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) adobe experience platform。 此源连接器将将Analytics数据引入一个称为 [体验数据模型(XDM)系统](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) 创建一个或多个连接和视图，以通知您的跨渠道报告。
