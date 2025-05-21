---
title: Customer Journey Analytics中的产品分析
description: 了解可在Customer Journey Analytics中使用哪些功能来有效执行产品分析。
exl-id: b185a2ed-18c8-4fb3-8c69-693d5fee0e67
source-git-commit: 3d8ebd90156f0e44e4c45913a524ed91360dd39e
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 1%

---

# Customer Journey Analytics中的产品分析

产品分析是了解用户在其历程的每个阶段与您的产品的交互情况的过程。 它涉及分析数据以揭示有关用户行为、产品性能和增长机会的见解。 有效的产品分析可帮助团队做出明智的决策，以改善用户体验、促进参与和实现业务目标。

Customer Journey Analytics为团队提供了一些工具，用于分析和优化产品体验，这些工具具有以下功能：

* **大规模管理产品数据**：轻松摄取、转换和管理产品数据以满足您的业务需求，确保获得可靠的见解。
* **衡量客户获取和激活**：跟踪新用户如何发现您的产品以及如何参与价值驱动型活动。
* **衡量参与度和采用情况**：了解用户如何通过产品漏斗、识别摩擦点并跟踪关键功能的采用情况。
* **衡量保留率和流失率**：分析一段时间内的用户保留率，确定流失率指标，并制定策略以减少流失率并提高忠诚度。
* **操作产品见解**：将数据驱动的见解转化为切实可行的策略，以改善用户体验并推动可持续的产品增长。
* **与您的组织分享见解**：跨团队传达关键发现以协调工作、促进协作，并确保每个人都在致力于共享的产品和业务目标。

利用这些功能，Customer Journey Analytics使您能够释放产品的全部潜力，并创建一种无缝、数据驱动的方法来推动用户和业务取得成功。

## 大规模管理产品数据

准确的产品数据是进行有效产品分析的基础。 数据摄取是指检测和收集产品数据的过程，而数据管理涉及转换和维护此数据，以确保其满足您的分析要求。

Adobe Experience Platform和Customer Journey Analytics中的以下功能使您能够大规模摄取和管理产品数据：

* Adobe Experience Platform
   * [数据集&#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview)
   * [数据准备&#x200B;](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/data-prep/home)
   * [数据Distiller&#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/query/data-distiller/overview)
* Customer Journey Analytics
   * [连接&#x200B;](/help/connections/overview.md)
   * [数据视图](/help/data-views/data-views.md)，包括[派生字段&#x200B;](/help/data-views/derived-fields/derived-fields.md)
   * [区段&#x200B;](/help/components/filters/filters-overview.md)
   * [计算量度](/help/components/calc-metrics/calc-metr-overview.md)
   * [引导式分析&#x200B;：时间线&#x200B;](/help/guided-analysis/types/timeline.md)

## 衡量客户获取和激活

产品增长依赖于可操作的漏斗顶部洞察，这些洞察可吸引新用户、揭示转化路径并消除历程中的摩擦。

* 客户获取可跟踪访问您产品的新用户，包括他们如何到达以及哪些工作最有效或最不有效。
* 激活可监控参与您的第一个值事件（根据特定目标定义）的新用户。

![积极增长](/help/guided-analysis/assets/active.png)

通过Customer Journey Analytics中的以下功能，您可以有效地衡量客户获取和激活情况：

* [引导式分析&#x200B;：主动式增长](/help/guided-analysis/types/active-growth.md)
* [指导分析：净增长](/help/guided-analysis/types/net-growth.md)
* [指导分析：趋势](/help/guided-analysis//types/trends.md)
* [归因面板&#x200B;](/help/analysis-workspace/c-panels/attribution.md)
* 包含营销渠道维度的[自由格式表](/help/analysis-workspace/c-panels/freeform-panel.md)（使用[派生字段](/help/data-views/derived-fields/derived-fields.md)创建）

## 衡量参与度和采用程度

获取新用户扩展了产品漏斗的顶部。 参与重点在于引导这些用户进一步降低漏斗并消除成功障碍。 他们的成功直接推动您的业务取得成功。

![参与分析](/help/guided-analysis/assets/feature-matrix.png)

Customer Journey Analytics中的以下功能可帮助您跟踪产品参与和采用情况：

* [指导分析：参与](/help/guided-analysis/types/engagement.md)
* [指导分析：趋势](/help/guided-analysis/types/trends.md)
* [引导式分析：频率](/help/guided-analysis/types/frequency.md)
* [引导式分析：漏斗](/help/guided-analysis/types/funnel.md)
* [指导分析：转化趋势](/help/guided-analysis/types/conversion-trends.md)
* [指导分析：发布影响](/help/guided-analysis/types/release-impact.md)
* [指导分析：首次使用影响&#x200B;](/help/guided-analysis/types/first-use-impact.md)
* [引导式分析：时间线](/help/guided-analysis/types/timeline.md)
* [自由格式表&#x200B;](/help/analysis-workspace/c-panels/freeform-panel.md)
* [流量](/help/analysis-workspace/visualizations/c-flow/flow.md)

## 衡量保留率和流失率

维系功能测量在初次购买和激活后有多少用户继续使用产品。 通过最大限度地利用与持续使用密切相关的功能，高性能产品可以维持稳定、忠诚的用户群。 留存用户会随着时间的推移返回产品并与之交互，而流失的用户则不会。 产品团队跟踪维系，以查明推动持续参与的功能，并设计干预措施，将流失的用户转变为保留的用户行为。

![保留分析](/help/guided-analysis/assets/retention.png)

Customer Journey Analytics中的以下功能可帮助您有效地跟踪保留和流失情况：

* [引导式分析：保留](/help/guided-analysis/types/retention.md)&#x200B;
* [指导分析：主动增长](/help/guided-analysis/types/active-growth.md)
* [指导分析：净增长](/help/guided-analysis/types/net-growth.md)
* [同类群组表&#x200B;](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)

## 可操作的产品洞察

只有分析可推动操作，它们才能带来价值。 将分析发现转化为改善用户体验并支持长期产品增长的操作。

Experience Cloud中的以下功能使您能够有效地根据见解采取行动：

* [创建并发布受众](/help/components/audiences/publish.md)&#x200B;以便从Customer Journey Analytics激活
* 通过Experience Cloud产品激活受众：
   * [在AJO和Adobe Target中运行实验](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/content-management/content-experiment/get-started-experiment)，并使用[实验面板](/help/analysis-workspace/c-panels/experimentation.md)测量Customer Journey Analytics中各种变化的影响
   * [向AJO中的用户提供应用程序内参与](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/in-app/get-started-in-app)
* 使用Adobe Real-time CDP [将受众](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/activation-overview)激活到外部目标&#x200B;

## 与组织共享见解&#x200B;。

跨团队传达关键调查结果，以协调工作、促进协作，并确保每个人都朝着共享的产品和业务目标努力。

在Workspace中![引导式分析](assets/guided-analysis-workspace.png)

Customer Journey Analytics中的以下功能可帮助您有效地共享见解：

* [共享](/help/analysis-workspace/curate-share/share-projects.md)针对特定业务问题定制的引导式分析视图，使消费者能够自助回答他们的下一个问题
* 在[Analysis Workspace](/help/analysis-workspace/home.md)中将引导式分析、面板和可视化组合到一个综合的仪表板中
* 创建一个[移动记分卡](/help/mobile-app/home.md)，其中包含面向执行官和其他移动消费者的关键产品见解
