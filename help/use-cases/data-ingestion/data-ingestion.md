---
title: Customer Journey Analytics 的数据摄取选项
description: 了解将数据摄取到 Customer Journey Analytics 的不同方式
exl-id: 4a47c587-f48e-4e29-b97f-00c7d7e6972c
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
autotag-review: '2026-05-19T11:01:56.579Z'
TQID: 'https://experienceleague.adobe.com/Uqoyk9k3hEOB90hzLtXhoYtmfX18wmXPHp-AWxgNIwU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 827
ht-degree: 86%

---

# Customer Journey Analytics 的数据摄取选项

在将数据摄取到 Customer Journey Analytics 时，有多种选项供您选择。 其中的有些选项假定您要转移传统 Adobe Analytics 的数据，而另一些选项则假定您直接从 Adobe Experience Platform 中摄取数据。 本参考提供了要遵循的高级步骤以及指向更多详细信息的链接。

## 从传统 Adobe Analytics 中摄取数据

此工作流利用Analytics源连接器，会因您使用DTM还是Launch作为标签管理器而有所不同。

### 通过 Adobe Experience Platform 中的标记（以前称为 [!UICONTROL Launch]）

1. [创建数据层](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=zh-Hans)（如果尚未创建）。 数据层是网站上 JavaScript 对象的框架，其中包含实施中使用的所有变量值。 它让您可以在实施中拥有更大的控制力且更便于维护。
1. 使用 [Adobe Experience Platform 标记](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=zh-Hans)在您的站点上实施代码以收集数据（如果尚未实施）。 这一款标记管理解决方案，可让您在满足其他标记要求的同时部署 Analytics 代码。 标记提供了与其他解决方案和产品的集成，并允许您部署自定义代码。 无需依赖组织中的开发团队，也可以完成以下所有任务，进而更新网站上的代码。
1. 在 Adobe Experience Platform 中创建一个 [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)。 该源连接器将会在名为[体验数据模型 (XDM) 系统](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)的标准化框架中，将分析数据摄取到 Experience Platform。 另查看[在 Customer Journey Analytics 中使用 Adobe Analytics 报告包](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)。
1. 使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=zh-Hans) 创建一个或多将纳入您的跨渠道报表的连接和数据视图。

## 通过 Adobe Experience PlatformWeb SDK和 Edge Network 获取数据

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)是客户端JavaScript库，它允许Adobe CX Enterprise的客户通过Adobe Experience Platform Edge Network与CX Enterprise中的各种服务进行交互。

1. [在标记](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html)中配置Adobe Experience Platform Web SDK扩展，以通过Adobe Experience Platform Edge Network从Web资产向CX Enterprise发送数据。
1. 请使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) 创建一个或多个将通知跨渠道报告的[连接](/help/connections/create-connection.md)和[数据视图](/help/data-views/data-views.md)。

## 通过批量摄取和流式摄取来获取数据

Adobe Experience Platform 将来自多个来源的数据整合在一起，以帮助营销人员更好地了解其客户的行为。 Adobe Experience Platform Data Ingestion 表示平台从这些来源获取数据的多种方法，以及该数据如何在“数据湖”中保留以供下游平台服务使用。

### 批量摄取

1. 设置[批量摄取](https://experienceleague.adobe.com/docs/experience-platform/ingestion/batch/overview.html#batch)，以允许您将数据作为批处理文件接入 Adobe Experience Platform。 所摄取的数据可以是来自 CRM 系统中平面文件（如 Parquet 文件）的轮廓数据，也可以是与 Experience Data Model (XDM) 注册表中的已知架构相符的数据。
1. 使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) 创建一个或多个将通知跨渠道报告的[连接](/help/connections/create-connection.md)和[数据视图](/help/data-views/data-views.md)。

### 流式摄取

1. 设置[流式摄取](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html#streaming)，以实时将数据从客户端和服务器端设备发送到 Experience Platform。
1. 请使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html) 创建一个或多个将通知跨渠道报告的[连接](/help/connections/create-connection.md)和[数据视图](/help/data-views/data-views.md)。

## 接入 Google Analytics 数据以在 Customer Journey Analytics 中分析

阅读本教程，了解如何[使用 Customer Journey Analytics 分析 Google Analytics 数据](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial-v22/module12/ex5.html)的详细步骤。

## 使用批量数据插入API将数据导入Analytics，然后通过Experience Platform中的Analytics源连接器进行摄取

1. [使用批量数据摄取 API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)，将服务器端收集数据提交到 Adobe Analytics。 它允许您提交包含事件数据的 CSV 格式文件。
1. [创建 Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)，将此使用者数据接入 Adobe Experience Platform。
1. 使用 [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=zh-Hans) 创建一个或多个将通知跨渠道报告的[连接](/help/connections/create-connection.md)和[数据视图](/help/data-views/data-views.md)。
