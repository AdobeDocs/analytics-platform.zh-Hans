---
title: 会话设置
description: 数据视图中可用于定义会话长度以及发起新会话的触发器的设置
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: bb2061f9119b8391bf3cedce4029685537d1e239
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 100%

---


# 会话设置

数据视图中的会话设置改变 Customer Journey Analytics 从您的连接中的数据计算会话的方式。

在数据视图的&#x200B;**[!UICONTROL 设置]**&#x200B;选项卡中，可通过任何方式定义会话，以匹配人员与您的数字体验交互的方式。会话设置定义是非破坏性的，因此不会改变底层数据。可设置多个数据视图（其中每个数据视图都有其特定的会话设置定义）作为工作区项目的基础。

要定义数据视图的会话上下文，请执行以下操作：

1. 在 Customer Journey Analytics UI 中，选择&#x200B;**[!UICONTROL 数据视图]**。

2. 创建新的或编辑现有的数据视图。有关更多信息，请参阅[创建或编辑数据视图](create-dataview.md)。

3. 选择&#x200B;**[!UICONTROL 设置]**&#x200B;选项卡。在[!UICONTROL 会话设置]下：

   1. 输入&#x200B;**[!UICONTROL 会话超时]**&#x200B;的值（以[!UICONTROL 分钟]、[!UICONTROL 小时]、[!UICONTROL 天]或[!UICONTROL 周]为单位）。会话超时可确定在开始新会话之前，会话可处于空闲状态（无事件发生）的时长。

      如果有意分析一般为在线的交互，请使用较短的会话超时（例如 30 分钟）。例如，分析访问您的在线商店产品页面的配置文件是否确实已将产品添加到其购物车甚至已在线购买。

      如果您要整合在线和离线数据，并要分析已购买您的一种或多种产品的客户是否在其购买后的前三个月内致电过您的联络中心，请使用较长的会话超时（例如 3 个月）。


   2. 从&#x200B;**[!UICONTROL 使用量度发起新会话]**&#x200B;下的&#x200B;**[!UICONTROL 在此放置量度]**&#x200B;列表中选择量度。或者，还可将量度从左窗格拖放到&#x200B;**[!UICONTROL 放置量度字段]**&#x200B;上。所选量度定义新会话的开始。您可以定义多个量度。

      可使用任何类型的量度定义新会话。举个例子，假设您希望在每次配置文件启动您的移动应用程序时定义一个新会话。在&#x200B;**[!UICONTROL 数据视图]** > **[!UICONTROL 组件]**&#x200B;中，您根据 **[!UICONTROL appInteraction]** **[!UICONTROL 名称]**&#x200B;模式字段定义一个量度类型的组件，名为&#x200B;**[!UICONTROL 启动次数]**。您进一步指定&#x200B;**[!UICONTROL 启动次数]**&#x200B;量度组件以仅在该值与 `launch` 匹配时计算该值。

      ![应用程序交互量度组件启动次数](assets/component-launches.png)

      然后拖放或选择&#x200B;**[!UICONTROL 启动次数]**&#x200B;量度作为定义新会话的量度。

      ![会话设置启动次数](assets/session-settings-launches-metric.png)



4. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;或&#x200B;**[!UICONTROL 保存并完成]**&#x200B;以保存会话设置定义。

