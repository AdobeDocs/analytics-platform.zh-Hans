---
title: 上下文感知会话
description: 数据视图中的设置，可用于定义上下文感知会话。
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 6235fbb128098e2a624d5fd4fd72c2c583cfd277
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 3%

---


# 上下文感知会话

数据视图中的上下文感知会话会更改Customer Journey Analytics根据连接中的数据计算会话的方式。

在 [!UICONTROL 设置] 选项卡中，您可以以任何方式定义会话，以匹配人员与您的数字体验的交互方式。 上下文感知会话定义是非破坏性的，不会更改基础数据。 您可以设置多个数据视图，每个视图都具有其特定的上下文感知会话定义，作为工作区项目的基础。

要为数据视图定义会话的上下文，请执行以下操作：

1. 选择 **[!UICONTROL 数据视图]** 在Customer Journey AnalyticsUI中。

1. 创建新数据视图或编辑现有数据视图。 请参阅 [创建或编辑数据视图](create-dataview.md) 以了解更多信息。

1. 选择&#x200B;**[!UICONTROL 设置]**&#x200B;选项卡。下方 [!UICONTROL 会话设置]：

   1. 输入值 **[!UICONTROL 会话超时]** 在 [!UICONTROL 分钟]， [!UICONTROL 小时]， [!UICONTROL 天]，或 [!UICONTROL 周]. 会话超时决定在启动新会话之前，会话可以空闲多久（不发生事件）。

   2. 从中选择一个量度 **[!UICONTROL 将指标拖放到此处]** 在下面列出 [!UICONTROL 使用量度开始新会话]. 或者，您可以从左侧窗格将量度拖放到 **[!UICONTROL 放置量度字段]**. 所选量度定义新会话的开始。 您可以定义多个量度。

1. 选择 **[!UICONTROL 保存]** 或 **[!UICONTROL 保存并完成]** 以保存上下文感知会话定义。

