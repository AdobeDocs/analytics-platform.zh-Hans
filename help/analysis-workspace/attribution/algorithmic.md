---
title: 算法属性
description: 算法归因模型的详细信息。
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 7%

---


# 算法属性

>[!NOTE]
>
>您正在查看Customer Journey Analytics中的Analysis Workspace文档。 其功能集与传统Adobe [Analytics的Analysis Workspace略有不同](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html)。 [了解更多...](/help/getting-started/cja-aa.md)

>[!NOTE]
>
>**[!UICONTROL 算法归因]** 目前处于有限测试中。 有关 [更多信息](https://docs.adobe.com/content/help/zh-Hans/analytics/landing/an-releases.html) ，请参阅AdobeAnalytics功能版本。

Analysis Workspace中 [的算法归因模型](models.md) (Algorithmic attribution model)与其他模型不同之处在于它使用统计技术在报表或自由表格的维度值之间分配信用。 与Analysis Workspace中的所有其他归因模型一样，它可用于任何维度或指标，并支持无限细分和细分，并将100%的转换分发到表中的维度（也称为“分数”归因）。

基于合作博弈论的Harsanyi Danyis算法用于归因。 哈桑尼派息是沙普利价值解决方案（以诺贝尔经济学奖获得者劳埃德·沙普利命名）的概括，用来在对结果贡献不均的游戏中在玩家之间分配信用。

在高层面，每个接触点的转换信用的归因计算将回顾窗口内的每个营销接触点视为必须公平分配盈余的玩家联盟。 每个联盟的盈余分配根据每个子联盟（或先前参与的维度值）以递归方式先前创建的盈余来确定。 有关详细信息，请参阅约翰·哈萨尼和劳埃德·沙普利的原文：

* 沙普利，劳埃德·S。 (1953)。 N人游戏的价值。 *对博弈论的贡献，2(28)*,307-317。
* 哈萨尼，约翰C. (1963)。 n人合作博弈的简化协商模型。 *《国际经济评论》* 4(2),194-220年。

>[!NOTE]
>
>仅当给定回顾窗口中存在多个接触点时，算法归因的结果才与其他模型不同。 无论归因模型如何，单个接触点的转化率均可获得100%的回报。
