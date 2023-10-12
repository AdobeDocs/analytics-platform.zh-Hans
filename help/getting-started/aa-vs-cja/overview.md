---
title: 与 Adobe Analytics 进行比较
description: 概述Customer Journey Analytics与Adobe Analytics的比较。
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 59aabb38ea3e5ba1501ab8da11d14ea2385d8a6b
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 8%

---

# 与 Adobe Analytics 进行比较

本文档的这一部分介绍了如何比较和了解与Adobe Analytics之间的Customer Journey Analytics差异。

这两种解决方案之间的根本区别在于构建报表和分析时您（可以）考虑的数据范围。

在Customer Journey Analytics中， *任意* 数据源可以是用于报表和分析的数据的一部分。 Adobe Analytics主要针对从网站和移动应用程序收集的在线数据。 Adobe Analytics提供从其他来源导入数据的功能，但主要目的是为前面提到的在线数据提供更多的上下文。

## 数据收集

Customer Journey Analytics依赖于Experience Platform数据集中存储的数据。 您可以使用多个选项收集数据并将这些数据摄取到Experience Platform中。 有关这些选项的详细说明，请参见 [数据引入概述](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html?lang=en).

Adobe Analytics最终会在解决方案中收集数据。 同样，您有多个选项可用于收集这些数据，详情请参见 [Adobe Analytics Implementation指南](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=zh-Hans).

您可以通过以下方式在Customer Journey Analytics中使用Adobe Analytics报表包数据 [Analytics源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans). 此连接器使用在Adobe Analytics中收集的数据来摄取Experience Platform，然后用于Customer Journey Analytics。 请参阅 [在Customer Journey Analytics中使用Adobe Analytics报表包数据](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=zh-Hans) 以了解更多信息。


## 数据处理

在报告数据之前，您通常需要处理该数据以确保可正确地为此目的使用数据。 可以在收集时间和报告时间处理数据。

通常，Customer Journey Analytics旨在处理在报告时收集并存储在Experience Platform数据集中的数据。 Customer Journey Analytics提供了强大的报表时间处理功能，确保数据准备好进行报告和分析。 如果您必须在数据被Experience Platform摄取之前映射、转换和验证数据，则可以使用 [数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hans) Experience Platform的功能。

在Adobe Analytics中，大多数数据处理会在收集数据后立即进行。

请参阅 [跨Adobe Analytics和Customer Journey Analytics比较数据处理](data-processing-comparisons.md) 和 [处理规则、VISTA和分类与数据准备](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=zh-Hans) 以了解更多信息。


## 术语

Customer Journey Analytics使您可以灵活地定义维度和量度，而基于基础Experience Data Model (XDM)的架构则提供了这种灵活性。 例如，在Adobe Analytics使用访客、访问和点击的情况下，Customer Journey Analytics使用人员、会话和事件作为等效概念，但您可以根据需要更改命名。

请参阅 [比较通过Analytics Source Connector传递的Analytics数据的术语](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html?lang=en) 以了解有关术语差异的更多信息。


## 虚拟报告环境和沙盒

Adobe Analytics具有虚拟报表包的概念，通过虚拟报表包，可对收集的数据进行分段并控制对该分段数据的访问。

Customer Journey Analytics有一个相似的概念，名为数据视图。 数据视图是容器，允许您确定如何解释来自连接的数据。 它提供了终极的灵活性，可指定和配置维度和量度，为您的报告和分析做准备。

Experience Platform提供沙盒，可以将其视为包含给定环境的数据和应用程序的容器。 沙盒的功能与Adobe Analytics虚拟报表包或Customer Journey Analytics数据视图无关。 Adobe Analytics本身与Experience Platform沙盒没有任何依赖关系或关系。 Customer Journey Analytics不支持Experience Platform沙盒，但存在一些重要注意事项。

请参阅 [虚拟报告包、数据视图、Adobe Experience Platform沙盒和Analytics源连接器](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=zh-Hans) 以了解更多信息。


## 标识

Customer Journey Analytics支持您在架构中定义的身份，其中包含您的数据的数据集符合这些身份。 因此，身份是Experience Platform的基本概念，Customer Journey Analytics在设置时使用该概念 [连接](../../connections/overview.md) （通过为每个数据集定义人员ID）并在应用时 [拼接](../../stitching/overview.md) 进行跨渠道分析。 Experience PlatformSDK和API使用的一个重要标识是Experience CloudID (ECID)。

Adobe Analytics使用一组更明确的标识字段，如Adobe Analytics ID (AAID)。 使用Analytics Source Connector时，这些Adobe Analytics标识字段将得到特殊处理。 请参阅 [AAID、ECID、AACUSTOMID和Analytics源连接器](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=en) 以了解更多信息。


## 功能

有关Adobe Analytics功能以及Customer Journey Analytics如何支持这些功能的概述，请访问 [Customer Journey Analytics功能支持](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html?lang=en).





