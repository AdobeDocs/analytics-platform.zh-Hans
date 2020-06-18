---
title: 使用对象数组
description: 了解CJA如何报告数据层次结构。
translation-type: tm+mt
source-git-commit: 52fecf03cc503fa59101f6280c671e153e2129e9
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---


# 使用对象数组

某些平台模式可以有对象数组。 最常见的示例之一是包含多个产品的购物车。 每个产品都有一个名称、SKU、类别、价格、数量以及要跟踪的任何其他维。 所有这些方面都有不同的要求，但必须都适合同一次点击。

在Adobe Analytics的先前版本中，此功能是使用变量完 `products` 成的。 它是一个由分号()分隔的连接`;`字符串，用于分隔产品的彩块化，而逗号()`,`划分的产品。 它是唯一支持“对象数组”的有限变量。 多值变量(如列表变量)可以支持等效的数组，但它们不能支持“对象数组”。 CJA通过支持单行数据中任意深度的层次结构扩展了这一概念，该功能在AdobeAnalytics的任何旧版本中都不可用。

## 同一点击示例

以下点击是一个JSON对象，它表示客户使用洗衣机和烘干机进行的购买。

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

创建数据视图时，以下维和度量可用(基于模式):

* **维度:**
   * ID
   * 产品： SKU
   * 产品： 名称
   * 产品： order_id
   * 产品： 担保： 覆盖
   * product: 担保： 长度
   * 产品： 担保： 名称
   * 产品： 担保： 类型
* **量度:**
   * 产品： 订单
   * 产品： 单位
   * 产品： 收入
   * 产品： 保修
   * 产品： 担保： 收入

### 相同的点击示例(报告行为)

仅使用上述命中，下表显示了包含某些维度和量度组合的Workspace报表。

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

CJA根据表有选择地查看对象的维度和度量。

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

CJA查看点击的这些部分以生成报告：

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

由于烘干机不包含保修，因此不包含在桌子中。

由于您可以将任何维与任何度量组合，下表显示了数据如何使用未指定维值：

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

产品订单不存在与其关联的担保名称，因此维值属于“未指定”。 产品担保订单也存在相同情况：

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

请注意与其没有关联名称的订单。 这些是“未指定”维值所属的顺序。

### 组合指标

如果CJA在不同的对象级别上，则它本身不会合并名称相似的度量。

| `product : category` | `product : revenue` | `product : warranty : revenue` |
| --- | --- | --- |
| `Washing Machines` | `1600` | `250` |
| `Dryers` | `500` | `0` |
| `Total` | `2100` | `250` |

但是，您可以创建将所需指标组合在一起的计算指标：

计算指标“总收入”: `[product : revenue] + [product : warranty : revenue]`

应用此计算度量可显示所需的结果：

| `product : warranty : name` | `Total revenue (calculated metric)` |
| --- | --- |
| `Washing Machines` | `1850` |
| `Dryers` | `500` |
| `Total` | `2350` |

## 持久性示例

