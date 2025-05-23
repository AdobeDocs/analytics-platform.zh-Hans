---
title: 与 Adobe Analytics 数据进行比较
description: 了解如何比较 Adobe Analytics 数据和 Customer Journey Analytics 中的数据
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: 查询服务；查询服务；sql 语法
source-git-commit: 90d1c51c11f0ab4d7d61b8e115efa8257a985446
workflow-type: ht
source-wordcount: '831'
ht-degree: 100%

---

# 与 Adobe Analytics 数据进行比较

当您的组织采用 Customer Journey Analytics 时，您可能会注意到 Adobe Analytics 和 Customer Journey Analytics 之间的数据存在一些差异。这是正常情况，并且可能由于若干原因出现这种情况。Customer Journey Analytics 旨在使您可改善对于您在 AA 中的数据存在的某些限制。但是，可能会出现意外和非预期的差异。本文旨在帮助您诊断和解决这些差异，以便您和您的团队可以使用 Customer Journey Analytics，而不受数据完整性问题的影响。

假设您通过 [Analytics 源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans)将 Adobe Analytics 数据导入 Adobe Experience Platform，然后使用此数据集创建了 Customer Journey Analytics 连接。

![数据从 Adobe Analytics 通过数据连接器流向 Adobe Experience Platform，然后使用 CJA 连接流向 Customer Journey Analytics](assets/compare.png)。

接下来，您创建了一个数据视图，随后在 Customer Journey Analytics 上制作此数据的报告时，您注意到与 Adobe Analytics 中的报告结果存在差异。

将原始 Adobe Analytics 数据与 Customer Journey Analytics 中的现有 Adobe Analytics 数据进行比较所要遵循的步骤如下。

## 先决条件

* 确保 Adobe Experience Platform 中的 Analytics 数据集包含您正在调查的日期范围的数据。

* 确保您在 Analytics 中选择的报表包与引入到 Adobe Experience Platform 中的报表包一致。

## 步骤 1：在 Adobe Analytics 中运行发生次数指标

[发生次数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=zh-Hans)指标显示设置或持久化某个给定维度所经历的点击次数。

1. 在“Analytics”>“[!UICONTROL 工作区]”中，将要报告的日期范围作为一个维度拖入到一个[!UICONTROL 自由格式]表格中。

1. [!UICONTROL 发生次数]指标将自动应用于该日期范围。

1. 保存此项目，以使您可在比较中使用它。

## 步骤 2：将结果与 Customer Journey Analytics 中的[!UICONTROL 按时间戳的总记录数]进行比较

现在比较 Analytics 中的[!UICONTROL 发生次数]与 Customer Journey Analytics 中的“按时间戳的总记录数”。

只要 Analytics 源连接器未丢弃任何记录，则“按时间戳的总记录数”应与“发生次数”一致——请参见下节。

>[!NOTE]
>
>这仅适用于常规中间值数据集，不适用于拼合的数据集（通过 [Stitching](/help/stitching/overview.md)）。请注意，将在 Customer Journey Analytics 中使用的人员 ID 考虑在内对于使这一比较发挥作用至关重要。可能并非总是很容易在 Adobe Analytics 中复制该内容，尤其是在已启用 Stitching 的情况下。

1. 在 Adobe Experience Platform [查询服务](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html?lang=zh-Hans)中，运行以下的[!UICONTROL 按时间戳的总记录数]查询：

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

1. [分析数据馈送](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hans)，从原始数据中识别某些行是否已被分析源连接器过滤掉。

   [分析源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans)可能在转换到 XDM 模式期间过滤某些行。整个行不适合进行转换的原因可能有多种。如果以下任何分析字段具有这些值，则将过滤掉整个行。

   | Analytics 字段 | 导致行丢弃的值 |
   | --- | --- |
   | Opt_out | y, Y |
   | In_data_only | 不为 0 |
   | Exclude_hit | 不为 0 |
   | Bot_id | 不为 0 |
   | Hit_source | 0, 3, 5, 7, 8, 9, 10 |
   | Page_event | 53, 63 |

   有关 hit\_source 详细信息，请参阅：[数据列参考](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hans)。有关 page\_event 详细信息，请参阅：[页面事件查找](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-page-event.html?lang=zh-Hans)。

1. 如果连接器过滤某些行，则将从[!UICONTROL 发生次数]量度中去除这些行。得到的数字应与 Adobe Experience Platform 数据集中的事件数一致。

## 为什么在从 Adobe Experience Platform 引入数据期间可能会过滤或跳过一些记录

Customer Journey Analytics [连接](/help/connections/create-connection.md)允许您根据数据集中的通用人员 ID 将多个数据集汇集并合并在一起。在后端，我们应用重复数据删除：首先，基于时间戳针对事件数据集进行完全的外部连接或合并，然后基于人员 ID 对配置文件和查找数据集进行内部连接。

以下是从 Adobe Experience Platform 中引入数据时可能会跳过记录的一些原因。

* **缺少时间戳** – 如果事件数据集中缺少时间戳，则在引入期间将完全忽略或跳过这些记录。

* **缺少人员 ID** -（事件数据集和/或配置文件/查找数据集）缺少人员 ID 将导致忽略或跳过这些记录。原因是没有共同的 ID 或匹配的键可连接这些记录。

* **人员 ID 无效或过大** – 对于无效的 ID，系统将无法在要连接的数据集中找到有效的共同 ID。在某些情况下，人员 ID 列具有无效的人员 ID，例如“未定义”或“00000000”。每个月在某个事件中出现超过 100 万次的人员 ID（数字和字母的任意组合）无法归因到任何特定的用户或个人。它将被归为无效。无法将这些记录引入到系统中，并将导致引入和报表容易出错。
