---
title: 数据馈送中阵列和映射的子事件组件
description: 了解Customer Journey Analytics数据馈送如何从数组和映射字段中导出子事件组件，以及如何在Data Warehouse中查询它们。
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
source-git-commit: a4ea9270d5bf27234fa229e8ba3df5998ecea0e1
workflow-type: tm+mt
source-wordcount: '1303'
ht-degree: 0%
---
# 数据馈送中的子事件组件

{{release-limited-testing}}

子事件组件是基于XDM架构中数组或映射内的字段的维度和量度。 您可以使用日期范围在比事件级别更精细的级别分析数据，例如购买中的单个产品。 有关在区段中使用此数据的信息，请参阅[子事件](/help/components/segments/sub-event.md)。

使用以下信息了解数组和映射字段中的子事件组件如何在您的Customer Journey Analytics数据馈送中显示。

## 了解子事件组件

### XDM架构中的子事件组件

在XDM架构中，数组的每个元素（字符串数组或对象数组）都是子事件。 映射字段中的每个条目也是子事件，如数据馈送](#use-map-fields-in-data-feeds)中的[映射字段中所述。 基于子事件内字段的维度和量度是子事件组件。

要在Adobe Experience Platform中查看XDM架构中的子事件，请选择&#x200B;[!UICONTROL **架构**]，然后展开包含子事件的事件。

在以下示例中，`Product list items`是包含各种子事件组件的对象数组。

![XDM架构包含对象数组和子事件组件](assets/df-sub-event-schema.png)

### Analysis Workspace和数据馈送之间的子事件差异

在Customer Journey Analytics中，子事件组件在Analysis Workspace和数据馈送中的表示方式有所不同。

| 位置 | 子事件组件的表示方式 |
| --- | --- |
| **Analysis Workspace（在Customer Journey Analytics中）** | 可选择作为单个组件，独立于任何可见层次结构。 |
| **数据馈送（在Customer Journey Analytics中）** | 表示为一个组，其层次结构保持不变。 |

### Adobe Analytics和Customer Journey Analytics之间的子事件差异

子事件数据（例如单个购买事件中的多个产品详细信息）在Customer Journey Analytics数据馈送中的显示方式与Adobe Analytics数据馈送中的显示方式不同。 下表比较了每个产品表示子事件数据的方式。

| 产品 | 子事件数据在数据馈送中的显示方式 | 示例：产品列表 |
| --- | --- | --- |
| **Adobe Analytics** | 在一列中拼合为分隔字符串。 | 产品列表包含在单个字符串中分组的多个产品：<p>`Power Tools;Cordless Drill;1;129.99,Power Tools;Drill Battery Pack;2;39.98` <!--screenshot of what this looks like: product lists, list vars. --></p> |
| **Customer Journey Analytics** | 子事件组件保留XDM架构中定义的层次结构。 在同一列中分组时，它们会向父事件和同级子事件显示其关系层次结构。 | 产品列表维护其在XDM架构中定义为数组的层次结构：<p>`[{"category":"Power Tools","product":"Cordless Drill","quantity":1,"revenue":129.99},{"category":"Power Tools","product":"Drill Battery Pack","quantity":2,"revenue":39.98}]` <!--screenshot of what this looks like: product lists, list vars. --></p> |

{style="table-layout:auto"}

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

## 将子事件组件添加到数据馈送

向数据馈送添加子事件组件时，会出现一个对话框，提示您从同一子事件添加其他组件。

![对话框提示您添加相关的子事件组件](assets/data-feeds-add-subevent.png)

来自同一子事件的字段在画布上显示为可折叠的嵌套组，而不是平面项。

![子事件组](assets/data-feeds-subevent-added.png)

此组反映底层数据结构。

在数据馈送输出中，所有这些组件都显示为单列中的嵌套数组。

有关如何将组件（包括子事件组件）添加到数据馈送的信息，请参阅[创建数据馈送](/help/components/exports/cja-data-feeds/create-feed.md)。

## 查询数据馈送输出中的子事件数据

由于子事件数据[在Customer Journey Analytics数据馈送](#sub-event-differences-between-adobe-analytics-and-customer-journey-analytics)中的显示方式不同，因此您对其使用的查询与您对Adobe Analytics数据馈送使用的查询不同。

以下示例显示如何查找包含特定产品的事件。 这些示例使用Google BigQuery语法，其中`UNNEST`将数组展开为行。 其他数据仓库支持对其自己的数组函数使用相同的方法，例如Snowflake中的`FLATTEN`或Databricks中的`explode`。

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

要筛选事件而不更改行数，请在`EXISTS`子查询中使用数组函数，如`UNNEST`：

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

若要为每个匹配的产品返回一行，请将数组函数移到外部`FROM`子句中：

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

## 在数据馈送中使用映射字段

映射XDM架构中的字段存储键值对。 数据馈送将每个映射导出为对象数组，方式与其他[子事件数据](#query-sub-event-data-in-data-feed-output)相同。 每个对象都包含映射键及其值作为单独的字段。

输出中的字段名称来自您为数据馈送配置的组件ID，而不是固定名称，如`key`或`value`。 本节中的示例使用了示例组件ID。

<!-- Confirm with Nate before publishing: how the outer array column is named in the output (for example, `survey_responses`). -->

### 简单映射

简单映射是您可以在自己的架构中创建的映射类型。 每个键都是一个字符串，每个值都是一个字符串或整数。

例如，调查图将每个问题存储为一个键，将响应存储为一个值：

```json
{
  "_yourtenant": {
    "surveyResponses": {
      "How did you hear about us?": "Search engine",
      "How likely are you to recommend us?": 9
    }
  }
}
```

在数据馈送输出中，`survey_question`和`survey_answer`是键和值的组件ID：

```json
{
  "survey_responses": [
    { "survey_question": "How did you hear about us?", "survey_answer": "Search engine" },
    { "survey_question": "How likely are you to recommend us?", "survey_answer": 9 }
  ]
}
```

### 标识映射

[`identityMap`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/profile/identitymap)字段中的每个标识都导出为一个对象。 对象包含身份命名空间（键），以及标识符、身份验证状态和主标志。 命名空间会为该命名空间中的每个身份重复。

仅导出作为数据视图中的维度存在并且添加到数据馈送中的身份映射属性。

```json
{
  "identity_map": [
    { "identity_namespace": "ECID", "identity_id": "83290187457380573620940587193016478103", "authenticated_state": "ambiguous", "is_primary": true },
    { "identity_namespace": "CRMID", "identity_id": "C-1048576", "authenticated_state": "authenticated", "is_primary": false }
  ]
}
```

### 嵌套映射

某些Adobe定义的字段，如`segmentMembership`，是映射的映射。 数据馈送将这些数据拼合为一个数组，其中第一级键和第二级键作为每个对象中的单独字段。 第一级密钥在其应用于的每个对象中重复，因此不会丢失任何数据或关系。

例如，`segment_namespace`和`segment_id`是第一级键和第二级键的组件ID：

```json
{
  "segment_membership": [
    { "segment_namespace": "ups", "segment_id": "04a81716-43d6-4e7a-a49c-f1d8b3129ba9", "status": "realized" },
    { "segment_namespace": "ups", "segment_id": "53cba6b2-a23b-454a-8069-fc41308f1c0f", "status": "exited" }
  ]
}
```








