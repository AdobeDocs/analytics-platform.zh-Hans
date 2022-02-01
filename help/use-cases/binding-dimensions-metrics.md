---
title: 在CJA中使用绑定维度和量度
description: 将维属性添加到对象数组以进行复杂持久性分析。
exl-id: 5e7c71e9-3f22-4aa1-a428-0bea45efb394
feature: Use Cases
source-git-commit: 38c10e395b816d812d30f0698dc821ee0ea5c9b1
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 1%

---

# 在CJA中使用绑定维度和量度

Customer Journey Analytics提供了多种方法来在设定的点击之外保留维度值。 Adobe选件的一种持久性方法称为“绑定”。 在Adobe Analytics的早期版本中，此概念称为推销。

虽然您可以将绑定维度与顶级事件数据结合使用，但在使用 [对象数组](object-arrays.md). 您可以将维度归因到对象数组的一个部分，而无需将其应用到给定事件中的所有属性。 例如，您可以将搜索词归因于购物车对象数组中的某个产品，而不将该搜索词绑定到整个事件。

## 示例1:使用捆绑维度将其他产品属性归因于购买

您可以将对象数组中的维度项目绑定到另一个维度。 当出现绑定维度项目时，CJA会回顾绑定维度，并将其包含在事件中。 请考虑以下客户历程：

1. 访客在洗衣机上查看产品页面。

   ```json
   {
       "PersonID": "1",
       "product_views": 1,
       "product": [
           {
               "name": "Washing Machine 2000",
               "color": "white",
               "type": "front loader",
           },
       ],
       "timestamp": 1534219229
   }
   ```

1. 然后，访客在烘干机上查看产品页面。

   ```json
   {
       "PersonID": "1",
       "product_views": 1,
       "product": [
           {
               "name": "Dryer 2000",
               "color": "neon orange",
           },
       ],
       "timestamp": 1534219502
   }
   ```

1. 最终他们会买东西。 购买事件中未包含每个产品的颜色。

   ```json
   {
       "PersonID": "1",
       "orders": 1,
       "product": [
           {
               "name": "Washing Machine 2000",
               "price": 1600,
           },
           {
               "name": "Dryer 2000",
               "price": 499
           }
       ],
       "timestamp": 1534219768
   }
   ```

如果您想要按颜色查看收入，而不使用捆绑维度，则维度 `product.color` 将信用保留并错误地归因于干燥器的颜色：

| product.color | 收入 |
| --- | --- |
| 霓虹橙 | 2099年 |

您可以进入数据视图管理器，并将产品颜色绑定到产品名称：

![绑定维度](assets/binding-dimension.png)

设置此持久性模型时，每当设置产品颜色时，Adobe都会注意产品名称。 当该访客在后续事件中识别相同的产品名称时，也会显示产品颜色。 将产品颜色与产品名称绑定时的相同数据应类似于以下内容：

| product.color | 收入 |
| --- | --- |
| 白色 | 1600 |
| 霓虹橙 | 499 |

## 示例2:使用捆绑量度将搜索词与产品购买绑定

Adobe Analytics中最常见的推销方法之一是将搜索词与产品绑定，以便每个搜索词都可以获得其相应产品的点数。 请考虑以下客户历程：

1. 访客到达您的网站并搜索“拳击手套”。

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "boxing gloves",
       "product": [
           {
               "name": "Beginner gloves",
               "color": "Red",
               "price": "25.69"
           },
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Professional gloves",
               "color": "Blue",
               "price": "224.99"
           }
       ]
   }
   ```

1. 他们找到一双他们喜欢的手套，然后把它加到车里。

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           }
       ]
   }
   ```

1. 然后，访客搜索“网球拍”。

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "tennis racket",
       "product": [
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Women's open racket",
               "price": "49.99"
           },
           {
               "name": "Extreme racket",
               "price": "134.99"
           }
       ]
   }
   ```

1. 他们找到自己喜欢的球拍，然后把它加到手推车里。

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           }
       ]
   }
   ```

1. 访客第三次搜索“鞋”。

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "shoes",
       "product": [
           {
               "name": "Men's walking shoes",
               "color": "Grey",
               "price": "54.95"
           },
           {
               "name": "Tennis shoes",
               "color": "White",
               "price": "42.59"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

1. 他们找到一双他们喜欢的鞋，然后把它加到购物车里。

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

1. 访客完成结帐流程并购买这三个项目。

   ```json
   {
       "PersonID": "1",
       "page_name": "Thank you for your purchase",
       "purchase": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

如果您将传统的分配模型与搜索词结合使用，则所有三种产品都只将收入归因于单个搜索词。 例如，如果您将首次分配与搜索词维度一起使用：

| search_term | 收入 |
| --- | --- |
| 拳击手套 | US$204.97 |

如果您将上次分配与搜索词维度一起使用，则所有三个产品仍会将收入归因于单个搜索词：

| search_term | 收入 |
| --- | --- |
| 请求 | US$204.97 |

虽然此示例仅包含一个访客，但许多搜索不同内容的访客可能会将搜索词错误地归因于不同的产品，从而难以确定最佳搜索结果的实际内容。

对于绑定维度，Adobe会注意它绑定的维度项目。 当在后续事件中看到相同的绑定值时，它会覆盖维度项目，以便您可以将所需量度归因到该维度项目。 在本例中，我们可以将search_term的绑定维度设置为产品名称。 在数据视图管理器中设置此维度时，还需要设置绑定量度，因为绑定维度位于对象数组中。 绑定量度充当绑定维度的触发器，因此它仅在存在绑定量度的事件上绑定自身。 在此示例实施中，搜索结果页面始终包含搜索词维度和搜索量度。 只要存在“搜索”量度，我们便可以将搜索词绑定到产品名称。

![绑定量度](assets/binding-metric.png)

将搜索词维度设置为此持久性模型可执行以下逻辑：

* 当search_term在事件中时，检查是否存在产品名称。
* 如果产品名称不在，则不执行任何操作。
* 如果存在产品名称，请检查是否存在搜索量度。
* 如果“搜索”量度不在，则不执行任何操作。
* 如果存在“搜索”量度，则将搜索词绑定到所有产品名称。 它的作用类似于它在与该事件的产品名称相同的级别。 在此示例中，它被视为product.search_term。
* 如果在后续事件中看到相同的产品名称，则绑定的搜索词也存在。

在Analysis Workspace中，生成的报表将类似于以下内容：

| search_term | 收入 |
| --- | --- |
| 拳击手套 | US$89.99 |
| 网球球 | US$34.99 |
| 请求 | US$79.99 |
