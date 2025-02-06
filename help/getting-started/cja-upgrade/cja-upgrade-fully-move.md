---
title: 评估升级到Customer Journey Analytics后需要Adobe Analytics多长时间
description: 了解如何评估升级到Customer Journey Analytics后需要Adobe Analytics的时长
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: f4440148d26e81938d029d4a077cd787c868f1be
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 0%

---

# 评估升级到Customer Journey Analytics后需要Adobe Analytics多长时间 {#evaluate-aa-needs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-fully-move"
>title="完全移至Customer Journey Analytics"
>abstract="（推荐）Customer Journey Analytics旨在成为贵组织的主要Analytics工具。 但是，如果贵组织在很大程度上依赖于Adobe Analytics独有的功能，并且无法更改这些工作流程，则可能仍需要使用该工具。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-keep-aa"
>title="保留两个分析产品"
>abstract="（不推荐）如果选择此选项，则您与Adobe签署的合同将同时包括Adobe Analytics和Customer Journey Analytics，这可能会使贵组织在一段时间内更加昂贵。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>此文档应该用作[Adobe AnalyticsCustomer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)的一部分。

大多数组织在升级到Customer Journey Analytics后最终都会禁用Adobe Analytics。 这是因为维护两个Analytics环境的成本和复杂性。

但是，Adobe建议您在实施Customer Journey Analytics后，让Adobe Analytics环境保持运行一段时间。 以下部分将介绍这样做的原因以及禁用Adobe Analytics的建议时间。

## 升级期间和升级后使用Adobe Analytics

在决定是否以及何时应禁用Adobe Analytics时，请考虑在升级到Customer Journey Analytics期间和之后使用Adobe Analytics的以下情况：

| 在升级期间和升级后使用Adobe Analytics | 说明 |
|---------|----------|
| 执行并排数据比较 | Adobe建议在新的Adobe Analytics环境运行并收集数据后，让Customer Journey Analytics环境保持运行一段时间。 这是将Customer Journey Analytics数据与Adobe Analytics数据并排比较的最佳方法。<p>在您熟悉Customer Journey Analytics环境中的数据之前，请勿禁用Adobe Analytics。</p><p>**注意：** Adobe建议为您的Customer Journey Analytics环境重新实施Web SDK，同时为历史数据使用Analytics源连接器。 [了解详情](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| 保留来自Adobe Analytics的历史数据 | Adobe建议您在新的Adobe Analytics环境运行并收集数据后，通过Analytics Source Connector保留Customer Journey Analytics环境一段时间。 这是将Adobe Analytics历史数据导入Customer Journey Analytics的最佳方法。<p>在收集了足够的历史数据并与新的Web SDK实施Customer Journey Analytics后，您可以完全删除Analytics源连接器。 当您只能依靠通过新的Customer Journey AnalyticsWeb SDK实施收集的历史数据时，可以这样做。</p><p>**注意：** Adobe建议为您的Customer Journey Analytics环境重新实施Web SDK，同时为历史数据使用Analytics源连接器。 [了解详情](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| 使用数据馈送或其他Adobe Analytics功能 | 一小部分功能在Customer Journey Analytics中尚未完全可用。 如果您需要访问这些功能，可能需要将Adobe Analytics与Customer Journey Analytics结合使用，直到这些功能可用为止。 <p>Customer Journey Analytics中未完全提供的功能包括数据馈送和贡献分析。 有关尚未提供的功能的完整列表，请参阅[Customer Journey Analytics功能支持](/help/getting-started/aa-vs-cja/cja-aa.md)。</p> |

## 禁用Adobe Analytics的流程和时间线 {#disable-adobe-analytics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement-third-pary"
>title="禁用第三方标记管理系统"
>abstract="借助Web SDK数据完全正常使用，请与标签管理员合作，从第三方标签管理系统中删除AppMeasurement库。<br><br>执行此步骤的预计时间取决于从您的标签管理产品中禁用AppMeasurement的难易程度，以及您的组织部署和管理标签代码的发布周期。"

<!-- markdownlint-enable MD034 -->

您现有的Adobe Analytics实施是成功升级到Customer Journey Analytics的关键部分，如上节[在升级期间和升级之后使用Adobe Analytics](#uses-of-adobe-analytics-during-and-after-an-upgrade)中所述。

当您不再需要Adobe Analytics来实现上节所述目的时，请使用以下信息删除Adobe Analytics：

1. 停止使用Adobe Analytics收集数据。

   在对您的Adobe Analytics数据与Customer Journey Analytics数据进行并排比较感到满意后，您可以停止在Adobe Analytics实施中收集数据。 新的Adobe Analytics数据将不再通过Analytics Source Connector流入Customer Journey Analytics。

   但是，在此时间点之前从Adobe Analytics环境收集的数据仍可以通过Analytics Source Connector作为Customer Journey Analytics中的历史数据使用。

   此过程因用于实施Adobe Analytics的数据收集方法而异：

+++ AppMeasurement

   [禁用AppMeasurement数据收集](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md)。

+++

+++ Analytics扩展（标记）

   在标记中禁用Analytics扩展。

+++

+++ API

   禁用API数据收集。

+++

+++ 第三方

   与您的标签管理员合作，从第三方标签管理系统中删除AppMeasurement库。

+++

1. 从数据流中删除Adobe Analytics即服务。

   在Web SDK数据完全正常工作的情况下，请与平台管理员合作，从数据流中删除Adobe Analytics即服务。

   在删除Adobe Analytics即服务之前，请确保您的Analytics用户使用的是Customer Journey Analytics而非Adobe Analytics。

1. 完全删除Analytics源连接器。

   在收集了足够的历史数据并与新的Web SDK实施Customer Journey Analytics后，您可以完全删除Analytics源连接器。

   当您不再需要通过Analytics源连接器从Adobe Analytics环境中获取历史数据，并且您可以仅依赖通过新的Web SDK实施收集的历史数据时，可以执行此操作。

