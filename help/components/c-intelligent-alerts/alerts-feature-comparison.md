---
description: 了解Customer Journey Analytics中的警报与Adobe Analytics中的警报有何不同
title: 警报功能比较：Customer Journey Analytics和Adobe Analytics
feature: Workspace Basics
role: User, Admin
exl-id: 04e819c4-9fb5-4459-9f8b-40d78385ed90
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 23%

---

# 警报功能比较

在 Customer Journey Analytics 中使用警报的过程与在 Adobe Analytics 中使用警报的过程几乎相同。然而，两者之间有着重要的区别。 以下各节描述了主要差异。

## 每小时警报不可用

在Customer Journey Analytics中，每小时警报是&#x200B;**非**&#x200B;可用；而在Adobe Analytics中，每小时警报可用。 在 Customer Journey Analytics 中，可以将警报配置为每日、每周或每月。

您可以通过多种方式将数据摄取到Adobe Experience Platform中。 因此，在一小时的时间范围内，数据完整性和可用性无法可靠实现。  灵活的数据摄取意味着由于极有可能出现不完整的数据，每小时的警报是不切实际的。 有关详细信息，请参阅[不同的数据摄取时间](#data-ingestion-times-vary-in-customer-journey-analytics)。

## 数据摄取时间各不相同

完成数据并在Customer Journey Analytics中报告数据之前所需的时间因组织而异。

这是由于以下原因：

* Platform保存各种数据架构和类型的能力

  与Adobe Analytics（仅报告Web数据）不同，可以将[多种不同类型的数据摄取到Adobe Experience Platform](/help/data-ingestion/data-ingestion.md)中以在Customer Journey Analytics中报告，并且并非所有类型的数据都可以按顺序实时发送。

* 向Platform数据集投放批量数据的延迟

  虽然某些数据可能会更快地报告，但所有[批次数据都会被摄取到Platform数据集](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.)，通常在数据事件时间后的3到9小时内完成。 要获得准确的警报，必须完成数据摄取，并在数据集中提供所有批次数据。<!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

出于这些原因，可摄取的各种事件数据的数据摄取只有在出现一定延迟后才会完成，延迟时间通常比数据事件时间晚3到9个小时。 为了确保警报准确无误，给定事件范围的事件数据必须是完整的，这意味着 Adobe 不会再接收指定事件范围的任何事件数据。

为了解决摄取时间的延迟，警报发送前的默认延迟时间为 9 小时。

您可以将默认延迟时间从 9 小时调整为 0 至 24 小时之间的任意值。但是，将延迟时间减少到 9 小时以下可能意味着您报告的数据不完整，从而会导致警报信息不准确。

有关如何调整延迟以及调整延迟时应考虑的因素的更多信息，请参阅[创建警报](/help/components/c-intelligent-alerts/alert-builder.md)。

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## 从Analysis Workspace创建警报不可用

在Adobe Analytics的Analysis Workspace中，您可以通过以下描述的任何方式从Analysis Workspace创建警报。 在Customer Journey Analytics中，从Analysis Workspace创建警报的选项尚不可用。 请改为访问警报生成器，如[创建警报](/help/components/c-intelligent-alerts/alert-builder.md)中所述。

在Adobe Analytics中，提供以下选项：

* 在自由格式表中选择一个或多个行项目，然后右键单击并选择&#x200B;**[!UICONTROL 从选定范围中创建警报]**。

  这会立即预填充警报生成器，以便使用正确的量度和区段创建警报。

* 在 Analysis Workspace 中打开一个项目，然后选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 创建警报]**。

* 在Analysis Workspace中打开项目，然后使用以下快捷方式： **[!UICONTROL *ctrl *]**+**[!UICONTROL * shift *]** + **[!UICONTROL *a *]**(Windows)或**[!UICONTROL * cmd *]** + **[!UICONTROL *shift *]**+**[!UICONTROL * a *]** (macOS)。
