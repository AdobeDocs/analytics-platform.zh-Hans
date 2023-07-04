---
title: Customer Journey Analytics 入门
description: 了解实施 Customer Journey Analytics 所需的先决条件和工作流。
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
source-git-commit: ff71d21235bd37da73c0b6c628c395da6cda7659
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 84%

---

# Customer Journey Analytics 入门

要实施 Customer Journey Analytics，您需要遵循下述工作流程。一些初始任务在 Adobe Experience Platform 中执行，一些则在 Customer Journey Analytics 中执行。

## 先决条件

Customer Journey Analytics 适用以下客户：

* 已配置 [Adobe Experience Platform](https://www.adobe.com/cn/experience-platform.html) 的客户，以及
* 已购买 Customer Journey Analytics SKU 的客户

## 工作流程

| 任务 | 详细信息 |
| --- | --- |
| **步骤1：如果您要从Adobe Analytics迁移到Customer Journey Analytics，请了解如何操作。** | 请参阅[在 Customer Journey Analytics 中使用 Adobe Analytics 报告包数据](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)和[从传统 Adobe Analytics 中摄取和使用数据](../data-ingestion/analytics.md)。 |
| **步骤 2：将其他数据导入 Adobe Experience Platform** | 此步骤在 Adobe Experience Platform 中执行，包含若干子步骤：<ul><li>**步骤 2a：准备数据架构**：使用 [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hans) 标准化客户体验数据并[定义用于客户体验管理的架构](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hans)。</li><li>**步骤2b：基于架构创建数据集**：Platform中的数据由数据集组成，例如电子邮件数据集、CRM数据集、POS数据集、Adobe Analytics数据集等。 每个数据集都由一个架构和批量数据组成。 您可以 [在Experience Platform中创建数据集](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=zh-Hans).</li><li>**步骤 2c：将数据摄取到 Experience Platform**：在此，您有多个选项。</li></ul> |
| **步骤 3：在 Platform 数据集与 Customer Journey Analytics 之间创建连接** | 通过创建连接，您可以将 Adobe Experience Platform 中的数据集集成到工作区中。要报告 Experience Platform 数据集，您必须首先在 Experience Platform 和工作区中的数据集之间建立连接。<br>请参阅[创建连接](/help/connections/create-connection.md)。 |
| **步骤 4：创建数据视图** | 数据视图是数据的“过滤”视图。您可以使用不同的访问超时、归因等设置为同一连接创建不同的数据视图。您可以为单个数据集创建多个视图。<br>请参阅[创建数据视图](/help/data-views/create-dataview.md)。 |
| **步骤 5：在工作区中报告跨渠道数据** | 创建连接和数据视图后，利用 Analysis Workspace 的强大功能和灵活性分析导入的数据。<br>请参阅[执行基本分析](/help/analysis-workspace/perform-basic-analysis.md)和[执行高级分析](/help/analysis-workspace/perform-adv-analysis.md)。 |

## 快速入门指南

[数据摄取](../data-ingestion/data-ingestion.md)部分提供了有关上述工作流程的快速入门指南。这些快速入门指南说明了如何在 Adobe Experience Platform 中摄取各种来源（包括 Adobe Analytics）中的数据，然后在 Customer Journey Analytics 中使用这些数据。
