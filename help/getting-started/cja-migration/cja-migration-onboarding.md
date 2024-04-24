---
title: 在迁移到Customer Journey Analytics时规划用户载入
description: 在迁移到Customer Journey Analytics时规划用户载入
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 34ccab37-a37f-4d69-aa96-ae1047b1f195
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 0%

---

# 步骤6：在迁移到Customer Journey Analytics时规划用户入门

+++展开此部分可查看此页面上的信息在较大的迁移过程中所处的位置。 确保所有先前的迁移步骤均已完成。

在继续此部分之前，请先确保已完成所有以前的迁移任务。

此页面上的信息涵盖了步骤6，如下表所示：

| 迁移任务 | 详细信息 |
|---------|----------|
| **第1步： [迁移入门](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 了解迁移到Adobe Analytics的好处以及基本迁移过程。 |
| **第2步： [选择迁移路径](/help/getting-started/cja-migration/cja-migration-path.md)** | 可以使用各种方法迁移到Customer Journey Analytics。 根据贵组织当前的Adobe Analytics环境和长期目标，选择最适合贵组织的方法。 |
| **步骤3： [将数据映射到XDM架构](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM架构](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重用的方式描述数据结构。 通过在系统中以一致的方式定义数据，更容易保留含义并因此从数据中获取价值。<p>大多数迁移路径都要求您创建新的XDM架构，或使用数据流映射将现有Adobe Analytics架构映射到XDM。</p> |
| **第4步： [将数据发送到Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 将数据发送到Adobe Experience Platform的过程因您在步骤2中选择的迁移路径而异。 |
| **步骤5： [保留历史数据](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多数组织都需要将其历史Adobe Analytics数据保留一定时间。 可以使用各种选项来完成此操作。 |
| <span class="preview">**步骤6： [计划用户载入](/help/getting-started/cja-migration/cja-migration-onboarding.md)**</span> | <span class="preview">您应该给用户充足的时间（3 - 6个月），以熟悉Analysis Workspace在Customer Journey Analytics方面的主要差异。</span> |
| **步骤7： [移植报表API使用情况](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics报表API采用相同的格式，但使用不同的端点。 将报表API使用情况从Adobe Analytics报表API移植到Customer Journey Analytics报表API。 |
| **步骤8： [替换数据馈送并Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | 决定如何使用Customer Journey Analytics中可用的导出选项，以替换在Adobe Analytics中使用的数据馈送和Data Warehouse功能。 |
| **第9步： [迁移项目和组件](/help/getting-started/cja-migration/cja-migration-projects.md)** | 利用Adobe Analytics中的组件迁移区域，可将项目及其关联的组件从Adobe Analytics迁移到Customer Journey Analytics。 |

{style="table-layout:auto"}

+++

Customer Journey Analytics与Adobe Analytics之间存在一些用户需要注意的关键区别。

与Adobe Analytics中一样，Analysis Workspace是Customer Journey Analytics中主要面向用户的工具。 但是，在Customer Journey Analytics中使用Analysis Workspace时存在一些用户需要注意的主要差异。

您应该给用户充足的时间（3 - 6个月），以熟悉Analysis Workspace在Customer Journey Analytics方面的主要差异。

有关Adobe Analytics与Customer Journey Analytics之间的一些主要差异的信息，请参阅 [适用于Adobe Analytics用户的用户指南](/help/getting-started/aa-to-cja-user.md).

## 接下来，移植报表API使用情况

Customer Journey Analytics报表API采用相同的格式，但使用不同的端点。 [移植报表API使用情况](/help/getting-started/cja-migration/cja-migration-api.md) 从Adobe Analytics报表API到Customer Journey Analytics报表API。
