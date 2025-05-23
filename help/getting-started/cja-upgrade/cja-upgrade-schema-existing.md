---
title: 选择 Customer Journey Analytics 的架构
description: 了解在选择 Customer Journey Analytics 架构时可用的选项，以及每个选项的优缺点
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: a2b90ab2-2fcb-4bf4-a862-2f0675dc2fe2
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '475'
ht-degree: 100%

---

# 选择 Customer Journey Analytics 的架构 {#choose-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-tailored"
>title="使用一个自定义架构"
>abstract="（推荐）自定义架构可以让您的组织只跟踪您需要的内容，避免那些与混乱和不需要的领域相关的开支。此选项包括 Web SDK 添加的字段组和您的组织自定义的字段组。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-default"
>title="使用默认架构"
>abstract="（不推荐）Adobe Analytics 架构包含一千多个字段，这可能会导致架构混乱、复杂。您的组织将不得不继续遵守 props 和 eVars 的概念，这个旧版概念在 Customer Journey Analytics 不使用。与其他 Adobe Experience Platform 服务的集成更加困难。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

<!-- this page exists as the "Learn more" link in the info icons for the options "I am comfortable using my Adobe Analytics schema as a basis" and "I want to use a schema tailored to my organization" -->

升级到 Customer Journey Analytics 时，Adobe 建议创建一个自定义的体验数据模型 (XDM) 架构，以便在您开始使用其他 Platform 服务时更好地满足组织的需求。或者，您可以选择使用现有的 Adobe Analytics 架构。

请考虑每种方法的优点和缺点。

## 创建一个适合您组织的自定义架构（推荐）

Adobe 建议在升级到 Customer Journey Analytics 时创建一个自定义架构。

| 优点 | 缺点 |
|----------|---------|
| <ul><p>更新到您自己的自定义架构的优点包括：</p><ul><li>根据您的组织需求和您使用的特定 Platform 应用程序量身定制的简化架构。</li><p>当需要更改架构时，您无需筛选数千个未使用的字段来找到需要更新的字段。</p></ul> | <p>更新到您自己的自定义架构的缺点包括：</p><ul><li>更新架构是一个耗时的过程，并且必须在开始向 Platform 发送数据之前进行。</li></ul> |

## 使用现有的 Adobe Analytics 架构

仅当您的 Adobe Analytics 实施配置了 Adobe Experience Platform Web SDK 时，才可以使用将现有 Adobe Analytics 架构与 Customer Journey Analytics 结合使用的选项。<!-- correct? Or can you do this with an AppMeasurement implementation?-->

| 优点 | 缺点 |
|----------|---------|
| <p>使用 Adobe Analytics 架构的优势包括：</p><ul><li>易于升级<p>如果您已经在使用 Adobe Experience Platform Web SDK 将数据发送到 Adobe Analytics，则可以向数据流添加附加服务，以将数据发送到 Adobe Experience Platform（然后可以在您的 Customer Journey Analytics 配置中使用）。</p></li></ul> | <p>使用 Adobe Analytics 架构的缺点包括：</p><ul><li>虽然使用 Adobe Analytics 架构不会限制您将其与其他 Platform 应用程序结合使用的方式，但它会使架构变得比原本更复杂。这是因为 Adobe Analytics 架构包含许多特定于 Adobe Analytics 的对象，而您的组织不太可能会使用这些对象。<p>当需要更改架构时，您必须筛选数千个未使用的字段来找到需要更新的字段。</p></li></ul> |




<!-- Not sure about any of this: 

If you plan to use your Adobe Analytics schema, the following steps are required:

For Adobe Analytics implementations using AppMeasurement:

1. Datastream mapping

For Adobe Analytics implementations using the Web SDK:

1. 



the upgrade steps provided by the Customer Journey Analytics Upgrade Guide.

If you want to create an XDM schema to use with Customer Journey Analytics, continue with [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).


Tags: (All 3 require data prep mapping. Would need to go into the datastream and map every single field to its appropriate place in XDM. Because whenever you use the data object, it always requires mapping. If you send something in the data object and it doesn't get mapped, the it is permanently lost and can't be recovered.)

1. Shim - Intercepts and instead of sending data to a report suite, it sends it to a Data View. (Data object)

1. Russ special - convert current implementation to a Web SDK implementation - put everything in the data object. 

1. Plop entire data layer into the data object and send that to the datastream. (not documented. Might be the Web SDK docs.)

-->
