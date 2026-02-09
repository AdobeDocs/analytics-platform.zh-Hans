---
title: 数据视图概述
description: 数据视图会指定您如何解释 Customer Journey Analytics 连接中的数据元素，例如量度、维度、会话等。
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 7835d4c5b46177ece4a146df8f0d4abb9605c670
workflow-type: tm+mt
source-wordcount: '1094'
ht-degree: 95%

---

# 数据视图概述

数据视图是 Customer Journey Analytics 专属的容器，通过它，可决定如何解释来自[连接](/help/connections/create-connection.md)的数据。它指定所有可在 Analysis Workspace 中找到的维度和量度，以及这些维度和量度从哪些列获取其数据。为准备 Analysis Workspace 中的报告而定义数据视图。

>[!NOTE]
>
>在数据视图中选择或更改的任何设置均可追溯，因此无破坏性。换言之，它们不会永久地改变您的底层数据。

您可以使用完全不同的组件集（维度/量度）为同一连接创建不同的数据视图。或者创建具有不同设置的数据视图，用于访问超时、属性等。例如，您可以具有一个将所有维度均设置为[!UICONTROL 最近联系]的数据视图，同时，还可以具有另一个将所有维度均设置为[!UICONTROL 首次联系]的数据视图（基于同一数据集）。

Customer Journey Analytics 中的 Workspace 项目均基于数据视图。

>[!IMPORTANT]
>
>可将最多 5000 个量度和 5000 个维度添加到单个数据视图。

## 数据视图功能 {#capabilities}

通过数据视图，您可以自发地更改架构元素设置，而不必更改 Adobe Experience Platform 中的架构或重新实施您的 Customer Journey Analytics 环境。

* 您可将组件从量度更改为维度，反之亦然。您可以根据字符串字段创建量度，或根据数值字段创建维度。此功能简化了您的工作，因为您不必在 XDM 架构中为所需的每个量度创建数值字段。您只需在数据视图对话框中自发地创建它。下面给出了一些示例：
   * **从一个架构字段创建一个或多个量度，以及/或者多个维度**。这是一对多关系。例如，您可以根据一个架构字段创建一个或多个“收入”量度以及/或一个或多个“收入”维度。
   * **使用字符串字段作为量度**：当您使用数据集填充 Experience Platform 中的架构时，您可能无法预先知道需要哪些架构元素。例如，您可能没有意识到您需要一个表示 *页面上的错误*&#x200B;的量度。因此，您未根据这种影响创建数值架构元素。通过将字符串元素用作量度，您现在可以使用数据视图设置来指定任何时候字符串包含 `error` 一词，都可以将其用作量度。
   * **使用数值字段作为维度**：例如，如果您要从“收入”维度中提取“收入”量度，“收入”维度会将每个值显示为一个维度项。并以每个维度项的实例数作为量度。

* 您可以根据同一架构字段创建具有不同的属性模型或回顾窗口的多个量度。

* 您可以编辑组件的 ID 用于实现跨数据视图兼容性。组件 ID 供报告 API 用于识别特定量度或维度。由于您可以从一个 XDM 字段中随意创建很多量度或维度，因此您可以选择定义自己的组件 ID。因此，您在一个 Workspace 项目中使用的量度可以跨数据视图（和 API）兼容使用。即使量度基于来自不同连接、数据视图或 XDM 中不同架构的完全不同的字段。

* 您可以指定在 Analysis Workspace 中显示的友好组件的名称。默认情况下，此名称是从架构显示名称沿用的，但现在您可以为该特定数据视图覆盖它。

* 您可以查看有关组件的更多架构相关信息。例如：

   * 组件源自哪种数据集类型（事件、轮廓、查找、摘要），
   * 它源自哪种架构类型（字符串、整数等），以及
   * 架构路径（其所基于的 XDM 字段）。

* 您可以标记组件，使其更易于在 Workspace 中搜索。

* 您可以在报告中隐藏组件。某些量度和维度设置需要配置另一个量度或维度（例如，量度内部重复数据删除或购买内部重复数据删除）。隐藏组件允许您定义一个组件，该组件可在另一个组件的设置中使用，而不会在报告中显示。

* 您可以对量度应用格式，例如显示小数、时间、百分比或货币；指定小数位；将上升趋势显示为绿色或红色；以及指定货币选项。

* 您可以仅根据架构字段中的部分值创建量度或维度。例如，如果您想要一个“错误”量度，您可以从页面名称字段创建一个量度，但只包括包含单词 `error`的页面。以这种方式创建的“错误”量度支持区段，可以插入到计算量度中，并可与属性、流量、流失等结合使用。

* 对于维度，您可以仅自动添加或排除特定字段中的某些值。例如，如果开发人员在字段中发送了错误的 `dev mistake` 值，您可以使用排除规则轻松地将其从报告中排除。该维度的行为就像数据中从未存在过错误值一样。

* 您可以在数据视图中重命名您的容器，并将这些重命名后的容器显示在基于该数据视图的任意 Workspace 项目中。

* 您可以为数据视图启用或禁用Data Insights Agent。

## 数据视图先决条件 {#prerequisites}

* 在创建数据视图之前，您需要[设置一个或多个与 Experience Platform 数据集的连接](/help/connections/create-connection.md)。
* 要创建或管理数据视图，您需要[在 Adobe Admin Console 中拥有一组权限](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-overview)。
* 如果您正在使用 [Adobe Analytics 源连接器](/help/data-ingestion/analytics.md)或确实了解 Adobe Analytics 背景知识，您可能希望了解架构和数据集中的字段如何与 Adobe Analytics 对应项相关联。有关更多信息，请参阅 [Analytics 字段映射](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics)。

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

如果您[删除](/help/data-views/manage-dataviews.md#delete-data-views)Customer Journey Analytics[!UICONTROL 中的数据视图]，将显示一条错误消息，指示所有依赖于这个已删除数据视图的[!UICONTROL Workspace]项目都将不再运行。

## 后续步骤

* [创建数据视图](/help/data-views/create-dataview.md)
* [管理数据视图](/help/data-views/manage-dataviews.md)
* [数据视图用例](/help/use-cases/data-views/data-views-usecases.md)
