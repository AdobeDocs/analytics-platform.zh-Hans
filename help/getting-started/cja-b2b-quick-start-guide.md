---
title: Customer Journey Analytics B2B 快速入门指南
description: Customer Journey Analytics B2B Edition 快速入门指南。
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
TQID: https://experienceleague.adobe.com/SjixkRCOmeUYuhZCVO7-7tLHalpnXO6QCVE1BiG9h2E
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: a67cb189-a535-41f6-afa2-448f39c4759f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9c87ce4fb30c7d1d66ce88174443369ef44a7377
workflow-type: tm+mt
source-wordcount: 499
ht-degree: 77%

---

# B2B Edition 快速入门指南

要实施 Customer Journey Analytics B2B Edition，请确保您首先了解 B2B 特定的概念和特点。 此外，您应该熟悉实施 Customer Journey Analytics 的传统工作流程。

本文档重点介绍实施 Customer Journey Analytics 特有的工作流程。

## 先决条件

要实施 Customer Journey Analytics B2B Edition，必须满足以下先决条件：

* 您必须拥有必要的[访问控制和权限](/help/technotes/access-control.md)，以在 Customer Journey Analytics 中提供管理任务。
* 您已购买了 Customer Journey Analytics B2B Edition 附加组件包。


## 工作流

| 任务 | 详细信息 |
| --- | --- |
| **步骤 1：将 B2B 数据导入 Experience Platform** | 此步骤在 Experience Platform 中执行，包含若干子步骤：<ul><li>**步骤 1a：准备数据架构**：使用 [Adobe Experience 数据模型 (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) 将 B2B 数据标准化，并为 B2B 数据[定义架构](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/rtcdp/schemas/b2b)。<br/>您可以将架构基于Real-time CDP B2B edition[&#128279;](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/rtcdp/schemas/b2b)中提供的标准类，也可以使用您自己的自定义类和架构。 [用例](/help/use-cases/b2b/b2b-edition/use-cases-overview.md)文章使用Real-time CDP B2B edition类和架构，但是，使用标准类和架构不需要Real-time CDP B2B edition许可证。</li><li>**步骤 1b：根据架构创建数据集**：平台中的数据由数据集组成，例如帐户数据、机会数据、购买群组数据、营销活动数据、营销列表数据、电子邮件数据集、CRM 数据集、POS 数据集等。 每个数据集都由一个架构和批量数据组成。 您可以[在 Experience Platform 中创建数据集。](https://experienceleague.adobe.com/zh-hans/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=zh-Hans)</li><li>**步骤 1c：将数据摄取到 Experience Platform**：您有[多个选项](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/ingestion/home)。</li></ul> |
| **步骤 2：在 Platform 数据集与 Customer Journey Analytics 之间创建连接** | 通过创建连接，您可以将 Adobe Experience Platform 中的数据集集成到工作区中。 要报告 Experience Platform 数据集，您必须首先在 Experience Platform 和工作区中的数据集之间建立连接。 配置与 B2B Edition 的连接时，您有更多选项。 <br>请参阅[创建或编辑连接](/help/connections/create-connection.md)。 |
| **步骤 3：创建数据视图** | 数据视图是数据的&#x200B;*筛选*&#x200B;视图。 您可以使用不同的访问超时、归因等设置为同一个连接创建不同的数据视图。 您可以为单个数据集创建多个数据视图。 当您使用B2B edition配置数据视图时，还有其他选项。<br>请参阅[创建数据视图](/help/data-views/create-dataview.md)。 |
| **步骤 4：在工作区中报告跨渠道数据** | 创建连接和数据视图后，使用Analysis Workspace的强大功能和灵活性分析您引入的B2B数据。<br>请参阅[执行基本分析](/help/analysis-workspace/perform-basic-analysis.md)和[执行高级分析](/help/analysis-workspace/perform-adv-analysis.md)。 |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->