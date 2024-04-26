---
title: 迁移到Customer Journey Analytics时将数据发送到Adobe Experience Platform
description: 迁移到Customer Journey Analytics时将数据发送到Adobe Experience Platform
solution: Customer Journey Analytics
feature: Basics
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 1c789264a9867279f58a3ad139207fec8db29c1b
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 1%

---

# 步骤3：迁移时将数据发送到Adobe Experience Platform

+++展开此部分可查看此页面上的信息在较大的迁移过程中所处的位置。 确保所有先前的迁移步骤均已完成。

在继续此部分之前，请先确保已完成所有以前的迁移任务。

此页面上的信息介绍了迁移的步骤3，如下表所示：

| 迁移任务 | 详细信息 |
|---------|----------|
| **第1步： [迁移入门](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 了解迁移到Adobe Analytics的好处以及基本迁移过程。 |
| **第2步： [选择迁移路径](/help/getting-started/cja-migration/cja-migration-path.md)** | 可以使用各种方法迁移到Customer Journey Analytics。 根据贵组织当前的Adobe Analytics环境和长期目标，选择最适合贵组织的方法。 |
| <span class="preview">**步骤3：将数据发送到Adobe Experience Platform**</span> | <span class="preview">将数据发送到Adobe Experience Platform的过程因您在步骤2中选择的迁移路径而异。</span> |
| **第4步： [保留历史数据](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多数组织都需要将其历史Adobe Analytics数据保留一定时间。 可以使用各种选项来完成此操作。 |
| **步骤5： [执行其他实施任务](/help/getting-started/cja-getting-started.md)** | 在迁移过程的这一阶段，您需要在Customer Journey Analytics环境准备就绪之前执行各种任务。<p>这些附加任务适用于从Adobe Analytics进行的迁移以及新的Customer Journey Analytics实施。</p><p>这些任务包括：</p><ul><li>将其他数据引入Experience Platform</li><li>在Platform数据集与Customer Journey Analytics之间创建连接</li><li>创建数据视图</li><li>移植报表API使用情况</li><li>考虑数据馈送和Data Warehouse</li><li>迁移项目和组件</li><li>Planning用户载入</li></ul> <p>有关更多信息，请参阅 [Customer Journey Analytics快速入门](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++


在您之后 [选择迁移路径](#step-2-choose-your-customer-journey-analytics-migration-method) 如果这样做对贵公司最合适，您可以开始向Adobe Experience Platform发送数据，以便在Customer Journey Analytics中使用该数据。

下面显示了为每个迁移路径将数据发送到Experience Platform的过程。 有关详细配置信息，请访问表中的链接。

| 迁移路径 | 将数据发送到Platform的过程 | 其他信息 |
|---------|----------|----------|
| Experience PlatformWeb SDK的新实施 | <ol><li>为您的组织创建XDM架构。<p>与您的数据团队合作，确定您组织适用于Customer Journey Analytics的理想架构设计。</p></li><li>实施Experience PlatformWeb SDK。</li><li>将数据发送到Platform。</li></ol><p>有关每个步骤的详细信息，请参阅 [通过Adobe Experience Platform Web SDK引入数据](/help/data-ingestion/aepwebsdk.md). | 由于这是Experience PlatformWeb SDK的新实施，因此不需要进行架构映射，因为您必须创建架构作为实施过程中的首要步骤之一。 |
| 迁移Adobe Analytics实施以使用Web SDK | <ol><li>将现有的Adobe Analytics实施移动到Experience PlatformWeb SDK，然后验证所有内容在Adobe Analytics中是否都正常工作。<p>有关如何执行此操作的信息，请根据当前实施是Analytics标记扩展还是AppMeasurement，使用以下资源：</p><ul><li>如果您使用的是Analytics标记扩展，请参阅 [从Adobe Analytics标记扩展迁移到Web SDK标记扩展](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>如果您正在使用AppMeasurement，请参阅 [从AppMeasurement迁移到Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[为您的组织创建XDM架构](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>与您的数据团队合作，确定您组织适用于Customer Journey Analytics的理想架构设计。</p></li><li>[使用数据准备将数据对象中的所有字段映射到您的XDM架构](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li><li>通过以下方式开始将数据发送到Platform [设置数据流](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).</li></ol> |  |
| 配置现有的Adobe Analytics Web SDK实施以将数据发送到Customer Journey Analytics | <ol><li>通过以下方式开始将数据发送到Platform [设置数据流](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).<p>由于您的Adobe Analytics实施已在使用Experience PlatformWeb SDK，因此您可以忽略中的其他部分 [通过Adobe Experience Platform Web SDK引入数据](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk).</li><li>（可选） [为您的组织创建XDM架构](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>与您的数据团队合作，确定您组织适用于Customer Journey Analytics的理想架构设计。</p><p>注意：有关创建XDM架构的优势的信息，请参阅 [选择您的架构](/help/getting-started/cja-migration/cja-migration-path.md#choose-your-schema).</li><li>（视情况而定）如果您创建了XDM架构， [使用数据准备将数据对象中的所有字段映射到您的XDM架构](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li></ol> |
| 使用Analytics源连接器 | [从传统 Adobe Analytics 摄取和使用数据](/help/data-ingestion/analytics.md) | 当您使用Adobe Analytics源连接器时，Analytics数据会自动映射到XDM架构。 不需要其他映射。 |

## 接下来，保留历史数据

接下来，决定如何操作 [保留Adobe Analytics历史数据](/help/getting-started/cja-migration/cja-migration-historical-data.md).
