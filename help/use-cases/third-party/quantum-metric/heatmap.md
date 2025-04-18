---
title: 在Customer Journey Analytics中使用量子度量热图
description: 使用量子量度热图数据，更好地了解页面级参与度并根据消费者行为优化页面。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
source-git-commit: 25a2c549c27918f80202bde4cd30e305f4a295f3
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 1%

---

# 在Customer Journey Analytics中使用量子度量热图

将Quantum量度热映射关联到CJA数据可让您更好地了解页面级参与度并根据消费者行为优化页面。 Workspace可用于了解消费者用户流并查看消费者遵循的路径从一个页面转到下一个页面。 然后，您可以单击超链接页面URL以直观地热图展示用户如何与内容互动。 通过将Quantum Metric Heatmapping链接到CJA，您现在可以将页面级交互与业务结果关联，从而将您的分析提升到新的水平。

该表将返回该区段中的所有会话，您可以单击其中的任何会话来进一步了解QM。  要了解有关量子量度会话重放的更多信息，请访问https://www.quantummetric.com/platform/session-replay

## 先决条件

您必须有权使用量子量度的&#x200B;**UX Ops**&#x200B;程序包，才能访问量子量度的热图功能。

## 步骤1：在Workspace中创建自由格式表并进行配置，以便会话ID值直接链接到Quantum Metric。

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
1. 测试其中一个链接，查看它是否在URL中打开且量子量度扩展可见。 这些链接将在新选项卡中打开，以便您的Workspace项目保持打开状态。

## 步骤2：通过单击Customer Journey Analytics中的链接来查看热图

找到要浏览热映射的页面后，可将其应用到所需的面板。 该表返回一个URL，允许您浏览热图、滚动深度以及使用量子度量进行交互的关键区域。 有关详细信息，请参阅[量子度量热图产品概述](https://www.quantummetric.com/platform/interaction-heatmaps)。 您还可以联系您的Quantum Metric客户支持代表，或通过[Quantum Metric客户请求门户](https://community.quantummetric.com/s/public-support-page)提交请求。
