---
title: 在Customer Journey Analytics中使用量子度量热图
description: 使用量子量度热图数据，更好地了解页面级参与度并根据消费者行为优化页面。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
source-git-commit: a0f82948895f3eac86cf00df1dec8abc2f723fc2
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 1%

---

# 在Customer Journey Analytics中使用量子度量热图

将Quantum量度热映射关联到CJA数据可让您更好地了解页面级参与度并根据消费者行为优化页面。 Workspace可用于了解消费者用户流并查看消费者遵循的路径从一个页面转到下一个页面。 然后，您可以单击超链接页面URL以直观地热图展示用户如何与内容互动。

该表将返回该区段中的所有会话，您可以单击其中的任何会话来进一步了解QM。  要了解有关量子量度会话重放的更多信息，请访问https://www.quantummetric.com/platform/session-replay

## 先决条件

此用例要求您将Quantum Metric的会话ID与其余实施一起收集。 请参阅[在Customer Journey Analytics中收集Quantum量度会话ID](collect-session-id.md)，了解如何修改您的实施。

您必须有权使用量子量度的&#x200B;**UX Ops**&#x200B;程序包，才能访问量子量度的热图功能。

## 在Workspace中创建自由格式表并进行配置，以便会话ID值直接链接到Quantum Metric。

1. 登录到[experience.adobe.com](https://experience.adobe.com)。
1. 导航到Customer Journey Analytics，然后在顶部菜单中选择&#x200B;**[!UICONTROL Workspace]**。
1. 选择现有项目，或创建项目。
1. 创建[自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。
1. 将页面URL维度拖到Workspace画布。
1. 右键单击维度列标题，然后选择&#x200B;**[!UICONTROL 为所有维度项目创建超链接]**。
1. 选择&#x200B;**[!UICONTROL 创建自定义URL]**。
1. 粘贴以下URL结构：

   ```
   $value?qm-visible=true
   ```

1. 单击&#x200B;**[!UICONTROL 创建]**。

1. 单击创建，然后测试其中一个链接，以查看它是否在URL中打开并弹出了QM扩展。 请注意 — 它将在单独的选项卡中打开，因此您不会丢失工作。


## 通过单击Customer Journey Analytics中的链接来查看热图

找到要为其浏览热映射的页面后，您可以将其应用于URL所在的面板。 该表将返回一个URL，允许您浏览相关页面的热图、滚动深度以及用于交互的关键区域。  要了解有关量子量度热图的更多信息，请访问https://www.quantummetric.com/platform/interaction-heatmaps


