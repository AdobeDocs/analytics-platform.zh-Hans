---
description: 了解如何在Analysis Workspace中使用实时报表。
title: 使用实时报表
feature: Filters, Segments
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta 版"
source-git-commit: 24834f6a1424a885c6f7b3dcf0ad84375e21b462
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 5%

---


# 使用实时报表

{{release-limited-testing}}

要使用实时报表，请在Workspace项目中的以下任何面板上启用&#x200B;**[!UICONTROL 实时刷新]**&#x200B;切换开关：



* [”空白“面板](/help/analysis-workspace/c-panels/blank-panel.md)
* [“自由格式”面板](/help/analysis-workspace/c-panels/freeform-panel.md)
* ...

您会看到一条消息，其中包含数据最近刷新时的时间戳。 例如： [!UICONTROL &#x200B; *上次刷新时间为晚上07:55*]。

从下拉菜单中选择要报告的实时时段。 可用选项包括：

* [!UICONTROL 最近15分钟]
* [!UICONTROL 最近30分钟]
* [!UICONTROL 上一小时]
* [!UICONTROL 最近8小时]
* [!UICONTROL 最近24小时]

现在，所有可视化图表每分钟更新一次，最多更新30分钟，同时启用了“实时刷新”面板的浏览器选项卡处于活动状态。

![实时刷新](assets/real-time-refresh.gif)

30分钟后，或浏览器选项卡处于非活动状态时，**[!UICONTROL 实时刷新]**&#x200B;切换会自动禁用，并且实时更新将停止。
