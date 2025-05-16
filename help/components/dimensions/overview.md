---
title: 维度概述
description: 了解维度是什么以及如何在 Customer Journey Analytics 中使用它们
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: 6cabedc5ed58dac450577fc3505be5f95b7a959d
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 86%

---

# 维度概述

维度是 Customer Journey Analytics 中用于分析数据的一个组件类型。例如，在 [Analysis Workspace](/help/analysis-workspace/home.md) 或在 [Report Builder](/help/report-builder/rb-overview.md) 中构建报告时会使用维度。

Customer Journey Analytics 维度是一种无限类型；值可以是数字、文本、对象、列表或所有这些值的组合。

Customer Journey Analytics 中的基本报告显示一个量度列（通常是数字值）的多个维度行（通常是字符串值）。

例如，如果将“页面”维度与“人员”量度相结合，您就会获得一个显示各人员最常访问页面的排名报告：

| 页面 | 人员 |
| --- | ---: |
| 主页 | 800 |
| 产品页面 | 500 |
| 购买页面 | 100 |

{style="table-layout:fixed"}

每个维度表示网站的不同部分或方面。您可以将其中一个或多个维度与一个或多个量度组合在一起，创建所需的报告。


## 创建维度

Customer Journey Analytics 管理员可以[在数据视图中创建维度](/help/data-views/create-dataview.md#components)。

## 标准维度

创建数据视图时，默认情况下会将以下组件作为维度添加到数据视图中：

{{standard-dimensions}}


## 添加维度描述

Customer Journey Analytics 管理员可以在数据视图中或直接在 Analysis Workspace 中添加维度和其他组件的描述。有关如何添加维度描述的信息，请参阅[添加组件描述](/help/components/add-component-descriptions.md)。

>[!MORELIKETHIS]
>
>[使用事件深度功能发现更深入的客户洞察](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/discover-deeper-customer-insights-with-adobe-customer-journey/ba-p/753947#M576)
>

