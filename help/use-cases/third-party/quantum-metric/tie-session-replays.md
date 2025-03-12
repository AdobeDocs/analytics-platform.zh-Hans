---
title: 系数量度会话重播到Customer Journey Analytics中的数据
description: 链接量子量度会话会重播CJA数据，以便更好地了解“内容”背后的“原因”。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: d722e88d163dd99aa7b98c6fa6cd75028d7d9e6f
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 1%

---

# 系数量度会话重播到Customer Journey Analytics中的数据

通过将Quantum Metric会话重播与CJA数据关联，客户可以更好地了解“内容”背后的“原因”。  Workspace可用于发现存在摩擦的会话，然后单击超链接会话ID以在Quantum Metric中浏览会话重放。  通过此数据，可查看会话中的行为并更好地了解导致消费者摩擦的因素。

## 先决条件

此用例要求您将Quantum Metric的会话ID与其余实施一起收集。 请参阅[在Customer Journey Analytics中收集Quantum量度会话ID](collect-session-id.md)，了解如何修改您的实施。

## 步骤1：配置Workspace以适应会话ID维度

在Workspace中创建自由格式表并进行配置，以便会话ID值直接链接到Quantum Metric。

1. 登录到[experience.adobe.com](https://experience.adobe.com)。
1. 导航到Customer Journey Analytics，然后在顶部菜单中选择&#x200B;**[!UICONTROL Workspace]**。
1. 选择现有项目，或创建项目。
1. 创建[自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。
1. 将会话ID维度拖动到Workspace画布。
1. 右键单击维度列标题，然后选择&#x200B;**[!UICONTROL 为所有维度项目创建超链接]**。
1. 选择&#x200B;**[!UICONTROL 创建自定义URL]**。
1. 粘贴以下URL结构：

   ```
   https://adobe.quantummetric.com/#/replay/cookie:$value
   ```

1. 单击&#x200B;**[!UICONTROL 创建]**。

现在，每个会话ID都是一个可单击的链接。 这些链接会将您转到新选项卡中的量子度量，从而允许您更详细地分析该特定会话。 有关向Analysis Workspace维度项目添加超链接的详细信息，请参阅[在自由格式表中创建超链接](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)。

## 步骤2从Customer Journey Analytics查看会话

创建包含可单击链接的Workspace报表后，您可以使用Customer Journey Analytics中的过滤器来识别可在Quantum Metric中进一步分析的有趣会话。
该表将返回该区段中的所有会话，您可以单击其中的任何会话来进一步了解QM。  要了解有关量子量度会话重放的更多信息，请访问https://www.quantummetric.com/platform/session-replay

