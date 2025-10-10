---
title: 将Analytics Source Connector数据与Adobe Analytics进行比较
description: 了解在Adobe Analytics和Customer Journey Analytics中查看类似报表时的数据差异。
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: 查询服务；查询服务；sql 语法
source-git-commit: d96404479aabe6020566e693245879b5ad4fad9c
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 4%

---

# 将Analytics Source Connector数据与Adobe Analytics进行比较

随着您的组织采用Customer Journey Analytics，可能会注意到Adobe Analytics与Customer Journey Analytics之间的数据差异。 这些差异是正常的，并且可能由于多种原因出现。 Customer Journey Analytics旨在允许您改进Adobe Analytics对数据的一些限制。 这种灵活性可能会导致Customer Journey Analytics解读数据的方式存在差异。 通过本文了解Customer Journey Analytics和Adobe Analytics处理数据的方式中的潜在差异。

本页假设您使用[Analytics源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)将Adobe Analytics数据摄取到Adobe Experience Platform，然后在Customer Journey Analytics中创建了[连接](/help/connections/overview.md)和[数据视图](/help/data-views/data-views.md)。

![数据从 Adobe Analytics 通过数据连接器流向 Adobe Experience Platform，然后使用 CJA 连接流向 Customer Journey Analytics](assets/compare.png)。

请注意以下可能导致报表平台间数据存在差异的原因：

* **不同的数据集或报表包**：确保Adobe Analytics中的报表包与Source Connector从中派生数据的报表包相同。
* **日历设置**： Adobe Analytics中的报表包包含您可以配置的时区和其他日历设置。 同样，Customer Journey Analytics中的数据视图具有一个您可以控制的单独设置。 如果需要奇偶校验，请确保这些设置在各产品之间匹配。
* **其他数据集**： Customer Journey Analytics提供在单个连接中包含多个数据集的功能。 这些差异包括其他事件数据集、配置文件数据集或查找数据集。 此功能是Adobe Analytics与Customer Journey Analytics之间的关键区别点，它允许insight处理跨渠道数据。
* **拼接的数据集**： Adobe提供在两个数据集之间分析人员ID的功能，从而生成包含拼接ID的新数据集。 这些[拼接数据集](/help/stitching/overview.md)包含的数据超出Adobe Analytics报表包提供的范围。
* **数据源**： Customer Journey Analytics不包含上载到Adobe Analytics报表包的任何类型的[数据源](https://experienceleague.adobe.com/en/docs/analytics/import/data-sources/overview)，包括概要数据源或交易ID数据源。
* **Dimension和量度设置**：在数据视图中，每个维度和量度都包含其自己的设置，贵组织可以更改这些设置。 这些更改在运行报告时应用，因此具有追溯性。 Adobe Analytics中的Dimension和量度设置可更改数据收集方式，以便今后应用这些更改。 如果更改了任一产品中的组件设置，则它们可能会创建报表差异。 如果侧重于特定维度，请确保归因和持久性设置在Adobe Analytics和Customer Journey Analytics之间匹配。

  >[!TIP]
  >
  >Adobe强烈建议Adobe Analytics中的维度使用“[!UICONTROL 最近（最后一个）]”的分配。 此分配设置在Customer Journey Analytics中允许更大的归因灵活性。

* **访问定义**：除了单个维度和量度设置外，数据视图本身还包含从根本上改变访客数据解释方式的设置。 例如，您可以将区段应用到整个数据视图(类似于Adobe Analytics中的[虚拟报表包](https://experienceleague.adobe.com/en/docs/analytics/components/virtual-report-suites/vrs-about))。 您还可以更改访问持续时间的定义，或在任何所需事件上自动开始新访问。 这些设置中的任何一个都会对Customer Journey Analytics和Adobe Analytics之间的报表差异产生显着影响。

## 检查产品之间的记录计数

如果以上所有设置看起来相似，并且您想至少验证产品之间的记录数，则可以使用以下步骤：

1. 在Adobe Experience Platform [查询服务](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/query/home)中，运行以下按时间戳的总记录数查询：

   ```sql
   SELECT
     Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) AS Day,
     Count(_id) AS Records
   FROM  {dataset}
   WHERE   timestamp >= from_utc_timestamp('{fromDate}','UTC')
     AND timestamp < from_utc_timestamp('{toDate}','UTC')
     AND timestamp IS NOT NULL
     AND enduserids._experience.aaid.id IS NOT NULL
   GROUP BY Day
   ORDER BY Day;
   ```

1. 在Adobe Analytics [数据馈送](https://experienceleague.adobe.com/zh-hans/docs/analytics/export/analytics-data-feed/data-feed-overview)中，生成所需日期范围的馈送文件。 计算每个文件中的行数，识别并排除以下行：

   * `exclude_hit`不是`0`(两个产品中从Analysis Workspace中排除的数据)
   * `hit_source`是`0`、`3`、`5`、`7`、`8`、`9`或`10`（数据源和其他非点击数据）
   * `page_event`是`53`或`63`（流媒体保持活动状态点击）

   符合上述任一条件的行将从Analytics Source Connector摄取工作流中排除，因此在对数据馈送行计数时也应排除。

1. 查询服务中的总记录数应与同一时间段内数据馈送中的行数匹配。
