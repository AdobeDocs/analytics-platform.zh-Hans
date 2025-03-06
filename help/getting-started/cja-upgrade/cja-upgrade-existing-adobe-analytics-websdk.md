---
title: 配置现有的Adobe Analytics Web SDK实施以将数据发送到Platform
description: 了解如何配置现有的Adobe Analytics Web SDK实施
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 8fdc90ff3392b5d6884872d191a40a762cad6a3f
workflow-type: tm+mt
source-wordcount: '1011'
ht-degree: 1%

---

# 配置现有的Adobe Analytics Web SDK实施以将数据发送到Platform {#existing-websdk-implementation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-remove-aa-from-datastream"
>title="将 Adobe Analytics 即服务从数据流中删除"
>abstract="在Web SDK数据完全正常工作的情况下，请与平台管理员合作，从数据流中删除Adobe Analytics即服务。 在执行此操作之前，请确保您的用户已经从使用Adobe Analytics过渡到Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

如果您的Adobe Analytics实施已经在使用Adobe Experience Platform Web SDK，则可以通过设置数据流开始向Platform发送数据。 或者，如果您已经将数据发送到Platform，则只需在Platform数据集和Customer Journey Analytics之间创建连接即可。


## 优缺点

考虑将现有Adobe Analytics Web SDK实施配置为将数据发送到Platform的以下优缺点：

| 优势 | 缺点 |
|----------|---------|
| 如果您的Adobe Analytics实施已经在使用Web SDK，那么这是首选的升级路径。<ul><li>**提供在Experience Edge Network中托管数据的所有优势**： <p>这些优势包括：</p><ul><li>高性能报表和数据可用性，因为Adobe Experience Platform旨在支持[实时个性化用例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>在其他Adobe Experience Cloud产品(AJO、RTCDP等)之间整合Experience Cloud数据收集的实施</li><li>不依赖于Adobe Analytics命名法(属性、eVar、事件等)</li></ul><li>**使用您现有的实施**：虽然此方法需要一些实施更改，但它不需要从头开始的全新实施。 您可以在不影响现有Adobe Analytics报表的情况下，使用现有数据层和代码，只需对实施逻辑进行最低限度的更改即可。</li><li>**提供使用XDM架构的选项**：您可以选择使用现有的Adobe Analytics架构，也可以创建XDM架构并将数据对象中的字段映射到XDM架构。 [XDM架构](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas)是一个灵活的架构，用于定义您需要的任何字段，并且只定义相关的字段。 <p>请参阅下面的“使用您自己的XDM架构”，详细了解使用您自己的XDM架构的优势。</p></li><li>**保留规则和数据元素**：虽然它确实需要新的规则操作，但您可以重复使用现有的数据元素和规则条件，只需很少的更改。</li><li>**未来验证**：如果您选择使用自己的XDM架构，则未来实施更新会更轻松。</li></ul> | <ul><li>**需要映射才能将数据发送到Platform**：当您的组织准备好使用Customer Journey Analytics时，您必须将数据发送到Adobe Experience Platform中的数据集。 此操作要求数据对象中的每个字段都是数据流映射工具中的条目，并将其分配给XDM架构字段。 此工作流的映射只需执行一次，并且不涉及对实施进行更改。 但是，这是一个额外的步骤，在XDM对象中发送数据时不需要执行此步骤。</li><li>**随着时间的推移引入更多复杂性**：将来添加的任何字段都必须映射到数据流中的XDM。<p>只要在实施中添加了新字段，就可以执行以下任一操作：</p><ul><li>**选项1：**&#x200B;在数据对象中填充新的任意evar或新prop，然后将其映射到所需的XDM字段。<p>此过程可促进客户端实施的一致性，但需要映射。</p></li><li>**选项2：**&#x200B;将数据对象保留为旧版实现，并开始仅为所有新字段填充XDM对象。<p>此过程不需要映射，但这意味着某些变量仅位于数据对象中，而其他变量仅位于XDM对象中。 无论何时需要对实施进行故障排除，都需要转到两个位置。 请确保您的内部工作流符合此要求。</p></li></ul> |

{style="table-layout:auto"}

## 实施步骤

1. 开始将数据从Edge Network发送到Platform。 通过数据对象以AppMeasurement格式发送所有变量。

   有关详细信息，请参阅[数据对象变量映射到Adobe Analytics](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/aep-edge/data-var-mapping)。

1. 选择您的架构。

   您可以选择是否使用现有Adobe Analytics架构，也可以创建XDM架构以在开始使用其他Platform服务时更好地满足贵组织的需求。

   Adobe建议创建XDM架构。 有关详细信息，请参阅[创建自定义架构以用于您的Customer Journey Analytics Web SDK实施](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

   +++使用Adobe Analytics架构

   | 优势 | 缺点 |
   |----------|---------|
   | <p>使用Adobe Analytics架构的优势包括：</p><ul><li>易于升级<p>如果您已经使用Adobe Experience Platform Web SDK将数据发送到Adobe Analytics，则可以将其他服务添加到您的数据流中以将数据发送到Adobe Experience Platform(这随后可以在您的Customer Journey Analytics配置中使用)。</p></li></ul> | <p>使用Adobe Analytics架构的缺点包括：</p><ul><li>虽然使用Adobe Analytics架构不会限制您如何将其与其他Platform应用程序一起使用，但它的确会导致架构比不使用该架构时复杂得多。 这是因为Adobe Analytics架构包含许多特定于Adobe Analytics的对象，您的组织不太可能使用这些对象。<p>当需要对架构进行更改时，您必须筛选成千上万个未使用的字段以查找需要更新的字段。</p></li></ul> |

+++

   +++创建XDM架构

   | 优势 | 缺点 |
   |----------|---------|
   | <ul><p>更新到您自己的XDM架构的优势包括：</p><ul><li>简化架构，根据贵组织的需求以及您使用的特定平台应用程序量身定制。</li><p>当需要对架构进行更改时，您不必在数千个未使用的字段中进行筛选，即可找到需要更新的字段。</p></ul> | <p>更新到您自己的XDM架构的缺点包括：</p><ul><li>在开始向Platform发送数据之前，需要更新架构，这是一个非常耗时的过程。</li></ul> |

+++

1. 使用数据流映射将数据对象中的所有字段映射到您的XDM架构。

   有关详细信息，请参阅Experience Platform文档中为数据收集](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep)准备数据中的[映射](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping)。[

1. 继续执行[建议的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[动态生成的升级步骤](https://gigazelle.github.io/cja-ttv/)。




