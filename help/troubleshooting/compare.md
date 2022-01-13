---
title: 将AA数据与CJA数据进行比较
description: 了解如何将Adobe Analytics数据与Customer Journey Analytics中的数据进行比较
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
source-git-commit: b0d29964c67d8a6a847a05dbe113b8213b346f9b
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 4%

---


# 比较Adobe Analytics数据与CJA数据

假设您通过Analytics源连接器将Adobe Analytics数据摄取到AEP，然后使用此数据集创建CJA连接。

![数据流](assets/compare.png)

接下来，您创建了一个数据视图，在随后在CJA上报告此数据时，您发现在Adobe Analytics中报告结果存在差异。

下面是一些要遵循的步骤，以比较原始Adobe Analytics数据与当前处于Customer Journey Analytics中的Adobe Analytics数据。

## 先决条件

* 确保AEP中的Analytics数据集包含您所调查日期范围的数据。

* 确保您在Analytics中选择的报表包与已摄取到Adobe Experience Platform中的报表包匹配。


## 步骤1:在Adobe Analytics中运行发生次数量度

的 [发生次数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en) 量度显示设置或保留给定维度的点击数。

1. 在Analytics >中 [!UICONTROL 工作区]，将要作为维度报告的日期范围拖动到 [!UICONTROL 自由格式] 表。

1. 的 [!UICONTROL 发生次数] 量度会自动应用到该日期范围。

1. 保存此项目，以便在比较中使用。

## 步骤2:将结果与 [!UICONTROL 按时间戳划分的记录总数] （在CJA中）

现在，将 [!UICONTROL 发生次数] 到Analytics中按时间戳划分的总记录Customer Journey Analytics。

按时间戳划分的记录总数应与发生次数匹配，前提是Analytics源连接器未删除任何记录 — 请参阅以下部分。

>[!NOTE]
>
>此操作仅适用于常规的中间值数据集，而不适用于拼合的数据集(通过 [跨渠道分析](/help/connections/cca/overview.md))。 请注意，考虑CJA中使用的人员ID对于进行比较至关重要。 在AA中复制这项操作可能并非总是很容易，尤其是在打开了跨渠道分析的情况下。

1. 在Adobe Experience Platform [查询服务](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html)，运行以下按时间戳划分的记录总数查询：

```
SELECT Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) as Day, \ 
        Count(_id) AS Records 
        FROM  {dataset} \ 
        WHERE timestamp>=from_utc_timestamp('{fromDate}','UTC') \ 
        AND timestamp<from_utc_timestamp('{toDate}','UTC') \ 
        AND timestamp IS NOT NULL \ 
        AND enduserids._experience.aaid.id IS NOT NULL  \ 
        GROUP BY Day \ 
        ORDER BY Day; 
```

1. 在 [Analytics数据馈送](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hans)，从原始数据中确定Analytics源连接器是否会删除某些行。

   的 [Analytics源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans) 在转换到XDM架构期间，可能会删除行。 整行可能因多种原因而无法进行转换。 如果以下任何Analytics字段具有这些值，则将删除整行。

   | Analytics字段 | 导致其丢弃的值 |
   | --- | --- |
   | Opt_out | `y, Y` |
   | In_data_only | 非0 |
   | Exclude_hit | 非0 |
   | Bot_id | 非0 |
   | Hit_source | 03578910万 |
   | Page_event | 5.363万 |

1. 如果连接器丢弃了行，则从发生次数量度中减去这些行。 结果数字应与AEP数据集中的事件数匹配。

## 在从AEP摄取期间为何会删除或跳过记录

CJA [连接](/help/connections/create-connection.md) 允许您根据跨数据集的通用人员ID将多个数据集合并在一起。 在后端，我们会应用重复数据删除：基于时间戳的事件数据集上的完全外部连接或并集，然后基于人员ID对用户档案和查询数据集上的内部连接。

以下是从AEP摄取数据时可能会跳过记录的一些原因。

* **缺少时间戳**  — 如果事件数据集中缺少时间戳，则在摄取期间将完全忽略或跳过这些记录。 因为它们允许数据集合并在一起。

* **缺少人员ID**  — 缺少人员ID（来自事件数据集和/或来自用户档案/查询数据集）会导致忽略或跳过这些记录。 原因是没有用于连接记录的通用ID或匹配键。

* **人员ID无效**  — 如果ID无效，则系统在要加入的数据集中找不到有效的通用ID。 在某些情况下，人员ID列具有无效的人员ID，如“未定义”或“00000000”。

* **大人员ID**  — 如果人员ID具有每月在事件中出现超过100万次的任意数字和字母组合，则不能将其归因于任何特定用户或人员。 它将被分类为无效。 这些记录无法摄取到系统中，并且会导致容易出错的摄取和报告。


