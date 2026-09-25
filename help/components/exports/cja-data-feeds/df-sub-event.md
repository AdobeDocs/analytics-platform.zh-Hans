---
title: 了解数据馈送中的子事件和对象数组
description: 了解Customer Journey Analytics数据馈送如何从架构数组导出子事件，从而保留层次结构而不是像Workspace那样将其扁平化。
hide: true
feature: Components
source-git-commit: afc1b55eb54b5f3342800489d0a7f63508ee8b10
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%
---
# 数据馈送中的子事件

{{release-limited-testing}}

在XDM架构中，任何属于数组（字符串或对象）的内容都是一个子事件。 Customer Journey Analytics中的子事件及其层级在数据馈送导出中表示。

在Adobe Analytics中，子事件表示为单列。

使用以下信息了解如何处理Customer Journey Analytics数据馈送中的子事件。

## XDM架构、Workspace和数据馈送中的子事件

您可以在XDM架构中将子事件定义为字符串数组或对象数组。

这些子事件的表示方式有所不同，具体取决于您在Analysis Workspace中还是数据馈送中查看它们。

| 位置 | 子事件的表示方式 |
| --- | --- |
| **Analysis Workspace** | 对象数组中的单个对象可以作为单个组件进行选择，独立于任何可见层次结构。 |
| **数据馈送** | 对象数组中的对象表示为一个组，其层次结构保持不变。 |

## 将子事件数据添加到数据馈送

当您尝试在构建数据馈送时添加作为子事件的列时，会显示一个对话框，允许您添加所有对等子事件。 所有这些事件都将显示在数据馈送输出的单列中。

## 在数据馈送输出中查看子事件数据

子事件数据（例如一个事件中有多个产品）在Customer Journey Analytics数据馈送中的显示方式与Adobe Analytics数据馈送中的显示方式不同。 下表比较了每个产品表示子事件数据的方式。

| 产品 | 子事件数据在数据馈送中的显示方式 | 示例：产品列表 |
| --- | --- | --- |
| **Adobe Analytics** | 在一列中拼合为分隔字符串。 | 产品列表包含在单个字符串中分组的多个产品：<p>`;LG Washing Machine 2000;1;1600,;LG Dryer 2000;1;500` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | 子事件会保留在XDM架构中定义的层次结构。 它们与其父事件和同级子事件一起保持在同一列中。 | 产品列表维护其在XDM架构中定义为数组的层次结构：<p>`[{"name":"LG Washing Machine 2000","units":1,"revenue":1600},{"name":"LG Dryer 2000","units":1,"revenue":500}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## 查询数据馈送输出中的子事件数据

由于子事件数据[在Customer Journey Analytics数据馈送](#customer-journey-analytics-vs-adobe-analytics)中的显示方式不同，因此您对其使用的查询与您对Adobe Analytics数据馈送使用的查询不同。

以下示例显示如何查找包含特定产品的事件。 这些示例使用Google BigQuery语法。 其他数据仓库（如Snowflake和Databricks）支持相同的方法，但语法略有差异。

+++ 在Adobe Analytics数据馈送中查询产品数据

在Adobe Analytics数据馈送中，包含一起购买的两个产品的事件在`product_list`列中会显示为单个分隔字符串：

```text
Power Tools;Cordless Drill;1;129.99;event1=1;eVar10=DrillBundle,Power Tools;Drill Battery Pack;2;39.98;event1=1;eVar10=DrillBundle
```

要查找包含Cordless Drill的事件，请使用正则表达式解析此字符串：

```sql
SELECT hitid_high, hitid_low, post_evar10
FROM aa_hit_data
WHERE REGEXP_CONTAINS(product_list, r'(^|,)[^;]*;Cordless Drill;')
```

+++

+++ 在Customer Journey Analytics数据馈送中查询产品数据

在Customer Journey Analytics数据馈送中，相同的两个产品在`product_list_items`列中显示为一个对象数组。 无需分隔符解析：

```json
{
  "row_id": "01K3F2M9-...-4821",
  "timestamp_utc": "2026-09-16T14:32:07.512000Z",
  "product_list_items": [
    { "category": "Power Tools", "product": "Cordless Drill", "quantity": 1, "revenue": 129.99,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} },
    { "category": "Power Tools", "product": "Drill Battery Pack", "quantity": 2, "revenue": 39.98,
      "events": {"event1": 1}, "merchandising": {"eVar10": "DrillBundle"} }
  ]
}
```

如何编写查询取决于您是希望每个事件有一行，还是希望每个匹配产品有一行。

**每个事件返回一行**

要筛选事件而不更改行数，请在`EXISTS`子查询中使用`UNNEST`：

```sql
SELECT row_id, timestamp_utc, product_list_items
FROM `project.dataset.cja_data_feed` AS f
WHERE EXISTS (
  SELECT 1
  FROM UNNEST(f.product_list_items) AS item
  WHERE item.product = 'Cordless Drill'
);
```

此查询为每个匹配事件返回一行，完整`product_list_items`数组保持不变，无论数组中有多少产品匹配。

**每个匹配产品返回一行**

若要为每个匹配的产品返回一行，请将`UNNEST`移到外部`FROM`子句中：

```sql
SELECT f.row_id, f.timestamp_utc, item.product, item.quantity, item.revenue
FROM `project.dataset.cja_data_feed` AS f,
     UNNEST(f.product_list_items) AS item
WHERE item.product = 'Cordless Drill';
```

具有多个匹配产品的事件显示为多行，并且事件的列（如`row_id`）在每行上重复。 仅在需要产品级详细信息时才使用此方法。 若要对结果中的事件进行计数，请使用`COUNT(DISTINCT row_id)`而不是对行进行计数。

此方法适用于XDM架构中的任何数组字段，而不仅仅是产品。

+++






