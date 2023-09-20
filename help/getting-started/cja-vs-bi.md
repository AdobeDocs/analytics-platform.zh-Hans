---
title: 比较 Customer Journey Analytics 和 BI 解决方案
description: 比较 Customer Journey Analytics 和 BI 解决方案
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: ae66cd06-7ec1-4174-a3cf-939c3a66b840
source-git-commit: dd83785ea67a48e2051c60568e6fe5b436edf4db
workflow-type: ht
source-wordcount: '1649'
ht-degree: 100%

---

# 比较 Customer Journey Analytics 和 BI 解决方案

随着当前对客户体验的关注，各个品牌需要先进的解决方案才能更好地了解整体客户历程。通过了解这一完整的客户历程，您可以分析并获得有关在线和离线渠道如何吸引客户并提高转化率、保留率和忠诚度的宝贵见解。在这种情况下，客户历程可以是在寿司食品连锁店在线订购餐点。或者购买新车，其中客户不仅在网上调查研究，还参观经销商展厅，最终亲自到场购买。

许多组织已将其全渠道数据整合到数据湖或 Data Warehouse 中。除了这些数据存储，还使用 Business intelligence (BI) 工具提供企业了解客户历程所需的报告、可视化图表和见解。这种解决方案与工具的组合一般有意在性质上通用，并不专门以客户为重心。Customer Journey Analytics 侧重于为营销人员、数据分析师、数据科学家等负责客户体验的人士助力。通过该工具，他们可实时地将各个渠道各种环境下的客户历程可视化，其中不存在许多其他 BI 工具所具有的限制。

这部分文档阐述 Customer Journey Analytics 与常用的 BI 工具之间的根本区别，其中首先审视用于实现上述“了解客户历程”目标的常规工作流。然后，更详细地介绍在 Customer Journey Analytics 与 BI 工具之间，存储、收集和查询数据的方式有何不同。最后，阐述各种可视化功能的区别。

## 传统的 BI 工作流

分析客户历程的传统方法有一个常见的障碍，即这些方法不以客户为中心。每个团队都将数据收集到孤岛中，并根据其有权访问的数据分析和优化体验。

![本节中描述的传统 BI 工作流](./assets/biworkflow.png)

如果要了解特定的数字营销活动如何影响存储在不同数据孤岛中的离线操作，请向 BI 团队的队列发出请求。BI 团队编写所需的查询以获取并转化数据。检索原始数据后，BI 团队即创建可视化图表。这些数据与您共享，而您需要耗时梳理这些见解并提取数据，以供在其他系统中激活。

其中每个步骤都可能耗时数小时、数日甚至数周。如果后续对于所查询的数据仍有疑问或问题，则可能需要耗时更长才能处理这些问题并继续各个环节。对于持续不断地分析、探索和了解客户历程，此过程效率低下且不可扩展。此外，BI 团队一般不仅处理与客户历程相关的问题。

## Customer Journey Analytics：线上和线下数据的民主化工作流

Customer Journey Analytics 提供了一个环境，可供在总体客户层面上连接在线和离线跨渠道数据，其唯一目的是了解客户历程。确实需要初始设置才能[连接](/help/connections/overview.md)并[定义](/help/data-views/data-views.md)针对您视为相关的数据的视图。不过，一旦完成设置，就可以利用这些数据进行持续的分析和探索。您可以逐步了解客户历程并从中获得深入见解。通过将结合在一起的在线和离线数据大众化，只需几秒时间即可解答与客户历程相关的疑问。

![本节中描述的 Customer Journey Analytics 工作流](./assets/cjaworkflow.png)

可使用 Customer Journey Analytics 询问有关使用可视化 Analysis Workspace 环境的疑问，并可近乎实时地获得见解。无需 SQL 代码，即可立即获得跨渠道数据和报告。只需在 UI 中简单地拖放，即可对完全相关的数据进行其他查询和分析。可继续提问，并根据需要逐步探索更多详细信息。然后可针对所发现的见解立即采取行动，如向外共享受众以供激活和编排。

## Customer Journey Analytics 强大的报告引擎

Customer Journey Analytics 使用一种强大的专有架构，该架构分散在数百甚至数千台服务器上进行分析，这样只需几秒时间即可在 Analysis Workspace 中显示数据。这种处理架构的某些显著特点包括：

* **为与个别客户相关的查询优化**：确切地说，Customer Journey Analytics 将数据存储在一个广泛使用缓存的分布式报告引擎中。为针对个人级别事件数据的响应式查询微调了该引擎，因此为与客户相关的查询进行了完善的优化。报告引擎将数据存储在面向列的位图索引中，这些索引有助于快速即时计算聚合度量。它具有一个包括万象的筛选引擎，可进行强大的分段/受众分析。并且它深刻理解数据点之间的顺序，这有助于分析这些数据点上的行为（事情发生的顺序）以及使用各种复杂的模型分配属性。

* **快速应用复杂的路径和筛选条件**：报告引擎处理部分排序的分层数据集（例如，人员 -> 会话 -> 事件）。顶级对象（个别配置文件）的所有数据都驻留在单个处理节点上，从而获得准确的结果。这种划分有助于快速应用复杂的路径和筛选条件。大规模执行复杂操作（如会话化、归因、数据属性的有状态持久化和复杂的数据操纵选项），并可快速生成报告。在 BI 环境中，这些类型的操作一般需要为每个用例都创建新的 OLAP 多维数据集。通过 Customer Journey Analytics 的报告引擎，可在每次查询时不受限地访问整个数据集，无需提前建立任何多维数据集，即可产生完全相关的数据。

* **高效查询复杂数据流**：报告引擎与传统 SQL 和 NoSQL 数据库的最大区别之一是，它能够在基本层面上根据面向序列的关系确定谓词。这些基本的查询操作可审视记录流，而后者由许多交错（甚至嵌套）的序列组成。它们通过高效地处理单个连续序列操作，针对所有这些交织在一起的数据流执行查询。

* **旨在快速响应大型查询**：报告引擎不像传统的大数据系统那样通用。但是，它经过专门设计，一般只需不足一秒时间，即可应答针对数百万甚至数十亿条记录（事件数据/体验事件）的查询。与其他大数据系统不同，它实现这一点并非通过对数据采样或预先计算它认为您可能会提出的所有问题的答案。而是能够以快到足以支持交互式查询用例的速度计算出答案。Customer Journey Analytics 报告引擎的这种独特设计更容易获得数据并高速地进行持续的分析和探索，从而使您可逐步深入了解和理解客户历程。

* **充当无界面 BI 解决方案**：可在一处定义维度、度量和筛选条件，然后任何 Customer Journey Analytics 客户端（包括我们的公共 Customer Journey Analytics API）均可访问这些组件。这样使得最终用户无需执行复杂的查询，并确保无论使用哪种报告或可视化客户端，结果均相同。

## Customer Journey Analytics 独特的可视化功能

报告引擎是 Customer Journey Analytics 的基础，它使您可逐步与该报告引擎中的所有客户历程数据进行交互并对其采取行动。Customer Journey Analytics 附带了一套广泛的组件，使您能够通过拖放直观地完成这项工作。通过 BI 可视化工具，可在 SQL 准备的数据（由 IT 定义）的范围内进行探索。通过 Customer Journey Analytics，无需要求 IT 部门构建另一个 SQL 视图，即可随心所欲地分解、切片和切块。

这里的“逐步”是一个关键概念：相对于 BI 工具中的大多数可视化图表，通过 Customer Journey Analytics 中直观的拖放式 UI，可根据特定需求不断分解数据：可以使用相关的度量、维度、筛选条件（区段）、计算、时间线、注释和其他分析值，以交互方式生成可视化查询。

这些可视化组件中内置了智能功能，例如：

* **虚拟分析师功能**，如[异常检测](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)，它使用预测算法和机器学习深入了解是什么促使您的数据中产生异常行为。

* 专门关注客户历程见解的&#x200B;**高级分析功能**，如[流量图](/help/analysis-workspace/visualizations/c-flow/flow.md)、[归因面板](/help/analysis-workspace/c-panels/attribution.md)、[流失图](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)和[维度细分。](/help/components/dimensions/t-breakdown-fa.md)开箱即用的可视化示例包括：

   * [通过队列/延迟表进行客户维系分析](/help/analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)，其中只需将度量/维度拖入构建器，即可在 30 秒内完成，

   * [流失](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md)/[流量](/help/analysis-workspace/visualizations/c-flow/create-flow.md)可视化。不到一分钟即可完成设置。

* **在逐步探索的每一步都有分段功能**：只要认为有意义，即可将受众发布回 Experience Platform 以及从那里发布到任何支持的目标。

* 完全[可自定义](/help/data-views/component-settings/persistence.md)的&#x200B;**会话化**：由您确定会话作为客户历程中某个渠道的一部分何时开始和结束。

* **管护和民主化**：在 Customer Journey Analytics 中创建的仪表板可以是：

   * 为组织中的其他个人[策划](/help/analysis-workspace/curate-share/curate.md)以供持续探索、
   * 使用 [Report Builder](/help/report-builder/report-buider-overview.md)（专用插件）导出到 Excel、
   * 以各种格式（包括 [PDF](/help/analysis-workspace/export/download-send.md)、[CSV](/help/analysis-workspace/export/download-send.md)）并通过[专用的移动应用程序](/help/mobile-app/home.md)[共享](/help/analysis-workspace/curate-share/share-projects.md)给对最终报告和/或可视化感兴趣的人士。

由于有多种多样的可视化可用，因此难以比较 Customer Journey Analytics 的可视化功能与 BI 工具提供的任何功能。某些 BI 工具拥有更高级的可视化，但 Customer Journey Analytics 专门关注交互式和可互操作的客户历程可视化，这样只需几秒时间即可分解数据，同时无需为每个额外的查询“付款”。


## 概要

Customer Journey Analytics 与 BI 工具的不同之处在于，它将高度优化的以客户历程为中心的报告引擎与方便用户使用的工具和组件无缝集成，以执行分析和构建报告和高级可视化。只需在一个 UI 中即可提供所有这些功能，使您无需在查询引擎与可视化环境之间往返。
