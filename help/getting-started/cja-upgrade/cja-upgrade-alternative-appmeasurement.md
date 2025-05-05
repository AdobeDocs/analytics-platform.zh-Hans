---
title: 升级到Customer Journey Analytics时的备用方法
description: 了解升级到Customer Journey Analytics时的替代方法
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 0bf35c67-c8ae-4349-93fb-b9806c1064a8
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1302'
ht-degree: 11%

---

# 升级替代方案：将 AppMeasurement 数据收集与 Experience Platform Web SDK 和 Customer Journey Analytics 结合使用 {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="将 AppMeasurement 逻辑与 Web SDK 结合使用"
>abstract="通过数据对象以 AppMeasurement 格式发送所有变量，而不是通过 XDM 对象发送数据。<br><br>此选项允许您将 AppMeasurement 逻辑映射到 XDM，而不是从头开始填充 XDM 对象，从而节省实施时间。但是，随着时间的推移，它会带来更多的复杂性，因为您将来添加的任何字段都必须映射到数据流中的 XDM。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic-step"
>title="更改 AppMeasurement 逻辑以指向 Web SDK"
>abstract="之所以出现这一步骤是因为您选择采取了一条实施捷径。复制或更改 AppMeasurement 逻辑以填充数据对象，而不是 s 对象。例如，将 s.eVar1 的赋值更改为数据。__adobe.analytics.eVar1 并对所有 Analytics 变量重复此操作。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

升级到Customer Journey Analytics时，Adobe [建议Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)的新实现。 但是，根据时间表和资源限制等多个因素，建议的升级步骤可能对您的组织不实用。

您可以将AppMeasurement或Analytics扩展数据收集逻辑与Web SDK结合使用，以便将数据发送到Platform和Customer Journey Analytics，而不是通过XDM对象收集数据。 但是，这种替代方法会随着时间的推移而增加复杂性。

## 优缺点

此方法与[将整个数据层发送到Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)互斥，因为两种方法都完成相同的任务。 (此方法比将整个数据层发送到Adobe更可取。 它更精细，因为prop和evar都处理数据。__adobe.analytics._variable-name_。)

请注意使用此升级替代方案的以下优缺点：

| 优势 | 缺点 |
|----------|---------|
| 如果您的Adobe Analytics实施已经在使用Web SDK，那么这是首选的升级路径。<ul><li>**提供在Experience Edge Network中托管数据的所有优势**： <p>这些优势包括：</p><ul><li>高性能报表和数据可用性，因为Adobe Experience Platform旨在支持[实时个性化用例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=zh-Hans)</li><li>在其他Adobe Experience Cloud产品(AJO、RTCDP等)之间整合Experience Cloud数据收集的实施</li><li>不依赖于Adobe Analytics命名法(属性、eVar、事件等)</li></ul><li>**使用您现有的实施**：虽然此方法需要一些实施更改，但它不需要从头开始的全新实施。 您可以在不影响现有Adobe Analytics报表的情况下，使用现有数据层和代码，只需对实施逻辑进行最低限度的更改即可。</li><li>**提供使用XDM架构的选项**：您可以选择使用现有的Adobe Analytics架构，也可以创建XDM架构并将数据对象中的字段映射到XDM架构。 [XDM架构](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/home#xdm-schemas)是一个灵活的架构，用于定义您需要的任何字段，并且只定义相关的字段。 <p>请参阅下面的“使用您自己的XDM架构”，详细了解使用您自己的XDM架构的优势。</p></li><li>**保留规则和数据元素**：虽然它确实需要新的规则操作，但您可以重复使用现有的数据元素和规则条件，只需很少的更改。</li><li>**未来验证**：如果您选择使用自己的XDM架构，则未来实施更新会更轻松。</li></ul> | <ul><li>**需要映射才能将数据发送到Platform**：当您的组织准备好使用Customer Journey Analytics时，您必须将数据发送到Adobe Experience Platform中的数据集。 此操作要求数据对象中的每个字段都是数据流映射工具中的条目，并将其分配给XDM架构字段。 此工作流的映射只需执行一次，并且不涉及对实施进行更改。 但是，这是一个额外的步骤，在XDM对象中发送数据时不需要执行此步骤。</li><li>**随着时间的推移引入更多复杂性**：将来添加的任何字段都必须映射到数据流中的XDM。<p>只要在实施中添加了新字段，就可以执行以下任一操作：</p><ul><li>**选项1：**&#x200B;在数据对象中填充新的任意evar或新prop，然后将其映射到所需的XDM字段。<p>此过程可促进客户端实施的一致性，但需要映射。</p></li><li>**选项2：**&#x200B;将数据对象保留为旧版实现，并开始仅为所有新字段填充XDM对象。<p>此过程不需要映射，但这意味着某些变量仅位于数据对象中，而其他变量仅位于XDM对象中。 无论何时需要对实施进行故障排除，都需要转到两个位置。 请确保您的内部工作流符合此要求。</p></li></ul> |

{style="table-layout:auto"}

## 基本步骤

迁移Adobe Analytics实施(AppMeasurement或Analytics扩展)以使用Web SDK将数据发送到Customer Journey Analytics的基本步骤如下：

1. 迁移Adobe Analytics实施以使用Adobe Experience Platform Web SDK，并开始将数据发送到Edge Network。

   此步骤允许您迁移现有的Adobe Analytics实施以使用Web SDK。 您可以选择在将数据发送到Adobe Analytics之前，将数据发送到Customer Journey Analytics以验证在Adobe Analytics中一切正常。 完成此项配置并且Adobe Analytics中的数据令人满意后，您可以将数据从Edge Network发送到Customer Journey Analytics。

   这种灵活性使得升级到Customer Journey Analytics时更加有条不紊、更加周到。

   有关如何执行此操作的信息，请参阅Adobe Analytics文档中的以下文章：

   * [使用标记迁移到Web SDK](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [使用JavaScript迁移到Web SDK](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. 开始将数据从Edge Network发送到Platform。

   1. 通过数据对象以AppMeasurement格式发送所有变量。

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

      有关详细信息，请参阅Experience Platform文档中为数据收集[&#128279;](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/data-prep)准备数据中的[映射](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/data-prep?lang=en#mapping)。

{{upgrade-final-step}}。




