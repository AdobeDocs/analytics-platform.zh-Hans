---
title: 数据导出用例
description: 了解用于Customer Journey Analytics的各种数据导出用例
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
source-git-commit: 40e4c3bd8f3c37e9a6143200b85ffe0ac4bcb2ca
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 0%

---

# 数据导出用例

本节提供了数据导出用例，以及如何通过Customer Journey Analytics或Experience Platform的一项或多项功能实施这些用例。 在单独的文章中进一步详细介绍了每个功能。

## 简介

Adobe Analytics和Customer Journey Analytics之间的独特区别之一与归因和会话化数据的处理有关。 请参阅 [跨Adobe Analytics和Customer Journey Analytics比较数据处理](/help/getting-started/aa-vs-cja/data-processing-comparisons.md) 以了解更多信息。

### Adobe Analytics：收集时间归因和会话化。

在Adobe Analytics中，所有事件均按设备ID实时和顺序处理，允许Adobe在收集时生成、存储和导出具有持久值或属性值的点击流数据，包括：

* Dimension持久性（例如，90天后过期的促销活动跟踪代码）。
* 访问次数和会话流程。
* Dimension值，通过处理和VISTA规则计算。

这会影响从Adobe Analytics导出数据：

* 初始收集后，数据处理是静态的。
* 数据馈送中包含“post”列，这些列反映了收集时间处理。


### Customer Journey Analytics：查询时间归因和会话流程

在Customer Journey Analytics中，事件未按顺序收集，并且使用了人员ID而不是设备ID，从而允许Customer Journey Analytics在报告时更新归因和会话处理。 此类型的数据收集引入了灵活性，例如：

* 拼接可以 _重播_ 每日或每周发送数据，将匿名事件与已知事件关联。 请参阅 [拼接](../../stitching/overview.md) 以了解更多信息。
* 会话和保留值每次都会更改
   * 收集新数据或
   * 拼接可将事件添加到人员的历史记录中。

报表时间处理会影响从Customer Journey Analytics导出数据。 包含持久值的导出与Customer Journey Analytics报表不匹配，并且值会随着时间的推移而逐渐消失。

为了保持量度一致性，建议在Customer Journey Analytics中使用新功能。 通常，Experience Platform和Customer Journey Analytics数据导出功能超过了Adobe Analytics的数据馈送功能。 Experience Platform和Customer Journey Analytics可提供：

* 新数据源和处理需要导出数据

   * 包括非数字数据源，
   * 根据业务规则应用自定义归因和会话化，以及
   * 通过拼合保持客户历程更新。

* 实现量身定制的数据导出用例

   * 将数据导出到您需要的地方，包括Business Intelligence(BI)工具和云目标，
   * 通过BI工具集成，保持数据与Analysis Workspace同步，
   * 无需在自己的系统中复制处理逻辑，
   * 新增对计算量度、派生字段和分段以及以下各项的支持

* 按设计考虑安全和数据治理

   * 按用户和目标监控所有数据导出，
   * 设置可用于导出的数据的限制，以及
   * 设置传送问题警报和计划传送时间范围限制。


## 用例和功能

通常，数据导出支持许多用例。 在所需数据以及如何访问和导出该数据方面，每个用例均不同。 Experience Platform和Customer Journey Analytics提供了许多功能，这些功能可以独立使用或组合使用来解决各种用例。 下表概述了已确定的数据导出用例以及实施这些用例的Experience Platform和Customer Journey Analytics功能。

| 数据导出用例 | Experience Platform和Customer Journey Analytics功能 |
|---|---|
| **数据备份**<br/>&#x200B;出于法规遵从性或管理法规目的，保留数字数据的完整拷贝。 | **Experience Platform**： [**导出数据集**](export-datasets.md)<br/>&#x200B;按计划或临时将Experience Platform收集的数据直接导出到云目标。<br/>*目前有限版本，预计2024年6月针对Customer Journey Analytics客户的完整版本。* |
| **数据验证**<br/>&#x200B;评估点击流数据的数据收集准确性。 | **Experience Platform**： [**查询服务(数据Distiller)和导出数据集**](queryservice-export-datasets.md)<br/> Interactive PostgreSQL接口使用您喜爱的SQL工具执行临时SQL查询，以验证数据集中的数据。<br/><br/>**Customer Journey Analytics**： [**导出完整表**](export-full-table.md)<br/>&#x200B;验证应用了归因和会话化的CJA中已处理的数据。 |
| **数据湖、Data Warehouse或BI工具**<br/>&#x200B;将数字数据纳入您自己的BI工具或数据湖以与其他数据集一起使用。 | **Customer Journey Analytics**： [**BI扩展**](bi-extension.md)<br/>&#x200B;将Customer Journey Analytics处理的指标添加到数据可视化工具(如Power BI)，并将其与自定义报表的附加数据相结合&#x200B;<br/><br/>**Experience Platform**： [**查询服务(数据Distiller)和导出数据集**](queryservice-export-datasets.md)<br>&#x200B;使用SQL生成要传送到云目标的自定义点击流数据。 |
| **为AI/ML做好准备**<br/>&#x200B;使用Customer Journey Analytics数据增强人工智能/机器学习模型和任务。 | **Customer Journey Analytics**： [**导出完整表**](export-full-table.md)<br/>&#x200B;一次性或循环将Customer Journey Analytics处理的维度和量度导出到Cloud Destinations，包括计算量度和分段。<br/><br/>**Experience Platform**： [**查询服务(数据Distiller)和导出数据集**](queryservice-export-datasets.md)<br/>&#x200B;使用SQL生成自定义点击流数据以丰富AI/ML模型。 |
