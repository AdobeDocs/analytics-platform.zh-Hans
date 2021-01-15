---
title: Customer Journey Analytics 的数据摄取选项
description: 了解将数据摄取到 Customer Journey Analytics 的不同方式
translation-type: tm+mt
source-git-commit: ab1ea4c75c4c28f196c6793a819ce4dbe656d52c
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 61%

---


# Customer Journey Analytics 的数据摄取选项

在将数据摄取到 Customer Journey Analytics 时，有多种选项供您选择。其中的有些选项假定您要转移传统 Adobe Analytics 的数据，而另一些选项则假定您直接从 Adobe Experience Platform 中摄取数据。本参考提供了要遵循的高级步骤以及指向更多详细信息的链接。

## 从传统 Adobe Analytics 中摄取数据

此工作流利用 Adobe Analytics Data Connector，会因您选择 DTM 还是 Launch 作为标签管理器而有所不同。

### 通过 Dynamic Tag Management (DTM)

1. [创建数据层](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/prepare/data-layer.html)（如果尚未创建）。数据层是网站上 JavaScript 对象的框架，其中包含实施中使用的所有变量值。它让您可以在实施中拥有更大的控制力且更便于维护。
1. 使用 [DTM](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/other/dtm/dtm-implementation-overview.html) 在您的站点上实施代码以收集数据（如果尚未实施）。Dynamic Tag Management 可提供一个用于从多个数据源提取数据的单一数据层。
1. 在 Adobe Experience Platform 中创建一个 [Adobe Analytics 源连接器](https://docs.adobe.com/content/help/zh-Hans/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)。该源连接器将会在名为[体验数据模型 (XDM) 系统](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/home.html)的标准化框架中，将 Analytics 数据摄取到 Experience Platform。
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/zh-Hans/analytics-platform/using/cja-overview/cja-getting-started.html) 创建一个或多将纳入您的跨渠道报表的连接和数据视图。

### 通过 Launch

1. [创建数据层](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html)（如果尚未创建）。数据层是网站上 JavaScript 对象的框架，其中包含实施中使用的所有变量值。它让您可以在实施中拥有更大的控制力且更便于维护。
1. 使用 [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/launch/overview.html) 在您的站点上实施代码以收集数据（如果尚未实施）。Launch 是一款标签管理解决方案，可让您在满足其他标记要求的同时部署 Analytics 代码。Launch 提供了与其他解决方案和产品的集成，并允许您部署自定义代码。无需依赖组织中的开发团队，也可以完成以下所有任务，进而更新网站上的代码。
1. 在 Adobe Experience Platform 中创建一个 [Adobe Analytics 源连接器](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)。该源连接器将会在名为[体验数据模型 (XDM) 系统](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html)的标准化框架中，将 Analytics 数据摄取到 Experience Platform。
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) 创建一个或多将纳入您的跨渠道报表的连接和数据视图。

## 通过Adobe Experience PlatformWeb SDK和Edge Network获取数据

[Adobe Experience Platform网](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 络SDK是客户端JavaScript库，它允许Adobe Experience Cloud的客户通过Adobe Experience Platform边缘网络与Experience Cloud中的各种服务进行交互。无论是否使用Launch，都可以配置此摄取。

### 无需启动

此链接无效：https://docs.adobe.com/content/help/en/experience-platform/edge/get-started/quick-start-without-launch.html。 如果没有Launch，这是否仍然可行？

### 使用Launch

1. [配置AEP Web SDK扩](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=en#configure-the-aep-web-sdk-extension) 展，通过Adobe Experience Platform边缘网络从Web属性向Adobe Experience Cloud发送数据。
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) 创建一个或多将纳入您的跨渠道报表的连接和数据视图。

## 通过批量摄取和流摄取来摄取数据

Adobe Experience Platform将来自多个来源的数据整合在一起，以帮助营销人员更好地了解其客户的行为。 Adobe Experience Platform数据摄取表示平台从这些来源收集数据的多种方法，以及该数据如何在数据湖中保留以供下游平台服务使用。

### 批量摄取

1. 设置[批处理摄取](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=en#batch)，以允许您将数据作为批处理文件引入Adobe Experience Platform。 所摄取的用户档案可以是CRM系统中平面文件（如拼花文件）中的模式数据，也可以是与体验数据模型(XDM)注册表中的已知数据相符的数据。
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) 创建一个或多将纳入您的跨渠道报表的连接和数据视图。

### 流摄取

1. 设置[流摄取](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=en#streaming)以将数据从客户端和服务器端设备实时发送到Experience Platform。
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) 创建一个或多将纳入您的跨渠道报表的连接和数据视图。

## 引入Google Analytics数据，以Customer Journey Analytics分析

阅读本教程，了解如何使用Customer Journey Analytics](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module16/ex5.html?lang=en#objectives)分析Google Analytics数据，以了解详细步骤。[

## 使用批量数据插入API将数据导入Analytics，然后在Experience Platform中通过Adobe源连接器进行摄取

1. [使用批量数据插](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) 入API将服务器端收集数据提交到Adobe Analytics。它允许您提交包含事件数据的CSV格式文件。
1. [创建Adobe Analytics源连](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) 接器，将此消费者数据引入Adobe Experience Platform。
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-overview/cja-getting-started.html) 创建一个或多将纳入您的跨渠道报表的连接和数据视图。