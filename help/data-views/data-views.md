---
title: 数据视图概述
description: 数据视图会指定您要如何解释Customer Journey Analytics连接中的数据元素，例如量度、维度、会话等。
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 0e4e4621abe02c022981e458282543908b2396c2
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 43%

---

# 数据视图概述

数据视图是 Customer Journey Analytics 专属的容器，通过它，可决定如何解释来自[连接](/help/connections/create-connection.md)的数据。它指定所有可在 Analysis Workspace 中找到的维度和量度，以及这些维度和量度从哪些列获取其数据。为准备 Analysis Workspace 中的报告而定义数据视图。

>[!NOTE]
>
>在数据视图中选择或更改的任何设置均可追溯，因此无破坏性。换言之，它们不会永久更改您的底层数据。

您可以使用完全不同的组件集（维度/量度）为同一连接创建不同的数据视图。或者，使用访问超时、归因等的不同设置创建数据视图。 例如，您可以具有一个将所有维度均设置为[!UICONTROL 最近联系]的数据视图，同时，还可以具有另一个将所有维度均设置为[!UICONTROL 首次联系]的数据视图（基于同一数据集）。

Customer Journey Analytics 中的 Workspace 项目均基于数据视图。

>[!IMPORTANT]
>
>可将最多 5000 个量度和 5000 个维度添加到单个数据视图。

## 数据视图功能 {#capabilities}

通过数据视图，您可以自发地更改架构元素设置，而不必更改 Adobe Experience Platform 中的架构或重新实施您的 Customer Journey Analytics 环境。

* 您可以将组件从量度更改为维度，反之亦然。 您可以根据字符串字段创建量度，或根据数值字段创建维度。此功能使您的生活更轻松，因为您不必在XDM架构中为所需的每个量度创建数值字段。 您只需在数据视图对话框中自发地创建它。下面给出了一些示例：
   * **根据一个架构字段创建一个或多个维度，以及/或仅创建一个维度**。这是一对多关系。例如，您可以根据一个架构字段创建一个或多个“收入”量度以及/或一个或多个“收入”维度。
   * **使用字符串字段作为量度**：当您使用数据集填充 Experience Platform 中的架构时，您可能无法预先知道需要哪些架构元素。例如，您可能没有意识到您需要页面&#x200B;*上*&#x200B;个错误的量度。 因此，您未根据这种影响创建数值架构元素。通过将字符串元素用作量度，您现在可以使用数据视图设置来指定只要字符串包含`error`一词，就可以将其用作量度。
   * **使用数值字段作为维度**：例如，如果您要从“收入”维度中提取“收入”量度，“收入”维度会将每个值显示为维度项。 以及每个维度项作为量度的实例数。

* 您可以根据同一架构字段创建多个量度，每个量度都有不同的归因模型或回顾时间范围。

* 您可以编辑组件的ID以实现跨数据视图兼容性。 组件 ID 供报告 API 用于识别特定量度或维度。由于您可以根据一个XDM字段随意创建许多量度或维度，因此您可以选择定义自己的组件ID。 因此，您可以跨数据视图（和API）兼容地使用在一个Workspace项目中使用的量度。 即使量度基于完全不同的字段，这些字段来自不同的连接、数据视图或XDM中的不同架构。

* 您可以指定在Analysis Workspace中显示的友好组件名称。 默认情况下，此名称是从架构显示名称沿用的，但现在您可以为该特定数据视图覆盖它。

* 您可以查看有关组件的更多与架构相关的信息。 例如：

   * 组件来自哪个数据集类型（事件、个人资料、查找、摘要），
   * 架构类型（字符串、整数等） 它源自、和
   * 架构路径（它所基于的XDM字段）。

* 您可以标记组件，使其更易于在Workspace中搜索。

* 您可以在报告中隐藏组件。 某些量度和维度设置需要配置另一个量度或维度（例如，量度内部重复数据删除或购买内部重复数据删除）。通过隐藏组件，您可以定义可用于其他组件设置的组件，而无需在报表中公开。

* 您可以对量度应用格式，例如显示小数、时间、百分比或货币；指定小数位；将上升趋势显示为绿色或红色；以及指定货币选项。

* 您可以仅根据架构字段中的部分值创建量度或维度。 例如，如果您需要一个“错误”量度，则可以根据页面名称字段创建一个量度，但仅包括包含单词`error`的页面。 通过这种方式创建的错误量度支持过滤器，可以插入到计算量度中，并可与归因、流量、流失等配合使用。

* 对于维度，您可以仅自动包含或排除特定字段中的某些值。 例如，如果开发人员将错误值`dev mistake`发送到某个字段中，您可以使用排除规则在报告中轻松排除该错误。 维度的行为就像数据中从不存在错误值一样。

* 您可以在数据视图中重命名您的容器，并将这些重命名后的容器显示在基于该数据视图的任何Workspace项目中。

## 数据视图先决条件 {#prerequisites}

* 在创建数据视图之前，您需要[设置一个或多个与 Experience Platform 数据集的连接](/help/connections/create-connection.md)。
* 要创建或管理数据视图，您需要[在 Adobe Admin Console 中拥有一组权限](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-overview)。
* 如果您使用的是[Adobe Analytics源连接器](/help/data-ingestion/analytics.md)，或者您确实了解Adobe Analytics背景知识，则可能需要了解架构和数据集中的字段如何与Adobe Analytics对应字段相关联。 有关更多信息，请参阅 [Analytics 字段映射](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics)。

## 您可以在 Workspace 中覆盖的数据视图设置 {#settings-override}

一些数据视图设置可以在 Analysis Workspace 中的项目级别被覆盖，而另一些则不然。

* [!UICONTROL 回顾时间范围]
* 量度属性
* 用户是否会在报告中看到[!UICONTROL 没有值]行项目

## 您无法在 Workspace 中覆盖的数据视图设置 {#settings-no-override}

* [!UICONTROL 组件类型]
* 量度格式
* 数据视图名称
* 维度分配

## 删除数据视图 {#delete}

如果删除[!UICONTROL Customer Journey Analytics]中的数据视图，将显示一条错误消息，指示所有依赖于这个已删除数据视图的[!UICONTROL Workspace]项目都将不再运行。

## 后续步骤

* [创建数据视图](/help/data-views/create-dataview.md)
* [数据视图用例](/help/use-cases/data-views/data-views-usecases.md)
