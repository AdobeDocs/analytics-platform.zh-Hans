---
title: 数据摄取概述
description: 了解将数据摄取到 Customer Journey Analytics 的不同方式
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 5de8c0daaa7eea0a9ab993d256e2b0a14f37301e
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 7%

---


# 数据摄取概述

在将数据摄取到 Customer Journey Analytics 时，有多种选项供您选择。其中一些选项假定您要转移传统的Adobe Analytics数据，而另一些选项则假定您使用直接摄取到Adobe Experience Platform的数据。

>[!IMPORTANT]
>
>在所有情况下，您希望 _use_ Customer Journey Analytics _摄取_ 在Adobe Experience Platform。


请参阅 [概述](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hans):

![客户历程分析](./assets/cja-architecture.png)

上述架构中的数据集可能源自多种来源：批量数据、流数据、来自当前Adobe Analytics部署的数据、来自使用Adobe Experience Platform Web/Mobile SDK跟踪您的网站/移动设备应用程序的数据，或来自Adobe为其提供源连接器的第三方数据提供商的数据。 你可以拥有很多这样的数据集。

本文档的此部分提供了多种情景的快速入门指南。

## 从传统Adobe Analytics中摄取和使用数据

您已经部署了Adobe Analytics，并且希望在Adobe Experience Platform中摄取此数据，并将其与Customer Journey Analytics中其他渠道和数据源的数据进行合并和分析。

请参阅 [从传统Adobe Analytics中摄取和使用数据](./analytics.md) 以了解更多信息。

## 通过Adobe Experience Platform Web SDK和边缘网络摄取和使用数据

您想要使用Adobe技术分析您的网站，从其他解决方案迁移或开始跟踪访客的行为。 您希望遵循Adobe实施的最佳实践(使用Adobe Experience Platform SDK和边缘网络)来摄取数据。 然后，您可以在Customer Journey Analytics中使用、合并和分析从其他渠道和数据源摄取的数据。

请参阅 [通过Adobe Experience Platform Web SDK和边缘网络摄取和使用数据](./aepwebsdk.md) 以了解更多信息。

## 摄取和使用批量数据

您提供了相关的批量数据，其中提供了可帮助您更好地了解客户行为并分析客户交互的详细信息。 此类批量数据的示例包括CSV、JSON或Parquet格式的平面文件(来自CRM系统、忠诚度应用程序或Adobe当前未提供源连接器的其他解决方案)。 将此批量数据摄取到Adobe Experience Platform后，您可以使用、合并和分析来自其他渠道的数据以及Customer Journey Analytics中的数据源。

请参阅 [摄取和使用批量数据](./batch.md) 以了解更多信息。

## 摄取和使用流数据

您有一个相关的数据源，如CRM系统、ERP系统或任何其他数据源，它提供了详细信息，可帮助您更好地了解客户行为并分析客户交互。 该数据源能够通过HTTP或公共云流基础架构进行通信，但其Adobe当前不提供源连接器。 通过将此流数据实时摄取到Adobe Experience Platform中，您可以将其与其他渠道和数据源中的数据Customer Journey Analytics，从而使用、合并和分析这些数据。

请参阅 [摄取和使用流数据](./streaming.md) 以了解更多信息。

## 使用源连接器摄取和使用数据

源连接器支持的源中有可用的数据。 源连接器是可配置的配置，允许您将数据从Adobe、第一方和第三方应用程序摄取到Adobe Experience Platform。 请参阅 [源连接器概述](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hans) 有关可用源连接器的概述。 使用源连接器，您可以轻松地将数据从源摄取到Adobe Experience Platform中，然后将其与其他渠道和数据源中的数据Customer Journey Analytics使用、合并和分析。

请参阅 [使用源连接器摄取和使用数据](./sources.md) 以了解更多信息。

