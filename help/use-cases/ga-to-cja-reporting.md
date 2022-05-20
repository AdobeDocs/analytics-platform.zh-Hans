---
title: 在 Customer Journey Analytics 中就 Google Analytics 数据给出报告
description: 在 Customer Journey Analytics 中就 Google Analytics 数据给出有价值的报告
exl-id: a7ac3c8d-c0d9-4fc2-80d7-c2b388250586
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: ht
source-wordcount: '807'
ht-degree: 100%

---

# 在 Customer Journey Analytics 中就 Google Analytics 数据给出报告

现在，您已[将 Google Analytics 数据摄取到 Experience Platform 和 Customer Journey Analytics (CJA)](/help/use-cases/ga-to-cja.md)，我们会为您显示给出该数据报告的一些实用场景。

## 将 Web 数据和应用程序数据可视化为组合数据集

此 Venn 图显示在您的网站（根据您的 Google Analytics 数据）、移动应用程序（根据您的 Firebase 数据）和呼叫中心中重叠的用户。您还可以看到表现最好的产品 - 不光在 Web 上，而且在移动应用程序上。您甚至可以使用计算量度得到两者收入的总和。您会注意到，当查看合并收入时，表现最好的产品表现不一。没有合并数据集，您永远想不到“Twill cap”表现如此卓著。

![](assets/combined-datasets.png)

## 识别呼叫原因并减少呼叫量

为了验证您接到很多呼叫，您可以查看过去 2 个月我们的呼叫中心所花时间的趋势。增长趋势很明显。这令人担忧，因为您的呼叫中心代表在电话上花的每一分钟都在消耗您的钱。这肯定会影响您的利润。

我们来看一下导致呼叫中心来电增多的主要原因是什么。我们注意到，“信用卡被拒”、“删除信用卡”和“产品损坏”是主要原因。这可能暗示应该设法改善在线体验了。您还可以了解到这些呼叫原因的趋势，看看哪些在整体峰值中占比最大。有意思的是，我们看到，称“产品损坏”的客户每次通话时间超过 3 分钟。

![](assets/call-volume.png)

我们进一步来看看哪些产品导致的呼叫最多，以及有多少客户打了这类电话。气泡图显示，有 20,000 人打了电话，花了 4 小时 30 多分钟，退回 33 件“男式短袖 T 恤”产品。

我们继续进一步分析，通过拖入维度“呼叫原因”来看看为什么这些人会退货。正如您看到的，这个产品之所以接到这么多电话，是因为“产品损坏”。下一步就是联系质量控制部门，了解客户为什么会收到损坏的 T 恤。

![](assets/call-reason.png)

现在，我们来看看哪些网页驱动了呼叫中心的来电。这让您可以了解到网站体验不能令人满意的地方，帮助您的产品经理解决这些挑战。

我们的做法是

* 使用计算量度筛选数据，只查看最终导致呼叫中心通话的会话。
* 使用 CJA 的 [Attribution IQ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html#cja-workspace) 中的“参与率”模型。

您可以轻松地看到哪些页面最常参与以呼叫结束的会话。您可以看到，“购物车”和“结账信息”页面驱动了大部分呼叫。由于您还包含了 Firebase 移动应用程序数据，所以您甚至可以看到生成呼叫的页面错误和应用程序崩溃。如果您想要提供良好的 Web 和移动应用程序体验，这是一个非常重要的数据点。

![](assets/contributing-pages.png)

最后，使用 Analysis Workspace 中的队列表，很容易看到用户通常在访问过网站多久后会呼叫我们的呼叫中心。在这里，您可以看到平均时间是 3 至 4 周。

![](assets/cohort.png)

## 使用高级营销归因

CJA 允许您在跨渠道数据上使用复杂的归因模型。在下面的示例中，您可以看到应用最近联系、首次联系、U 形和收入算法归因与 Google Analytics 渠道分组维度的比较。

![](assets/mktg-attribution.png)

使用计算量度，您可以将该归因应用于 Web 收入、移动应用程序收入，甚至可以删除产品退货。结果，您可以看到每个营销渠道的真实净收入。

![](assets/calc-metric.png)

Attribution IQ 还让您能够轻松筛选数据。您可以看到仅针对特定用户集的归因，例如那些使用多个设备的用户。

![](assets/filter.png)

最后，您还可以将您的 Web 和应用程序收入归因于您的 Google 广告内容。您会发现，从受到我们的在线 Google 广告驱动的移动应用程序获得的收入比从 Web 获得的多。通过按 Web 和应用程序收入排序广告，您对于表现最好的 Google 广告的认识会有很大不同。

![](assets/google-ad.png)

如果没有 CJA，您可能无法知道您的在线广告对于通过您的移动应用程序购买的产品有怎样的影响。现在，您可以看到单与 Web 相比，来自 Google 广告的移动应用程序收入多出 5,000-1.4 万美元。

![](assets/google-ad2.png)
