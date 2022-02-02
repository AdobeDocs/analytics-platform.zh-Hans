---
title: Customer Journey Analytics 的数据摄取选项
description: 了解将数据摄取到 Customer Journey Analytics 的不同方式
exl-id: 4a47c587-f48e-4e29-b97f-00c7d7e6972c
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '779'
ht-degree: 100%

---

# Customer Journey Analytics 的数据摄取选项

在将数据摄取到 Customer Journey Analytics 时，有多种选项供您选择。其中的有些选项假定您要转移传统 Adobe Analytics 的数据，而另一些选项则假定您直接从 Adobe Experience Platform 中摄取数据。本参考提供了要遵循的高级步骤以及指向更多详细信息的链接。

## 从传统 Adobe Analytics 中摄取数据

此工作流利用 Adobe Analytics Data Connector，会因您选择 DTM 还是 Launch 作为标签管理器而有所不同。

### 通过 Launch

1. [创建数据层](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=zh-Hans)（如果尚未创建）。数据层是网站上 JavaScript 对象的框架，其中包含实施中使用的所有变量值。它让您可以在实施中拥有更大的控制力且更便于维护。
1. 使用 [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=zh-Hans) 在您的站点上实施代码以收集数据（如果尚未实施）。Launch 是一款标签管理解决方案，可让您在满足其他标记要求的同时部署 Analytics 代码。Launch 提供了与其他解决方案和产品的集成，并允许您部署自定义代码。无需依赖组织中的开发团队，也可以完成以下所有任务，进而更新网站上的代码。
1. 在 Adobe Experience Platform 中创建一个 [Adobe Analytics 源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans)。该源连接器将会在名为[体验数据模型 (XDM) 系统](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hans)的标准化框架中，将 Analytics 数据摄取到 Experience Platform。
1. 使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=zh-Hans) 创建一个或多将纳入您的跨渠道报表的连接和数据视图。

## 通过 Adobe Experience PlatformWeb SDK和 Edge Network 获取数据

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hans) 是客户端 JavaScript 库，它允许 Adobe Experience Cloud 的客户通过 Adobe Experience Platform Edge Network 与 Experience Cloud 中的各种服务进行交互。

1. [在 Launch 中配置 AEP Web SDK 扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=en)，通过 Adobe Experience Platform Edge Network 从 Web 资产向 Adobe Experience Cloud 发送数据。
1. 使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=zh-Hans) 创建一个或多将纳入您的跨渠道报表的连接和数据视图。

## 通过批量摄取和流式摄取来获取数据

Adobe Experience Platform 将来自多个来源的数据整合在一起，以帮助营销人员更好地了解其客户的行为。Adobe Experience Platform Data Ingestion 表示平台从这些来源获取数据的多种方法，以及该数据如何在“数据湖”中保留以供下游平台服务使用。

### 批量摄取

1. 设置[批量摄取](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html?lang=zh-Hans#batch)，以允许您将数据作为批处理文件接入 Adobe Experience Platform。 所摄取的数据可以是来自 CRM 系统中平面文件（如 Parquet 文件）的配置文件数据，也可以是与 Experience Data Model (XDM) 注册表中的已知架构相符的数据。
1. 使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=zh-Hans) 创建一个或多将纳入您的跨渠道报表的连接和数据视图。

### 流式摄取

1. 设置[流式摄取](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=zh-Hans#streaming)，以实时将数据从客户端和服务器端设备发送到 Experience Platform。
1. 使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=zh-Hans) 创建一个或多将纳入您的跨渠道报表的连接和数据视图。

## 接入 Google Analytics 数据以在 Customer Journey Analytics 中分析

阅读本教程，了解如何[使用 Customer Journey Analytics 分析 Google Analytics 数据](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module16/ex5.html?lang=zh-Hans#objectives)的详细步骤。

## 使用批量数据摄取 API 将数据接入 Analytics，然后在 Experience Platform 中通过 Adobe Source Connector 进行摄取。

1. [使用批量数据摄取 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)，将服务器端收集数据提交到 Adobe Analytics。它允许您提交包含事件数据的 CSV 格式文件。
1. [创建 Adobe Analytics 源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans)，将此使用者数据接入 Adobe Experience Platform。
1. 使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=zh-Hans) 创建一个或多将纳入您的跨渠道报表的连接和数据视图。
