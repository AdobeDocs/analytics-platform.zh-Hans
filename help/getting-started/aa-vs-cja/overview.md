---
title: 与 Adobe Analytics 进行比较
description: Customer Journey Analytics 与 Adobe Analytics 的比较概述。
solution: Customer Journey Analytics
feature: Basics
exl-id: bde36283-86af-4b1a-9cbe-e251676b2951
role: User
autotag-review: '2026-05-19T09:13:47.721Z'
TQID: 'https://experienceleague.adobe.com/MU9ywSyInHtsdzqvxO3yxTSY5bcDvdhnTUkhAgDHmZ4'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
    internal-label: Upgrade
  - id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
    internal-label: Basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 1f480cda20e0b2d54dd42b909bfa8bf8a2bc0c95
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 52%
---
# 与 Adobe Analytics 进行比较

文档的此部分阐述如何比较 Adobe Customer Journey Analytics 与 Adobe Analytics 以及理解两者之间的区别。

这两个解决方案之间的根本区别在于构建报告和分析时（可）考虑的数据广度。

在 Customer Journey Analytics 中，*任何*&#x200B;数据源都可以是用于报告和分析的数据的一部分。 Adobe Analytics主要针对从网站和移动应用程序收集的在线数据。 Adobe Analytics提供从其他来源导入数据的功能，但此功能的主要目的是围绕前面提到的在线数据提供更多上下文。

## 数据收集

Customer Journey Analytics 依赖存储在 Adobe Experience Platform 数据集中的数据。 您有若干选项可在 Experience Platform 中从这些数据集收集和摄取数据。 [数据摄取概述](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-data-ingestion/data-ingestion)中详细介绍了这些选项。

Adobe Analytics 最终在解决方案本身中收集数据。 同样，您有多个选项可用于收集这些数据，在[Adobe Analytics Implementation Guide](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/home)中有详细介绍。

可使用 [Analytics Source Connector](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) 在 Customer Journey Analytics 中使用您的 Adobe Analytics 报告包数据。 此连接器将在 Adobe Analytics 中收集的数据摄取到 Experience Platform 中。 您随后即可在 Customer Journey Analytics 中创建与此数据集的连接。 有关更多信息，请参阅[在 Customer Journey Analytics 中使用 Adobe Analytics 报告包数据](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja)。

Adobe Analytics报表包中的数据与构成Customer Journey Analytics连接的Adobe Experience Platform数据集中所存储的数据无关。 因此，Adobe建议您单独评估每个平台中的数据，而不是希望两个平台都反映相同的值。

## 数据处理

一般需要处理这些数据以确保可正确地将数据用于报告，然后才能报告这些数据。 可在收集时和报告时处理数据。

通常，Customer Journey Analytics设计用于在报告时处理Experience Platform数据集中所收集和存储的数据。 Customer Journey Analytics 提供强大的报告时处理功能以确保数据准备好进行报告和分析。 可以修改[派生字段](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/derived-fields)和[组件设置](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/overview)，并将其逆向应用于历史数据。 如果您必须在摄取数据之前映射、转换和验证数据，则可以使用Experience Platform的[数据准备](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/data-prep/home)功能。

在 Adobe Analytics 中，在收集数据后立即进行大部分数据处理。 此时会应用营销渠道规则、处理规则、eVar持久性和其他后处理逻辑，这些规则在报表包中是永久性的。 对其中任何配置所做的更改只会影响从该时间点开始的新传入数据。

有关更多信息，请参阅[比较 Adobe Analytics 和 Customer Journey Analytics 的数据处理](data-processing-comparisons.md)和[处理规则、VISTA 和分类与数据准备](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep)。


## 术语

Customer Journey Analytics 可灵活定义维度和量度，这得益于底层基于体验数据模型 (XDM) 的架构所提供的灵活性。 例如，在Adobe Analytics使用访客、访问和点击的情况下，Customer Journey Analytics使用人员、会话和事件（您可以根据需要更改命名）。

有关术语中各种区别的详细信息，请参阅[比较通过 Analytics Source Connector 传递的 Analytics 数据的术语](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology)。


## 虚拟报告环境和沙盒

Adobe Analytics 具有虚拟报告包的概念，通过这个概念，可为收集的数据分段并控制对该分段数据的访问。

Customer Journey Analytics 具有一个类似的概念，称为数据视图。 数据视图是一些容器，通过这些容器，可确定如何解释从连接获得的数据。 利用它们，可以非常灵活地指定和配置维度和量度以准备用于您的报告和分析。

Experience Platform提供了沙盒，沙盒可用作容纳给定环境的数据和应用程序的容器。 沙盒的功能与 Adobe Analytics 虚拟报告包或 Customer Journey Analytics 数据视图无关。 Adobe Analytics本身与Experience Platform沙盒没有依赖关系或关系。 Customer Journey Analytics 支持 Experience Platform 沙盒，但有一些重要的注意事项。

有关更多信息，请参阅[虚拟报告包、数据视图、Adobe Experience Platform 沙盒和 Analytics Source Connector](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc)。


## 身份标识

Customer Journey Analytics 支持您定义的身份标识，这些身份标识是包含您的数据的数据集所遵循的架构的一部分。 因此，身份标识是 Experience Platform 的基本概念，Customer Journey Analytics 在设置[连接](../../connections/overview.md)（通过为每个数据集定义人员 ID）以及应用[拼合](../../stitching/overview.md)以进行跨渠道分析时将使用这一概念。 Experience Platform SDK和API使用的一个重要标识是ECID。

Adobe Analytics 使用一组更明确的身份标识字段，例如 Adobe Analytics ID (AAID)。 使用Analytics Source Connector时，这些Adobe Analytics标识字段将得到特殊处理。 有关更多信息，请参阅 [AAID、ECID、AACUSTOMID 和 Analytics Source Connector](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc)。


## 高基数维度

Customer Journey Analytics存储整个维度值，并且一个维度可以跨越的唯一值数量没有限制。 相比之下，Adobe Analytics使用32位哈希来映射维度值，以优化报表和存储。 此行为可能导致报表中出现[哈希冲突](https://experienceleague.adobe.com/en/docs/analytics/implementation/validate/hash-collisions)。 在达到唯一限制阈值后，Adobe Analytics还会将值存储到[低流量](https://experienceleague.adobe.com/en/docs/analytics/technotes/low-traffic)行项目中。 使用这些维度的区段可能会显示Adobe Analytics报表与Customer Journey Analytics报表之间的差异。

## 支持的功能

您可以在[Adobe Analytics功能支持](https://experienceleague.adobe.com/en/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa)上找到Customer Journey Analytics功能以及Customer Journey Analytics如何支持这些功能的概述。
