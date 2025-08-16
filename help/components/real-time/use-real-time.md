---
description: 了解如何在Analysis Workspace中使用实时报表。
title: 使用实时报表
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta 版"
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
source-git-commit: b833914e7066fa660f856737d6b8a6392aae2feb
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 14%

---

# 使用实时报告 {#use-real-time-reporting}

>[!CONTEXTUALHELP]
>id="workspace_panel_realtime_refresh"
>title="实时刷新"
>abstract="启用后，可实时刷新此面板中的数据和可视化内容。"

{{release-limited-testing}}

要使用实时报表，请在Workspace项目中的以下任何面板上启用&#x200B;**[!UICONTROL 实时刷新]**&#x200B;切换开关：

* [”空白“面板](/help/analysis-workspace/c-panels/blank-panel.md)
* [自由格式表](/help/analysis-workspace/c-panels/freeform-panel.md)
* [归因](/help/analysis-workspace/c-panels/attribution.md)
* [下一项或上一项](/help/analysis-workspace/c-panels/next-previous.md)

您会看到一条消息，其中包含数据最近刷新时的时间戳。 例如： [!UICONTROL  *上次刷新时间： 07:55下午*]。

从下拉菜单中选择要报告的实时时段。 可用选项包括：

* [!UICONTROL 最近15分钟]
* [!UICONTROL 最近30分钟]
* [!UICONTROL 上一小时]
* [!UICONTROL 最近8小时]
* [!UICONTROL 最近24小时]

现在，当启用了实时刷新面板的浏览器选项卡处于活动状态时，面板中的所有可视化图表每分钟更新一次，最多更新30分钟。

例如，查看下面的&#x200B;**[!UICONTROL 实时报表面板]**&#x200B;快照，该快照在时间从&#x200B;**[!UICONTROL 06]**&#x200B;移至&#x200B;**[!UICONTROL 06]**&#x200B;下午&#x200B;**[!UICONTROL *时刷新了:26pm*]**&#x200B;总收入/小时&#x200B;**[!UICONTROL *条形图可视化图表和:27总收入/小时&#x200B;*]**自由格式表。

![实时刷新](assets/real-time-refresh.gif)

30分钟后，或浏览器选项卡处于非活动状态时，**[!UICONTROL 实时刷新]**&#x200B;切换会自动禁用，并且实时更新将停止。
