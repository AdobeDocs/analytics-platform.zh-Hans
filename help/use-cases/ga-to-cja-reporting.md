---
title: 报告Google AnalyticsCustomer Journey Analytics
description: 在Customer Journey Analytics中显示有关Google Analytics数据的有用报告
translation-type: tm+mt
source-git-commit: a4e95424ee304869e76a0532b7240290a3f13418
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 0%

---


# 报告Google AnalyticsCustomer Journey Analytics

现在，您已将[Google Analytics数据引入Experience Platform和Customer Journey Analytics(CJA)](/help/use-cases/ga-to-cja.md)，我们将向您展示一些对该数据进行报告的有用方案。

## 将Web数据和应用程序数据可视化为组合数据集

此Venn图显示了您网站上(来自您的Google Analytics数据)和移动App（来自您的Firebase数据）和呼叫中心的用户重叠。 您还可以在Web上以及移动应用程序中看到表现最好的产品。 您甚至可以使用计算量度从两者中获取总收入。 请注意，当您查看总收入时，顶级产品如何呈现不同的情况。 如果没有数据集，你永远不会知道“Twill cap”的表现如此出色。

![](assets/combined-datasets.png)

## 确定呼叫原因并减少呼叫量

要验证您是否接到了大量呼叫，您可以趋势化我们呼叫中心在过去2个月中所花费的时间。 很容易看到这种增长趋势。 这令人担忧，因为每一分钟您的呼叫中心代表都在打电话，你就会为此付出金钱。 这肯定会影响您的盈利。

让我们看看导致呼叫中心呼叫增加的主要原因。 请注意，“已拒绝信用卡”、“删除信用卡”和“损坏的产品”是主要原因。 这已经可以提示如何改进在线体验。 您还可以趋势化这些呼叫原因，并查看哪些因素对整体峰值贡献最大。 “损坏产品”的客户每次呼叫花费的时间超过3分钟，这非常有趣。

![](assets/call-volume.png)

让我们进一步查看哪些产品导致呼叫中心的大部分呼叫以及有多少客户拨打了这些呼叫。 泡泡图显示，有2万人打电话，花了4小时30分钟，并退回了33套“男士短袖Te”产品。

我们可以分析这一洞察，并通过在维度“呼叫原因”中拖动来了解这些人返回产品的原因。 如您所见，此产品收到如此多呼叫的原因是“损坏的产品”。 下一步是与质量控制部门联系，了解客户为何收到损坏的T恤。

![](assets/call-reason.png)

现在，让我们看看哪些网页驱动呼叫中心的来电。 这样，您就可以了解网站上表现欠佳的体验所在的位置，并帮助您的产品经理解决这些难题。

我们通过

* 使用计算量度将数据向下过滤到仅以呼叫中心呼叫结束的会话。
* 使用CJA的[Attribution IQ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=en#cja-workspace)中的“参与”模型。

您可以轻松查看哪些页面最频繁地参加以呼叫结束的会话。 您可以看到“购物车”和“结帐信息”页面驱动了大多数呼叫。 由于您还包含了Firebase移动应用程序数据，因此您甚至可以看到生成调用的页面错误和应用程序崩溃。 如果您希望提供出色的Web和移动App体验，这确实是一个重要的数据点。

![](assets/contributing-pages.png)

最后，使用Analysis Workspace中的同期群表，可以轻松了解用户在访问过网站后通常需要多长时间来呼叫我们的呼叫中心。 这里你可以看到平均3到4周。

![](assets/cohort.png)

## 使用高级营销归因

CJA允许您对跨渠道数据使用复杂的归因模型。 在以下示例中，您可以看到将收入的“最近触摸”、“首次触摸”、“u形”和算法归因应用于“Google Analytics渠道分组”维度的比较。

![](assets/mktg-attribution.png)

使用计算量度，您可以将该归因应用于您的Web收入、移动App收入，甚至删除产品回报。 因此，您可以看到每个营销渠道的真实净收入。

![](assets/calc-metric.png)

Attribution IQ还可让您轻松筛选数据。 您只能针对特定的用户集查看归因，如使用多个设备的用户。

![](assets/filter.png)

最后，您还可以将Web和App收入归因于您的Google广告内容。 您会注意到，我们的在线Google Ads驱动的移动App比Web带来的收入要多。 通过按网络和App收入对广告进行排序，您可以获得与您不同的谷歌广告效果。

![](assets/google-ad.png)

如果没有CJA，您就无法知道您的在线广告对在您的移动App上购买的产品有任何影响。 现在您可以看到，与仅Web相比，Google Ads的移动应用程序收入额增加了1.4万美元 — 5万美元。

![](assets/google-ad2.png)