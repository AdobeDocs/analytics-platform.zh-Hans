---
title: Customer Journey Analytics升级入门
description: 计划从Adobe Analytics升级到Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 9%

---

# 步骤1：开始升级到Customer Journey Analytics

>[!AVAILABILITY]
>
>此页面上的信息将替换为以下更全面的升级信息： <ul><li>**建议的升级步骤**<p>有关详细信息，请参阅[从Adobe Analytics升级到Customer Journey Analytics时推荐的路径](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。</p></li><li>**Customer Journey Analytics升级指南**<p>提供了新的升级指南，可动态生成针对贵组织和独特环境定制的升级步骤。</p><p>要从Customer Journey Analytics访问指南，请选择&#x200B;**[!UICONTROL Workspace]**&#x200B;选项卡，然后在左侧面板中选择&#x200B;**[!UICONTROL 升级到Customer Journey Analytics]**。 按照屏幕上的说明操作。</p></li></ul>

Customer Journey Analytics是新一代Analytics。 它允许多渠道数据收集（在线和离线数据），结合强大的报表时间处理功能（通过定义数据视图中的组件和派生字段）。

在开始从Adobe Analytics升级到Customer Journey Analytics的过程之前，您应该了解Customer Journey Analytics的好处以及成功升级所需的步骤。

## 了解Customer Journey Analytics的好处

以下是一些主要优势：(有关这些主要功能的完整列表以及详细信息，请参阅[仅在Customer Journey Analytics中可用的功能](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics)。)

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

  值可以是数字、文本、对象、列表或所有这些的混合。 维度可以是嵌套的或分层的。

## 了解升级过程

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
此页面上的信息涵盖了升级过程的步骤1，如下表所示。 完成此表中的所有步骤以从Adobe Analytics升级到Customer Journey Analytics。

| 升级任务 | 详细信息 |
|---------|----------|
| <span class="preview">**步骤1：开始升级**</span> | <span class="preview">了解升级到Customer Journey Analytics的好处以及基本升级过程。</span> |
| **步骤2：[选择升级路径](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | 有多种方法可用于升级到Customer Journey Analytics。 根据贵组织当前的Adobe Analytics环境和长期目标，选择最适合贵组织的方法。 |
| **步骤3：[将数据发送到Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | 将数据发送到Adobe Experience Platform的过程因您在步骤2中选择的升级路径而异。 |
| **步骤4：[保留历史数据](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | 大多数组织都需要将其历史Adobe Analytics数据保留一定时间。 可以使用各种选项来完成此操作。 |
| **步骤5：[执行其他实施任务](/help/getting-started/cja-getting-started.md)** | 在升级过程的这一阶段，您需要在Customer Journey Analytics环境准备好使用之前执行各种任务。<p>这些其他任务适用于从Adobe Analytics升级以及新的Customer Journey Analytics实施。</p><p>这些任务包括：</p><ul><li>将其他数据引入Experience Platform</li><li>在Platform数据集与Customer Journey Analytics之间创建连接</li><li>创建数据视图</li><li>移植报表API使用情况</li><li>考虑数据馈送和Data Warehouse</li><li>迁移项目和组件</li><li>Planning用户载入</li></ul> <p>有关详细信息，请参阅[Customer Journey Analytics快速入门](/help/getting-started/cja-getting-started.md)。 |

{style="table-layout:auto"}

## 首先，选择升级路径

有多种方法可用于升级到Customer Journey Analytics。 [选择最适合您组织的方法](/help/getting-started/cja-upgrade/cja-upgrade-path.md)。

您选择的升级路径取决于贵组织当前的Adobe Analytics环境和长期目标。
