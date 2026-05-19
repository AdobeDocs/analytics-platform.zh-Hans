---
description: 了解如何在Analysis Workspace中使用实时报表。
title: 使用实时报表
feature: Real-time Reporting
role: User
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
autotag-review: '2026-05-19T08:47:15.932Z'
TQID: 'https://experienceleague.adobe.com/t20pdV4qS-FIBGrxOXAD5xAD58f4gtN74uheJ94sK4s'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: d1779026-aeed-458e-a1c7-839d4acac922
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 239
ht-degree: 12%

---

# 使用实时报告 {#use-real-time-reporting}

>[!CONTEXTUALHELP]
>id="workspace_panel_realtime_refresh"
>title="实时刷新"
>abstract="启用后，可实时刷新此面板中的数据和可视化内容。"

要使用实时报表，请在Workspace项目中的以下任何面板上启用&#x200B;**[!UICONTROL 实时刷新]**&#x200B;切换开关：

* [空白面板](/help/analysis-workspace/c-panels/blank-panel.md)
* [自由格式表](/help/analysis-workspace/c-panels/freeform-panel.md)
* [归因](/help/analysis-workspace/c-panels/attribution.md)
* [下一项或上一项](/help/analysis-workspace/c-panels/next-previous.md)

您会看到一条消息，其中包含数据最近刷新时的时间戳。 例如： [!UICONTROL &#x200B; *上次刷新时间： 07:55下午*]。

从下拉菜单中选择要报告的实时时段。 可用选项包括：

* [!UICONTROL 最近15分钟]
* [!UICONTROL 最近30分钟]
* [!UICONTROL 上一小时]
* [!UICONTROL 最近8小时]
* [!UICONTROL 最近24小时]

现在，当启用了实时刷新面板的浏览器选项卡处于活动状态时，面板中的所有可视化图表每分钟更新一次，最多更新30分钟。

例如，查看下面的&#x200B;**[!UICONTROL 实时报表面板]**&#x200B;快照，该快照在时间从&#x200B;**[!UICONTROL *06:26pm*]**&#x200B;移至&#x200B;**[!UICONTROL *06:27下午&#x200B;*]**&#x200B;时刷新了&#x200B;**[!UICONTROL &#x200B;总收入/小时&#x200B;]**&#x200B;条形图可视化图表和&#x200B;**[!UICONTROL &#x200B;总收入/小时&#x200B;]**&#x200B;自由格式表。

![实时刷新](assets/real-time-refresh.gif)

30分钟后，或浏览器选项卡处于非活动状态时，**[!UICONTROL 实时刷新]**&#x200B;切换会自动禁用，并且实时更新将停止。

禁用实时刷新切换后，面板（及其中的所有可视化图表）即会返回[使用Customer Journey Analytics](real-time.md#how-it-works)中的标准报表数据和功能。
