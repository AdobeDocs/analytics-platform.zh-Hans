---
title: 配置流式处理 Google Analytics 数据
description: 了解如何设置实施以将 Google 数据层发送到 Adobe Experience Platform
exl-id: 58854f4b-ae28-424e-a2cf-0e76219cb802
feature: Use Cases
role: Admin
TQID: https://experienceleague.adobe.com/K8UjF-HBF3vnDXiZdi46b7-ZdkTGib9LDvocFT79m4c
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 259
ht-degree: 90%

---

# 配置流式处理 Google Analytics 数据

本页面重点介绍如何将您的实时 Google Analytics 数据提取到 Adobe Experience Platform，从而允许您在 Customer Journey Analytics 的数据视图中引用该数据集。 您可以将此页面上的步骤与[将 Google Analytics 历史数据提取到 Adobe Experience Platform](backfill.md)结合使用，后者会生成包含历史数据的数据集。 将流式数据集与回填数据集相结合，在 Customer Journey Analytics 中无缝查看过去和现在的数据。

配置数据收集涉及以下步骤：

1. 实施[Adobe Experience Platform 的标签](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=zh-Hans)。 请参阅[快速入门指南](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=zh-Hans)以启动和运行基本实施。
1. 安装 [Google 数据层扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html?lang=zh-Hans)。 此扩展作为安装 Web SDK 扩展的替代方案，专门针对 Google 数据层。
1. 在 Adobe Experience Platform 数据收集中[创建数据流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=zh-Hans)。 配置数据流以将数据发送到 Adobe Experience Platform。 您当前必须在此处将每个 Google 数据层对象映射到适用的 XDM 字段。 Adobe 计划在未来简化此映射工作流。

在您的网站上实施并发布所需的标记后，您可以继续[创建连接](/help/connections/create-connection.md)，然后[创建数据视图](/help/data-views/create-dataview.md)。
