---
title: 数据摄取概述
description: 了解将数据导入 Customer Journey Analytics 的不同方式
solution: Customer Journey Analytics
feature: Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 70%

---

# 数据摄取概述

将数据摄取到Customer Journey Analytics时，有几个选项可供您选择。 他们中的一些人假设你想移动传统的 Adobe Analytics 数据，有些人假设你使用的是从 Adobe Experience Platform 获取的数据。

>[!IMPORTANT]
>
>在所有情况下，您希望在 Customer Journey Analytics 中&#x200B;_使用的_&#x200B;数据实际上都是在 Adobe Experience Platform 中&#x200B;_获取的_。


请参阅前面[概述](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hans)中所示的高级 Customer Journey Analytics 体系结构：

![本节中描述的Customer Journey Analytics架构](./assets/cja-architecture.png)

上述模式中的数据集可以来自各种来源：

- 批次数据，

- 流式数据，

- 来自当前 Adobe Analytics 部署的数据，

- 来自使用Adobe Experience Platform Web/Mobile SDK跟踪您的网站/移动应用程序的数据，

- 来自使用Adobe Experience Platform Edge Network Server API跟踪桌面应用程序、控制台游戏、机顶盒或IoT设备的数据，或者

- 来自 Adobe 提供源连接器的第三方数据提供商的数据。

您可以拥有许多这些数据集。

文档的这一部分提供了各种场景的快速入门指南。

## 从传统 Adobe Analytics 中获取和使用数据

您已经部署了 Adobe Analytics，并希望在 Adobe Experience Platform 中获取这些数据，并将其与 Customer Journey Analytics 中其他渠道和数据源的数据一起使用、组合和分析。

有关更多信息请参阅[摄取并使用传统 Adobe Analytics 的数据](./analytics.md)。


## 通过Edge Network引入和使用数据

### 使用Adobe Experience Platform Web SDK

您希望使用Adobe技术分析您的网站，从其他解决方案进行迁移或开始跟踪您的人员的行为。 您希望遵循 Adobe 的最佳实施实践，即使用 Adobe Experience Platform SDK 和 Edge Network 来获取数据。然后您可以在 Customer Journey Analytics 中使用、组合和分析摄入的数据与来自其他渠道和数据源的数据。

请参阅 [通过Adobe Experience Platform Web SDK摄取和使用数据](./aepwebsdk.md) 以了解更多信息。

### 使用Adobe Experience Platform Mobile SDK

您要使用Adobe技术分析您的移动应用程序，并可能从其他解决方案进行迁移，或者从头开始跟踪人员在应用程序中的行为。 您希望遵循 Adobe 的最佳实施实践，即使用 Adobe Experience Platform SDK 和 Edge Network 来获取数据。然后您可以在 Customer Journey Analytics 中使用、组合和分析摄入的数据与来自其他渠道和数据源的数据。

请参阅 [通过Adobe Experience Platform Mobile SDK摄取和使用数据](./aepmobilesdk.md) 以了解更多信息。

### 使用Adobe Experience Platform Edge Network服务器API

您想要分析桌面应用程序、游戏主机上所玩的游戏、机顶盒上的视频流应用程序的使用情况或使用Adobe技术的IoT设备。 可以从其他解决方案进行迁移，或从头开始跟踪人员在这些设备上的行为。 您需要遵循Adobe的最佳实施实践，即使用Adobe Experience Platform Edge Network服务器API和Edge Network来摄取数据。 然后您可以在 Customer Journey Analytics 中使用、组合和分析摄入的数据与来自其他渠道和数据源的数据。

请参阅 [通过Adobe Experience Platform Edge Network服务器API摄取和使用数据](./serverapi.md) 以了解更多信息。

## 摄取和使用批次数据

您有相关的批处理数据这些数据提供了详细信息可以帮助您更好地了解客户行为并分析客户互动。此类批处理数据的示例是来自 CRM 系统、忠诚度应用程序或 Adobe 当前未提供源连接器的其他解决方案的 CSV、JSON 或 Parquet 格式的平面文件。通过将此批数据导入 Adobe Experience Platform，您可以在 Customer Journey Analytics 中使用、组合并分析来自其他渠道和数据源的数据。

有关详细信息请参阅[摄入和使用批次数据](./batch.md)。

## 摄取和使用流式数据

您有一个相关的数据源，如 CRM 系统、ERP 系统或任何其他提供详细信息的源，可以帮助您更好地了解客户行为并分析客户互动。该数据源能够通过 HTTP 或公共云流基础设施进行通信，但 Adobe 目前没有提供源连接器。将这些流式数据实时导入 Adobe Experience Platform，使您能够使用、组合并分析来自 Customer Journey Analytics 中其他渠道和数据源的数据。

有关详细信息请参阅[摄取并使用流数据](./streaming.md)。

## 使用源连接器摄取和使用数据

您可以从源连接器支持的源获取数据。源连接器是可配置的配置允许您将数据从 Adobe、第一方和第三方应用程序摄取到 Adobe Experience Platform 中。有关可用源连接器的概述请参见[源连接器概述](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hans)。使用源连接器您可以轻松地将数据从源导入 Adobe Experience Platform，然后在 Customer Journey Analytics 中使用、组合和分析来自其他渠道和数据源的数据。

有关详细信息请参阅[摄取并使用源连接器使用数据](./sources.md)。
