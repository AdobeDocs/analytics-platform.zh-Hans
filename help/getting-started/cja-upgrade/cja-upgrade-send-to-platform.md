---
title: 迁移到 Customer Journey Analytics 时将数据发送到 Adobe Experience Platform
description: 迁移到 Customer Journey Analytics 时将数据发送到 Adobe Experience Platform
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 98%

---

# 步骤 3：升级时将数据发送到 Adobe Experience Platform

+++展开此部分可查看此页面上的信息在较大的升级过程中的位置。 确保所有先前的升级步骤均已完成。

在继续本部分之前，请首先确保您已完成所有先前的升级任务。

该页面上的信息涵盖升级过程中的第 3 步，如下表所示：

| 升级任务 | 详细信息 |
|---------|----------|
| **步骤 1：[开始升级](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | 了解升级到 Customer Journey Analytics 的好处以及基本升级流程。 |
| **步骤 2：[选择升级路径](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | 有多种方法可以升级到 Customer Journey Analytics。根据您组织当前的 Adobe Analytics 环境和长期目标，选择最适合您组织的方法。 |
| <span class="preview">**步骤 3：将数据发送到 Adobe Experience Platform**</span> | <span class="preview">将数据发送到 Adobe Experience Platform 的流程因您在步骤 2 中选择的升级路径而异。</span> |
| **步骤 4：[保留历史数据](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | 大多数组织需要在一定时间内保留其 Adobe Analytics 的历史数据。有多种选项可以实现此目的。 |
| **步骤 5：[执行额外的实施任务](/help/getting-started/cja-getting-started.md)** | 在升级流程的这个阶段，您需要执行各种任务，然后您的 Customer Journey Analytics environment 环境才可供使用。<p>这些额外的任务适用于从 Adobe Analytics 进行升级，以及新的 Customer Journey Analytics 实施。</p><p>这些任务包括：</p><ul><li>将其他数据引入 Experience Platform</li><li>在 Platform 数据集与 Customer Journey Analytics 之间创建连接</li><li>创建数据视图</li><li>移植报告 API 使用情况</li><li>数据源和 Data Warehouse 的核算</li><li>迁移项目和组件</li><li>规划用户加入流程</li></ul> <p>有关更多信息，请参阅 [Customer Journey Analytics 快速入门](/help/getting-started/cja-getting-started.md)。 |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>此页面上的信息将被以下更全面的升级信息取代： <ul><li>**建议的升级步骤**<p>有关详细信息，请参阅[从 Adobe Analytics 升级到 Customer Journey Analytics 时的推荐路径](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。</p></li><li>**Customer Journey Analytics 升级指南**<p>现有新的升级指南可用，用于动态生成适合您的组织和独特情况的升级步骤。</p><p>要从 Customer Journey Analytics 访问升级指南，请选择&#x200B;**[!UICONTROL 工作区]**&#x200B;选项卡，然后在左侧面板中选择&#x200B;**[!UICONTROL 升级到 Customer Journey Analytics]**。按照屏幕上的说明操作。</p></li></ul>

在您[选择最适合您组织的升级路径](/help/getting-started/cja-upgrade/cja-upgrade-path.md)后，您可以开始将数据发送到 Adobe Experience Platform，以便在 Customer Journey Analytics 中使用它。

下面显示了每个升级路径向 Experience Platform 发送数据的流程。请按照表中的链接获取详细的配置信息。

| 升级路径 | 向 Platform 发送数据的流程 | 其他信息 |
|---------|----------|----------|
| Experience Platform Web SDK 的新实施  | <ol><li>为您的组织创建一个 XDM 架构。<p>与您的数据团队合作，确定您组织的 Customer Journey Analytics 的理想架构设计。</p></li><li>实施 Experience Platform Web SDK。</li><li>向 Platform 发送数据。</li></ol><p>有关每个步骤的详细信息，请参阅[通过 Adobe Experience Platform Web SDK 摄取数据](/help/data-ingestion/aepwebsdk.md)。 | 由于这是 Experience Platform Web SDK 的新实施，因此无需进行架构映射，因为在实施过程中，您必须首先创建架构。 |
| 迁移您的 Adobe Analytics 实施，以使用 Web SDK | <ol><li>将现有的 Adobe Analytics 实施移至 Experience Platform Web SDK，然后验证 Adobe Analytics 中的所有功能是否正常工作。<p>有关如何执行此操作的信息，请使用以下资源，具体取决于您当前的实施是 Analytics 标记扩展还是 AppMeasurement：</p><ul><li>如果您正在使用 Analytics 标记扩展，请参阅[从 Adobe Analytics 标记扩展迁移到 Web SDK 标记扩展](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>如果您正在使用 AppMeasurement，请参阅[从 AppMeasurement 迁移到 Web SDK](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[为您的组织创建一个 XDM 架构](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset)。<p>与您的数据团队合作，确定您组织的 Customer Journey Analytics 的理想架构设计。</p></li><li>[使用“数据准备”将数据对象中的所有字段映射到您的 XDM 架构](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/data-prep/home)。</li><li>通过[设置一个数据流](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream)来开始向 Platform 发送数据。</li></ol> |  |
| 配置现有的 Adobe Analytics Web SDK 实施，以向 Platform 发送数据 | <ol><li>通过[设置一个数据流](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream)来开始向 Platform 发送数据。<p>由于您的 Adobe Analytics 实施已在使用 Experience Platform Web SDK，因此您可以忽略[通过 Adobe Experience Platform Web SDK 摄取数据](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk)中的其他部分。</p><p>如果您已经在使用 Adobe Analytics 实施向 Platform 发送数据，则不需要此步骤。您只需要在 Platform 数据集和 Customer Journey Analytics 之间创建连接即可，如本流程后面所述。</p></li><li>（可选）[为您的组织创建一个 XDM 架构](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset)。<p>与您的数据团队合作，确定您组织的 Customer Journey Analytics 的理想架构设计。</p><p>注释：有关创建 XDM 架构的优势的信息，请参阅[选择您的架构](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema)。</li><li>（可选）如果您创建了一个 XDM 架构，请[使用“数据准备”将数据对象中的所有字段映射到您的 XDM 架构中](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/data-prep/home)。</li></ol> |  |
| 使用 Analytics 源连接器 | [从传统 Adobe Analytics 摄取和使用数据](/help/data-ingestion/analytics.md) | 当您使用 Analytics 源连接器时，Adobe Analytics 数据会自动映射到 XDM 架构。不需要额外的映射。 |

## 接下来，保留历史数据

接下来，决定如何[保留 Adobe Analytics 历史数据](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)。
