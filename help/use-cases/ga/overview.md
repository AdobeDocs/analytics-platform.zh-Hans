---
title: 从Google Analytics迁移数据
description: 了解有关如何将数据从 Google Analytics 移动到 Adobe Experience Platform 以及在 Customer Journey Analytics 中查看报告的总体工作流。
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
feature: Use Cases
role: Admin
source-git-commit: 90d1c51c11f0ab4d7d61b8e115efa8257a985446
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 75%

---

# 从Google Analytics迁移数据

如果您是 Customer Journey Analytics 的新手，您的组织可能在另一个分析平台（例如 Google Analytics）上拥有现有数据。您可以按照这些总体步骤将该数据移动到 Adobe Experience Platform，从而允许您在 Customer Journey Analytics 中查看报告。

为历史数据和当前数据收集提供了工作流。您可以遵循这些工作流中的一个或两个，具体取决于您组织的数据需求。

## 将来自 Google Analytics 的历史数据引入 Adobe Experience Platform

提取历史（回填）数据涉及从 Google 导出数据并将该数据导入 Adobe Experience Platform。查看[将 Google Analytics 数据摄取到 Adobe Experience Platform](backfill.md)。

成功将历史数据引入平台后，您可以[配置流式当前数据](streaming.md)，或通过[创建连接](/help/connections/create-connection.md)立即开始报告Customer Journey Analytics中的回填数据。

## 为 Adobe Experience Platform 配置现有的 Google Analytics 实施 {#configure}

摄取当前（流）数据涉及将数据发送到Adobe Experience PlatformEdge Network，然后将该数据转发到Adobe Experience Platform。 查看[在 Adobe Experience Platform 中设置流式 Google Analytics 数据](streaming.md)。

## 在Customer Journey Analytics中配置连接和数据视图

成功提取历史数据和/或将数据收集配置到 Adobe Experience Platform 后，您可以[创建连接](/help/connections/create-connection.md)以允许 Customer Journey Analytics 引用该数据。

使用连接创建一个或多个[数据视图](/help/data-views/create-dataview.md)以在 Analysis Workspace 中使用。

## 创建报告

在数据视图中配置维度和指标后，您可以开始使用 Analysis Workspace 生成所需的报告。查看[在 Customer Journey Analytics 中就 Google Analytics 数据给出报告](report.md)。
