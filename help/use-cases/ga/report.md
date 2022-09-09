---
title: 在 Customer Journey Analytics 中就 Google Analytics 数据给出报告
description: 在 Customer Journey Analytics 中就 Google Analytics 数据给出有价值的报告
exl-id: a7ac3c8d-c0d9-4fc2-80d7-c2b388250586
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 35%

---

# 在 Customer Journey Analytics 中就 Google Analytics 数据给出报告

在Customer Journey Analytics中提供数据后，以下示例会为报告该数据提供一些有用的情景。

## 将 Web 数据和应用程序数据可视化为组合数据集

此 Venn 图显示在您的网站（根据您的 Google Analytics 数据）、移动应用程序（根据您的 Firebase 数据）和呼叫中心中重叠的用户。您还可以看到表现最好的产品 - 不光在 Web 上，而且在移动应用程序上。您甚至可以使用计算量度从这两个渠道获得总收入。 您会注意到，当查看合并收入时，表现最好的产品表现不一。没有合并数据集，您永远想不到“Twill cap”表现如此卓著。

![组合的数据集](../assets/combined-datasets.png)

## 识别呼叫原因并减少呼叫量

您可以跟踪呼叫中心过去两个月的逗留时间趋势，以确定呼叫量。 以下示例显示了过去两个月内此数据的趋势。 以下示例显示了增加的趋势，这可能会影响组织成本。

![呼叫量](../assets/call-volume.png)

使用“调用原因”维度可以提示改进Web体验的方法，从而阻止访客首先进行调用。 上例显示，“损坏产品”的每次呼叫平均呼叫时间为近3分钟，这为贵组织提供了一种精确的方法来改善客户体验并降低呼叫中心成本。

您可以查看哪些产品导致呼叫中心的大部分呼叫以及有多少客户发出这些呼叫。 泡泡图显示，有2万人打电话，花了4小时30分钟，并返回了33件“男士短袖T恤”产品。

![来电原因](../assets/call-reason.png)

应用“调用原因”的维度划分，此示例显示“损坏的产品”维度项目。 下一步就是联系质量控制部门，了解客户为什么会收到损坏的 T 恤。

您可以查看哪些网站页面将呼叫引至呼叫中心。 此报表可让您了解网站上不那么理想的体验所在的位置，并帮助您的产品经理解决这些难题。 以下示例使用计算量度将数据向下过滤到仅以呼叫中心呼叫结束的会话。 它还在CJA的 [Attribution IQ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html#cja-workspace).

以下示例显示“购物车”和“结帐信息”页面驱动大部分调用。

![参与页面](../assets/contributing-pages.png)

同类群组表允许您查看用户在访问网站后通常需要多长时间来呼叫呼叫中心。 以下示例表示此示例数据集的平均时间在三到四周之间。

![同类群组](../assets/cohort.png)

## 使用高级营销归因

CJA允许您对跨渠道数据使用复杂的归因模型。 在下面的示例中，您可以看到应用最近联系、首次联系、U 形和收入算法归因与 Google Analytics 渠道分组维度的比较。

![营销归因](../assets/mktg-attribution.png)

使用计算量度，您可以将该归因应用于 Web 收入、移动应用程序收入，甚至可以删除产品退货。结果，您可以看到每个营销渠道的真实净收入。

![计算量度](../assets/calc-metric.png)

Attribution IQ还允许您过滤数据。 您可以看到仅针对特定用户集的归因，例如那些使用多个设备的用户。

![过滤器](../assets/filter.png)

您还可以将Web和应用程序收入归因于Google广告内容。 此数据集的示例从由在线Google Ads驱动的移动设备应用程序获得的收入多于从Web获得的收入。 通过按Web和应用程序收入对广告进行排序，您可以获得表现最佳的Google广告的不同图片。

![Google广告](../assets/google-ad.png)

通过合并CJA中的数据集，您可以在此示例中看到，在线广告对在您的移动设备应用程序上购买的产品有任何影响。 以下可视化图表显示，与仅Web应用程序相比，Google Ads的移动应用程序收入额额外为1.4万至1.5万美元。

![Google广告2](../assets/google-ad2.png)
