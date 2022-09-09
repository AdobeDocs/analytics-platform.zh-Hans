---
title: 将流Google Analytics数据配置为Adobe Experience Platform
description: 了解如何设置实施以将Google数据层发送到Adobe Experience Platform
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 2%

---

# 将流Google Analytics数据配置为Adobe Experience Platform

本页重点介绍如何将实时Google Analytics数据摄取到Adobe Experience Platform中，以便您在Customer Journey Analytics的“数据视图”中引用该数据集。 您可以将此页上的步骤与 [将Google Analytics历史数据摄取到Adobe Experience Platform](backfill.md)，可生成包含历史数据的数据集。 将流数据集与回填数据集合并，以无缝查看Customer Journey Analytics中的过去和当前数据。

配置数据收集涉及以下步骤：

1. 实施 [用于Adobe Experience Platform的标记](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=zh-Hans). 请参阅 [快速入门指南](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) 以启动并运行基本实施。
1. 安装 [Google数据层扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html). 此扩展可用作安装Web SDK扩展的替代方法，专门面向Google数据层。
1. [创建数据流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) 在Adobe Experience Platform数据收集中。 配置数据流以将数据发送到Adobe Experience Platform。 您当前必须在此处将每个Google数据层对象映射到适用的XDM字段。 Adobe计划在将来简化此映射工作流。

在网站上实施和发布所需标记后，您可以继续 [创建连接](/help/connections/create-connection.md)，则 [创建数据视图](/help/data-views/create-dataview.md).
