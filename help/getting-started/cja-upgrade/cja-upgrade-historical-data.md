---
title: 升级到Customer Journey Analytics时保留历史数据
description: 了解在升级到Customer Journey Analytics时如何保留历史数据
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 0%

---

# 步骤4：升级时保留历史数据

+++展开此部分，查看此页面上的信息在较大的升级过程中的位置。 确保已完成所有以前的升级步骤。

在继续此部分之前，请先确保已完成所有以前的升级任务。

此页面上的信息介绍了升级过程的步骤4，如下表所示：

| 升级任务 | 详细信息 |
|---------|----------|
| **步骤1：[开始升级](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | 了解升级到Customer Journey Analytics的好处以及基本升级过程。 |
| **步骤2：[选择升级路径](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | 有多种方法可用于升级到Customer Journey Analytics。 根据贵组织当前的Adobe Analytics环境和长期目标，选择最适合贵组织的方法。 |
| **步骤3：[将数据发送到Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | 将数据发送到Adobe Experience Platform的过程因您在步骤2中选择的升级路径而异。 |
| <span class="preview">**步骤4：保留历史数据**</span> | <span class="preview">大多数组织都需要保留其历史Adobe Analytics数据一段特定时间。 有多种选项可用于完成此操作。</span> |
| **步骤5：[执行其他实施任务](/help/getting-started/cja-getting-started.md)** | 在升级过程的这一阶段，您需要在Customer Journey Analytics环境准备好使用之前执行各种任务。<p>这些其他任务适用于从Adobe Analytics升级以及新的Customer Journey Analytics实施。</p><p>这些任务包括：</p><ul><li>将其他数据引入Experience Platform</li><li>在Platform数据集与Customer Journey Analytics之间创建连接</li><li>创建数据视图</li><li>移植报表API使用情况</li><li>考虑数据馈送和Data Warehouse</li><li>迁移项目和组件</li><li>Planning用户载入</li></ul> <p>有关详细信息，请参阅[Customer Journey Analytics快速入门](/help/getting-started/cja-getting-started.md)。 |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>此页面上的信息将替换为以下更全面的升级信息： <ul><li>**建议的升级步骤**<p>有关详细信息，请参阅[从Adobe Analytics升级到Customer Journey Analytics时推荐的路径](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。</p></li><li>**Customer Journey Analytics升级指南**<p>提供了新的升级指南，可动态生成针对贵组织和独特环境定制的升级步骤。</p><p>要从Customer Journey Analytics访问指南，请选择&#x200B;**[!UICONTROL Workspace]**&#x200B;选项卡，然后在左侧面板中选择&#x200B;**[!UICONTROL 升级到Customer Journey Analytics]**。 按照屏幕上的说明操作。</p></li></ul>

选择下列选项之一，以在从Adobe Analytics移动到Customer Journey Analytics时保留历史数据：

>[!IMPORTANT]
>
>选择如何保留历史数据时，请联系您的Adobe客户代表以确定价格。

## 使用Analytics源连接器

您可以使用[Analytics Source Connector](/help/data-ingestion/analytics.md)保留历史数据。 无论您选择什么升级路径(即使使用Web SDK升级)，都可以使用Analytics Source Connector保留Adobe Analytics环境中的历史数据。

您可以使用Analytics Source Connector将历史数据引入其自己的专用位置（与当前数据分开），以保留历史数据。

Analytics Source Connector必须在您需要访问历史数据时正常运行。

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## 维护您现有的Adobe Analytics实施

您可以在特定的时间范围内（例如，1年）维护现有Adobe Analytics实施以及新的Customer Journey Analytics实施。 选择此选项时，请考虑以下事项：

* 数据在Experience Platform中不可用。

* 在Customer Journey Analytics中拥有足够的数据后，您应该计划停用Adobe Analytics实施。

## 接下来，执行其他实施任务

在升级过程的这一阶段，您需要在Customer Journey Analytics环境准备好使用之前执行各种实施任务。

这些其他任务适用于从Adobe Analytics升级以及新的Customer Journey Analytics实施。

这些任务包括：

* 将其他数据引入Experience Platform

* 在Platform数据集与Customer Journey Analytics之间创建连接

* 创建数据视图

* 移植报表API使用情况

* 考虑数据馈送和Data Warehouse用例

* 迁移项目和组件

* Planning用户载入

有关详细信息，请从[Customer Journey Analytics快速入门](/help/getting-started/cja-getting-started.md)中的步骤2开始。
