---
title: 开始升级到 Customer Journey Analytics
description: 规划从 Adobe Analytics 升级到 Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: eb9b749a5c61da3b4b5d2eeeed93bf5e4702a415
workflow-type: ht
source-wordcount: '721'
ht-degree: 100%

---

# 步骤 1：开始升级到 Customer Journey Analytics

>[!AVAILABILITY]
>
>此页面上的信息将被以下更全面的升级信息取代： <ul><li>**建议的升级步骤**<p>有关详细信息，请参阅[从 Adobe Analytics 升级到 Customer Journey Analytics 时的推荐路径](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。</p></li><li>**Customer Journey Analytics 升级指南**<p>现有新的升级指南可用，用于动态生成适合您的组织和独特情况的升级步骤。</p><p>要从 Customer Journey Analytics 访问升级指南，请选择&#x200B;**[!UICONTROL 工作区]**&#x200B;选项卡，然后在左侧面板中选择&#x200B;**[!UICONTROL 升级到 Customer Journey Analytics]**。按照屏幕上的说明操作。</p></li></ul>

Customer Journey Analytics 是下一代分析产品。它允许进行多渠道数据收集（在线和离线数据），并结合了强大的报告时处理功能（通过在数据视图中定义组件和派生字段）。

在开始从 Adobe Analytics 升级到 Customer Journey Analytics 之前，您应该了解 Customer Journey Analytics 的优势以及成功升级所需的步骤。

## 了解 Customer Journey Analytics 的好处

以下是一些主要优势：（如需查看完整列表以及每个主要功能的更多信息，请参阅[仅在 Customer Journey Analytics 中提供的功能](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics)。）

* [多渠道报告](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  Customer Journey Analytics 与 Experience Platform 保存各种数据架构和类型的能力相结合。收集和报告来自多种渠道的数据，例如数字（网络）、销售点系统、移动设备、CRM 系统等。

* [数据视图中的报告时转换](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  通过 Customer Journey Analytics 中的数据视图，可进一步解释从某个连接获得的数据。您可以在不更改实施方法的情况下更改或删除数据，使用子字符串来改变维度，从任何值创建量度，将子事件分段，或使用派生字段。所有这些转换都是非破坏性的。

* [转换适用于历史数据和新数据](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  数据视图操作可以以非破坏性的方式应用于历史数据和新数据。

* [派生字段](/help/data-views/derived-fields/derived-fields.md)

  派生字段允许在报告时对数据进行转换。可即时组合、更正或创建数据，并以追溯的方式将数据应用于所有报告。

* [数据视图取代了虚拟报告包](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  数据视图继承了当前存在的虚拟报告包的概念，并对其进行了扩展，以便对通过连接获得的数据进行更多控制。这些更改使常规设置（如时区和会话超时间隔）可进行配置并具有可回溯性。

* [无限量的客户维度和量度](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  值可以是数字、文本、对象、列表，也可以是它们的混合。维度可以是嵌套的或分层的。

## 了解升级流程

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
该页面上的信息涵盖升级过程中的第 1 步，如下表所示。完成此表中的所有步骤即可从 Adobe Analytics 升级到 Customer Journey Analytics。

| 升级任务 | 详细信息 |
|---------|----------|
| <span class="preview">**步骤 1：开始升级**</span> | <span class="preview">了解升级到 Customer Journey Analytics 的好处以及基本升级流程。</span> |
| **步骤 2：[选择升级路径](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | 有多种方法可以升级到 Customer Journey Analytics。根据您组织当前的 Adobe Analytics 环境和长期目标，选择最适合您组织的方法。 |
| **步骤 3：[将数据发送到 Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | 将数据发送到 Adobe Experience Platform 的流程因您在步骤 2 中选择的升级路径而异。 |
| **步骤 4：[保留历史数据](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | 大多数组织需要在一定时间内保留其 Adobe Analytics 的历史数据。有多种选项可以实现此目的。 |
| **步骤 5：[执行额外的实施任务](/help/getting-started/cja-getting-started.md)** | 在升级流程的这个阶段，您需要执行各种任务，然后您的 Customer Journey Analytics environment 环境才可供使用。<p>这些额外的任务适用于从 Adobe Analytics 进行升级，以及新的 Customer Journey Analytics 实施。</p><p>这些任务包括：</p><ul><li>将其他数据引入 Experience Platform</li><li>在 Platform 数据集与 Customer Journey Analytics 之间创建连接</li><li>创建数据视图</li><li>移植报告 API 使用情况</li><li>数据源和 Data Warehouse 的核算</li><li>迁移项目和组件</li><li>规划用户加入流程</li></ul> <p>有关更多信息，请参阅 [Customer Journey Analytics 快速入门](/help/getting-started/cja-getting-started.md)。 |

{style="table-layout:auto"}

## 首先，选择升级路径

有多种方法可以升级到 Customer Journey Analytics。[选择最适合您组织的方法](/help/getting-started/cja-upgrade/cja-upgrade-path.md)。

您选择的升级路径取决于您组织当前的 Adobe Analytics 环境和长期目标。
