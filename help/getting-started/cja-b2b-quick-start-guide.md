---
title: Customer Journey Analytics B2B快速入门指南
description: Customer Journey Analytics的B2B edition快速入门指南。
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
source-git-commit: c021dc012f74126c6d0af5cd4ffdf908dd5c696a
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 22%

---

# B2B edition快速入门指南

{{draft-b2b}}

要实施Customer Journey Analytics B2B edition，请确保您首先了解B2B特定的概念和功能。 此外，您应该熟悉实施Customer Journey Analytics的传统工作流程。

本文档重点介绍特定于实施Customer Journey Analytics的工作流。

## 先决条件

要实施Customer Journey Analytics B2B edition，必须满足以下先决条件：

* 您在Customer Journey Analytics中拥有必要的[访问控制和权限](/help/technotes/access-control.md)才能执行管理任务。
* 您已购买Customer Journey Analytics B2B edition附加组件包。


## 工作流

| 任务 | 详细信息 |
| --- | --- |
| **步骤1：将B2B数据获取到Experience Platform** | 此步骤在Experience Platform中执行，包含几个子步骤：<ul><li>**步骤1a：准备数据架构**：使用[Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)标准化B2B数据并[为您的B2B数据定义架构](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/schemas/b2b)。</li><li>**步骤1b：基于架构创建数据集**： Platform中的数据由数据集组成，例如帐户数据、商机数据、购买团体数据、促销活动数据、营销列表数据、电子邮件数据集、CRM数据集、POS数据集等。 每个数据集都由一个架构和批量数据组成。您可以[在 Experience Platform 中创建数据集。](https://experienceleague.adobe.com/cn/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=zh-Hans)</li><li>**步骤1c：将数据摄取到Experience Platform**：您有[多个选项](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/ingestion/home)。</li></ul> |
| **步骤 2：在 Platform 数据集与 Customer Journey Analytics 之间创建连接** | 通过创建连接，您可以将 Adobe Experience Platform 中的数据集集成到工作区中。为了报告Experience Platform数据集，您必须首先在Experience Platform和Workspace中的数据集之间建立连接。 配置与B2B edition的连接时，您还有其他选项。 <br>请参阅[创建或编辑连接](/help/connections/create-connection.md)。 |
| **步骤 3：创建数据视图** | 数据视图是数据的&#x200B;*过滤*&#x200B;视图。 您可以使用不同的访问超时、归因等设置为同一连接创建不同的数据视图。 您可以为单个数据集创建多个视图。在使用B2B edition配置数据视图时，您还有其他选项。<br>请参阅[创建数据视图](/help/data-views/create-dataview.md)。 |
| **步骤 4：在工作区中报告跨渠道数据** | 创建连接和数据视图后，使用Analysis Workspace的强大功能和灵活性分析您引入的B2B数据。<br>请参阅[执行基本分析](/help/analysis-workspace/perform-basic-analysis.md)和[执行高级分析](/help/analysis-workspace/perform-adv-analysis.md)。 |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->