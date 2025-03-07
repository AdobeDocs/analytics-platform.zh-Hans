---
title: 在Customer Journey Analytics中收集量子度量会话ID
description: 修改您的实施以包含会话ID，以便您可以在Customer Journey Analytics中分析它们。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
source-git-commit: d71f39d25c52b0389d0441f238cb5b1809986b2d
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 1%

---

# 在Customer Journey Analytics中收集量子度量会话ID

某些用例（如[绑定量子度量会话重播](tie-session-replays.md)或[使用量子度量热图](heatmap.md)）要求您修改实现以收集量子度量会话ID。 本页概述了将该数据成功引入现有实施的过程。

这些步骤假定您使用Adobe Experience Platform数据收集中的标记。 如果您的组织不使用标记，则可以调整这些数据收集方法，以便手动实施Web SDK。

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

有关详细信息，请参阅[Quantum量度标记扩展](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric)文档。

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

现在，每个会话ID都是一个可单击的链接。 这些链接会将您转到新选项卡中的量子度量，从而允许您更详细地分析该特定会话。 有关向Analysis Workspace维度项目添加超链接的详细信息，请参阅[在自由格式表中创建超链接](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)。
