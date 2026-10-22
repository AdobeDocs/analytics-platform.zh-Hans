---
title: 算法归因
description: 了解算法归因模型的详细信息。
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
autotag-review: '2026-05-19T07:20:44.651Z'
TQID: 'https://experienceleague.adobe.com/XPFzwdaB2d1PaGEyiYSlzri7Luo4E2uqlMdKClsExdw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: c91f8bd2-df97-4c6a-afcd-f1cde8221302
    internal-label: Attribution
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: c6330935bb6b36fab622b7884e9182ebd4bdc610
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 43%
---
# 算法归因

>[!NOTE]
>
>您必须具有Customer Journey Analytics **Ultimate**&#x200B;程序包才能使用本节中介绍的功能。 如果您不确定您拥有的是哪个 Customer Journey Analytics 包，请联系您的管理员。

Analysis Workspace 中的算法[归因模型](models.md)与其他模型有所不同，因为该模型会使用统计技术为报表或自由格式表中的各维度项目分配点数。 与Analysis Workspace中的所有其他归因模型一样，算法归因可用于任何维度或量度。 算法归因支持无限分段和细分，并为表中的一个或多个维度分配100%的转化（也称为“分数”归因）。

<!-- 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Algorithmic attribution](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/algorithmic-model-in-attribution-iq){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

归因所用的算法基于合作博弈理论中的 Harsanyi Dividend。 Harsanyi Dividend算法是Shapley值解(以诺贝尔经济学奖获得者罗伊德·沙普利(Lloyd Shapley)命名)的推广形式，用于为对结果具有不同贡献的各参与者分配信用。

在为每个接触点计算转化点数的归因时，会将回顾时间范围内的每个营销接触点视为一个参与者联盟。 对于由参与者组成的联盟，盈余必须公平分配。 每个联盟的剩余价值分配取决于每个子联盟之前递归产生的剩余价值。

有关更多详细信息，请参阅约翰·海萨尼和劳埃德·沙普利的原稿：

* 夏普利，劳埃德S (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi，约翰C (1963). n 人合作博弈的简化议价模型。 *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>仅当指定的回顾时间范围内存在多个接触点时，算法归因的结果才会与其他模型不同。 无论使用何种归因模型，具有单个接触点的转化均可获得 100% 的点数。
