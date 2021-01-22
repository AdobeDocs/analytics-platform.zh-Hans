---
title: 使用对象数组
description: 了解 CJA 如何报告数据层次结构。
translation-type: ht
source-git-commit: 6229c5bb08f6f153c625932ed06e85030bc08c5a
workflow-type: ht
source-wordcount: '418'
ht-degree: 100%

---


# 使用对象数组

某些平台架构可以具有对象数组。最常见的示例之一是包含多个产品的购物车。每个产品都有一个名称、SKU、类别、价格、数量以及要跟踪的任何其他维度。所有这些方面都有不同的要求，但必须都属于相同点击。

在以前版本的 Adobe Analytics 中，此功能是通过 `products` 变量实现的。它是一个连接字符串，用分号 (`;`) 分隔以区分产品不同方面，同时用逗号 (`,`) 描述不同产品。它是有限支持“对象数组”的唯一变量。多值变量（如列表变量）可以支持数组的等效内容，但它们不能支持“对象数组”。CJA 通过支持单行数据中任意深度的层次结构扩展了这一概念，任何以前版本的 Adobe Analytics 均不提供该功能。

## 相同点击示例

以下点击是一个 JSON 对象，它表示客户购买洗衣机和烘干机。

```json
{
  "ID": "1", 
  "product": [
    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
  ], 
  "timestamp": 1534219229
}
```

创建数据视图时，以下维度和量度可用（基于架构）：

* **维度：**
   * ID
   * product : SKU
   * product : name
   * product : order_id
   * product : warranty : coverage
   * prodcut : warranty : length
   * product : warranty : name
   * product : warranty : type
* **量度：**
   * product : orders
   * product : units
   * product : revenue
   * product : warranty
   * product : warranty : revenue

### 相同点击示例（报表行为）

仅使用上述点击，下表显示了包含某些维度和量度组合的工作区报表。

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

CJA 会根据表有选择地查看对象的维度和度量。

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
+      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
+      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
+      "name": "LG Dryer 2000", 
+      "orders": 1, 
+      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

如果您仅希望报告保修收入，则您的项目将类似于以下内容：

| `product : warranty : coverage` | `product : warranty : revenue` |
| --- | --- |
| `full coverage` | `200` |
| `extended` | `50` |
| `Total` | `250` |

CJA 查看点击的这些部分以生成报表：

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
+          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
+          "revenue": 200
+        }, 
+        {
+          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
+          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
+  ], 
+  "timestamp": 1534219229
+}
```

由于烘干机不包含保修，因此未纳入表中。

由于您可以将任何维度与度量组合，下表显示了数据如何包含未指定的维度项目：

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

产品订单存在，却不包含与其关联的保修名称，因此该维度项目属于“未指定”。产品保修订单也存在相同情况：

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
          "coverage": "full coverage", 
          "length": "2 year", 
+          "name": "LG 2000 standard", 
+          "orders": 1, 
          "revenue": 200
+        }, 
+        {
          "coverage": "extended", 
          "length": "1 year", 
+          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
+      "orders": 1, 
      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

请注意那些没有关联名称的订单。它们是归因于“未指定”维度项目的订单。

### 组合量度

如果 CJA 在不同的对象级别上，则它本身不会组合名称相似的量度。

| `product : category` | `product : revenue` | `product : warranty : revenue` |
| --- | --- | --- |
| `Washing Machines` | `1600` | `250` |
| `Dryers` | `500` | `0` |
| `Total` | `2100` | `250` |

但是，您可以创建将所需量度组合在一起的计算量度：

计算量度“总收入”：`[product : revenue] + [product : warranty : revenue]`

应用此计算量度可显示所需的结果：

| `product : warranty : name` | `Total revenue (calculated metric)` |
| --- | --- |
| `Washing Machines` | `1850` |
| `Dryers` | `500` |
| `Total` | `2350` |
