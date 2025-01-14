---
title: 升级快捷方式迁移AppMeasurement或Analytics扩展实施以使用Web SDK
description: 了解从Adobe Analytics升级到Customer Journey Analytics时推荐的路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 83927cf0-b3b4-42b4-9ca5-0c81c091383f
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 15%

---

# 升级快捷键：迁移 AppMeasurement 或 Analytics 扩展实施，以使用 Web SDK {#shortcut-migrate-websdk}

>[!NOTE]
>
>此文档应该用作[Adobe AnalyticsCustomer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)的一部分。

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_migrate_aa_to_websdk"
>title="迁移您的 Analytics 实施，以使用 Web SDK"
>abstract="您可以通过数据对象以 AppMeasurement 格式发送所有变量，而不是通过 XDM 对象发送数据。此快捷方式允许您继续使用 AppMeasurement 逻辑将数据发送到 Platform。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migrate_aa_to_websdk"
>title="迁移您的 Analytics 实施，以使用 Web SDK"
>abstract="您可以通过数据对象以 AppMeasurement 格式发送所有变量，而不是通过 XDM 对象发送数据。此快捷方式允许您继续使用 AppMeasurement 逻辑将数据发送到 Platform。"

<!-- markdownlint-enable MD034 -->

升级到Customer Journey Analytics时，Adobe[建议Experience PlatformWeb SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)的新实现。 但是，根据时间表和资源限制等多个因素，建议的升级步骤可能对您的组织不实用。

如果您的Adobe Analytics实施AppMeasurement或Analytics扩展，则提供了一个升级快捷方式，通过该方式，您可以迁移Adobe Analytics实施以使用Adobe Experience Platform Web SDK开始向Edge Network和Adobe Analytics发送数据，然后再将数据发送到Customer Journey Analytics。

## 优缺点

请考虑以下升级快捷方式的优缺点，以迁移AppMeasurement或Analytics扩展实施以使用Web SDK：

| 优势 | 缺点 |
|----------|---------|
| <ul><li>**提供在ExperienceEdge Network中托管数据的所有优点**： <p>这些优势包括：</p><ul><li>高性能报表和数据可用性，因为Adobe Experience Platform旨在支持[实时个性化用例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>在其他Experience Cloud产品(AJO、RTCDP等)之间整合Adobe Experience Cloud数据收集的实施</li><li>不依赖于Adobe Analytics命名法(属性、eVar、事件等)</li></ul><li>**使用您现有的实施**：虽然此方法需要一些实施更改，但它不需要从头开始的全新实施。 您可以在不影响现有Adobe Analytics报表的情况下，使用现有数据层和代码，只需对实施逻辑进行最低限度的更改即可。</li><li>**提供灵活性，以便稍后为您的组织创建XDM架构**：您可以迁移现有的Adobe Analytics实施以使用Web SDK并验证所有内容在Adobe Analytics中是否都正常工作，然后创建XDM架构。 这种灵活性使得升级到Customer Journey Analytics的过程更加有条不紊，而且更加深思熟虑。</li></ul> | <ul><li>**需要映射才能将数据发送到Platform**：当您的组织准备好使用Customer Journey Analytics时，您必须将数据发送到Adobe Experience Platform中的数据集。 此操作要求数据对象中的每个字段都是数据流映射工具中的条目，并将其分配给XDM架构字段。 此工作流的映射只需执行一次，并且不涉及对实施进行更改。 但是，这是一个额外的步骤，在XDM对象中发送数据时不需要执行此步骤。</li><li>**技术债务**：由于此方法使用现有实施的修改形式，因此将来需要跟踪实施逻辑和执行更改会更加困难。 </li></ul> |

{style="table-layout:auto"}

## 基本步骤

如果决定使用升级快捷方式迁移AppMeasurement或Analytics扩展实施以使用Web SDK，则会在[Adobe Analytics中为贵组织动态生成的步骤添加一个新步骤，以Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。

迁移AppMeasurement或Analytics扩展实施以使用Web SDK的基本步骤如下：

1. 开始将数据发送到Platform。

   如果您已经使用Adobe Analytics实施将数据发送到Platform，则不需要执行此步骤。 您只需在Platform数据集与Customer Journey Analytics之间创建连接即可，如本流程后面部分所述。

1. （可选）根据需要为您的组织创建XDM架构。

1. （视情况而定）如果您创建了XDM架构，请使用数据流映射将数据对象中的所有字段映射到XDM架构。
