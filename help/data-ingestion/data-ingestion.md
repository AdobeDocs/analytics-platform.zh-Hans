---
title: 数据摄取概述
description: 了解将数据导入 Customer Journey Analytics 的不同方式
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: ead96b72-40f1-4ce9-8d91-c8ceea6c4458
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 96%

---

# 数据摄取概述

在将数据导入 Customer Journey Analytics 时您有多种选择。他们中的一些人假设你想移动传统的 Adobe Analytics 数据，有些人假设你使用的是从 Adobe Experience Platform 获取的数据。

>[!IMPORTANT]
>
>在所有情况下，您希望在 Customer Journey Analytics 中&#x200B;_使用的_&#x200B;数据实际上都是在 Adobe Experience Platform 中&#x200B;_获取的_。


请参阅前面[概述](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hans)中所示的高级 Customer Journey Analytics 体系结构：

![Customer Journey Analytics](./assets/cja-architecture.png)

上述模式中的数据集可以来自各种来源：

- 批次数据，

- 流式数据，

- 来自当前 Adobe Analytics 部署的数据，

- 使用 Adobe Experience Platform Web/Mobile SDK 跟踪您的网站/移动应用程序的数据，或

- 来自 Adobe 提供源连接器的第三方数据提供商的数据。

您可以拥有许多这些数据集。

文档的这一部分提供了各种场景的快速入门指南。

## 从传统 Adobe Analytics 中获取和使用数据

您已经部署了 Adobe Analytics，并希望在 Adobe Experience Platform 中获取这些数据，并将其与 Customer Journey Analytics 中其他渠道和数据源的数据一起使用、组合和分析。

有关更多信息请参阅[摄取并使用传统 Adobe Analytics 的数据](./analytics.md)。

## 通过 Adobe Experience Platform Web SDK 和 Edge Network 获取和使用数据

您希望使用Adobe技术分析您的网站，从其他解决方案进行迁移或开始跟踪您的人员的行为。 您希望遵循 Adobe 的最佳实施实践，即使用 Adobe Experience Platform SDK 和 Edge Network 来获取数据。然后您可以在 Customer Journey Analytics 中使用、组合和分析摄入的数据与来自其他渠道和数据源的数据。

有关更多信息请参阅[通过 Adobe Experience Platform Web SDK 和 Edge Network 摄取和使用数据](./aepwebsdk.md)。

## 摄取和使用批次数据

您有相关的批处理数据这些数据提供了详细信息可以帮助您更好地了解客户行为并分析客户互动。此类批处理数据的示例是来自 CRM 系统、忠诚度应用程序或 Adobe 当前未提供源连接器的其他解决方案的 CSV、JSON 或 Parquet 格式的平面文件。通过将此批数据导入 Adobe Experience Platform，您可以在 Customer Journey Analytics 中使用、组合并分析来自其他渠道和数据源的数据。

有关详细信息请参阅[摄入和使用批次数据](./batch.md)。

## 摄取和使用流式数据

您有一个相关的数据源，如 CRM 系统、ERP 系统或任何其他提供详细信息的源，可以帮助您更好地了解客户行为并分析客户互动。该数据源能够通过 HTTP 或公共云流基础设施进行通信，但 Adobe 目前没有提供源连接器。将这些流式数据实时导入 Adobe Experience Platform，使您能够使用、组合并分析来自 Customer Journey Analytics 中其他渠道和数据源的数据。

有关详细信息请参阅[摄取并使用流数据](./streaming.md)。

## 使用源连接器摄取和使用数据

您可以从源连接器支持的源获取数据。源连接器是可配置的配置允许您将数据从 Adobe、第一方和第三方应用程序摄取到 Adobe Experience Platform 中。有关可用源连接器的概述请参见[源连接器概述](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hans)。使用源连接器您可以轻松地将数据从源导入 Adobe Experience Platform，然后在 Customer Journey Analytics 中使用、组合和分析来自其他渠道和数据源的数据。

有关详细信息请参阅[摄取并使用源连接器使用数据](./sources.md)。
