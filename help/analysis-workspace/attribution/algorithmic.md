---
title: 算法归因
description: 有关算法归因模型的详细信息。
exl-id: ce174253-4864-4fb0-8a96-a134a9fc9fba
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 80%

---

# 算法归因

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 略有不同。[了解更多...](/help/getting-started/cja-aa.md)

>[!NOTE]
>
>**[!UICONTROL 算法]** 属性当前处于有限测试中。有关更多信息，请参阅[Adobe Analytics功能发布](https://experienceleague.adobe.com/docs/analytics/landing/an-releases.html)。

Analysis Workspace 中的算法[归因模型](models.md)与其他模型有所不同，因为该模型会使用统计技术为报表或自由格式表中的各维度项目分配点数。与Analysis Workspace中的所有其他归因模型一样，该模型也可用于任何维度或量度，并支持无限制的过滤器和划分，并为表中的维度分配100%的转化（也称为“分数”归因）。

归因算法基于合作博弈理论中的 Harsanyi Dividend 算法。Harsanyi Dividend 算法是对“沙普利值”解决方案（以诺贝尔经济学奖获得者罗伊德·沙普利 (Lloyd Shapley) 命名）的推广形式，用于为对结果具有不同贡献的各参与者分配功能值（点数）。

概言之，在对每个接触点的转化点数进行归因计算时，会将回顾时间范围内的每个营销接触点视为由各参与者组成的联盟，其中必须在每位参与者之间平均分配剩余价值。按照递归方式，每个联盟的剩余价值分配取决于由先前的每个子联盟（即先前参与的维度项目）产生的剩余价值。有关更多详细信息，请参阅约翰·海萨尼 (John Harsanyi) 和罗伊德·沙普利的原文：

* Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>仅当指定的回顾时间范围内存在多个接触点时，算法归因的结果才会与其他模型不同。无论使用何种归因模型，具有单个接触点的转化均可获得 100% 的点数。
