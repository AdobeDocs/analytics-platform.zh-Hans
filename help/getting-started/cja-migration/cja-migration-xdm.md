---
title: 迁移到Customer Journey Analytics时将数据映射到XDM架构
description: 了解在迁移到Customer Journey Analytics时如何将数据映射到XDM架构
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 86ce60cf-b3c7-43b5-aa18-9e16fa942e54
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 0%

---

# 步骤4：迁移到Customer Journey Analytics时将数据映射到XDM架构

+++展开此部分可查看此页面上的信息在较大的迁移过程中所处的位置。 确保所有先前的迁移步骤均已完成。

在继续此部分之前，请先确保已完成所有以前的迁移任务。

此页面上的信息涵盖了步骤4，如下表所示：

| 迁移任务 | 详细信息 |
|---------|----------|
| **第1步： [迁移入门](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 了解迁移到Adobe Analytics的好处以及基本迁移过程。 |
| **第2步： [选择迁移路径](/help/getting-started/cja-migration/cja-migration-path.md)** | 可以使用各种方法迁移到Customer Journey Analytics。 根据贵组织当前的Adobe Analytics环境和长期目标，选择最适合贵组织的方法。 |
| <span class="preview">**步骤3： [将数据映射到XDM架构](/help/getting-started/cja-migration/cja-migration-xdm.md)**</span> | <span class="preview">[XDM架构](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重用的方式描述数据结构。 通过在系统中以一致的方式定义数据，更容易保留含义并因此从数据中获取价值。<p>大多数迁移路径都要求您创建新的XDM架构，或使用数据流映射将现有Adobe Analytics架构映射到XDM。</p></span> |
| **第4步： [将数据发送到Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 将数据发送到Adobe Experience Platform的过程因您在步骤2中选择的迁移路径而异。 |
| **步骤5： [保留历史数据](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多数组织都需要将其历史Adobe Analytics数据保留一定时间。 可以使用各种选项来完成此操作。 |
| **步骤6： [计划用户载入](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 您应该给用户充足的时间（3 - 6个月），以熟悉Analysis Workspace在Customer Journey Analytics方面的主要差异。 |
| **步骤7： [移植报表API使用情况](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics报表API采用相同的格式，但使用不同的端点。 将报表API使用情况从Adobe Analytics报表API移植到Customer Journey Analytics报表API。 |
| **步骤8： [替换数据馈送并Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | 决定如何使用Customer Journey Analytics中可用的导出选项，以替换在Adobe Analytics中使用的数据馈送和Data Warehouse功能。 |
| **第9步： [迁移项目和组件](/help/getting-started/cja-migration/cja-migration-projects.md)** | 利用Adobe Analytics中的组件迁移区域，可将项目及其关联的组件从Adobe Analytics迁移到Customer Journey Analytics。 |

{style="table-layout:auto"}

+++

[XDM架构](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重用的方式描述数据结构。 通过在系统中以一致的方式定义数据，更容易保留含义并因此从数据中获取价值。<p>大多数迁移路径都要求您创建新的XDM架构，或使用数据流映射将现有Adobe Analytics架构映射到XDM。</p>

并非所有迁移路径都需要将Adobe Analytics数据映射到XDM架构。 下表显示了哪些实施方法需要XDM架构映射：


| 迁移路径 | 是否需要XDM映射？ | 更多信息 |
|---------|----------|---------|
| **Experience PlatformWeb SDK的新实施**<p>基本步骤为：</p><ol><li>为您的组织创建XDM架构</li><li>实施Web SDK</li><li>将数据发送到Platform</li></ol> | 否 | 不需要映射，因为您已经 [设置新的XDM架构](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) 作为新实施的一部分。 |
| **迁移Adobe Analytics实施以使用Web SDK**<p>基本步骤为：</p><ol><li>将您现有的Adobe Analytics实施移动到Web SDK中，并验证在那里的所有组件是否都正常工作。</li><li>根据需要为您的组织创建XDM架构。</li><li>使用数据流映射将数据对象中的所有字段映射到您的XDM架构。</li><li>将数据发送到Platform</li></ol> | 是 | 与您的数据团队合作，确定贵组织适用于Customer Journey Analytics的理想架构设计，然后确定如何将eVar和Prop映射到XDM。</br>[使用数据准备将数据对象中的所有字段映射到您的XDM架构](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **配置现有的Adobe Analytics Web SDK实施以将数据发送到Customer Journey Analytics**<p>基本步骤为：</p><ol><li>开始向Customer Journey Analytics发送数据。<!-- What's involved here? Just point it at CJA? --></li><li>（可选）根据需要为您的组织创建XDM架构。</li><li>使用数据流映射将数据对象中的所有字段映射到您的XDM架构。</li></ol> | 是 | 与您的数据团队合作，确定贵组织适用于Customer Journey Analytics的理想架构设计，然后确定如何将eVar和Prop映射到XDM。</br>[使用数据准备将数据对象中的所有字段映射到您的XDM架构](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **Analytics源连接器**</br>&#x200B;如果您的Adobe Analytics实施AppMeasurement或Analytics扩展，则可以开始以Customer Journey Analytics将数据发送到数据视图。<p>这是将数据导入Customer Journey Analytics的最简单方法，但长期而言是最不可行的方法。</p> | 否 | 不需要映射，因为Analytics Source Connector使用您现有的Adobe Analytics架构而不是XDM架构。 |

{style="table-layout:auto"}

<!-- Does it benefit the customer to do this all at the same time if they're using multiple AEP apps? If so, have multiple sections like this. Or can they do CJA first and AJO later?

### Plan data mapping for Customer Journey Analytics


### Plan data mapping for Customer Journey analytics and other Adobe Experience platform applications

-->

## 接下来，将数据发送到Adobe Experience Platform

使用上述信息选择迁移路径后，了解如何 [将数据发送到Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) 具体取决于您选择的迁移路径。
