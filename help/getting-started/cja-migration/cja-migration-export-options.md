---
title: 迁移到Customer Journey Analytics时替换数据馈送和Data Warehouse
description: 规划从Adobe Analytics到Customer Journey Analytics的迁移
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 3a99aed3-26b9-494f-aaf9-f8eaa2c2d88f
source-git-commit: 21d77f06595993172460b724dc7991cb9a5a02a8
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 1%

---

# 步骤8：在迁移到Customer Journey Analytics时替换数据馈送和Data Warehouse

+++展开此部分可查看此页面上的信息在较大的迁移过程中所处的位置。 确保所有先前的迁移步骤均已完成。

在继续此部分之前，请先确保已完成所有以前的迁移任务。

此页面上的信息涵盖了步骤8，如下表所示：

| 迁移任务 | 详细信息 |
|---------|----------|
| **第1步： [迁移入门](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 了解迁移到Adobe Analytics的好处以及基本迁移过程。 |
| **第2步： [选择迁移方法](/help/getting-started/cja-migration/cja-migration-method.md)** | 可以使用各种方法迁移到Customer Journey Analytics。 根据贵组织当前的Adobe Analytics环境和长期目标，选择最适合贵组织的方法。 |
| **步骤3： [将数据发送到Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 将数据发送到Adobe Experience Platform的过程因您在步骤1中选择的迁移方法而异。 |
| **第4步： [将数据映射到XDM架构](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM架构](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重用的方式描述数据结构。 通过在系统中以一致的方式定义数据，更容易保留含义并因此从数据中获取价值。<p>大多数迁移方法都要求您创建新的XDM架构，或使用数据流映射将现有Adobe Analytics架构映射到XDM。</p> |
| **步骤5： [保留历史数据](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多数组织都需要将其历史Adobe Analytics数据保留一定时间。 可以使用各种选项来完成此操作。 |
| **步骤6： [计划用户载入](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 您应该给用户充足的时间（3 - 6个月），以熟悉Analysis Workspace在Customer Journey Analytics方面的主要差异。 |
| **步骤7： [移植报表API使用情况](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics报表API采用相同的格式，但使用不同的端点。 将报表API使用情况从Adobe Analytics报表API移植到Customer Journey Analytics报表API。 |
| <span class="preview">**步骤8： [替换数据馈送并Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)**</span> | <span class="preview">决定如何使用Customer Journey Analytics中可用的导出选项，以替换在Adobe Analytics中使用的数据馈送和Data Warehouse功能。</span> |
| **第9步： [迁移项目和组件](/help/getting-started/cja-migration/cja-migration-projects.md)** | 利用Adobe Analytics中的组件迁移区域，可将项目及其关联的组件从Adobe Analytics迁移到Customer Journey Analytics。 |
| **步骤10： [执行迁移后任务](/help/getting-started/cja-getting-started.md)** | 完成迁移后，您需要执行各种任务，包括将其他数据导入Experience Platform、在Platform数据集与Customer Journey Analytics之间创建连接、创建数据视图以及学习如何在Analysis Workspace中报告跨渠道数据。 |

{style="table-layout:auto"}

+++

如果您当前使用Adobe Analytics中的数据馈送或Data Warehouse，请使用下表了解Customer Journey Analytics中可用的各种导出选项：

| Adobe Analytics | Customer Journey Analytics |
|---------|----------|
| 数据馈送 | 评估您的数据馈送用例，然后使用Customer Journey Analytics中提供的任意替代导出方法组合： <ul><li>要导出原始数据集， [将数据集导出到云存储目标](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets). &#x200B;</li><li>对于使用人员ID或时间戳的受众或事件级导出，请使用 [完整表导出](/help/analysis-workspace/export/export-cloud.md). &#x200B;</li><li>要与Power BI和Tableau直接集成，请使用 [Customer Journey AnalyticsBI扩展](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension). &#x200B;</li><li>要直接SQL访问Adobe Experience Platform中的数据，请使用 [Adobe Experience Platform查询服务](https://experienceleague.adobe.com/en/docs/experience-platform/query/home).</li></ul> |
| Data Warehouse | 更改要使用的Adobe AnalyticsData Warehouse导出 [完整表导出](/help/analysis-workspace/export/export-cloud.md) Customer Journey Analytics中。<p>Customer Journey Analytics完整表格导出是Adobe Analytics中Data Warehouse报表的演变，具有许多现在在Data Warehouse中不可用的经常请求的新功能。</p> |

{style="table-layout:auto"}

## 接下来，迁移项目和组件

使用Adobe Analytics中的组件迁移区域可以 [迁移项目及其关联的组件](/help/getting-started/cja-migration/cja-migration-projects.md) 从Adobe Analytics到Customer Journey Analytics。
