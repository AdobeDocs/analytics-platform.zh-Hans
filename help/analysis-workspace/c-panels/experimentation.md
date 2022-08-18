---
description: 了解如何在CJA实验面板中分析A/B测试的结果。
title: 实验面板
feature: Panels
source-git-commit: 2c217c7d31819ac8eb27d2d1010e0df787601e21
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 4%

---


# 实验面板

>[!NOTE]
>
>此功能当前正在进行[小范围测试](/help/release-notes/releases.md)。

的 **[!UICONTROL 实验]** 通过面板，您可以比较不同的用户体验、营销或消息传递变量，从而确定哪个变量最适合产生特定结果。 您可以评估来自任何实验平台(在线、离线、Adobe解决方案、Adobe Journey Optimizer甚至BYO（自带）数据)的任何A/B实验的提升度和置信度。

>[!IMPORTANT]
>
>此时， [Adobe Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=zh-Hans) (A4T)数据无法在 [!UICONTROL 实验] 的上界。

## 访问控制

所有Customer Journey Analytics(CJA)用户都可以使用“实验”面板。 无需管理员权限或其他权限。 但是，设置需要数据视图中只有管理员才能分配的标签。

## 术语

* **实验**:实验是针对向最终用户展示的体验进行的一组变体，旨在确定哪些体验最好永久保留。 实验由两个或多个变量组成，其中一个变量被视为控制变量。

* **变量**:为了确定更好的替代方案而正在比较的最终用户体验中的两个或多个更改之一。 必须选择一个变量作为控制，并且只能将一个变量视为控制变量。

* **控制**:表示用户体验现状或默认状态的特定变体。 与其他变量进行比较。

* **标准化量度**:运行测试的基础（会话或人员）。 例如，测试可能会比较多个变体的转化率，其中转化率计算为每个会话的转化率或每人的转化率。

* **转化量度**:用户比较变体与的量度。 对于转化量度（无论最高还是最低），具有最理想结果的变量将被宣布为实验的“入选者”。

## 步骤1:创建与实验数据集的连接

在您的实验数据 [摄取](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=en) 进入Adobe Experience Platform, [在CJA中创建连接](/help/connections/create-connection.md) 到一个或多个实验数据集。

## 步骤2:在数据视图中添加上下文标签

在CJA数据视图设置中，管理员可以添加 [上下文标签](/help/data-views/component-settings/overview.md) 到维度或量度和CJA服务，例如 [!UICONTROL 实验] 面板可以将这些标签用于其用途。 实验面板使用两个预定义的标签：

* [!UICONTROL 实验]
* [!UICONTROL 变体]

在包含实验数据的数据视图中，选取两个维度，一个包含实验数据，一个包含变体数据。 然后，使用 **[!UICONTROL 实验]** 和 **[!UICONTROL 变体]** 标签。

![上下文标签](assets/context-label.png)

如果不显示这些标签，“实验”面板将不起作用。

## 步骤3:配置“实验”面板

1. 在CJA工作区中，将“实验”面板拖到项目中。

![实验面板](assets/experiment.png)




