---
title: 维度概述
description: 了解维度是什么以及在Customer Journey Analytics中使用维度的方式
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: 1564c91616015311393a643fe7fcecd429cf3a36
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 37%

---

# 维度概述

Dimension是Customer Journey Analytics中用于分析数据的一种组件类型。 例如，在[Analysis Workspace](/help/analysis-workspace/home.md)或[Report Builder](/help/report-builder/report-buider-overview.md)中构建报表时，使用维度。

Customer Journey Analytics维度没有限制；值可以是数字、文本、对象、列表或所有这些的混合。

Customer Journey Analytics中的基本报表根据量度列（通常是数值）显示维度的行（通常是字符串值）。

例如，如果将“页面”维度与“访问量”量度相结合，您将获得一个显示最常访问的页面的排名报告：

| `Page` | `Visits` |
| --- | --- |
| `Home page` | `800` |
| `Product page` | `500` |
| `Purchase page` | `100` |

每个维度表示网站的不同部分或方面。您可以将其中一个或多个维度与一个或多个量度组合在一起，创建所需的报告。

## 创建维度

Customer Journey Analytics管理员可以[在数据视图](/help/data-views/create-dataview.md#components)中创建维度。

## 添加维度描述

Customer Journey Analytics管理员可以在数据视图内或直接在Analysis Workspace中为维度和其他组件添加描述。 有关如何向维度添加描述的信息，请参阅[添加组件描述](/help/components/add-component-descriptions.md)。
