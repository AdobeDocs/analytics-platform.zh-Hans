---
title: 移植到Customer Journey Analytics时的报表API使用情况
description: 了解如何将API的使用从Adobe Analytics移植到Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d26a6956-870f-44f2-9c32-f732bff17737
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# 步骤7：在迁移到Customer Journey Analytics时移植报表API的使用情况

+++展开此部分可查看此页面上的信息在较大的迁移过程中所处的位置。 确保所有先前的迁移步骤均已完成。

在继续此部分之前，请先确保已完成所有以前的迁移任务。

此页面上的信息涵盖了步骤7，如下表所示：

| 迁移任务 | 详细信息 |
|---------|----------|
| **第1步： [迁移入门](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 了解迁移到Adobe Analytics的好处以及基本迁移过程。 |
| **第2步： [选择迁移路径](/help/getting-started/cja-migration/cja-migration-path.md)** | 可以使用各种方法迁移到Customer Journey Analytics。 根据贵组织当前的Adobe Analytics环境和长期目标，选择最适合贵组织的方法。 |
| **步骤3： [将数据发送到Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 将数据发送到Adobe Experience Platform的过程因您在步骤2中选择的迁移路径而异。 |
| **第4步： [保留历史数据](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多数组织都需要将其历史Adobe Analytics数据保留一定时间。 可以使用各种选项来完成此操作。 |
| **步骤5： [执行其他实施任务](/help/getting-started/cja-getting-started.md)** | 在迁移过程的这一阶段，您需要在Customer Journey Analytics环境准备就绪之前执行各种任务。<p>这些附加任务适用于从Adobe Analytics进行的迁移以及新的Customer Journey Analytics实施。</p><p>这些任务包括：</p><ul><li>将其他数据引入Experience Platform</li><li>在Platform数据集与Customer Journey Analytics之间创建连接</li><li>创建数据视图</li><li>移植报表API使用情况</li><li>考虑数据馈送和Data Warehouse</li><li>迁移项目和组件</li><li>Planning用户载入</li></ul> <p>有关更多信息，请参阅 [Customer Journey Analytics快速入门](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

将报表API使用情况从Adobe Analytics报表API移植到Customer Journey Analytics报表API。

Customer Journey Analytics报表API采用相同的格式，但使用了不同的子域。

请参阅Adobe Analytics和Customer Journey Analytics的端点指南。

大多数API调用都可以轻松地从Adobe Analytics转换为Customer Journey Analytics。

将Customer Journey AnalyticsAPI添加到其API项目中。

将IMS组织ID添加到其API调用的标头。

cja.adobe.io与analytics.adobe.io

其他标题

## 接下来，替换数据馈送并Data Warehouse

决定如何使用Customer Journey Analytics中可用的导出选项，以 [替换数据馈送和Data Warehouse功能](/help/getting-started/cja-migration/cja-migration-export-options.md) 您在Adobe Analytics中使用。
