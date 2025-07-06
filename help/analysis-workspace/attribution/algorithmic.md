---
title: 算法归因
description: 了解算法归因模型的详细信息。
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 42%

---

# 算法归因

Analysis Workspace 中的算法[归因模型](models.md)与其他模型有所不同，因为该模型会使用统计技术为报表或自由格式表中的各维度项目分配点数。与Analysis Workspace中的所有其他归因模型一样，算法归因可用于任何维度或量度。 算法归因支持无限分段和细分，并为表中的一个或多个维度分配100%的转化（也称为“分数”归因）。


>[!BEGINSHADEBOX]

观看演示视频的![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [算法归因](https://video.tv.adobe.com/v/40050?quality=12&learn=on&captions=chi_hans){target="_blank"}。

>[!ENDSHADEBOX]


归因算法基于合作博弈理论中的 Harsanyi Dividend 算法。Harsanyi Dividend算法是Shapley值解(以诺贝尔经济学奖获得者罗伊德·沙普利(Lloyd Shapley)命名)的推广形式，用于为对结果具有不同贡献的各参与者分配信用。

从高层面来看，在为每个接触点计算转化点数的归因时，会将回顾时间范围内的每个营销接触点视为一个参与者联盟。 对于由参与者组成的联盟，盈余必须公平分配。 每个联盟的剩余价值分配取决于每个子联盟递归产生的剩余价值。

有关更多详细信息，请参阅约翰·海萨尼和劳埃德·沙普利的原稿：

* Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>仅当指定的回顾时间范围内存在多个接触点时，算法归因的结果才会与其他模型不同。无论使用何种归因模型，具有单个接触点的转化均可获得 100% 的点数。
