---
title: 适用于Adobe Analytics用户的CJA用户指南
description: 当您的公司将数据从Adobe Analytics移动到Customer Journey Analytics时，从用户的角度应该考虑什么
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 570fb36de0ed81f001ed6115e73d1d4347f368ec
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 21%

---

# 适用于Adobe Analytics用户的CJA用户指南

你的公司开始雇佣Customer Journey Analytics。 作为熟悉Adobe Analytics的用户，您已经拥有了良好的开端。 使用Customer Journey Analytics时，您会注意到一些相似之处和一些重大差异。 本页旨在解释那些未更改的内容，以及一些主要差异。 我们还将告诉您如何获取有关新概念的更多信息，以及进一步的步骤，以使您的客户历程更轻松、更成功。

与传统的Adobe Analytics相比，为了符合行业标准，CJA中的几项功能已重命名并重新构建。 一些更新的术语包括区段、虚拟报表包、分类、客户属性和容器名称。 耳熟能详的概念（如eVar和prop）已不复存在，而且这些概念也存在限制。

## 未更改的内容

您在报表端所熟悉的许多内容并未发生更改。

* 您仍然可以使用 [Analysis Workspace](/help/analysis-workspace/home.md) 分析数据。 工作区的工作方式与在传统Adobe Analytics中相同。
* 您还具有相同版本的 [Adobe Analytics功能板](/help/mobile-app/home.md) 随你。 功能板(又称Mobile应用程序)的工作方式与在传统Adobe Analytics中相同。
* [Report Builder](/help/report-builder/report-buider-overview.md) 拥有新的界面，现在可以在PC、Mac和Excel的Web版本上运行。

在报告方面， **不同之处** 即您有权访问更多要分析的跨渠道数据。 以下是一些包含跨渠道数据源的可视化图表示例：

![多渠道可视化图表](assets/cross-channel.png)

## 新架构 {#architecture}

Customer Journey Analytics从Adobe Experience Platform获取其数据。 Experience Platform让您能够集中和标准化来自任何系统或渠道的客户数据和内容，并应用数据科学和机器学习来改进个性化体验的设计和交付。

Platform 中的客户数据将作为数据集存储，数据集由一个架构和批量数据组成。有关 Platform 的更多详细信息，请参阅 [Adobe Experience Platform 体系架构概述](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en)。

您的CJA管理员已建立 [连接](/help/connections/create-connection.md) 到平台中的数据集。 然后他们建了 [数据视图](/help/data-views/data-views.md) 在这些关系中。 将数据视图视为类似于虚拟报表包的视图。 数据视图是报告Customer Journey Analytics的基础。 报表包的概念已不复存在。

## 连接

通过建立连接，Analytics管理员可以集成 [!DNL Adobe Experience Platform] into [!UICONTROL 工作区]. 为了报告 [!DNL Experience Platform] 数据集，您必须首先在 [!DNL Experience Platform] 和[!UICONTROL 工作区]中的数据集之间建立连接。

以下是一段视频概述：

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## 报表包 {#report-suites}

如果贵组织仍在Adobe Analytics平台上并添加CJA/AEP，则可以通过Adobe Analytics源连接器或Web SDK将报表包数据引入Experience Platform。 您通常会源使用Analytics架构的特定于报表包的数据集。

但是，报表包不再是在CJA中报告的基础 —  [数据视图](/help/data-views/data-views.md) 。 有关数据视图的更多信息，请参阅下面的部分。

可以在Experience Platform中组合来自多个数据集的现有实施。 基于这些数据集的连接和数据视图可以合并之前存在于单独报表包中的数据。

## （虚拟）报表包现在为“数据视图” {#data-views}

[!UICONTROL 数据视图] 采用虚拟报表包当前存在的概念，并将其扩展到 [对数据启用其他控制](/help/data-views/create-dataview.md) 由连接提供。 这可以配置时区和会话超时间隔。 您还可以动态地对各个维度应用归因和到期属性。 请注意，这些量度会追溯应用于所有数据。

**您需要执行的操作**:

* 请注意，在工作区中，您现在使用的报表包选择器允许您从管理员与您共享的数据视图中进行选择：

   ![数据视图选择器](assets/data-views.png)

* 熟悉许多 [数据视图用例](/help/data-views/data-views-usecases.md).

## eVar和prop

[!UICONTROL Customer Journey Analytics] 中不再存在传统 Adobe Analytics 意义上的 [!UICONTROL eVar]、[!UICONTROL 属性]和[!UICONTROL 事件]。您有无限的架构元素（维度、量度、列表字段）。因此，您在数据收集过程中使用的所有属性设置现在都会在查询时应用。

**您需要执行的操作**:

* 熟悉这些架构元素可用于深入查看数据的多种方式。

## 区段现在为“过滤器”

[!UICONTROL Customer Journey Analytics] 不再使用 eVar、prop 或事件，而是使用任何 AEP 架构。这意味着，任何现有区段都与 [!UICONTROL Customer Journey Analytics]. 此外，“区段”已重命名为“过滤器”。

目前，您无法共享/发布 [!UICONTROL 过滤器] ([!UICONTROL 区段])从 [!DNL Customer Journey Analytics] Experience Platform统一配置文件或其他Experience Cloud应用程序。 此功能当前正在开发中。

**您需要执行的操作**:

* 如果要将现有Adobe Analytics区段移动到Customer Journey Analytics，请查看 [此视频](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=zh-Hans).
* 否则，请在Customer Journey Analytics中重新创建过滤器。

## 计算量度

[!UICONTROL Customer Journey Analytics] 不再使用 eVar、prop 或事件，而是使用任何 AEP 架构。这意味着，任何现有的计算量度都与 [!UICONTROL Customer Journey Analytics].

**您需要执行的操作**:

* 如果要将Adobe Analytics计算量度移动到Customer Journey Analytics，请查看 [此视频](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=zh-Hans).
* 否则，请在Customer Journey Analytics中重新创建计算量度。

## 会话和变量持久性设置

[!UICONTROL Customer Journey Analytics] 在报告时应用所有这些设置，这些设置现在位于 [数据视图](/help/data-views/component-settings/persistence.md). 对这些设置所做的更改现在具有可回溯性，您可以使用多个数据视图来拥有多个版本！

## 分类现在为“查找数据集”

查找数据集用于查找在“事件”或“配置文件”数据中找到的值或键。 例如，您可以上传将事件数据中的数字 ID 映射到产品名称的查找数据。有关示例，请参阅[此用例](/help/use-cases/b2b.md)。

## 客户属性现在为“用户档案数据集”

配置文件数据集包含应用于 [!UICONTROL 事件] 数据。 例如，它允许您上传有关客户的CRM数据。 您可以选择想要包含的人员 ID。[!DNL Experience Platform] 中定义的每个数据集，都拥有自己定义的一个或多个人员 ID 集，例如 Cookie ID、拼合 ID、用户 ID、跟踪代码等。

## 标识

CJA扩展了ECID之外的身份概念，以包含您要使用的任何ID，包括客户ID、Cookie ID、拼合ID、用户ID、跟踪代码等。 跨数据集使用通用命名空间ID，或使用 [跨渠道分析](/help/connections/cca/overview.md) 可帮助将不同数据集中的人员关联在一起。 在CJA中设置工作区项目的任何用户都需要了解跨数据集使用的ID。

以下视频重点介绍了身份在Customer Journey Analytics中的使用：

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## 容器已重命名

您为 [创建的每个数据视图](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#containers).

* **点击容器现在为“事件”容器**. [!UICONTROL 人员]容器包括访客在指定的时间范围内的每个会话和事件。
* **访问容器现在为“会话”容器**. 通过[!UICONTROL 会话]容器可以识别页面交互、营销活动或特定会话的转化。
* **现在，访客容器为 [!UICONTROL 人员] 容器**. [!UICONTROL 人员]容器包括访客在指定的时间范围内的每个会话和事件。

**您需要执行的操作**:

您可以选择重命名任何容器以符合贵组织的需求。

## `Uniques Exceeded` 限制

[!UICONTROL Customer Journey Analytics] 没有唯一值限制，因此无需担心！
