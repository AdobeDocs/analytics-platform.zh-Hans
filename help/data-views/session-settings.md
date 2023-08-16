---
title: 会话设置
description: 数据视图中的设置，可用于定义会话的长度以及启动新会话的触发器
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 25ff6feda28f0447927a52f44aed800cdd89e0cb
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 38%

---


# 会话设置

数据视图中的会话设置会更改Customer Journey Analytics根据连接中的数据计算会话的方式。

在数据视图的&#x200B;**[!UICONTROL 设置]**&#x200B;选项卡中，可通过任何方式定义会话，以匹配人员与您的数字体验交互的方式。会话设置定义是非破坏性的，不会更改基础数据。 您可以将多个数据视图（每个视图都有其各自的特定会话设置定义）设置为工作区项目的基础。

要定义数据视图的会话上下文，请执行以下操作：

1. 在 Customer Journey Analytics UI 中，选择&#x200B;**[!UICONTROL 数据视图]**。

2. 创建新的或编辑现有的数据视图。有关更多信息，请参阅[创建或编辑数据视图](create-dataview.md)。

3. 选择&#x200B;**[!UICONTROL 设置]**&#x200B;选项卡。在[!UICONTROL 会话设置]下：

   1. 输入&#x200B;**[!UICONTROL 会话超时]**&#x200B;的值（以[!UICONTROL 分钟]、[!UICONTROL 小时]、[!UICONTROL 天]或[!UICONTROL 周]为单位）。会话超时可确定在开始新会话之前，会话可处于空闲状态（无事件发生）的时长。

      如果您有兴趣分析大多数在线交互，请使用较短的会话超时（例如30分钟）。 例如，分析访问在线商店产品页面的用户档案是否确实将产品添加到购物车，甚至在线购买。

      如果您要合并在线和离线数据，并想要分析已购买您的一种或多种产品的客户是否在购买后的前三个月内致电您的联系中心，请使用较长的会话超时（例如3个月）。


   2. 从&#x200B;**[!UICONTROL 使用量度发起新会话]**&#x200B;下的&#x200B;**[!UICONTROL 在此处放置量度]**&#x200B;列表中选择量度。或者，还可将量度从左窗格拖放到&#x200B;**[!UICONTROL 放置量度字段]**&#x200B;上。所选量度定义新会话的开始。您可以定义多个量度。

      您可以使用任何类型的量度来定义新会话。 例如，假设您希望在每次用户档案启动您的移动应用程序时定义一个新会话。 在 **[!UICONTROL 数据视图]** > **[!UICONTROL 组件]**，您可以定义一个量度类型的组件，名为 **[!UICONTROL 启动次数]**，基于 **[!UICONTROL appInteraction]** **[!UICONTROL 名称]** 架构字段。 您可以进一步指定 **[!UICONTROL 启动次数]** 量度组件，用于仅在值匹配时计算值 `launch`.

      ![应用程序交互量度组件启动次数](assets/component-launches.png)

      然后拖放或选择 **[!UICONTROL 启动次数]** 量度，用作定义新会话的量度。

      ![会话设置启动项](assets/session-settings-launches-metric.png)



4. 选择 **[!UICONTROL 保存]** 或 **[!UICONTROL 保存并完成]** 以保存会话设置定义。

