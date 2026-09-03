---
title: 从 Google Analytics 迁移数据
description: 了解有关如何将数据从 Google Analytics 移动到 Adobe Experience Platform 以及在 Customer Journey Analytics 中查看报告的总体工作流。
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
feature: Use Cases
role: Admin
TQID: https://experienceleague.adobe.com/C9rt1pyuM6ykLUlXCHc0ITwGeGcuLw6qisXnJxwX4uU
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 046df00868ca4a5b3bab3eb36cca7d91b141333a
workflow-type: tm+mt
source-wordcount: 342
ht-degree: 70%

---

# 从 Google Analytics 迁移数据

>[!BEGINSHADEBOX]

本指南介绍面向管理员的数据迁移。 如果您是希望在Customer Journey Analytics中查找GA4报表的分析师，请参阅[从Google Analytics 4过渡到Customer Journey Analytics](/help/getting-started/ga-to-cja/home.md)和[Customer Journey Analytics中的GA4报表](/help/getting-started/ga-to-cja/reports.md)。

>[!ENDSHADEBOX]

如果您是 Customer Journey Analytics 的新手，您的组织可能在另一个分析平台（例如 Google Analytics）上拥有现有数据。 您可以按照这些总体步骤将该数据移动到 Adobe Experience Platform，从而允许您在 Customer Journey Analytics 中查看报告。

为历史数据和当前数据收集提供了工作流。 您可以遵循这些工作流中的一个或两个，具体取决于您组织的数据需求。

## 将来自 Google Analytics 的历史数据引入 Adobe Experience Platform

摄取历史（回填）数据涉及从 Google 导出数据并将该数据导入 Adobe Experience Platform。 查看[将 Google Analytics 数据摄取到 Adobe Experience Platform](backfill.md)。

成功将历史数据引入平台后，您可以[配置流式当前数据](streaming.md)，或通过[创建连接](/help/connections/create-connection.md)立即开始在Customer Journey Analytics中报告回填数据。

## 为 Adobe Experience Platform 配置现有的 Google Analytics 实施 {#configure}

摄取当前（流）数据涉及将数据发送到Adobe Experience Platform Edge Network，然后将数据转发到Adobe Experience Platform。 查看[在 Adobe Experience Platform 中设置流式 Google Analytics 数据](streaming.md)。

## 在Customer Journey Analytics中配置连接和数据视图

成功提取历史数据和/或将数据收集配置到 Adobe Experience Platform 后，您可以[创建连接](/help/connections/create-connection.md)以允许 Customer Journey Analytics 引用该数据。

使用连接创建一个或多个[数据视图](/help/data-views/create-dataview.md)以在 Analysis Workspace 中使用。

## 创建报告

在数据视图中配置维度和指标后，您可以开始使用 Analysis Workspace 生成所需的报告。 查看[在 Customer Journey Analytics 中就 Google Analytics 数据给出报告](report.md)。
