---
title: 在Customer Journey Analytics中利用Adobe Analytics报表包数据
description: 如何配置Adobe Analytics报表包以将其摄取到AEP和CJA中
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: dbb7edae43fdc970cacf5863ecd13df75deaefad
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 13%

---

# 在Customer Journey Analytics中利用Adobe Analytics报表包数据

Adobe Analytics客户可以使用 [Analytics源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hans). 以下讨论将说明如何执行此操作。

## 准备

在AEP和CJA中开始使用Adobe Analytics报表包时，您应当考虑执行以下几项操作来准备数据，以便无缝迁移到Customer Journey Analytics。 有关详细信息，请查看以下页面：

* [Adobe Analytics 到 Customer Journey Analytics 的演变](/help/getting-started/aa-to-cja.md)

## 设置报表包以将数据摄取到Adobe Experience Platform和CJA中

准备好数据后，即可开始配置报表包以在AEP和CJA中使用。

1. **为要在AEP和CJA中使用的每个报表包创建数据流。** 的 [Analytics源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en) 是用于 [创建连接](/help/connections/create-connection.md) （也称为数据流）。 您将使用源连接器为要在AEP中使用的每个报表包创建一个数据流。 数据流会创建报表包数据的副本，其中架构已转换为  [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=zh-Hans) 供AEP应用程序（包括CJA）使用。 通过源连接器配置了数据流的每个报表包都会作为单独的数据集存储在AEP数据湖中。 每个数据流中将自动包含13个月的历史报表包数据，并且新数据将持续流入AEP。 使用Analytics源连接器，您无需担心要提前创建架构。 系统将自动为您创建特定于Adobe Analytics的标准化架构。 但是，AEP的 [数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hans) 工具可用于在将数据存储到数据湖中并可供CJA使用之前增强此模式。 请注意，某些类型的数据由源连接器过滤出来，并且不会出现在AEP Data Lake的数据集中。 其他行可能会在Data Lake和CJA之间过滤掉。 请参阅 [比较Adobe Analytics数据与CJA数据](/help/troubleshooting/compare.md) 以了解更多详细信息。
1. **使用数据准备可帮助您在CJA中组合报表包。** 数据准备可用于多种类型的数据转换，而Adobe Analytics数据的一个常见用途是解决多个报表包中的prop和/或eVar映射差异，以便在CJA中轻松组合报表包。 请参阅 [将不同架构的报表包组合在一起](/help/use-cases/aa-data/combine-report-suites.md) 以了解更多详细信息。
1. **启用跨渠道分析** 视需要。 在CJA中合并多个数据集时，跨渠道分析的身份拼合功能可帮助将不同的ID命名空间解析为跨设备和渠道的客户单个视图的单个拼合ID。 请参阅 [跨渠道分析概述](/help/connections/cca/overview.md) 以了解更多详细信息。
1. **创建一个或多个CJA连接。** 在AEP数据湖中提供报表包的数据集后，您可以创建一个或多个 [CJA连接](/help/connections/overview.md) 将数据集导入CJA。 在连接中，报表包数据可以与其他类型的数据组合使用，从而创建真实的客户体验跨渠道视图。
1. **创建一个或多个CJA数据视图。** A [数据视图](/help/data-views/data-views.md) 是特定于Customer Journey Analytics的容器，可让您确定如何解释CJA连接中的数据。 数据视图具有许多功能强大 [配置选项](/help/data-views/create-dataview.md) 用于自定义在 [Analysis Workspace](/help/analysis-workspace/home.md).

## 比较Customer Journey Analytics和Adobe Analytics

Customer Journey Analytics和Adobe Analytics有很多相似之处。 例如，CJA和Adobe Analytics都提供了Analysis Workspace的强大功能，可进行自由格式的思想速度分析。 但是，由于CJA是Adobe Experience Platform中的一个应用程序，并且将AEP用于数据摄取，因此CJA和Adobe Analytics在许多重要方面存在差异。 以下文章有助于了解这些差异：

* [将 Adobe Analytics 数据与 CJA 数据进行比较](/help/troubleshooting/compare.md)
* [Customer Journey Analytics 功能支持](/help/getting-started/aa-vs-cja/cja-aa.md)
* [比较通过 Analytics Source Connector 传递的 Analytics 数据的术语](/help/getting-started/aa-vs-cja/terminology.md)
* [跨 Adobe Analytics 和 CJA 报告功能比较数据处理](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [虚拟报告包、数据视图、AEP 沙盒和 Analytics Source Connector ](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [处理规则、VISTA 和分类与数据准备](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID、ECID、AACUSTOMID 和 Analytics Source Connector](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
