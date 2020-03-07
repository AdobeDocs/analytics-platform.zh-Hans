---
title: 创建数据视图
description: 介绍如何在客户旅程分析(CJA)中创建平台数据集的数据视图。
translation-type: tm+mt
source-git-commit: c85b5d2e702a38aa6569da893a25bacd39604f8a

---


# 创建数据视图

数据视图与Analytics中的虚拟报告套件类似，因为它在意义上是数据的“筛选”视图。 您可以为同一连接创建不同的数据视图，并且对访问超时、归因等设置不同。 您可以为单个数据集创建多个数据视图。 例如，您可以有一个数据视图，其中所有维度都设置为“上次触碰”，同时，另一个数据视图（基于同一数据集）的所有维度都设置为“首次触碰”。

客户旅程分析中的工作区项目基于数据视图。

单击 [此处](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html) ，查看视频概述。

## 先决条件

在创建数据视图之前，您需要 [设置一个或多个与Adobe Experience Platform数据集的连接](/help/connections/create-connection.md)。

## 配置设置

1. 在“客户旅程分析”中，转到选项 **[!UICONTROL Data Views]** 卡。

1. 单击 **[!UICONTROL Add]** 以添加数据视图并配置其设置。

   | 会话设置 | 定义 |
   |---|---|
   | 连接 | 此字段将数据视图链接到您之前建立的连接，该连接包含平台数据集。 |
   | 名称 | 必须为数据视图命名。 |
   | 描述 | 详细说明不是强制性的，但建议使用。 |
   | 添加标记 | 标记允许您将数据视图组织到类别中。 |
   | 时区 | 为数据视图选择时区。 |
   | 会话超时 | 选择“会话”的定义。 会话超时设置定义唯一访客在自动启动新会话之前必须处于非活动状态的数量。 默认为 30 分钟。For example, if you set the session timeout to 45 minutes, a new session grouping is created for each sequence of hits collected, separated by 45 minutes of inactivity. <!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | 开始新的活动会话 | 无论会话是否超时，均会在事件被触发时启动新会话。新创建的会话包含启动该会话的事件。此外，您可以使用多个事件启动会话，如果在数据中观察到这些事件中的任何一个，便会触发新会话。此设置将影响您的访问计数、会话（以前称为访问）区段容器以及维度的访问到期逻辑。 |
   | 添加过滤器 | “过滤器”是客户旅程分析中“细分”的术语。 如果要过滤数据，请从左边栏将相应的过滤器拖动到此处。 如果未选择过滤器，则数据视图将包含您的所有数据。 |

1. 单击 **[!UICONTROL Continue]**.

## 添加组件

1. 现在是时候向数据视图添加组件（维度、指标）了（与虚拟报表包中的特选体验类似）。注意，数据集中的每个字段现在都转换为维度或度量。 将维度和量度拖入面板或 **[!UICONTROL选择全部** ，以添加所有组件。

   ![](assets/add-all-components.png)

1. 单击选 **[!UICONTROL Add Components]** 项卡，将维度和量度添加到数据视图。

   ![](assets/add-all-components2.png)

1. （可选）您可以将组件重命名为友好名称，或通过选择组件并编辑其设置来更改其属性设置。 请注意，基础名称将被保留。 有关详细信息，请参 [阅配置数据视图和属性](/help/data-views/configure-dataviews.md)。

1. 下一步是指 [定组件和属性设置](/help/data-views/configure-dataviews.md)。