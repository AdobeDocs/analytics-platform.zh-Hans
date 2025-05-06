---
title: 升级到 Customer Journey Analytics 时保留历史数据
description: 学习如何在升级到 Customer Journey Analytics 时保留历史数据
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '673'
ht-degree: 100%

---

# 步骤 4：升级时保留历史数据

+++展开此部分，了解此页面上的信息在更大范围的升级过程中所占的位置。确保所有先前的升级步骤均已完成。

在继续本部分之前，请首先确保您已完成所有先前的升级任务。

该页面上的信息涵盖升级过程中的第 4 步，如下表所示：

| 升级任务 | 详细信息 |
|---------|----------|
| **步骤 1：[开始升级](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | 了解升级到 Customer Journey Analytics 的好处以及基本升级流程。 |
| **步骤 2：[选择升级路径](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | 有多种方法可以升级到 Customer Journey Analytics。根据您组织当前的 Adobe Analytics 环境和长期目标，选择最适合您组织的方法。 |
| **步骤 3：[将数据发送到 Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | 将数据发送到 Adobe Experience Platform 的流程因您在步骤 2 中选择的升级路径而异。 |
| <span class="preview">**步骤 4：保留历史数据**</span> | <span class="preview">大多数组织需要在一定时间内保留其 Adobe Analytics 的历史数据。有多种选项可以实现此目的。</span> |
| **步骤 5：[执行额外的实施任务](/help/getting-started/cja-getting-started.md)** | 在升级流程的这个阶段，您需要执行各种任务，然后您的 Customer Journey Analytics environment 环境才可供使用。<p>这些额外的任务适用于从 Adobe Analytics 进行升级，以及新的 Customer Journey Analytics 实施。</p><p>这些任务包括：</p><ul><li>将其他数据引入 Experience Platform</li><li>在 Platform 数据集与 Customer Journey Analytics 之间创建连接</li><li>创建数据视图</li><li>移植报告 API 使用情况</li><li>数据源和 Data Warehouse 的核算</li><li>迁移项目和组件</li><li>规划用户加入流程</li></ul> <p>有关更多信息，请参阅 [Customer Journey Analytics 快速入门](/help/getting-started/cja-getting-started.md)。 |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>此页面上的信息将被以下更全面的升级信息取代： <ul><li>**建议的升级步骤**<p>有关详细信息，请参阅[从 Adobe Analytics 升级到 Customer Journey Analytics 时的推荐路径](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。</p></li><li>**Customer Journey Analytics 升级指南**<p>现有新的升级指南可用，用于动态生成适合您的组织和独特情况的升级步骤。</p><p>要从 Customer Journey Analytics 访问升级指南，请选择&#x200B;**[!UICONTROL 工作区]**&#x200B;选项卡，然后在左侧面板中选择&#x200B;**[!UICONTROL 升级到 Customer Journey Analytics]**。按照屏幕上的说明操作。</p></li></ul>

在从 Adobe Analytics 迁移到 Customer Journey Analytics 时，选择以下选项之一来保留历史数据：

>[!IMPORTANT]
>
>选择如何保留历史数据时，请联系您的 Adobe 客户代表，以确定定价。

## 使用 Analytics 源连接器

您可以使用[ Analytics 源连接器](/help/data-ingestion/analytics.md)来保留历史数据。无论您选择哪种升级路径（即使您使用 Web SDK 升级），您都可以使用 Analytics 源连接器保留来自 Adobe Analytics 环境的历史数据。

您可以使用 Analytics 源连接器将历史数据放入与当前数据分开的专用位置，从而保留历史数据。

在您需要访问历史数据的时候，Analytics 源连接器都必须一直正常工作。

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## 维护您现有的 Adobe Analytics 实施

您可以在特定时间范围内（例如 1 年）维护现有的 Adobe Analytics 实施以及新的 Customer Journey Analytics 实施。选择此选项时，请考虑以下因素：

* 数据无法在 Experience Platform 中使用。

* 在 Customer Journey Analytics 中拥有足够的数据后，您应该计划停止使用 Adobe Analytics 实施。

## 接下来，执行额外的实施任务

在升级流程的这个阶段，您需要执行各种实施任务，然后您的 Customer Journey Analytics environment 环境才可供使用。

这些额外的任务适用于从 Adobe Analytics 进行升级，以及新的 Customer Journey Analytics 实施。

这些任务包括：

* 将其他数据引入 Experience Platform

* 在 Platform 数据集与 Customer Journey Analytics 之间创建连接

* 创建数据视图

* 移植报告 API 使用情况

* 核算数据源和 Data Warehouse 用例

* 迁移项目和组件

* 规划用户加入流程

如需了解更多信息，请从 [Customer Journey Analytics 快速入门](/help/getting-started/cja-getting-started.md)中的第 2 步开始。
