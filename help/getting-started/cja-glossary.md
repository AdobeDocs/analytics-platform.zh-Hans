---
title: Customer Journey Analytics 术语表
description: Customer Journey Analytics 术语表。
translation-type: tm+mt
source-git-commit: 307bfae11f44d088aa8d004f1f7ddd17375f60fc
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 87%

---


# Customer Journey Analytics 术语表

部分 Customer Journey Analytics 术语与 Adobe Analytics 中传统使用的术语有所不同：

| Customer Journey Analytics 新术语 | Adobe Analytics 术语 | 描述 |
|---|---|---|
| 查找数据集 | 分类 | 使用查找功能从具有1对1关系的键／匹配键的指定数据集(在事件数据集中)检索值。 例如，您可以指定“tracking_code”作为与事件数据集中的“tracking_code”匹配的键。 |
| 用户档案数据集 | 客户属性 | 如果您在客户关系管理 (CRM) 数据库中捕获到企业客户数据，则可以将该数据上传到 Adobe Experience Platform 中的用户档案数据集。当您在 Customer Journey Analytics 中创建与该数据集的连接并创建数据视图后，可在工作区中利用该数据。 |
| 登录公司 | Experience Cloud 组织 | 请参阅[组织和帐户关联](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/manage-users-and-products/organizations.html#topic_C31CB834F109465A82ED57FF0563B3F1)。 |
| 不适用 | 报表包 | 传统 Adobe Analytics 中的报表包不再存在。实际上，您需要从与之创建连接的 Platform 数据集创建（虚拟）[数据视图](/help/data-views/create-dataview.md)。 |
| 过滤器 | 区段 | 现在，区段更改为“过滤器”。Customer Journey Analytics 中的过滤器，其行为与“区段”是相同的。只是术语发生了更改。 |
| 数据视图 | 虚拟报表包 | 在 Adobe Analytics 中，虚拟报表包是父报表包的分段视图。虚拟报表包与 CJA 中的数据视图的主要区别在于，虚拟报表包是“基础”或“父”报表包的子集，因此它会继承父报表包的某些设置。由于父/基础报表包不再存在，您可以使用自已的设置来定义数据视图。 |

## Adobe Experience Platform 术语表

Adobe Experience Platform 实现了整个企业内的数据和内容的标准化，从而为实时消费者用户档案提供强大动力，支持数据科学，加速内容处理速度以推动客户历程中的体验个性化。有关更多信息，请参阅 [Adobe Experience Platform 术语表](https://www.adobe.io/apis/experienceplatform/home/services/acp-glossary.html)。
