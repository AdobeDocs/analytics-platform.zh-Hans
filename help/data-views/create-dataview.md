---
title: 创建数据视图
description: 介绍如何在 Customer Journey Analytics (CJA) 中创建 Platform 数据集的视图。
translation-type: tm+mt
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 94%

---


# 创建数据视图

数据视图类似于 Analytics 中的虚拟报表包，因为从某种意义上说，它是“过滤的”数据视图。您可以使用不同的访问超时、归因等设置为同一连接创建不同的数据视图。您可以为单个数据集创建多个视图。例如，您可以具有一个将所有维度均设置为“最后接触”的视图，同时，还可以具有另一个将所有维度均设置为“首次接触”的视图（基于同一数据集）。

Customer Journey Analytics 中的工作区项目均基于数据视图。

单击[此处](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html)，查看视频概述。

## 先决条件

在创建数据视图之前，您需要[设置一个或多个与 Experience Platform 数据集的连接](/help/connections/create-connection.md)。

## 配置设置

1. 在 Customer Journey Analytics 中，转到&#x200B;**[!UICONTROL 数据视图]**&#x200B;选项卡。

1. 单击&#x200B;**[!UICONTROL 添加]**&#x200B;以添加数据视图，并配置其设置。

   | 会话设置 | 定义 |
   |---|---|
   | 连接 | 此字段会将数据视图链接到您之前已建立的连接，其中包含 [!UICONTROL Experience Platform] 数据集。 |
   | 名称 | 必须为数据视图命名。 |
   | 描述 | 不强制要求提供详细描述，但建议提供。 |
   | 添加标记 | 标记让您可以将数据视图组织成不同的类别。 |
   | 时区 | 选择数据视图的时区。 |
   | 会话超时 | 选择“会话”的定义。会话超时设置定义独特访客在新会话自动开始之前必须处于非活动状态的时间。默认为 30 分钟。例如，如果将会话超时设置为 45 分钟，则会以 45 分钟的非活动状态进行分隔，为每个收集的点击序列创建一个新会话组。<!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | 通过事件开始新会话 | 无论会话是否超时，均会在事件被触发时启动新会话。新创建的会话包含启动该会话的事件。此外，您可以使用多个事件启动会话，如果在数据中观察到这些事件中的任何一个，便会触发新会话。此设置将影响您的访问计数、会话（以前的“访问”）区段容器，以及维度上的访问过期逻辑。 |
   | 添加过滤器 | “过滤器”是 Customer Journey Analytics 中的“区段”术语。如果要过滤数据，请将相应的过滤器从左边栏拖动到此处。如果不选择过滤器，数据视图将包含您的所有数据。 |

1. 单击&#x200B;**[!UICONTROL 继续]**。

## 添加组件

1. 现在就可以向数据视图添加组件（维度、量度）了（类似于虚拟报表包中的策划体验）。请注意，数据集中的每个字段现在均已转换成维度或量度。将维度和量度拖入面板或单击&#x200B;**[!UICONTROL 全选]**&#x200B;以添加所有组件。

   ![](assets/add-all-components.png)

1. 单击&#x200B;**[!UICONTROL 添加组件]**&#x200B;选项卡，将维度和量度添加到数据视图。

   ![](assets/add-all-components2.png)

1. （可选）您可以将组件重命名为友好名称，或通过选择组件并编辑其设置来更改组件的归因设置。请注意，基础名称将保留。有关详细信息，请参阅[配置视图和归因](/help/data-views/configure-dataviews.md)。

1. 下一步是[指定组件和归因设置](/help/data-views/configure-dataviews.md)。

## 删除数据视图

如果在[!UICONTROL Customer Journey Analytics]中删除视图，将显示一条错误消息，指示依赖此已删除数据视图的任何Workspace项目将停止工作。