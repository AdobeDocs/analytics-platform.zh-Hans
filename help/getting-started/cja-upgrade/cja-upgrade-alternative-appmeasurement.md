---
title: 升级到Customer Journey Analytics时的备用方法
description: 了解升级到Customer Journey Analytics时的替代方法
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 2b66e2db9b22bab5304fe981e58828d4ae9fabbd
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 0%

---

# 升级替代方案：将AppMeasurement数据收集与Experience Platform Web SDK和Customer Journey Analytics结合使用 {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="在Web SDK中使用AppMeasurement逻辑"
>abstract="不要通过XDM对象发送数据，而是通过数据对象以AppMeasurement格式发送所有变量。<br><br>此选项允许您将AppMeasurement逻辑映射到XDM，而不是从头开始填充XDM对象，从而节省实施时间。 但是，随着时间的推移，它会引入额外的复杂性，因为您将来添加的任何字段都必须映射到数据流中的XDM。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>在回答[Customer Journey Analytics升级核对清单](https://gigazelle.github.io/cja-ttv/)中的问题时，使用此页上的信息。

升级到Customer Journey Analytics时，Adobe [建议Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)的新实现。 但是，根据时间表和资源限制等多个因素，建议的升级步骤可能对您的组织不实用。

您可以将AppMeasurement或Analytics扩展数据收集逻辑与Web SDK结合使用，以便将数据发送到Platform和Customer Journey Analytics，而不是通过XDM对象收集数据。 但是，这种替代方法会随着时间的推移而增加复杂性。

## 优缺点

此方法与[将整个数据层发送到Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)互斥，因为两种方法都完成相同的任务。 (此方法比将整个数据层发送到Adobe更可取。 它更精细，因为prop和evar都处理数据。__adobe.analytics._variable-name_。)

请注意使用此升级替代方案的以下优缺点：

| 优势 | 缺点 |
|----------|---------|
| <ul><li>**提供在Experience Edge Network中托管数据的所有优势**： <p>这些优势包括：</p><ul><li>高性能报表和数据可用性，因为Adobe Experience Platform旨在支持[实时个性化用例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>在其他Adobe Experience Cloud产品(AJO、RTCDP等)之间整合Experience Cloud数据收集的实施</li><li>不限于Adobe Analytics命名法(属性、eVar、事件等)</li></ul><li>**使用您现有的实施**：虽然此方法需要一些实施更改，但它不需要从头开始的全新实施。 它允许您将AppMeasurement逻辑映射到XDM，而不是从头开始填充XDM对象。</li></ul> | <ul><li>**需要映射才能将数据发送到Platform**：当您的组织准备好使用Customer Journey Analytics时，您必须将数据发送到Adobe Experience Platform中的数据集。 此操作要求数据对象中的每个字段都是数据流映射工具中的条目，并将其分配给XDM架构字段。 此工作流的映射只需执行一次，并且不涉及对实施进行更改。 但是，这是一个额外的步骤，在XDM对象中发送数据时不需要执行此步骤。</li><li>**随着时间的推移引入更多复杂性**：将来添加的任何字段都必须映射到数据流中的XDM。<p>只要在实施中添加了新字段，就可以执行以下任一操作：</p><ul><li>**选项1：**&#x200B;在数据对象中填充新的任意evar或新prop，然后将其映射到所需的XDM字段。<p>此过程可促进客户端实施的一致性，但需要映射。</p></li><li>**选项2：**&#x200B;将数据对象保留为旧版实现，并开始仅为所有新字段填充XDM对象。<p>此过程不需要映射，但这意味着某些变量仅位于数据对象中，而其他变量仅位于XDM对象中。 无论何时需要对实施进行故障排除，都需要转到两个位置。 请确保您的内部工作流符合此要求。</p></li></ul> </li></ul> |

{style="table-layout:auto"}

## 基本步骤

迁移Adobe Analytics实施(AppMeasurement或Analytics扩展)以使用Web SDK将数据发送到Customer Journey Analytics的基本步骤如下：

1. （可选）迁移您的Adobe Analytics实施以使用Adobe Experience Platform Web SDK，并开始将数据发送到Edge Network。

   这是一个可选步骤，允许您迁移现有的Adobe Analytics实施以使用Web SDK并验证所有内容在Adobe Analytics中是否都正常工作。 完成此项配置并且Adobe Analytics中的数据令人满意后，您可以将数据从Edge Network发送到Customer Journey Analytics。

   这种灵活性使得升级到Customer Journey Analytics时更加有条不紊、更加周到。

   有关如何执行此操作的信息，请参阅Adobe Analytics文档中的以下文章：

   * [使用标记迁移到Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [使用JavaScript迁移到Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. 将数据从Edge Network发送到Customer Journey Analytics。

   1. 通过数据对象以AppMeasurement格式发送所有变量。

      有关详细信息，请参阅[数据对象变量映射到Adobe Analytics](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/aep-edge/data-var-mapping)。

   1. 如果您还没有这样的文件，请为您的组织创建一个XDM架构。

      有关详细信息，请参阅[创建自定义架构以用于您的Customer Journey Analytics Web SDK实施](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

   1. 使用数据流映射将数据对象中的所有字段映射到您的XDM架构。

      有关详细信息，请参阅Experience Platform文档中为数据收集](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep)准备数据中的[映射](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping)。[

