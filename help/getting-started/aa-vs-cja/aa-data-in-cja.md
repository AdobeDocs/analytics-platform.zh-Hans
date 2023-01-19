---
title: 在 Customer Journey Analytics 中使用 Adobe Analytics 报告包
description: 如何配置 Adobe Analytics 报告包以引入 AEP 和 CJA
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: a9009c44a8e739add7fbcb9f9c31676d38af0094
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 100%

---

# 在 Customer Journey Analytics 中使用 Adobe Analytics 报告包

Adobe Analytics 客户可以使用 [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hans) 在 Adobe Experience Platform 和 Customer Journey Analytics 中轻松利用他们的报告包。以下讨论解释了如何这样做。

## 准备

当您准备开始在 AEP 和 CJA 中使用 Adobe Analytics 报告包时，您应该考虑采取几项措施准备数据以无缝迁移到 Customer Journey Analytics。请查看以下页面获取更多信息：

* [从 Adobe Analytics 演变到 Customer Journey Analytics](/help/getting-started/aa-to-cja.md)

## 设置报告包以引入 Adobe Experience Platform 和 CJA

准备好数据后，您就可以开始配置用于 AEP 和 CJA 的报告包。

1. **为您希望在 AEP 和 CJA 中使用的每个报告包创建一个数据流。**[Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hans) 是一款允许您在 Adobe Analytics 和 AEP 之间[创建连接](/help/connections/create-connection.md)（即数据流）的工具。您将使用源连接器为要在 AEP 中使用的每个报告包创建一个数据流。数据流创建报告包数据的副本，其中架构已转换为 [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=zh-Hans) 供 AEP 应用程序（包括 CJA）使用。通过源连接器配置了数据流的每个报告包都作为单独的数据集存储在 AEP 数据湖中。每个数据流将自动包含 13 个月的历史报告包数据，新数据将持续流入 AEP。使用 Analytics Source Connector，您无需担心提前创建架构。系统会自动为您创建特定于 Adobe Analytics 的标准化架构。但是，AEP 的[数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hans)工具可用于在数据存储在数据库中并提供给 CJA 之前增强此架构。请注意，某些类型的数据会被源连接器过滤掉，不会出现在 AEP 数据湖的数据集中。其他行可能会在数据库和 CJA 之间被过滤掉。请参见[将 Adobe Analytics 数据与 CJA 数据进行比较](/help/troubleshooting/compare.md)，了解更多详细信息。
1. **使用数据准备帮助您在 CJA 中组合报告包。**&#x200B;数据准备可用于多种类型的数据转换，Adobe Analytics 数据的一个常见用途是解决多个报告包之间的 prop 和/或 eVar 映射差异，以便报告包可以轻松地在 CJA 中组合。请参阅[将报告包与不同架构相结合](/help/use-cases/aa-data/combine-report-suites.md)，了解更多详细信息。
1. 根据需要&#x200B;**启用跨渠道分析**。在 CJA 中组合多个数据集时，跨渠道分析的身份拼接功能可以帮助将不同的 ID 命名空间解析为单个拼接 ID，以实现跨设备和渠道的单一客户视图。请参阅[跨渠道分析概述](/help/cca/overview.md)，了解详细信息。
1. **创建一个或多个 CJA 连接。**&#x200B;一旦您的报告包的数据集在 AEP 数据湖中可用，您就可以创建一个或多个 [CJA 连接](/help/connections/overview.md) 以将这些数据集导入 CJA。在一个连接中，报告包数据可以与其他类型的数据相结合，使您能够创建真正的跨渠道客户体验视图。
1. **创建一个或多个 CJA 数据视图。**[数据视图](/help/data-views/data-views.md)是 Customer Journey Analytics 专属的容器，通过它，可决定如何解释来自 CJA 连接的数据。 数据视图具有许多强大的[配置选项](/help/data-views/create-dataview.md)，用于自定义在 [Analysis Workspace](/help/analysis-workspace/home.md) 中呈现给用户的数据。

## 比较 Customer Journey Analytics 和 Adobe Analytics

Customer Journey Analytics 和 Adobe Analytics 有许多相似之处。例如，CJA 和 Adobe Analytics 都提供 Analysis Workspace 的强大功能以进行自由形式的思维速度分析。但是，由于 CJA 是 Adobe Experience Platform 中的一个应用程序并利用 AEP 进行数据摄取，因此 CJA 和 Adobe Analytics 在许多重要方面有所不同。以下文章有助于理解这些差异：

* [将 Adobe Analytics 数据与 CJA 数据进行比较](/help/troubleshooting/compare.md)
* [Customer Journey Analytics 功能支持](/help/getting-started/aa-vs-cja/cja-aa.md)
* [比较通过 Analytics Source Connector 传递的 Analytics 数据的术语](/help/getting-started/aa-vs-cja/terminology.md)
* [跨 Adobe Analytics 和 CJA 报告功能比较数据处理](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [虚拟报告包、数据视图、AEP 沙盒和 Analytics Source Connector ](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [处理规则、VISTA 和分类与数据准备](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID、ECID、AACUSTOMID 和 Analytics Source Connector](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
