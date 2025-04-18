---
title: 系数量度会话重播到Customer Journey Analytics中的数据
description: 链接量子量度会话会重播CJA数据，以便更好地了解“内容”背后的“原因”。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 25a2c549c27918f80202bde4cd30e305f4a295f3
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 1%

---

# 系数量度会话重播到Customer Journey Analytics中的数据

通过将Quantum Metric会话重播与CJA数据关联，客户可以更好地了解“内容”背后的“原因”。  Workspace可用于发现存在摩擦的会话，然后单击超链接会话ID以在Quantum Metric中浏览会话重放。  通过此数据，可查看会话中的行为并更好地了解导致消费者摩擦的因素。  通过与CJA绑定的会话重播，您可以捕获体验中有关客户行为的关键上下文。

## 先决条件

这些步骤假定您使用Adobe Experience Platform数据收集中的标记。 如果您的组织不使用标记，则可以调整这些数据收集方法，以便手动实施Web SDK。

有关详细信息，请参阅[Quantum量度标记扩展](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric)文档。

## 步骤1：使用量度标记扩展捕获量度会话ID

按照以下步骤将量子量度会话ID附加到您发送到Adobe Experience Platform的数据。

1. 在标记UI中使用Quantum Metric扩展将数据发送到Quantum Metric。
1. 创建四个数据元素：
   1. 一个从名为`QuantumMetricSessionID`的量子量度Cookie中捕获量子量度会话ID
   1. 从`localStorage`中提取量子度量会话ID的服务器。 有时，此数据元素的加载速度会比另一个数据元素中设置的Cookie更快。
   1. 使用数据元素助理或自定义JavaScript从`localStorage`数据元素中提取`s`节点。
   1. 一个使用逻辑来首先查找Cookie数据元素并将其返回到XDM对象路径（如果找到）。 如果未定义，请尝试查看提取的`localStorage`对象数据元素。
1. 将最终量子量度会话ID数据元素发送到在每个事件中发送的XDM对象。

>[!NOTE]
>有时Web SDK的运行速度会比Quantum Metric代码更快。 在这些情况下，会话ID会在后续点击时发送。 如果访客跳出，则在这些实例中不会收集会话ID。

## 步骤2：确认包含的数据集字段

确认连接中的数据集现在具有所需数据集中的量子量度会话ID。

## 步骤3：添加量子度量会话ID作为可用维度

编辑现有数据视图，在Customer Journey Analytics中将会话ID添加为可用维度。

1. 登录到[experience.adobe.com](https://experience.adobe.com)。
1. 导航到Customer Journey Analytics，然后在顶部菜单中选择&#x200B;**[!UICONTROL 数据视图]**。
1. 选择所需的现有数据视图。
1. 在左侧找到量子度量会话ID字段列表，并将其拖动到中心的维度区域。
1. 在右窗格中，将[persistence](/help/data-views/component-settings/persistence.md)设置设置为“Session”。
1. 单击&#x200B;**[!UICONTROL 保存]**。

## 步骤4：配置Workspace以适应会话ID维度

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

## 步骤5：从Customer Journey Analytics查看会话

找到想要探索会话重放的耐用区段后，可将其应用于包含会话ID链接的面板，并按区段进行筛选。 该表返回该区段中的所有会话，您可以单击其中的任何会话以在量子度量中进一步探讨。

有关详细信息，请参阅[Quantum量度上的会话重播企业指南](https://www.quantummetric.com/resources/ebook/the-enterprise-guide-to-session-replay)。 您还可以联系您的Quantum Metric客户支持代表，或通过[Quantum Metric客户请求门户](https://community.quantummetric.com/s/public-support-page)提交请求。
