---
title: 迁移到Customer Journey Analytics时将数据发送到Adobe Experience Platform
description: 迁移到Customer Journey Analytics时将数据发送到Adobe Experience Platform
solution: Customer Journey Analytics
feature: Basics
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 773c03dfec99abcabdc667c549cce0dc1b1aabc4
workflow-type: tm+mt
source-wordcount: '811'
ht-degree: 1%

---

# 步骤3：升级时将数据发送到Adobe Experience Platform

+++展开此部分，查看此页面上的信息在较大的升级过程中的位置。 确保已完成所有以前的升级步骤。

在继续此部分之前，请先确保已完成所有以前的升级任务。

此页面上的信息介绍了升级过程的步骤3，如下表所示：

| 升级任务 | 详细信息 |
|---------|----------|
| **步骤1：[开始升级](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | 了解升级到Customer Journey Analytics的好处以及基本升级过程。 |
| **步骤2：[选择升级路径](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | 有多种方法可用于升级到Customer Journey Analytics。 根据贵组织当前的Adobe Analytics环境和长期目标，选择最适合贵组织的方法。 |
| <span class="preview">**步骤3：将数据发送到Adobe Experience Platform**</span> | <span class="preview">将数据发送到Adobe Experience Platform的过程因您在步骤2中选择的升级路径而异。</span> |
| **步骤4：[保留历史数据](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | 大多数组织都需要将其历史Adobe Analytics数据保留一定时间。 可以使用各种选项来完成此操作。 |
| **步骤5：[执行其他实施任务](/help/getting-started/cja-getting-started.md)** | 在升级过程的这一阶段，您需要在Customer Journey Analytics环境准备好使用之前执行各种任务。<p>这些其他任务适用于从Adobe Analytics升级以及新的Customer Journey Analytics实施。</p><p>这些任务包括：</p><ul><li>将其他数据引入Experience Platform</li><li>在Platform数据集与Customer Journey Analytics之间创建连接</li><li>创建数据视图</li><li>移植报表API使用情况</li><li>考虑数据馈送和Data Warehouse</li><li>迁移项目和组件</li><li>Planning用户载入</li></ul> <p>有关详细信息，请参阅[Customer Journey Analytics快速入门](/help/getting-started/cja-getting-started.md)。 |

{style="table-layout:auto"}

+++


在您[选择最适合贵组织的升级路径](/help/getting-started/cja-upgrade/cja-upgrade-path.md)后，您可以开始向Adobe Experience Platform发送数据，以便在Customer Journey Analytics中提供该数据。

下面显示了为每个升级路径将数据发送到Experience Platform的过程。 有关详细配置信息，请访问表中的链接。

| 升级路径 | 将数据发送到Platform的过程 | 其他信息 |
|---------|----------|----------|
| Experience Platform Web SDK的新实施 | <ol><li>为您的组织创建XDM架构。<p>与您的数据团队合作，确定贵组织适用于Customer Journey Analytics的理想架构设计。</p></li><li>实施Experience Platform Web SDK。</li><li>将数据发送到Platform。</li></ol><p>有关每个步骤的详细信息，请参阅[通过Adobe Experience Platform Web SDK摄取数据](/help/data-ingestion/aepwebsdk.md)。 | 由于这是Experience Platform Web SDK的新实施，因此不需要架构映射，因为您必须创建架构作为实施过程中的首要步骤之一。 |
| 迁移Adobe Analytics实施以使用Web SDK | <ol><li>将现有的Adobe Analytics实施迁移到Experience Platform Web SDK，然后验证所有内容在Adobe Analytics中是否都正常工作。<p>有关如何完成此操作的信息，请根据当前实施是Analytics标记扩展还是AppMeasurement，使用以下资源：</p><ul><li>如果您使用的是Analytics标记扩展，请参阅[从Adobe Analytics标记扩展迁移到Web SDK标记扩展](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>如果您使用的是AppMeasurement，请参阅[从AppMeasurement迁移到Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[为您的组织创建XDM架构](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset)。<p>与您的数据团队合作，确定贵组织适用于Customer Journey Analytics的理想架构设计。</p></li><li>[使用数据准备将数据对象中的所有字段映射到您的XDM架构](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home)。</li><li>通过[设置数据流](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream)开始将数据发送到Platform。</li></ol> |  |
| 配置现有的Adobe Analytics Web SDK实施以将数据发送到Platform | <ol><li>通过[设置数据流](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream)开始将数据发送到Platform。<p>由于您的Adobe Analytics实施已在使用Experience Platform Web SDK，因此您可以忽略[通过Adobe Experience Platform Web SDK摄取数据](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk)中的其他部分。</p><p>如果您已经使用Adobe Analytics实施将数据发送到Platform，则不需要执行此步骤。 您只需在Platform数据集与Customer Journey Analytics之间创建连接即可，如本流程后面部分所述。</p></li><li>（可选） [为您的组织创建XDM架构](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset)。<p>与您的数据团队合作，确定贵组织适用于Customer Journey Analytics的理想架构设计。</p><p>注意：有关创建XDM架构的优势的信息，请参阅[选择您的架构](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema)。</li><li>（视情况而定）如果您创建了XDM架构，[请使用数据准备将数据对象中的所有字段映射到您的XDM架构](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home)。</li></ol> |  |
| 使用Analytics源连接器 | [从传统 Adobe Analytics 摄取和使用数据](/help/data-ingestion/analytics.md) | 当您使用Adobe Analytics源连接器时，Analytics数据会自动映射到XDM架构。 不需要其他映射。 |

## 接下来，保留历史数据

接下来，决定如何[保留历史Adobe Analytics数据](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)。
