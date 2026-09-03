---
title: Customer Journey Analytics 快速入门指南
description: 了解实施 Customer Journey Analytics 所需的先决条件和工作流。
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
TQID: https://experienceleague.adobe.com/qYz2G6gugkSMH-BITMExxjkheGHrYFvDTZbR66c-Rr0
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 837
ht-degree: 85%

---

# 快速入门指南

要实施 Customer Journey Analytics，您需要遵循下述工作流。 一些初始任务在 Adobe Experience Platform 中执行，一些则在 Customer Journey Analytics 中执行。

## 先决条件

Customer Journey Analytics 适用以下客户：

* 已配置 [Adobe Experience Platform](https://www.adobe.com/cn/experience-platform.html) 的客户，以及
* 已购买 Customer Journey Analytics SKU 的客户

## 工作流

| 任务 | 详细信息 |
| --- | --- |
| **步骤 1：如果您要从 Adobe Analytics 升级到 Customer Journey Analytics：选择一个升级路径，并将数据发送到 Adobe Experience Platform** | 从 Adobe Analytics 升级到 Customer Journey Analytics 时，有多种可用的路径。 每种可能的升级路径都有其优点和缺点，适合一个组织的路径可能对另一个组织来说并不适用。 <p>要开始从 Adobe Analytics 升级到 Customer Journey Analytics，请执行以下操作之一：</p><ul><li>按照 Adobe 推荐的升级路径进行操作。 有关详细信息，请参阅[从 Adobe Analytics 升级到 Customer Journey Analytics 时的推荐路径](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。</li><li>了解所有可用的升级路径并选择最适合您组织的路径。 有关详细信息，请参阅[开始升级到 Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)。</li></ul> |
| **步骤 2：将其他数据导入 Adobe Experience Platform** | 此步骤在 Adobe Experience Platform 中执行，包含若干子步骤：<ul><li>**步骤 2a：准备数据架构**：使用 [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/home.html?lang=zh-Hans) 标准化客户体验数据并[定义用于客户体验管理的架构](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hans)。</li><li>**步骤2b：基于架构创建数据集**： Platform中的数据由数据集组成，例如电子邮件数据集、CRM数据集、POS数据集、Adobe Analytics数据集等。每个数据集都由一个架构和批量数据组成。 您可以[在 Experience Platform 中创建数据集。](https://experienceleague.adobe.com/zh-hans/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=zh-Hans)</li><li>**步骤 2c：将数据摄取到 Experience Platform**：在此，您有多个选项。</li></ul> |
| **步骤 3：在 Platform 数据集与 Customer Journey Analytics 之间创建连接** | 通过创建连接，您可以将 Adobe Experience Platform 中的数据集集成到工作区中。 为了报告Experience Platform数据集，您必须首先在Experience Platform和Workspace中的数据集之间建立连接。<br>请参阅[创建或编辑连接](/help/connections/create-connection.md)。 |
| **步骤 4：创建数据视图** | 数据视图是数据的“筛选”视图。 您可以使用不同的访问超时、归因等设置为同一连接创建不同的数据视图。您可以为单个数据集创建多个数据视图。<br>请参阅[创建数据视图](/help/data-views/create-dataview.md)。 |
| **步骤 5：移植报告 API 用法**</br>&#x200B;仅适用于从 Adobe Analytics 迁移时 | Customer Journey Analytics 报告 API 采用相同的格式，但使用的是不同的端点。 将报告 API 用法从 Adobe Analytics 报告 API 移植到 Customer Journey Analytics 报告 API。 |
| **第 6 步：考虑数据馈送和 Data Warehouse 用例**</br>&#x200B;仅适用于从 Adobe Analytics 迁移的情况 | 确定如何使用 Customer Journey Analytics 中可用的导出选项，以便以最佳的方式复制您在 Adobe Analytics 中使用的数据馈送和 Data Warehouse 功能。<!-- link to docs Rob is creating --> |
| **步骤 7：迁移项目和组件**</br>&#x200B;仅适用于从 Adobe Analytics 迁移的情况 | Adobe Analytics 中的组件迁移区域允许您将项目及其相关的组件从 Adobe Analytics 迁移到 Customer Journey Analytics。<p>迁移过程包括：</p><ul><li>在 Customer Journey Analytics 中重新创建 Adobe Analytics 项目。</li><li>将来自 Adobe Analytics 报告包的维度和指标映射到 Customer Journey Analytics 数据视图中的维度和指标。</li></ul><p>在开始迁移之前，首先[准备将组件和项目从 Adobe Analytics 迁移到 Customer Journey Analytics](https://experienceleague.adobe.com/zh-hans/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)。</p><p>作出所有必要的准备后，即可[将组件和项目从 Adobe Analytics 迁移到 Customer Journey Analytics](https://experienceleague.adobe.com/zh-hans/docs/analytics/admin/admin-tools/component-migration/component-migration.html)。</p> |
| **步骤 8：规划用户加入** | 与 Adobe Analytics 一样，Analysis Workspace 是 Customer Journey Analytics 中面向用户的主要工具。 但是，用户需要注意在 Customer Journey Analytics 中使用 Analysis Workspace 时的一些关键差异。<p>您应该给予用户充足的时间（3 - 6 个月）来熟悉 Customer Journey Analytics 中 Analysis Workspace 的主要区别。</p><p>有关 Adobe Analytics 和 Customer Journey Analytics 之间的一些主要差异的信息，请参阅 [Adobe Analytics 用户指南](/help/getting-started/aa-to-cja-user.md)。</p> |
| **步骤 9：在工作区中报告跨渠道数据** | 创建连接和数据视图后，使用Analysis Workspace的强大功能和灵活性分析导入的数据。<br>请参阅[执行基本分析](/help/analysis-workspace/perform-basic-analysis.md)和[执行高级分析](/help/analysis-workspace/perform-adv-analysis.md)。 |

## 快速入门指南

[数据摄取](../data-ingestion/data-ingestion.md)部分提供了有关上述工作流的快速入门指南。 这些快速入门指南说明了如何在 Adobe Experience Platform 中摄取各种来源（包括 Adobe Analytics）中的数据，然后在 Customer Journey Analytics 中使用这些数据。
