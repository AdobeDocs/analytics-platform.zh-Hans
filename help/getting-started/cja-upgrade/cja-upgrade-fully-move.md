---
title: 评估升级到 Customer Journey Analytics 后需要使用 Adobe Analytics 多长时间
description: 了解如何评估升级到 Customer Journey Analytics 后需要使用 Adobe Analytics 多长时间
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 7142ef84-66a6-49eb-938b-b67c9b65bf93
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 100%

---

# 评估升级到 Customer Journey Analytics 后何时禁用 Adobe Analytics {#evaluate-aa-needs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-fully-move"
>title="完全转换到 Customer Journey Analytics "
>abstract="（推荐）Adobe 建议您从 Adobe Analytics 完全过渡到 Customer Journey Analytics。在过渡期间，您应该计划同时运行 Adobe Analytics 和 Customer Journey Analytics，以便执行并排数据比较。当您对数据满意时，可以禁用 Adobe Analytics。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-keep-aa"
>title="保留两种分析产品"
>abstract="（不推荐）如果您选择此选项，您与 Adobe 签订的合同将同时包含 Adobe Analytics 和 Customer Journey Analytics，时间长了会增加您组织的开支。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-source-connector"
>title="禁用 Analytics 源连接器，以便仅使用来自 Web SDK 的数据"
>abstract="Analytics 源连接器用于提供并排数据比较、历史数据以及访问 Customer Journey Analytics 中未完全提供的一些功能。当您不再需要将 Adobe Analytics 用于这些目的时，您可以禁用 Analytics 源连接器。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

大多数组织在升级到 Customer Journey Analytics 后最终会禁用 Adobe Analytics。这是由于维护两个分析环境的成本和复杂性所导致的。

但是，Adobe 建议您在实施 Customer Journey Analytics 后，继续让 Adobe Analytics 环境运行一段时间。以下部分描述了这样做的原因，以及禁用 Adobe Analytics 的建议时间。

## 在升级期间和升级之后使用 Adobe Analytics

在决定您的组织是否以及何时应禁用 Adobe Analytics 时，请考虑在升级到 Customer Journey Analytics 期间和之后，Adobe Analytics 的以下用途：

| 在升级期间和升级之后使用 Adobe Analytics | 说明 |
|---------|----------|
| 执行并排数据比较 | Adobe 建议您在新的 Customer Journey Analytics 环境开始运行并收集数据后，继续让您的 Adobe Analytics 环境运行一段时间。这是将您的 Customer Journey Analytics 数据与 Adobe Analytics 数据进行并排比较的最佳方法。<p>在您对 Customer Journey Analytics 环境中的数据感到满意之前，请不要禁用 Adobe Analytics。</p><p>**注释：** Adobe 建议为您的 Customer Journey Analytics 环境实施一个新的 Web SDK，并将其与用于历史数据的 Analytics 源连接器结合使用。[了解详情](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| 保留 Adobe Analytics 的历史数据 | Adobe 建议您在新的 Customer Journey Analytics 环境开始运行并收集数据后，将 Adobe Analytics 环境与 Analytics 源连接器保留一段时间。这是将 Adobe Analytics 历史数据纳入 Customer Journey Analytics 的最佳方式。<p>在通过新的 Web SDK 实施在 Customer Journey Analytics 中收集了足够的历史数据后，您可以完全删除 Analytics 源连接器。当您可以完全依赖使用新的 Customer Journey Analytics Web SDK 实施收集的历史数据时，请执行此操作。</p><p>**注释：** Adobe 建议为您的 Customer Journey Analytics 环境实施一个新的 Web SDK，并将其与用于历史数据的 Analytics 源连接器结合使用。[了解详情](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| 使用数据源或 Adobe Analytics 的其他功能 | Customer Journey Analytics 中的一小部分功能尚未完全可用。如果您需要访问这些功能，可能需要结合使用 Adobe Analytics 和 Customer Journey Analytics，直到这些功能可用。 <p>Customer Journey Analytics 中未完全提供的功能包括数据源和贡献度分析。有关尚未提供的功能的完整列表，请参阅[ Customer Journey Analytics 功能支持](/help/getting-started/aa-vs-cja/cja-aa.md)。</p> |

## 禁用 Adobe Analytics 的过程和时间线 {#disable-adobe-analytics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement-third-pary"
>title="禁用第三方标记管理系统"
>abstract="在 Web SDK 数据完全发挥作用的情况下，与您的标记管理员一起从第三方标记管理系统中删除 AppMeasurement 库。<br><br>执行此步骤的预计时间取决于从标记管理产品中禁用 AppMeasurement 的难易程度，以及您的组织用于部署和管理标记代码的发布周期。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-tags"
>title="在标记中禁用 Analytics 扩展"
>abstract="在 Web SDK 数据完全发挥作用的情况下，与标记管理员合作从标记属性中移除 Adobe Analytics 扩展。在执行此操作之前，请确保您的用户已从使用 Adobe Analytics 过渡到使用 Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-api"
>title="禁用 Adobe Analytics 的 API 数据收集"
>abstract="在 Web SDK 数据完全发挥作用的情况下，与适用的工程团队合作从项目中移除 Adobe Analytics 代码。在执行此操作之前，请确保您的用户已从使用 Adobe Analytics 过渡到使用 Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

您现有的 Adobe Analytics 实施是成功升级到 Customer Journey Analytics 的关键部分，如上一节[在升级期间和升级之后使用 Adobe Analytics](#uses-of-adobe-analytics-during-and-after-an-upgrade)中所述。

当您不再需要使用 Adobe Analytics 来实现上一节中所述的目的时，请使用以下信息移除 Adobe Analytics：

1. 停止使用 Adobe Analytics 收集数据。

   在对 Adobe Analytics 数据和 Customer Journey Analytics 数据的并排比较感到满意后，您可以停止使用 Adobe Analytics 实施来收集数据。新的 Adobe Analytics 数据将不会再通过 Analytics 源连接器流向 Customer Journey Analytics。

   但是，您在此之前从 Adobe Analytics 环境收集的数据仍然可以通过 Analytics 源连接器作为 Customer Journey Analytics 中的历史数据使用。

   此流程根据您用于实施 Adobe Analytics 的数据收集方法而有所不同：

+++ AppMeasurement

   [禁用 AppMeasurement 数据收集](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md)。

+++

+++ Analytics 扩展（标记）

   在标记中禁用 Analytics 扩展。

+++

+++ API

   禁用 API 数据收集。

+++

+++ 第三方

   与您的标记管理员合作从第三方标记管理系统中移除 AppMeasurement 库。

+++

1. 将 Adobe Analytics as a Service 从数据流中移除。

   在 Web SDK 数据完全发挥作用的情况下，与 Platform 管理员合作从数据流中删除 Adobe Analytics 服务。

   在移除 Adobe Analytics as a Service 之前，请确保您的 Analytics 用户使用的是 Customer Journey Analytics，而不是 Adobe Analytics。

1. 完全移除 Analytics 源连接器。

   在通过新的 Web SDK 实施在 Customer Journey Analytics 中收集了足够的历史数据后，您可以完全删除 Analytics 源连接器。

   当您不再需要通过 Analytics 源连接器获取来自 Adobe Analytics 环境的历史数据，并且您可以完全依赖使用新的 Web SDK 实施来收集的历史数据时，请执行此操作。

{{upgrade-final-step}}

