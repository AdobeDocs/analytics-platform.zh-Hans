---
title: 在 Customer Journey Analytics 中使用 Adobe Analytics 报告包
description: 如何配置Adobe Analytics报表包以引入Adobe Experience Platform和Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: ca329bd551990c1fefeda2fe272ed17551cfaac8
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 30%

---

# 在 Customer Journey Analytics 中使用 Adobe Analytics 报告包

Adobe Analytics 客户可以使用 [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hans) 在 Adobe Experience Platform 和 Customer Journey Analytics 中轻松利用他们的报告包。以下讨论解释了如何这样做。

## 准备

当您准备好在Adobe Experience Platform和Customer Journey Analytics中开始使用Adobe Analytics报表包时，您应考虑执行以下操作，以便为无缝迁移到Customer Journey Analytics准备数据。 请查看以下页面获取更多信息：

* [从 Adobe Analytics 演变到 Customer Journey Analytics](/help/getting-started/aa-to-cja.md)

## 设置报表包以引入Adobe Experience Platform和Customer Journey Analytics

准备好数据后，您就可以开始配置报表包，以便在Adobe Experience Platform和Customer Journey Analytics中使用。

1. **为您希望在Adobe Experience Platform和Customer Journey Analytics中使用的每个报表包创建一个数据流。** 此 [Analytics源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hans) 是允许您 [创建连接](/help/connections/create-connection.md) （也称为数据流）在Adobe Analytics和Adobe Experience Platform之间。 您将使用源连接器为要在Adobe Experience Platform中使用的每个报告包创建一个数据流。 数据流创建报告包数据的副本，其中架构已转换为  [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=zh-Hans) 供Adobe Experience Platform应用程序(包括Customer Journey Analytics)使用。<p>通过源连接器配置了数据流的每个报表包都作为单独的数据集存储在Adobe Experience Platform数据湖中。 每个数据流将自动包含13个月的历史报表包数据，新数据将持续流入Adobe Experience Platform。 （请注意，从2023年4月26日开始，非生产沙盒中的回填限制为3个月。） 使用 Analytics Source Connector，您无需担心提前创建架构。系统会自动为您创建特定于 Adobe Analytics 的标准化架构。但是，Adobe Experience Platform [数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hans) tool可用于在数据存储在数据湖中并供Customer Journey Analytics使用之前增强此架构。 请注意，某些类型的数据会被源连接器过滤掉，不会出现在Adobe Experience Platform数据湖的数据集中。 其他行可能会在数据湖和Customer Journey Analytics之间被过滤掉。 参见 [将Adobe Analytics数据与Customer Journey Analytics数据进行比较](/help/troubleshooting/compare.md) 了解更多详细信息。
1. **使用数据准备可帮助您在Customer Journey Analytics中组合报告包。** 数据准备可用于多种类型的数据转换，Adobe Analytics数据的一个常见用途是解决多个报表包之间的prop和/或eVar映射差异，以便报表包可以轻松地在Customer Journey Analytics中合并。 请参阅[将报告包与不同架构相结合](/help/use-cases/aa-data/combine-report-suites.md)，了解更多详细信息。
1. 根据需要&#x200B;**启用跨渠道分析**。在Customer Journey Analytics中组合多个数据集时，跨渠道分析的身份拼接功能可以帮助将不同的ID命名空间解析为单个拼接ID，以实现跨设备和渠道的单一客户视图。 请参阅[跨渠道分析概述](/help/cca/overview.md)，了解详细信息。
1. **创建一个或多个Customer Journey Analytics连接。** 一旦您的报表包的数据集在Adobe Experience Platform数据湖中可用，您就可以创建一个或多个 [Customer Journey Analytics连接](/help/connections/overview.md) 将这些数据集导入Customer Journey Analytics。 在一个连接中，报告包数据可以与其他类型的数据相结合，使您能够创建真正的跨渠道客户体验视图。
1. **创建一个或多个Customer Journey Analytics数据视图。** A [数据视图](/help/data-views/data-views.md) 是特定于Customer Journey Analytics的容器，通过它，可决定如何解释来自Customer Journey Analytics连接的数据。 数据视图具有许多强大的[配置选项](/help/data-views/create-dataview.md)，用于自定义在 [Analysis Workspace](/help/analysis-workspace/home.md) 中呈现给用户的数据。

## 比较 Customer Journey Analytics 和 Adobe Analytics

Customer Journey Analytics 和 Adobe Analytics 有许多相似之处。例如，Customer Journey Analytics和Adobe Analytics都提供Analysis Workspace的强大功能以进行自由形式的思维速度分析。 但是，由于Customer Journey Analytics是Adobe Experience Platform中的一个应用程序，并利用Adobe Experience Platform进行数据摄取，因此Customer Journey Analytics和Adobe Analytics在许多重要方面有所不同。 以下文章有助于理解这些差异：

* [将Adobe Analytics数据与Customer Journey Analytics数据进行比较](/help/troubleshooting/compare.md)
* [Customer Journey Analytics 功能支持](/help/getting-started/aa-vs-cja/cja-aa.md)
* [比较通过 Analytics Source Connector 传递的 Analytics 数据的术语](/help/getting-started/aa-vs-cja/terminology.md)
* [跨Adobe Analytics和Customer Journey Analytics报表功能比较数据处理](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [虚拟报告包、数据视图、Adobe Experience Platform沙盒和Analytics Source Connector](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [处理规则、VISTA 和分类与数据准备](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID、ECID、AACUSTOMID 和 Analytics Source Connector](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
