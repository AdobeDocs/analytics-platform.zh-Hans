---
title: 迁移到Customer Journey Analytics入门
description: 规划从Adobe Analytics到Customer Journey Analytics的迁移
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: 21d77f06595993172460b724dc7991cb9a5a02a8
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 8%

---

# 步骤1：迁移到Customer Journey Analytics入门

Customer Journey Analytics是下一代分析。 它允许多渠道数据收集（在线和离线数据），结合强大的报表时间处理功能（通过定义数据视图中的组件和派生字段）。

在开始从Adobe Analytics迁移到Customer Journey Analytics的过程之前，您应该了解Customer Journey Analytics的好处以及成功迁移所需的步骤。

## 了解Customer Journey Analytics的好处

以下是一些主要优势：(有关所有这些主要功能的完整列表以及更多信息，请参阅 [仅在Customer Journey Analytics中可用的功能](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics).)

* [多渠道报表](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  Customer Journey Analytics 与 Experience Platform 保存各种数据架构和类型的能力相结合。从多个渠道(如数字(Web)、销售点系统、移动设备、CRM系统等)收集和报告数据。

* [数据视图中的报表时间转换](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  通过 Customer Journey Analytics 中的数据视图，可进一步解释从某个连接获得的数据。您可以在不更改实施的情况下更改或删除数据，使用子字符串处理维度，从任何值创建量度，过滤子项或使用派生字段。 所有这些转变都是非破坏性的。

* [转换适用于历史数据和新数据](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  数据视图操作能够以无损的方式应用于历史数据和新数据。

* [派生字段](/help/data-views/derived-fields/derived-fields.md)

  通过派生字段，可为数据转换报告时间。可即时组合、更正或创建数据，并以追溯的方式将数据应用于所有报告。

* [数据视图替换虚拟报表包](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  数据视图采用虚拟报表包当前存在的概念，并将其扩展到对数据启用其他控制由连接提供。 这些更改使常规设置（如时区和会话超时间隔）可进行配置并具有可回溯性。

* [无限量的客户维度和量度](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  值可以是数字、文本、对象、列表或所有这些的混合。 Dimension可以嵌套或分层。

## 了解迁移过程

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
此页面表示迁移的步骤1，如下表所示。 完成此表中的所有步骤以从Adobe Analytics迁移到Customer Journey Analytics。

| 任务 | 详细信息 |
|---------|----------|
| **第1步： [迁移入门](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 了解迁移到Adobe Analytics的好处以及基本迁移过程。 |
| **第2步： [选择迁移方法](/help/getting-started/cja-migration/cja-migration-method.md)** | 可以使用各种方法迁移到Customer Journey Analytics。 选择最适合您组织的方法，同时考虑到您组织当前的Adobe Analytics环境和您的长期目标。 |
| **步骤3： [将数据发送到Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 将数据发送到Adobe Experience Platform的过程因您在步骤1中选择的迁移方法而异。 |
| **第4步： [将数据映射到XDM架构](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM架构](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重用的方式描述数据结构。 通过在系统中以一致的方式定义数据，更容易保留含义并因此从数据中获取价值。<p>大多数迁移方法都要求您创建新的XDM架构，或使用数据流映射将现有Adobe Analytics架构映射到XDM。</p> |
| **步骤5： [保留历史数据](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多数组织都需要将其历史Adobe Analytics数据保留一定时间。 可以使用各种选项来完成此操作。 |
| **步骤6： [计划用户载入](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 您应该给用户充足的时间（3 - 6个月），以熟悉Analysis Workspace在Customer Journey Analytics方面的主要差异。 |
| **步骤7： [移植报表API使用情况](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics报表API采用相同的格式，但使用不同的端点。 将报表API使用情况从Adobe Analytics报表API移植到Customer Journey Analytics报表API。 |
| **步骤8： [替换数据馈送并Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | 决定如何使用Customer Journey Analytics中可用的导出选项，以替换在Adobe Analytics中使用的数据馈送和Data Warehouse功能。 |
| **第9步： [迁移项目和组件](/help/getting-started/cja-migration/cja-migration-projects.md)** | 利用Adobe Analytics中的组件迁移区域，可将项目及其关联的组件从Adobe Analytics迁移到Customer Journey Analytics。 |
| **步骤10： [执行迁移后任务](/help/getting-started/cja-getting-started.md)** | 完成迁移后，您需要执行各种任务，包括将其他数据导入Experience Platform、在Platform数据集与Customer Journey Analytics之间创建连接、创建数据视图以及学习如何在Analysis Workspace中报告跨渠道数据。 |

{style="table-layout:auto"}

## 首先，选择迁移方法

可以使用各种方法迁移到Customer Journey Analytics。 [选择最适合您组织的方法](/help/getting-started/cja-migration/cja-migration-method.md).

您选择的迁移方法取决于贵组织当前的Adobe Analytics环境和长期目标。
