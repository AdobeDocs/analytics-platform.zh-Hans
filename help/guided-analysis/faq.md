---
title: 指导分析常见问题解答
description: 有关引导式分析的常见问题解答。
exl-id: 32bfce23-a59c-45cb-b1cd-82f048fb13d2
feature: Guided Analysis
keywords: 产品分析
source-git-commit: 4aed07568d345770183d18041a762adc441e6bc3
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 2%

---

# 指导分析常见问题解答

有关引导式分析的常见问题解答。

+++**如何为我的组织配置引导式分析？**

引导式分析是Customer Journey Analytics的一个付费附加功能。 如果您想开始使用此加载项，请与您的Adobe客户团队联系。

+++

+++**使用引导式分析需要进行哪些实施更改？**

如果您目前已在使用Customer Journey Analytics，则无需进行额外的实施更改。 引导式分析使用相同的 [数据视图](../data-views/data-views.md) 和 [连接](../connections/overview.md) 与其他CJA界面(如 [Analysis Workspace](../analysis-workspace/home.md).

为了让最终用户在引导式分析方面获得最大成功，建议您在Adobe Experience Platform中制定强有力的事件模式和管理策略， [数据视图](../data-views/data-views.md).

+++

+++**何时应使用引导式分析还是Analysis Workspace？**

**引导式分析** 可以帮助用户快速获得高质量的见解。 它对于产品团队、希望更自信地处理数据的用户，甚至对于分析人员都是有用的，可借此开始更深入的分析。

**[Analysis Workspace](../analysis-workspace/home.md)** 是一个更自由的空间，可让您深入了解数据以揭示更多见解。 它对于非常了解数据并希望深入了解数据的分析师和高级用户非常有用。

+++

+++**引导式分析和Analysis Workspace中的术语有何异同？**

引导式分析使用的术语在产品团队中更为常用。 在引导式分析与之间切换时，可引用此表 [Analysis Workspace](../analysis-workspace/home.md).

| 指导分析词 | Analysis Workspace术语 |
| --- | --- |
| 事件 | 度量 |
| 用户 | 人员 |
| 属性 | 维度 |
| 值 | 维度项 |
| 区段 | 过滤器 |

{style="table-layout:auto"}

+++

+++**关于引导式分析和Analysis Workspace方法报告的方式有哪些差异？**

同时 [Analysis Workspace](../analysis-workspace/home.md) 和引导式分析使用相同的基础数据，每种工具允许您形成对这些数据的查询的方式各不相同。

* **Analysis Workspace是一种以维度为中心的体验。** 表通常由维行组成，而列通常为量度。 可在行和列中应用过滤器以获取所需数据。

* **引导式分析是一种以事件为中心的体验。** 每个分析都从选择事件开始，然后可以添加维度和过滤器来优化该事件数据。

![结构](assets/structure.png)

请考虑以下示例，其中您侧重于网站主页的相关数据。 团队提出类似的问题，但分析方法可能不同。

* 典型的以维度为中心的Analysis Workspace方法是，“让我们看一下主页，看看它收到了多少次页面查看。”

  ![以Dimension为中心](assets/dimension-centered.png)

* 典型的以事件为中心的引导式分析方法是，“有多少用户查看了主页？”

  ![以事件为中心](assets/event-centered.png)

+++
