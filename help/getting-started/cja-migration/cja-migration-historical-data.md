---
title: 迁移到Customer Journey Analytics时保留历史数据
description: 了解在迁移到Customer Journey Analytics时如何保留历史数据
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 923dfac33fcde368392fe29c6530069cc0d8fb9d
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 0%

---

# 步骤5：迁移到Customer Journey Analytics时保留历史数据

+++展开此部分可查看此页面上的信息在较大的迁移过程中所处的位置。 确保所有先前的迁移步骤均已完成。

在继续此部分之前，请先确保已完成所有以前的迁移任务。

此页面上的信息涵盖了步骤5，如下表所示：

| 迁移任务 | 详细信息 |
|---------|----------|
| **第1步： [迁移入门](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 了解迁移到Adobe Analytics的好处以及基本迁移过程。 |
| **第2步： [选择迁移方法](/help/getting-started/cja-migration/cja-migration-method.md)** | 可以使用各种方法迁移到Customer Journey Analytics。 根据贵组织当前的Adobe Analytics环境和长期目标，选择最适合贵组织的方法。 |
| **步骤3： [将数据发送到Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 将数据发送到Adobe Experience Platform的过程因您在步骤1中选择的迁移方法而异。 |
| **第4步： [将数据映射到XDM架构](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM架构](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重用的方式描述数据结构。 通过在系统中以一致的方式定义数据，更容易保留含义并因此从数据中获取价值。<p>大多数迁移方法都要求您创建新的XDM架构，或使用数据流映射将现有Adobe Analytics架构映射到XDM。</p> |
| <span class="preview">**步骤5： [保留历史数据](/help/getting-started/cja-migration/cja-migration-historical-data.md)**</span> | <span class="preview">大多数组织都需要将其历史Adobe Analytics数据保留一定时间。 可以使用各种选项来完成此操作。</span> |
| **步骤6： [计划用户载入](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 您应该给用户充足的时间（3 - 6个月），以熟悉Analysis Workspace在Customer Journey Analytics方面的主要差异。 |
| **步骤7： [移植报表API使用情况](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics报表API采用相同的格式，但使用不同的端点。 将报表API使用情况从Adobe Analytics报表API移植到Customer Journey Analytics报表API。 |
| **步骤8： [替换数据馈送并Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | 决定如何使用Customer Journey Analytics中可用的导出选项，以替换在Adobe Analytics中使用的数据馈送和Data Warehouse功能。 |
| **第9步： [迁移项目和组件](/help/getting-started/cja-migration/cja-migration-projects.md)** | 利用Adobe Analytics中的组件迁移区域，可将项目及其关联的组件从Adobe Analytics迁移到Customer Journey Analytics。 |

{style="table-layout:auto"}

+++

选择下列选项之一，以在从Adobe Analytics移动到Customer Journey Analytics时保留历史数据：

## 利用Analytics Source Connector

您可以利用 [Analytics源连接器](/help/data-ingestion/analytics.md) 以保留历史数据。 无论选择哪种迁移方法（即使使用Web SDK迁移），您都可以使用Analytics Source Connector保留Adobe Analytics环境中的历史数据。

您可以使用Analytics Source Connector通过以下方式保留历史数据：

* 将历史数据引入其自身的专用位置，与当前数据分开。

* 以允许您将其绑定到新数据的方式映射历史数据。 <!-- Possible? Explain -->

## 维护您现有的Adobe Analytics实施

您可以在特定的时间范围内（例如，1年）维护现有Adobe Analytics实施以及新的Customer Journey Analytics实施。 选择此选项时，您必须计划在Customer Journey Analytics中有足够的数据后停用Adobe Analytics实施。

请联系您的Adobe客户代表以确定此选项的定价。

## 接下来，计划用户载入

[规划Customer Journey Analytics用户入门培训](/help/getting-started/cja-migration/cja-migration-onboarding.md). 您应该给用户充足的时间（3 - 6个月），以熟悉Analysis Workspace在Customer Journey Analytics方面的主要差异。
