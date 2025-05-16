---
title: Customer Journey Analytics B2B 快速入门指南
description: Customer Journey Analytics B2B Edition 快速入门指南。
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
source-git-commit: 326a82e93c0c8d57db224023ed5f3a7ab94a8997
workflow-type: ht
source-wordcount: '396'
ht-degree: 100%

---


# B2B Edition 快速入门指南

{{draft-b2b}}

要实施 Customer Journey Analytics B2B Edition，请确保您首先了解 B2B 特定的概念和特点。此外，您应该熟悉实施 Customer Journey Analytics 的传统工作流程。

本文档重点介绍实施 Customer Journey Analytics 特有的工作流程。

## 先决条件

要实施 Customer Journey Analytics B2B Edition，必须满足以下先决条件：

* 您必须拥有必要的[访问控制和权限](/help/technotes/access-control.md)，以在 Customer Journey Analytics 中提供管理任务。
* 您已购买了 Customer Journey Analytics B2B Edition 附加组件包。


## 工作流

| 任务 | 详细信息 |
| --- | --- |
| **步骤 1：将 B2B 数据导入 Experience Platform** | 此步骤在 Experience Platform 中执行，包含若干子步骤：<ul><li>**步骤 1a：准备数据架构**：使用 [Adobe Experience 数据模型 (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hans) 将 B2B 数据标准化，并为 B2B 数据[定义架构](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/rtcdp/schemas/b2b)。</li><li>**步骤 1b：根据架构创建数据集**：平台中的数据由数据集组成，例如帐户数据、机会数据、购买群组数据、营销活动数据、营销列表数据、电子邮件数据集、CRM 数据集、POS 数据集等。每个数据集都由一个架构和批量数据组成。您可以[在 Experience Platform 中创建数据集。](https://experienceleague.adobe.com/cn/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=zh-Hans)</li><li>**步骤 1c：将数据摄取到 Experience Platform**：您有[多个选项](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/ingestion/home)。</li></ul> |
| **步骤 2：在 Platform 数据集与 Customer Journey Analytics 之间创建连接** | 通过创建连接，您可以将 Adobe Experience Platform 中的数据集集成到工作区中。要报告 Experience Platform 数据集，您必须首先在 Experience Platform 和 Workspace 的数据集之间建立连接。配置与 B2B Edition 的连接时，您有更多选项。<br>请参阅[创建或编辑连接](/help/connections/create-connection.md)。 |
| **步骤 3：创建数据视图** | 数据视图是数据的&#x200B;*筛选*&#x200B;视图。您可以使用不同的访问超时、归因等设置为同一个连接创建不同的数据视图。您可以为单个数据集创建多个数据视图。如果您拥有 B2B Edition，配置数据视图时您有更多选项。<br>请参阅[创建数据视图](/help/data-views/create-dataview.md)。 |
| **步骤 4：在工作区中报告跨渠道数据** | 创建连接和数据视图后，使用 Analysis Workspace 的强大功能和灵活性分析导入的 B2B 数据。<br>请参阅[执行基本分析](/help/analysis-workspace/perform-basic-analysis.md)和[执行高级分析](/help/analysis-workspace/perform-adv-analysis.md)。 |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->