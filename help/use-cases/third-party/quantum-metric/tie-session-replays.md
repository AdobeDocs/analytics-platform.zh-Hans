---
title: 系数量度会话重播到Customer Journey Analytics中的数据
description: 链接量子量度会话会重播CJA数据，以便更好地了解“内容”背后的“原因”。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 752e8564c341cf02b5378a12a820f52ca6164a3d
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 1%

---

# 系数量度会话重播到Customer Journey Analytics中的数据

通过将Quantum Metric会话重播与CJA数据关联，客户可以更好地了解“内容”背后的“原因”。  Workspace可用于发现存在摩擦的会话，然后单击超链接会话ID以在Quantum Metric中浏览会话重放。  通过此数据，可查看会话中的行为并更好地了解导致消费者摩擦的因素。  通过与CJA绑定的会话重播，您可以捕获体验中有关客户行为的关键上下文。

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

现在，每个会话ID都是一个可单击的链接。 有关向Analysis Workspace维度项目添加超链接的详细信息，请参阅[在自由格式表中创建超链接](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)。

## 步骤2从Customer Journey Analytics查看会话

找到想要探索会话重放的耐用区段后，可将其应用于包含会话ID链接的面板，并按区段进行筛选。 该表将返回该区段中的所有会话，您可以单击其中的任何会话以在量子度量中进一步探索。

在[https://www.quantummetric.com/platform/session-replay](https://www.quantummetric.com/platform/session-replay)上了解有关量子度量会话重播的更多信息。 有关任何其他资源，请与您的Quantum Metric客户支持代表联系，或通过Quantum Metric [客户请求门户](https://community.quantummetric.com/s/public-support-page)提交请求。

