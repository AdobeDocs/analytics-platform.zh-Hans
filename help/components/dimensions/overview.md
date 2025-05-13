---
title: 维度概述
description: 了解什么是维度以及如何在Customer Journey Analytics中使用维度
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: 6cabedc5ed58dac450577fc3505be5f95b7a959d
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 25%

---

# 维度概述

维度是Customer Journey Analytics中用于分析数据的组件类型。 例如，在[Analysis Workspace](/help/analysis-workspace/home.md)或[Report Builder](/help/report-builder/rb-overview.md)中构建报表时，使用维度。

Customer Journey Analytics维度的类型不受限制；值可以是数字、文本、对象、列表或所有这些的混合。

Customer Journey Analytics中的基本报表根据一列指标（通常是数值）显示维度行（通常是字符串值）。

例如，如果将“页面”维度与“人员”量度相结合，您将获得一个排名报表，其中按人员显示您最常访问的页面：

| 页面 | 人员 |
| --- | ---: |
| 主页 | 800 |
| 产品页 | 500 |
| 购买页面 | 100 |

{style="table-layout:fixed"}

每个维度表示网站的不同部分或方面。您可以将其中一个或多个维度与一个或多个量度组合在一起，创建所需的报告。


## 创建维度

Customer Journey Analytics管理员可以[在数据视图](/help/data-views/create-dataview.md#components)中创建维度。

## 标准维度

创建数据视图时，默认情况下会将以下组件作为维度添加到数据视图中：

{{standard-dimensions}}


## 添加维度描述

Customer Journey Analytics管理员可以在数据视图内或直接在Analysis Workspace中为维度和其他组件添加描述。 有关如何向维度添加描述的信息，请参阅[添加组件描述](/help/components/add-component-descriptions.md)。

>[!MORELIKETHIS]
>
>[使用事件深度功能发现更深入的客户洞察](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/discover-deeper-customer-insights-with-adobe-customer-journey/ba-p/753947#M576)
>

