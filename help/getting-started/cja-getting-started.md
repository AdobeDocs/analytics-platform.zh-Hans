---
title: Customer Journey Analytics 入门
description: Customer Journey Analytics 入门。
translation-type: tm+mt
source-git-commit: e30bbae59e11bbf93668ffe072508727f6efdd51
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 71%

---


# Customer Journey Analytics 入门

要实施 Customer Journey Analytics，您需要遵循下述工作流程。一些初始任务在 Adobe Experience Platform 中执行，一些则在 Customer Journey Analytics 中执行。

## 先决条件

Customer Journey Analytics 适用以下客户：

* Adobe Analytics [Select、Prime 或 Ultimate](https://www.adobe.com/cn/analytics/compare-adobe-analytics-packages.html) 客户，以及
* 已配置 [Adobe Experience Platform](https://www.adobe.com/cn/experience-platform.html) 的客户，以及
* 已购买 Customer Journey Analytics SKU 的客户

## 工作流

| 任务 | 详细信息 |
|---|---|---|
| **步骤 1：将数据导入 Adobe Experience Platform** | 此步骤在Adobe Experience Platform中执行，涉及几个子步骤：<br>**步骤1a: 准备数据模式&#x200B;**: 使用[Adobe体验数据模型(XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html)，实现客户体验数据标准化，[为客户体](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)验管理定义模式。<br>**步骤1b: 根据模式创建数据集**: 平台中的数据由数据集组成，如电子邮件数据集、CRM数据集、POS数据集、Adobe Analytics数据集等。 每个数据集都由一个架构和批量数据组成。您可以在 [Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md) 中创建一个数据集。<br>**步骤1c: 将数据引入Experience Platform **: 使用现成的Adobe Analytics Platform Connector将传统的Adobe Analytics数据引入Platform。 您可以为每个报表包创建一个源连接。请参阅 Adobe Experience Platform 文档中的[创建与 Adobe Analytics 的源连接](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md)。创建连接后，将自动创建目标架构和数据集，以包含传入数据。此外，还会进行数据回填，并摄取至多 13 个月的历史数据。完成初始摄取后，您可以继续执行`Step 2`以便在此 Analytics 数据集与 Customer Journey Analytics 之间创建连接。<br>或者，您也可以通过批处理摄取、流[摄取](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/ingest_architectural_overview/ingest_architectural_overview.md),[或通过其](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/streaming_ingest_overview.md)他源连接器摄[取其他数据类型](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/acp-connectors-overview.md)。 |
| **步骤 2：在 Platform 数据集与 Customer Journey Analytics 之间创建连接** | 通过连接，您可以将Adobe Experience Platform中的数据集集成到Workspace中。 为了报告Experience Platform数据集，您首先必须在Experience Platform和Workspace中的数据集之间建立连接。<br>请参阅[创建连接](/help/connections/create-connection.md)。 |
| **步骤 3：创建数据视图** | 数据视图是数据的“筛选”视图。 您可以使用不同的访问超时、归因等设置为同一连接创建不同的数据视图。您可以为单个数据集创建多个视图。<br>请参阅[创建数据视图](/help/data-views/create-dataview.md)。 |
| **步骤 4：在 Workspace 中报告跨渠道数据** | 创建连接和数据视图后，利用 Analysis Workspace 的强大功能和灵活性分析导入的数据。<br>请参阅[执行基本分析](/help/projects/perform-basic-analysis.md)和[执行高级分析](/help/projects/perform-adv-analysis.md)。 |
