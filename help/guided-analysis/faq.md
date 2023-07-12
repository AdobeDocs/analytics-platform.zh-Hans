---
title: 引导式分析常见问题解答
description: 有关引导式分析的常见问题解答。
exl-id: 32bfce23-a59c-45cb-b1cd-82f048fb13d2
feature: Guided Analysis
source-git-commit: 23d3e6a9662cda932a376c09849ab078d22830dc
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---

# 引导式分析常见问题解答

{{release-limited-testing}}

有关引导式分析的常见问题解答。

+++**引导式分析是否对每个人都可用？**

否；引导式分析是Customer Journey Analytics的付费附加功能。 如果您希望开始使用此加载项，请联系您的Adobe客户团队。

+++

+++**使用引导式分析需要进行哪些实施更改？**

如果您已在Customer Journey Analytics中使用Analysis Workspace，则无需进行其他实施更改。 引导式分析使用与Analysis Workspace相同的数据视图和连接。 载入和使用任何项目类型的过程对于所有Customer Journey Analytics（包括引导式分析）都是相同的。

+++

+++**术语在引导式分析内外如何相互关联？**

引导式分析使用的术语在产品分析行业中更为常用。 在引导式分析和Analysis Workspace之间切换时，可引用此表。

| 指导分析词 | Analysis Workspace术语 |
| --- | --- |
| 事件 | 度量 |
| 用户 | 人员 |
| 属性 | 维度 |
| 值 | 维度项 |
| 区段 | 过滤器 |

{style="table-layout:auto"}

+++

+++**Analysis Workspace和引导式分析方法的分析方式有哪些区别？**

虽然Analysis Workspace和引导式分析使用相同的底层数据，但每种工具允许您形成该数据查询的方式各不相同。

* **Analysis Workspace是一种以维度为中心的体验。** 表通常由维度项目行组成，而列通常为量度。 您可以将过滤器同时应用于行和列，以获取所需的数据。

* **引导式分析是一种以事件为中心的体验。** 可视化图表侧重于事件，使用维度和过滤器补充这些数据。

![结构](assets/structure.png)

请考虑以下示例，其中您侧重于网站主页的相关数据。 团队提出类似的问题，但分析方法可能不同。

* 典型的以维度为中心的Analysis Workspace方法是，“主页收到了多少次页面查看？”

  ![Dimension居中](assets/dimension-centered.png)

* 典型的以事件为中心的引导式分析方法是，“有多少用户查看了主页？”

  ![以事件为中心](assets/event-centered.png)

这些语句说明了实现同一报告的两种不同方法，具体取决于您的事件管理策略。

+++
