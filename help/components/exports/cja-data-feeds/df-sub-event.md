---
title: 了解数据馈送中的子事件和对象数组
description: 了解Customer Journey Analytics数据馈送如何从架构数组导出子事件，从而保留层次结构而不是像Workspace那样将其扁平化。
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: a4fdb1f8d49b42b6de21881e0c8392995124c1ea
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 2%
---
# 数据馈送中的子事件

{{release-limited-testing}}

Customer Journey Analytics中的[子事件](/help/components/segments/sub-event.md)允许您在比事件级别更精细的级别分析事件数据。

使用以下信息了解如何处理Customer Journey Analytics数据馈送中的子事件。

## 了解子事件

### XDM架构中的子事件

在XDM架构中，数组的每个元素（字符串数组或对象数组）都是子事件。

要在Adobe Experience Platform的XDM架构中查看包含子事件的事件，请选择&#x200B;[!UICONTROL **架构**]，然后展开包含子事件的事件。

在以下示例中，`Product list items`是包含各种子事件的对象数组。

![XDM架构包含对象数组和子事件](assets/df-sub-event-schema.png)

### 子事件示例：购买事件中的产品

一位客户在一次订购中购买了两款产品：一个无绳钻床和两个钻床电池组。 您的实施发送了一个购买事件，该事件包括`productListItems`对象数组中的两个产品：

```json
{
  "eventType": "commerce.purchases",
  "timestamp": "2026-09-16T14:32:07.512Z",
  "commerce": {
    "purchases": { "value": 1 }
  },
  "productListItems": [
    { "SKU": "CD-2000", "name": "Cordless Drill", "quantity": 1, "priceTotal": 129.99 },
    { "SKU": "BP-2000", "name": "Drill Battery Pack", "quantity": 2, "priceTotal": 39.98 }
  ]
}
```

此事件包含两个子事件，`productListItems`数组中的每个对象一个。 下表显示了哪些字段属于该事件，哪些字段属于其子事件。

| 级别 | 字段 | 字段描述内容 |
| --- | --- | --- |
| **事件** | `eventType`, `timestamp`, `commerce.purchases.value` | 整个购买过程。 每个字段都有一个事件值。 **订单**&#x200B;量度对此事件计数`1`，无论它包含多少产品。 |
| **子事件** | 每个`productListItems`对象中的`SKU`、`name`、`quantity`、`priceTotal` | 购买中的单个产品。 每个字段为每个产品具有一个值。 例如，`quantity`对于无绳钻孔机为`1`，对于钻孔电池组为`2`。 |

{style="table-layout:auto"}

>[!NOTE]
>
>子事件仅包括随事件发送的数据。 Customer Journey Analytics不会根据之前的事件重建购物车内容，例如购物车添加或结账。 要使产品显示为购买事件的子事件，您的实施必须包含在该购买事件的`productListItems`中。

## 将子事件数据添加到数据馈送

当您尝试在构建数据馈送时添加作为子事件的列时，将显示一个对话框，提示您添加任何对等子事件。 在数据馈送输出中，所有这些事件都显示在一列中。

## 在数据馈送输出中查看子事件数据

### Analysis Workspace和数据馈送之间的子事件差异

在Customer Journey Analytics中，子事件在Analysis Workspace和数据馈送中的表示方式有所不同。

| 位置 | 子事件的表示方式 |
| --- | --- |
| **Analysis Workspace（在Customer Journey Analytics中）** | 可选择作为单个组件，独立于任何可见层次结构。 |
| **数据馈送（在Customer Journey Analytics中）** | 表示为一个组，其层次结构保持不变。 |

### Adobe Analytics和Customer Journey Analytics之间的子事件差异

子事件数据（例如单个购买事件中的多个产品详细信息）在Customer Journey Analytics数据馈送中的显示方式与Adobe Analytics数据馈送中的显示方式不同。 下表比较了每个产品表示子事件数据的方式。

| 产品 | 子事件数据在数据馈送中的显示方式 | 示例：产品列表 |
| --- | --- | --- |
| **Adobe Analytics** | 在一列中拼合为分隔字符串。 | 产品列表包含在单个字符串中分组的多个产品：<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | 子事件会保留XDM架构中定义的层次结构。 在同一列中分组时，它们会向父事件和同级子事件显示其关系层次结构。 | 产品列表维护其在XDM架构中定义为数组的层次结构：<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

### 与Adobe Analytics的差异

### Adobe Analytics和Customer Journey Analytics数据馈送之间的输出有何不同

子事件数据（例如单个购买事件中的多个产品详细信息）在Customer Journey Analytics数据馈送中的显示方式与Adobe Analytics数据馈送中的显示方式不同。 下表比较了每个产品表示子事件数据的方式。

| 产品 | 子事件数据在数据馈送中的显示方式 | 示例：产品列表 |
| --- | --- | --- |
| **Adobe Analytics** | 在一列中拼合为分隔字符串。 | 产品列表包含在单个字符串中分组的多个产品：<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | 子事件会保留XDM架构中定义的层次结构。 在同一列中分组时，它们会向父事件和同级子事件显示其关系层次结构。 | 产品列表维护其在XDM架构中定义为数组的层次结构：<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## Analysis Workspace和数据馈送输出之间子事件的差异

在Customer Journey Analytics中，子事件在Analysis Workspace和数据馈送中的表示方式有所不同。

| 位置 | 子事件的表示方式 |
| --- | --- |
| **Analysis Workspace** | 可选择作为单个组件，独立于任何可见层次结构。 |
| **数据馈送** | 表示为一个组，其层次结构保持不变。 |


## 在数据馈送输出中查看子事件数据

子事件数据（例如单个购买事件中的多个产品详细信息）在Customer Journey Analytics数据馈送中的显示方式与Adobe Analytics数据馈送中的显示方式不同。 下表比较了每个产品表示子事件数据的方式。

| 产品 | 子事件数据在数据馈送中的显示方式 | 示例：产品列表 |
| --- | --- | --- |
| **Adobe Analytics** | 在一列中拼合为分隔字符串。 | 产品列表包含在单个字符串中分组的多个产品：<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | 子事件会保留XDM架构中定义的层次结构。 在同一列中分组时，它们会向父事件和同级子事件显示其关系层次结构。 | 产品列表维护其在XDM架构中定义为数组的层次结构：<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

## 查询数据馈送输出中的子事件数据

由于子事件数据[在Customer Journey Analytics数据馈送](#view-sub-event-data-in-data-feed-output)中的显示方式不同，因此您对其使用的查询与您对Adobe Analytics数据馈送使用的查询不同。

以下示例显示如何查找包含特定产品的事件。 这些示例使用Google BigQuery语法。 其他数据仓库（如Snowflake和Databricks）支持相同的方法，但语法略有差异。

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






