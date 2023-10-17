---
title: 与 Adobe Analytics 进行比较
description: Customer Journey Analytics 与 Adobe Analytics 相比的概述。
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 4cbf01d397e7f89e67ae20702790129478d45cce
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 73%

---

# 与 Adobe Analytics 进行比较

本文档的这一部分介绍了如何比较和了解Adobe Customer Journey Analytics与Adobe Analytics之间的差异。

这两个解决方案之间的根本区别在于构建报告和分析时（可）考虑的数据广度。

在 Customer Journey Analytics 中，*任何*&#x200B;数据源都可以是用于报告和分析的数据的一部分。Adobe Analytics 主要针对从网站和移动应用程序收集的在线数据。Adobe Analytics提供从其他来源导入数据的功能，但主要目的是围绕前面提到的在线数据提供更多的上下文。

## 数据收集

Customer Journey Analytics依赖存储在Adobe Experience Platform数据集中的数据。 您可以使用多个选项从Experience Platform中的这些数据集收集和摄取数据。 [数据摄取概述](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html?lang=zh-Hans)中更详细地介绍了这些选项。

Adobe Analytics 最终在解决方案本身中收集数据。同样，您有若干选项可收集这些数据，在 [Adobe Analytics 实施指南](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=zh-Hans)中更详细地概述了这些选项。

可使用 [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans) 在 Customer Journey Analytics 中使用您的 Adobe Analytics 报告包数据。此连接器会将Adobe Analytics中收集的数据摄取到Experience Platform中。 然后，您可以在Customer Journey Analytics中创建与此数据集的连接。 有关更多信息，请参阅[在 Customer Journey Analytics 中使用 Adobe Analytics 报告包数据](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=zh-Hans)。


## 数据处理

在您能够报告数据之前，通常需要处理该数据以确保能够正确地将数据用于报告。 可以在收集时间和报告时间进行数据处理。

Customer Journey Analytics 一般是要在报告时处理所收集并存储在 Experience Platform 数据集中的数据。Customer Journey Analytics 提供强大的报告时处理功能以确保数据准备好进行报告和分析。如果必须映射、转换和验证数据后才能将数据摄取到 Experience Platform 中，则可使用 Experience Platform 的[数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hans)功能。

在 Adobe Analytics 中，在收集数据后立即进行大部分数据处理。

有关更多信息，请参阅[比较 Adobe Analytics 和 Customer Journey Analytics 的数据处理](data-processing-comparisons.md)和[处理规则、VISTA 和分类与数据准备](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=zh-Hans)。


## 术语

通过基于底层体验数据模型 (XDM) 的架构产生的灵活性，可在 Customer Journey Analytics 中灵活地定义维度和量度。例如，在Adobe Analytics使用访客、访问和点击的情况下，Customer Journey Analytics使用人员、会话和事件作为等效概念（您可以根据需要更改命名）。

有关术语中各种区别的详细信息，请参阅[比较通过 Analytics Source Connector 传递的 Analytics 数据的术语](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html?lang=zh-Hans)。


## 虚拟报告环境和沙盒

Adobe Analytics具有虚拟报表包的概念，通过虚拟报表包，可对收集的数据进行分段并控制对该分段数据的访问。

Customer Journey Analytics有一个相似的概念，称为数据视图。 数据视图是一些容器，通过这些容器，可确定如何解释从连接获得的数据。它们提供了终极的灵活性，可指定和配置维度和量度，为您的报告和分析做准备。

Experience Platform 提供可被视为容器的沙盒，而该容器中容纳给定环境的数据和应用程序。沙盒的功能与 Adobe Analytics 虚拟报告包或 Customer Journey Analytics 数据视图无关。Adobe Analytics 自身完全不依赖 Experience Platform 沙盒，并且完全与其无关。Customer Journey Analytics不支持Experience Platform沙盒，但存在一些重要注意事项。

有关更多信息，请参阅[虚拟报告包、数据视图、Adobe Experience Platform 沙盒和 Analytics Source Connector](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=zh-Hans)。


## 标识

Customer Journey Analytics 支持将标识定义为包含数据的数据集所遵循的架构的一部分。因此，标识是 Experience Platform 的基本概念，Customer Journey Analytics 在设置[连接](../../connections/overview.md)（通过为每个数据集定义人员 ID）以及应用[拼合](../../stitching/overview.md)以进行跨渠道分析时将使用这一概念。Experience Platform SDK 和 API 使用的一个重要标识是 Experience Cloud ID (ECID)。

Adobe Analytics 使用一组更明确的标识字段，例如 Adobe Analytics ID (AAID)。在使用 Analytics Source Connector 时，将对这些 Adobe Analytics 标识字段进行特殊处理。有关更多信息，请参阅 [AAID、ECID、AACUSTOMID 和 Analytics Source Connector](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=zh-Hans)。


## 支持的功能

有关 Adobe Analytics 功能以及 Customer Journey Analytics 如何支持这些功能的概述，请参阅 [Customer Journey Analytics 功能支持](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html?lang=zh-Hans)。





