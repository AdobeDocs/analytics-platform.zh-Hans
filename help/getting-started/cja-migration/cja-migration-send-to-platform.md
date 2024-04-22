---
title: 迁移到Customer Journey Analytics时将数据发送到Adobe Experience Platform
description: 迁移到Customer Journey Analytics时将数据发送到Adobe Experience Platform
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 21d77f06595993172460b724dc7991cb9a5a02a8
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 1%

---

# 步骤3：迁移到Customer Journey Analytics时将数据发送到Adobe Experience Platform

+++展开此部分可查看此页面上的信息在较大的迁移过程中所处的位置。 确保所有先前的迁移步骤均已完成。

在继续此部分之前，请先确保已完成所有以前的迁移任务。

此页面上的信息涵盖了步骤3，如下表所示：

| 迁移任务 | 详细信息 |
|---------|----------|
| **第1步： [迁移入门](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 了解迁移到Adobe Analytics的好处以及基本迁移过程。 |
| **第2步： [选择迁移方法](/help/getting-started/cja-migration/cja-migration-method.md)** | 可以使用各种方法迁移到Customer Journey Analytics。 根据贵组织当前的Adobe Analytics环境和长期目标，选择最适合贵组织的方法。 |
| <span class="preview">**步骤3： [将数据发送到Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)**</span> | <span class="preview">将数据发送到Adobe Experience Platform的过程因您在步骤1中选择的迁移方法而异。</span> |
| **第4步： [将数据映射到XDM架构](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM架构](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重用的方式描述数据结构。 通过在系统中以一致的方式定义数据，更容易保留含义并因此从数据中获取价值。<p>大多数迁移方法都要求您创建新的XDM架构，或使用数据流映射将现有Adobe Analytics架构映射到XDM。</p> |
| **步骤5： [保留历史数据](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多数组织都需要将其历史Adobe Analytics数据保留一定时间。 可以使用各种选项来完成此操作。 |
| **步骤6： [计划用户载入](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 您应该给用户充足的时间（3 - 6个月），以熟悉Analysis Workspace在Customer Journey Analytics方面的主要差异。 |
| **步骤7： [移植报表API使用情况](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics报表API采用相同的格式，但使用不同的端点。 将报表API使用情况从Adobe Analytics报表API移植到Customer Journey Analytics报表API。 |
| **步骤8： [替换数据馈送并Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | 决定如何使用Customer Journey Analytics中可用的导出选项，以替换在Adobe Analytics中使用的数据馈送和Data Warehouse功能。 |
| **第9步： [迁移项目和组件](/help/getting-started/cja-migration/cja-migration-projects.md)** | 利用Adobe Analytics中的组件迁移区域，可将项目及其关联的组件从Adobe Analytics迁移到Customer Journey Analytics。 |

{style="table-layout:auto"}

+++


在您之后 [选择迁移方法](#step-2-choose-your-customer-journey-analytics-migration-method) 如果这样做对贵公司最合适，您可以开始向Adobe Experience Platform发送数据，以便在Customer Journey Analytics中使用该数据。

下面显示了为每个迁移方法将数据发送到Experience Platform的过程。 有关更多详细信息，请访问下表中的链接。

| 迁移方法 | 将数据发送到Platform的过程 |
|---------|----------|
| Web SDK的新实施 | [通过Adobe Experience Platform Web SDK引入数据](/help/data-ingestion/aepwebsdk.md) |
| 迁移Adobe Analytics实施以使用Web SDK | 如果您使用的是Analytics标记扩展： [从Adobe Analytics标记扩展迁移到Web SDK标记扩展](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)<p>或</p><p>如果您使用AppMeasurement： [从AppMeasurement迁移到Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) |
| 配置现有的Adobe Analytics Web SDK实施以将数据发送到Customer Journey Analytics | [设置数据流](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream) 在 [通过Adobe Experience Platform Web SDK引入数据](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) |
| Analytics源连接器 | [从传统 Adobe Analytics 摄取和使用数据](/help/data-ingestion/analytics.md) |

## 接下来，将数据映射到XDM架构

按照上表中的链接向Experience Platform发送数据后，您可能需要 [将数据映射到XDM架构](/help/getting-started/cja-migration/cja-migration-xdm.md)，具体取决于您选择的实施方法。

以下实施方法要求您将数据映射到XDM架构：

* 从Adobe Analytics标记扩展迁移到Web SDK标记扩展

* 配置现有的Adobe Analytics Web SDK实施以将数据发送到Customer Journey Analytics

或者，如果您选择重新实施Web SDK，则无需映射，因为您已经 [设置新的XDM架构](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) 作为新实施的一部分。

如果您选择使用Analytics Source Connector进行迁移，则不需要映射，因为Analytics Source Connector使用您现有的Adobe Analytics架构，而不是XDM架构。
