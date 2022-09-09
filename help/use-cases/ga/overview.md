---
title: 将数据从Google Analytics迁移到Customer Journey Analytics
description: 了解有关如何将数据从Google Analytics移动到Adobe Experience Platform以及在Customer Journey Analytics中查看报表的总体工作流程。
source-git-commit: 7c195453490499cc42e7d5b2f2d111e2654f918c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# 将数据从Google Analytics迁移到Customer Journey Analytics

如果您是初次Customer Journey Analytics，则贵组织可能在其他Analytics平台(如Google Analytics)上拥有现有数据。 您可以按照以下主要步骤将该数据移入Adobe Experience Platform，以便以Customer Journey Analytics查看报表。

为历史数据和当前数据收集提供了工作流。 您可以根据贵组织的数据需求，执行其中一个或两个工作流。

## 将历史数据从Google Analytics导入Adobe Experience Platform

摄取历史（回填）数据涉及从Google导出数据并将该数据导入Adobe Experience Platform。 请参阅 [在Adobe Experience Platform中摄取Google Analytics数据](backfill.md).

成功将历史数据导入平台后，您可以 [配置流当前数据](streaming.md)，或立即开始在CJA中报告回填数据 [创建连接](/help/connections/create-connection.md).

## 为Adobe Experience Platform配置现有Google Analytics实施 {#configure}

摄取当前（流）数据包括将数据发送到Adobe Experience Edge，然后Adobe Experience Edge将该数据转发到Adobe Experience Platform。 请参阅 [在Adobe Experience Platform中设置流Google Analytics数据](streaming.md).

## 在CJA中配置连接和数据视图

成功摄取历史数据和/或配置数据收集到Adobe Experience Platform后，您可以 [创建连接](/help/connections/create-connection.md) 以允许Customer Journey Analytics引用该数据。

使用连接创建一个或多个 [数据视图](/help/data-views/create-dataview.md) 用于Analysis Workspace。

## 创建报表

在数据视图中配置维度和量度后，您可以开始使用Analysis Workspace生成所需的报表。 请参阅 [在Customer Journey Analytics中报告Google Analytics数据](report.md).
