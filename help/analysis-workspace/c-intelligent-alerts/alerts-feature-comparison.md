---
description: 了解智能警报与Adobe Analytics的Customer Journey Analytics有何不同
title: “智能警报”功能比较Customer Journey Analytics和Adobe Analytics
feature: Workspace Basics
role: User, Admin
source-git-commit: 1613b3fc7e9cce1fb74b86bb7435612b2d469eb1
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# 智能警报功能比较：Customer Journey Analytics和Adobe Analytics

在 Customer Journey Analytics 中使用智能警报的过程与在 Adobe Analytics 中使用智能警报的过程几乎相同。然而，两者之间有着重要的区别。

以下各节描述了主要差异。

## 每小时警报在Customer Journey Analytics中不可用

在Adobe Analytics中，小时警报在Customer Journey Analytics中不可用。 在Customer Journey Analytics中，可以配置每日、每周或每月警报。

这是因为在Customer Journey Analytics中报告数据之前，可以将数据摄取到Adobe Experience Platform中的各种方式。 数据完整性和可用性无法在一小时内可靠地实现，因此由于数据不完整的可能性很高，每小时警报变得不切实际。 有关详细信息，请参阅[不同的数据摄取时间](#data-ingestion-times-vary-in-customer-journey-analytics)。

## 数据摄取时间因Customer Journey Analytics而异

完成数据并可以在Customer Journey Analytics中报告之前所需的时间因组织而异。

这是由于以下原因：

* Platform保存各种数据架构和类型的能力

  与Adobe Analytics（仅报告Web数据）不同，可以将[多种不同类型的数据摄取到Adobe Experience Platform](/help/data-ingestion/data-ingestion.md)中以在Customer Journey Analytics中报告，并且并非所有类型的数据都可以按顺序实时发送。

* 向Platform数据集投放批量数据的延迟

  虽然某些数据可能会更快地报告，但所有[批次数据都会被摄取到Platform数据集](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.)，通常在数据事件时间后的3到9小时内完成。 要获得准确的警报，必须完成数据摄取，并在数据集中提供所有批次数据。<!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

出于这些原因，可摄取的各种事件数据的数据摄取只有在出现一定延迟后才会完成，延迟时间通常比数据事件时间晚3到9个小时。 要获得准确的警报，给定事件范围的事件数据必须完整，这意味着Adobe不再接收指定事件范围的任何事件数据。

考虑到摄取时间的这种延迟，警报的默认延迟为9小时，之后才发送。

您可以将默认延迟9小时调整为0到24小时之间的任何时间。 但是，将延迟降低到9小时以下可能意味着您报告的数据不完整，这会导致警报信息不准确。

有关如何调整延迟以及调整延迟时应考虑的因素的更多信息，请参阅<!--add link -->。

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->





