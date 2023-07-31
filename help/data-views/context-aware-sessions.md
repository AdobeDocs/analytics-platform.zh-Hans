---
title: 上下文感知会话
description: 数据视图中的设置，可用于定义上下文感知会话。
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 5e4bf2985a0ec75cc0120e2a9549d720077cd5cc
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 83%

---


# 上下文感知会话

数据视图中的上下文感知会话改变了 Customer Journey Analytics 根据连接中的数据计算会话的方式。

在数据视图的[!UICONTROL 设置]选项卡中，可通过任何方式定义会话，以匹配人员与您的数字体验交互的方式。上下文感知会话定义是无损的，不会更改底层数据。您可以将多个数据视图（每个视图都有其特定的上下文感知会话定义）设置为工作区项目的基础。

要定义数据视图的会话上下文，请执行以下操作：

1. 在 Customer Journey Analytics UI 中，选择&#x200B;**[!UICONTROL 数据视图]**。

1. 创建新的或编辑现有的数据视图。有关更多信息，请参阅[创建或编辑数据视图](create-dataview.md)。

1. 选择&#x200B;**[!UICONTROL 设置]**&#x200B;选项卡。在[!UICONTROL 会话设置]下：

   1. 输入&#x200B;**[!UICONTROL 会话超时]**&#x200B;的值（以[!UICONTROL 分钟]、[!UICONTROL 小时]、[!UICONTROL 天]或[!UICONTROL 周]为单位）。会话超时可确定在开始新会话之前，会话可处于空闲状态（无事件发生）的时长。

   2. 从[!UICONTROL 使用量度发起新会话]下的&#x200B;**[!UICONTROL 在此处放置量度]**&#x200B;列表中选择量度。或者，您可以从左侧窗格将量度拖放到 **[!UICONTROL 放置量度字段]**. 所选量度定义新会话的开始。您可以定义多个量度。

1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;或&#x200B;**[!UICONTROL 保存并完成]**&#x200B;以保存上下文感知会话定义。

