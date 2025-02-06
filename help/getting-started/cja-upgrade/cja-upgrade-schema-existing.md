---
title: 选择要Customer Journey Analytics的架构
description: 了解在为Customer Journey Analytics选择架构时可用的选项以及各个选项的优缺点
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: a2b90ab2-2fcb-4bf4-a862-2f0675dc2fe2
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 0%

---

# 选择要Customer Journey Analytics的架构 {#choose-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-tailored"
>title="使用自定义架构"
>abstract="（推荐）通过自定义架构，您的组织可以仅跟踪您需要的内容，并避免与混乱和不需要的字段相关的开销。 此选项包括由Web SDK添加的字段组和自定义到您组织的字段组。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-default"
>title="使用默认架构"
>abstract="（不推荐）Adobe Analytics架构包含超过一千个字段，这可能会导致架构混乱而复杂。 您的组织将被迫继续遵循prop和eVar的概念，这是一个未在Customer Journey Analytics中使用的旧概念。 与其他Adobe Experience Platform服务集成比较困难。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>此文档应该用作[Adobe AnalyticsCustomer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)的一部分。

<!-- this page exists as the "Learn more" link in the info icons for the options "I am comfortable using my Adobe Analytics schema as a basis" and "I want to use a schema tailored to my organization" -->

升级到Customer Journey Analytics时，Adobe建议创建一个自定义Experience Data Model (XDM)架构，以便在您开始使用其他Platform服务时更好地满足贵组织的需求。 或者，您也可以选择使用现有的Adobe Analytics架构。

考虑每种方法的优缺点。

## 创建为您的组织定制的自定义架构（推荐）

Adobe建议在升级到Customer Journey Analytics时创建自定义架构。

| 优势 | 缺点 |
|----------|---------|
| <ul><p>将更新到您自己的自定义架构的优点包括：</p><ul><li>简化架构，根据贵组织的需求以及您使用的特定平台应用程序量身定制。</li><p>当需要对架构进行更改时，您不必在数千个未使用的字段中进行筛选，即可找到需要更新的字段。</p></ul> | <p>更新到您自己的自定义架构的缺点包括：</p><ul><li>在开始向Platform发送数据之前，需要更新架构，这是一个非常耗时的过程。</li></ul> |

## 使用您现有的Adobe Analytics架构

只有使用Adobe Analytics Web SDK配置了Adobe Analytics实施时，用于在Customer Journey Analytics中使用现有Adobe Experience Platform架构的选项才可用。<!-- correct? Or can you do this with an AppMeasurement implementation?-->

| 优势 | 缺点 |
|----------|---------|
| <p>使用Adobe Analytics架构的优势包括：</p><ul><li>易于升级<p>如果您已经使用Adobe Experience Platform Web SDK将数据发送到Adobe Analytics，则可以将其他服务添加到您的数据流以将数据发送到Adobe Experience Platform(然后可以在您的Customer Journey Analytics配置中使用)。</p></li></ul> | <p>使用Adobe Analytics架构的缺点包括：</p><ul><li>虽然使用Adobe Analytics架构不会限制您如何将其与其他Platform应用程序一起使用，但它的确会导致架构比不使用该架构时复杂得多。 这是因为Adobe Analytics架构包含许多特定于Adobe Analytics的对象，您的组织不太可能使用这些对象。<p>当需要对架构进行更改时，您必须筛选成千上万个未使用的字段以查找需要更新的字段。</p></li></ul> |




<!-- Not sure about any of this: 

If you plan to use your Adobe Analytics schema, the following steps are required:

For Adobe Analytics implementations using AppMeasurement:

1. Datastream mapping

For Adobe Analytics implementations using the Web SDK:

1. 



the upgrade steps provided by the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).

If you want to create an XDM schema to use with Customer Journey Analytics, continue with [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).


Tags: (All 3 require data prep mapping. Would need to go into the datastream and map every single field to its appropriate place in XDM. Because whenever you use the data object, it always requires mapping. If you send something in the data object and it doesn't get mapped, the it is permanently lost and can't be recovered.)

1. Shim - Intercepts and instead of sending data to a report suite, it sends it to a Data View. (Data object)

1. Russ special - convert current implementation to a Web SDK implementation - put everything in the data object. 

1. Plop entire data layer into the data object and send that to the datastream. (not documented. Might be the Web SDK docs.)

-->
