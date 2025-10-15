---
title: 配置现有的 Adobe Analytics Web SDK 实施，以向 Platform 发送数据
description: 了解如何配置现有的Adobe Analytics Web SDK实施
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1459a512-bfa8-4805-97e8-5b6acc6e4ac9
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '998'
ht-degree: 66%

---

# 配置现有的 Adobe Analytics Web SDK 实施，以向 Platform 发送数据 {#existing-websdk-implementation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-remove-aa-from-datastream"
>title="将 Adobe Analytics 即服务从数据流中删除"
>abstract="在 Web SDK 数据完全发挥作用的情况下，与 Platform 管理员合作从数据流中删除 Adobe Analytics 服务。在执行此操作之前，请确保您的用户已从使用 Adobe Analytics 过渡到使用 Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

如果您的Adobe Analytics实施已经在使用Adobe Experience Platform Web SDK，则可以通过设置数据流开始向Platform发送数据。 或者，如果您已经将数据发送到 Platform，则只需在 Platform 数据集和 Customer Journey Analytics 之间创建连接。


## 优点和缺点

考虑将现有Adobe Analytics Web SDK实施配置为将数据发送到Platform的以下优缺点：

| 优点 | 缺点 |
|----------|---------|
| 如果您的 Adobe Analytics 实施已经在使用 Web SDK，则这是首选的升级路径。<ul><li>**提供在 Experience Edge Network 中托管数据的所有优点**： <p>这些优点包括：</p><ul><li>Adobe Experience Platform 专为支持[实时个性化用例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)而构建，因此具有高性能报告和数据可用性</li><li>在其他 Experience Cloud 产品（AJO、RTCDP 等）之间整合对 Adobe Experience Cloud 数据收集的实施</li><li>不依赖于 Adobe Analytics 命名法（属性、eVar、事件等）</li></ul><li>**使用您现有的实施**：虽然这种方法需要进行一些实施方面的变更，但它并不需要从头开始进行全新的实施。您可以使用现有的数据层和代码，只需对实施逻辑进行最少的更改，而不会影响现有的 Adobe Analytics 报告。</li><li>**提供使用 XDM 架构的选项**：您可以选择使用现有的 Adobe Analytics 架构，或者创建一个 XDM 架构，并将数据对象中的字段映射到该 XDM 架构。[XDM 架构](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/home#xdm-schemas)是一种灵活的架构，它可以定义您需要的任何字段，并且仅会定义相关的字段。 <p>有关使用您自己的 XDM 架构的优势的更多信息，请参阅下面的“使用您自己的 XDM 架构”。</p></li><li>**保留规则和数据元素**：虽然这确实需要新的规则操作，但您只需进行最小的更改，即可重复使用现有的数据元素和规则条件。</li><li>**面向未来**：如果您选择使用自己的 XDM 架构，那么未来的实施更新将会更容易。</li></ul> | <ul><li>**需要映射才能将数据发送到 Platform**：当您的组织准备好使用 Customer Journey Analytics 时，您必须将数据发送到 Adobe Experience Platform 中的数据集。此操作要求数据对象中的每个字段都是数据流映射工具中的一个条目，并且该条目会将其分配给一个 XDM 架构字段。对于此工作流程，仅需进行一次映射，并且不涉及对实施进行更改。但是，这是一个额外的步骤，在 XDM 对象中发送数据时并不需要该步骤。</li><li>**随着时间的推移引入更多复杂性**：将来添加的任何字段都必须映射到数据流中的XDM。<p>只要在实施中添加了新字段，就可以执行以下任一操作：</p><ul><li>**选项1：**&#x200B;在数据对象中填充新的任意evar或新prop，然后将其映射到所需的XDM字段。<p>此过程可促进客户端实施的一致性，但需要映射。</p></li><li>**选项2：**&#x200B;将数据对象保留为旧版实现，并开始仅为所有新字段填充XDM对象。<p>此过程不需要映射，但这意味着某些变量仅位于数据对象中，而其他变量仅位于XDM对象中。 无论何时需要对实施进行故障排除，都需要转到两个位置。 请确保您的内部工作流符合此要求。</p></li></ul> |

{style="table-layout:auto"}

## 实施步骤

1. 开始将数据从Edge Network发送到Platform。 通过数据对象以AppMeasurement格式发送所有变量。

   有关详细信息，请参阅[数据对象变量映射到Adobe Analytics](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/aep-edge/data-var-mapping)。

1. 选择您的架构。

   您可以选择是否使用现有Adobe Analytics架构，也可以创建XDM架构以在开始使用其他Platform服务时更好地满足贵组织的需求。

   Adobe建议创建XDM架构。 有关详细信息，请参阅[创建自定义架构以用于您的Customer Journey Analytics Web SDK实施](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

   +++使用Adobe Analytics架构

   | 优点 | 缺点 |
   |----------|---------|
   | <p>使用 Adobe Analytics 架构的优势包括：</p><ul><li>易于升级<p>如果您已经在使用 Adobe Experience Platform Web SDK 将数据发送到 Adobe Analytics，则可以向数据流添加附加服务，以将数据发送到 Adobe Experience Platform（然后可以在您的 Customer Journey Analytics 配置中使用）。</p></li></ul> | <p>使用 Adobe Analytics 架构的缺点包括：</p><ul><li>虽然使用 Adobe Analytics 架构不会限制您将其与其他 Platform 应用程序结合使用的方式，但它会使架构变得比原本更复杂。这是因为 Adobe Analytics 架构包含许多特定于 Adobe Analytics 的对象，而您的组织不太可能会使用这些对象。<p>当需要更改架构时，您必须筛选数千个未使用的字段来找到需要更新的字段。</p></li></ul> |

   +++

   +++创建 XDM 架构

   | 优点 | 缺点 |
   |----------|---------|
   | <ul><p>升级到您自己的 XDM 架构的优点包括：</p><ul><li>根据您的组织需求和您使用的特定 Platform 应用程序量身定制的简化架构。</li><p>当需要更改架构时，您无需筛选数千个未使用的字段来找到需要更新的字段。</p></ul> | <p>升级到您自己的 XDM 架构的缺点包括：</p><ul><li>更新架构是一个耗时的过程，并且必须在开始向 Platform 发送数据之前进行。</li></ul> |

   +++

1. 使用数据流映射将数据对象中的所有字段映射到您的XDM架构。

   有关详细信息，请参阅Experience Platform文档中为数据收集[准备数据中的](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping)映射[。](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep)

{{upgrade-final-step}}
