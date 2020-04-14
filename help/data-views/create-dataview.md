---
title: 创建数据视图
description: 介绍如何在客户旅程分析(CJA)中创建平台数据集的数据视图。
translation-type: tm+mt
source-git-commit: d6101371fc9c055a73c7b7bcd1a8d6d6fdc13322

---


# 创建数据视图

数据视图与Analytics中的虚拟报告包类似，因为它在意义上是数据的“筛选”视图。 您可以为同一连接创建不同的数据视图，并针对访问超时、归因等设置不同。 您可以为单个数据集创建多个数据视图。 例如，您可以有一个数据视图，其中所有维度都设置为“最近联系”，同时，还可以设置另一个数据视图（基于同一数据集），所有维度都设置为“首次联系”。

客户旅程分析中的工作区项目基于数据视图。

单击 [此处](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html) ，查看视频概述。

## 先决条件

在创建数据视图之前，您需要 [设置一个或多个与Experience Platform数据集的连接] ](/help/connections/create-connection.md)。

## 配置设置

1. 在“客户旅程分析”中，转到选项 **[!UICONTROL Data Views]** 卡。

1. 单击 **[!UICONTROL Add]** 以添加数据视图并配置其设置。

   | 会话设置 | 定义 |
   |---|---|
   | 连接 | 此字段将数据视图链接到您之前建立的连接，该连接包含 [!UICONTROL Experience Platform] 数据集。 |
   | 名称 | 必须为数据视图命名。 |
   | 描述 | 详细说明不是强制性的，但建议使用。 |
   | 添加标记 | 标记允许您将数据视图组织到类别中。 |
   | 时区 | 选择数据视图的时区。 |
   | 会话超时 | 选择“会话”的定义。 会话超时设置定义了在自动启动新会话之前唯一访客必须具有的不活动量。 默认为30分钟。 例如，如果将会话超时设置为45分钟，则会为收集的每个点击序列创建一个新的会话分组，以45分钟不活动分隔。 <!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | 开始与事件的新会议 | 当事件被触发时，新会话开始，而不管会话是否超时。 新创建的会话包括启动该会话的事件。 此外，您还可以使用多个事件来开始会话，如果数据中观察到了其中的任何一个事件，则将触发新会话。 此设置将影响您的访问计数、会话（以前称为访问）区段容器以及维度的访问到期逻辑。 |
   | 添加过滤器 | “过滤器”是客户旅程分析中“细分”的术语。 如果要过滤数据，请从左边栏将相应的过滤器拖动到此处。 如果不选择过滤器，数据视图将包含您的所有数据。 |

1. 单击 **[!UICONTROL Continue]**.

## 添加组件

1. 现在是时候向数据视图添加组件（维度、指标）了（与虚拟报表包中的特选体验类似）。注意，数据集中的每个字段现在都转换为维度或度量。 将维度和量度拖入面板或 **[!UICONTROL选择全部** ，以添加所有组件。

   ![](assets/add-all-components.png)

1. 单击选 **[!UICONTROL Add Components]** 项卡，将维和量度添加到数据视图。

   ![](assets/add-all-components2.png)

1. （可选）您可以将组件重命名为友好名称，或通过选择组件并编辑其设置来更改其属性设置。 请注意，基础名称将被保留。 有关详细信息，请参 [阅配置数据视图和归因](/help/data-views/configure-dataviews.md)。

1. 下一步是指 [定组件和属性设置](/help/data-views/configure-dataviews.md)。