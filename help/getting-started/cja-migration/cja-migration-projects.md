---
title: 将项目和组件迁移到Customer Journey Analytics
description: 了解组件迁移以将项目和组件迁移到Customer Journey Analytics。
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 6e5c3ecf-6eba-4dfa-8bf2-e43d56cfc65f
source-git-commit: 21d77f06595993172460b724dc7991cb9a5a02a8
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 11%

---

# 步骤9：将项目和组件迁移到Customer Journey Analytics

+++展开此部分可查看此页面上的信息在较大的迁移过程中所处的位置。 确保所有先前的迁移步骤均已完成。

在继续此部分之前，请先确保已完成所有以前的迁移任务。

此页面上的信息涵盖了步骤9，如下表所示：

| 迁移任务 | 详细信息 |
|---------|----------|
| **第1步： [迁移入门](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 了解迁移到Adobe Analytics的好处以及基本迁移过程。 |
| **第2步： [选择迁移方法](/help/getting-started/cja-migration/cja-migration-method.md)** | 可以使用各种方法迁移到Customer Journey Analytics。 根据贵组织当前的Adobe Analytics环境和长期目标，选择最适合贵组织的方法。 |
| **步骤3： [将数据发送到Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 将数据发送到Adobe Experience Platform的过程因您在步骤1中选择的迁移方法而异。 |
| **第4步： [将数据映射到XDM架构](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM架构](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重用的方式描述数据结构。 通过在系统中以一致的方式定义数据，更容易保留含义并因此从数据中获取价值。<p>大多数迁移方法都要求您创建新的XDM架构，或使用数据流映射将现有Adobe Analytics架构映射到XDM。</p> |
| **步骤5： [保留历史数据](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多数组织都需要将其历史Adobe Analytics数据保留一定时间。 可以使用各种选项来完成此操作。 |
| **步骤6： [计划用户载入](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 您应该给用户充足的时间（3 - 6个月），以熟悉Analysis Workspace在Customer Journey Analytics方面的主要差异。 |
| **步骤7： [移植报表API使用情况](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics报表API采用相同的格式，但使用不同的端点。 将报表API使用情况从Adobe Analytics报表API移植到Customer Journey Analytics报表API。 |
| **步骤8： [替换数据馈送并Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | 决定如何使用Customer Journey Analytics中可用的导出选项，以替换在Adobe Analytics中使用的数据馈送和Data Warehouse功能。 |
| <span class="preview">**第9步： [迁移项目和组件](/help/getting-started/cja-migration/cja-migration-projects.md)**</span> | <span class="preview">利用Adobe Analytics中的组件迁移区域，可将项目及其关联的组件从Adobe Analytics迁移到Customer Journey Analytics。</span> |
| **步骤10： [执行迁移后任务](/help/getting-started/cja-getting-started.md)** | 完成迁移后，您需要执行各种任务，包括将其他数据导入Experience Platform、在Platform数据集与Customer Journey Analytics之间创建连接、创建数据视图以及学习如何在Analysis Workspace中报告跨渠道数据。 |

{style="table-layout:auto"}

+++

利用Adobe Analytics中的组件迁移区域，可将项目及其关联的组件从Adobe Analytics迁移到Customer Journey Analytics。

迁移过程包括：

* 在 Customer Journey Analytics 中重新创建 Adobe Analytics 项目。

* 将来自 Adobe Analytics 报告包的维度和指标映射到 Customer Journey Analytics 数据视图中的维度和指标。

在开始迁移之前，首先[准备将组件和项目从 Adobe Analytics 迁移到 Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)。

作出所有必要的准备后，即可[将组件和项目从 Adobe Analytics 迁移到 Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html)。

## 接下来，执行迁移后的任务

在您之后 [将组件和项目从Adobe Analytics迁移到Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html)中，您需要执行各种任务以完成设置Customer Journey Analytics环境。 这些任务包括将其他数据引入Experience Platform、在Platform数据集与Customer Journey Analytics之间创建连接、创建数据视图以及学习如何在Analysis Workspace中报告跨渠道数据。

要了解有关这些迁移任务的更多信息，请参阅 [Customer Journey Analytics快速入门](/help/getting-started/cja-getting-started.md).
