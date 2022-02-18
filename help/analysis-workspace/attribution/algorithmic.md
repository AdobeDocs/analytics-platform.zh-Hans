---
title: 算法归因
description: 有关算法归因模型的详细信息。
feature: Attribution
exl-id: ce174253-4864-4fb0-8a96-a134a9fc9fba
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '298'
ht-degree: 100%

---

# 算法归因

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html) 略有不同。[了解详情...](/help/getting-started/cja-aa.md)

下面是算法归因的视频概述：

>[!VIDEO](https://video.tv.adobe.com/v/36205/?quality=12)

Analysis Workspace 中的算法[归因模型](models.md)与其他模型有所不同，因为该模型会使用统计技术为报表或自由格式表中的各维度项分配点数。与 Analysis Workspace 中的所有其他归因模型一样，该模型也可以用于任何维度或量度，支持无限过滤器和划分，并为表中的维度分配 100% 的转化率（因而也称为“分数”归因）。

归因算法基于合作博弈理论中的 Harsanyi Dividend 算法。Harsanyi Dividend 算法是对“沙普利值”解决方案（以诺贝尔经济学奖获得者罗伊德·沙普利 (Lloyd Shapley) 命名）的推广形式，用于为对结果具有不同贡献的各参与者分配功能值（点数）。

概言之，在对每个接触点的转化点数进行归因计算时，会将回顾时间范围内的每个营销接触点视为由各参与者组成的联盟，其中必须在每位参与者之间平均分配剩余价值。按照递归方式，每个联盟的剩余价值分配取决于由先前的每个子联盟（即先前参与的维度项目）产生的剩余价值。有关更多详细信息，请参阅约翰·海萨尼 (John Harsanyi) 和罗伊德·沙普利的原文：

* Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!IMPORTANT]
>
>仅当指定的回顾时间范围内存在多个接触点时，算法归因的结果才会与其他模型不同。无论使用何种归因模型，具有单个接触点的转化均可获得 100% 的点数。
