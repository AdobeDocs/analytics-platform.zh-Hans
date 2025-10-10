---
title: 报告Marketo Engage数据
description: 了解如何在Customer Journey Analytics中报告Marketo Engage数据
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
role: Admin
source-git-commit: fedb1337b32e44fc00989bace6a4d1788043f55f
workflow-type: tm+mt
source-wordcount: '1059'
ht-degree: 13%

---

# 报告Marketo Engage数据

您可以利用Experience Platform中提供的Marketo Engage数据集，为B2B营销人员提供有价值的分析和报表解决方案。 然后在Customer Journey Analytics中报告这些数据集。

请注意：

* Marketo Engage报表最适合直接在Marketo中衡量和优化营销项目，具有快速、规范性并且便于营销人员使用。
* Customer历程分析为跨越多个渠道、产品和业务部门的客户历程提供了一个更广泛的、可自定义的分析解决方案，其中包括但不限于Marketo数据。

有关详细信息，请参阅[报表比较](#reporting-comparison)。

>[!NOTE]
>
>您可以考虑[Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md)以从Marketo Engage数据中获取更多的价值。 您可以将Marketo Engage数据集与帐户和查找数据集结合使用。 并报告Customer Journey Analytics B2B edition中的客户和机会级别。
>


要在Customer Journey Analytics中报告Marketo Engage数据，请执行以下操作：

+++ 1.将Marketo源数据字段映射到其XDM目标

将 [人员](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo) 和 [活动](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo) 对象映射到各自的 XDM 架构目标字段。

+++

+++ 2.将Marketo数据摄取到Adobe Experience Platform

使用 [Marketo Engage 连接器](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo)将 Marketo 的数据传送到 Experience Platform，并使用与平台连接的应用程序使这些数据保持最新。

+++

+++ 3.在Customer Journey Analytics中设置与此数据集的连接

要报告Experience Platform数据集，您必须首先在Experience Platform和Customer Journey Analytics中的数据集之间建立连接。 请参阅[创建或编辑连接](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-connections/create-connection)。

+++


+++ 4.创建一个或多个数据视图

[数据视图](/help/data-views/data-views.md) 是 Customer Journey Analytics 专属的容器，通过它，可决定如何解释来自连接的数据。 它指定所有可在 Analysis Workspace 中找到的维度和量度，在本例中，特指 Marketo 的量度和维度。 它还指定这些维度和量度从哪些列获取数据。 为准备 Analysis Workspace 中的报表而定义数据视图。

+++ 

+++ 5.在Analysis Workspace中报告

您可以探索的一个用例是：2020年4月至6月，潜在客户访问了多少网页？

1. 打开 [Analytics Workspace](/help/analysis-workspace/home.md) 并创建新项目。拥有B2B/B2P CDP的客户可以在Customer Journey Analytics中进行B2C风格分析。 B2B 对象尚不可用。

1. 为网页视图创建一个[区段](/help/components/segments/seg-create.md)，如下所示：事件类型= web.webpagedetails.pageViews ：

   显示事件和事件类型的![定义窗口](../assets/marketo-filter.png)

1. 将您创建的区段拉入自由格式表 — 网页查看次数，然后拉入月份日期范围。 此操作为您提供每个月潜在客户的网页访问次数：

   ![自由格式表，按月份显示事件。](../assets/marketo-freeform.png)

1. 或者拉入以下维度：人员密钥或工作电子邮件地址。 此操作将为您提供每个潜在客户的网页访问量：

   ![自由格式表，显示事件和workEmail.Address及网页视图。](../assets/marketo-freeform2.png)

Customer Journey Analytics中的Marketo Engage数据可能与您在Marketo Engage中的报表中看到的不同。

+++


## 报表比较

下面对Customer Journey Analytics中的报表与Marketo Engage中的报表进行了比较，详细说明了分析功能、灵活性、真实来源和使用案例方面的一些重要差异。

### Customer Journey Analytics

Customer Journey Analytics是基于Adobe Experience Platform构建的高级跨渠道分析工具。 Customer Journey Analytics专为需要跨数字和离线数据源进行强大、灵活且可自定义的报表的企业团队而设计。

#### 关键功能

* **数据源**：可以合并多个数据集(Web、CRM、电子邮件、呼叫中心、离线、Marketo等)以进行360°客户历程报告。
* **自助分析**：具有高度交互性、可自定义的仪表板和可视化图表的拖放工作区。
* **高级归因**：支持所有连接数据的复杂、多点接触和自定义归因模型，而不仅仅是营销计划。
* **受众和路径分析**：跨购买者历程的深度分段、同类群组和路径分析。
* **可操作的分析**：启用数据驱动编排（例如，将分析发送回营销或个性化引擎）。
* **企业规模**：适用于需要企业治理、多个品牌和高数据量的组织。

#### 典型Customer Journey Analytics用例

* 跨多个渠道和接触点的高级客户历程映射。
* 在线和离线数据的复杂分段和混合。
* 用于执行级别和运营报告的自定义KPI仪表板。
* 全面归因建模（不仅限于数字或电子邮件）。


### Marketo Engage

Marketo Engage提供了着重于营销自动化KPI、项目和营销活动测量以及营销影响分析的应用程序内报告。 所有这些报表都直接与Marketo中的活动相关联。

#### 关键功能

* **本机营销分析**：电子邮件、登陆页面、营销活动、潜在客户、商机、管道和收入归因的标准报表（首次联系、最近联系、多点联系）。
* **高级BI分析（加载项）**：拖放、点击式自定义Report Builder以分析项目/帐户/商机数据（请参阅最近的高级BI分析概述）。
* **预建功能板**：对于营销活动效果、渠道效果、管道/收入贡献。
* **项目和渠道分析**：特定于Marketo管理的历程的归因和ROI。
* **以营销为中心**：重点关注那些需要提高营销funnel透明度的用户：电子邮件统计信息、表单、智能营销活动和收入影响。


#### 典型Marketo Engage用例

* 跟踪和优化电子邮件、项目和活动效果。
* 将潜在客户和管道归因于营销策略。
* 监控参与趋势并对潜在客户进行评分。
* 在没有数据工程资源的情况下与销售/营销团队分享见解。
* 访问现成且对营销人员友好的报表。


有关Marketo Engage和Customer Journey Analytics之间报表功能的快速比较表，请参阅下文：

| 功能 | Marketo Engage | Customer Journey Analytics |
|---|---|---|
| **主要焦点** | 营销项目和以活动为中心的报表。 | 全面、全渠道历程以及行为分析和报告。 |
| **数据源** | 通过Marketo Engage在中生成的数据。 | 将来自任何支持Experience Platform的数据(包括Marketo、网站、移动应用程序、线下渠道等)的数据整合在一起。 |
| **归因** | Marketo数据中的单点和多点接触归因。 | 对解决方案中可用的任何数据进行自定义的跨渠道归因。 |
| **自定义报告和灵活性** | 用于深入了解项目和帐户的高级BI（插件）。 | 高度灵活地使用所有可用数据构建自定义工作区、功能板或报表。 |
| **受众分析** | 过滤并划分项目列表、参与和智能列表。 | 丰富的角色和历程可视化图表、受众路径和区段重叠分析。 |
| **目标用户** | 营销人员、营销人员、需求挖掘人员、收入管理员。 | 分析师、数据科学家、营销策划师、客户体验专业人士。 |
| **量度去重** | 对于电子邮件性能报表，会按潜在客户ID、促销活动ID和电子邮件资产ID自动为量度去重。 如果从同一电子邮件资产创建了多封电子邮件，又从同一项目群将其发送给同一潜在客户，则这些电子邮件将仅计为一封电子邮件。 | 如果不应用其他过滤器和量度，则将电子邮件报告数据报告为没有[量度去重](/help/data-views/component-settings/metric-deduplication.md)的电子邮件性能总数。 |

{style="table-layout:fixed"}
