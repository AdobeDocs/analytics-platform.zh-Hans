---
title: 升级到Customer Journey Analytics时的备用方法
description: 了解升级到Customer Journey Analytics时的替代方法
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 5e80e68c6b5d3dca19dae21c6719b040b28afaf9
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 0%

---

# 升级替代方案：将数据层发送到Customer Journey Analytics {#data-collection-data-layer}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer"
>title="将数据层发送到Adobe"
>abstract="您可以通过该数据对象将整个数据层发送到Adobe，而不是通过XDM对象发送数据。<br><br>此选项允许您将数据层映射到XDM，而不是从头开始填充XDM对象，从而节省实施时间。 但是，此映射需要大量工作，因为会有大量数据是Adobe不易解释的。 随着时间的推移，此选项还会引入额外的复杂性，因为您以后添加到数据的任何字段都必须映射到数据流中的XDM。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-send-data-layer"
>title="将数据层发送到Adobe"
>abstract="将您的实施配置为在所需时间将数据发送到Adobe，并将JSON有效负载完全配置为您的数据层。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer-map"
>title="将每个数据层元素分配给XDM"
>abstract="将每个数据层元素映射到所需的XDM字段。 任何未映射到XDM字段的数据层元素将被永久删除，因为Adobe不知道将数据存储在何处以及如何存储。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>在回答[Customer Journey Analytics升级核对清单](https://gigazelle.github.io/cja-ttv/)中的问题时，使用此页上的信息。

升级到Customer Journey Analytics时，Adobe [建议Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)的新实现。 但是，根据时间表和资源限制等多个因素，建议的升级步骤可能对您的组织不实用。

您可以将整个数据层发送到Customer Journey Analytics，而不是使用XDM对象收集数据。 但是，这种替代方法会随着时间的推移而增加复杂性。

## 优缺点

此方法与[在Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)中使用AppMeasurement数据收集逻辑是互斥的，因为这两种方法都完成相同的任务。

以下是使用此升级替代方案的优缺点：

| 优势 | 缺点 |
|----------|---------|
| <ul><li>**提供在Experience Edge Network中托管数据的所有优势**： <p>这些优势包括：</p><ul><li>高性能报表和数据可用性，因为Adobe Experience Platform旨在支持[实时个性化用例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>在其他Adobe Experience Cloud产品(AJO、RTCDP等)之间整合Experience Cloud数据收集的实施</li><li>不依赖于Adobe Analytics命名法(属性、eVar、事件等)</li></ul><li>**使用当前数据层逻辑**：此方法使用当前数据层逻辑代替传统的Web SDK实施。 虽然此方法需要一些配置，但它不需要从头开始的全新实施，并且不需要填充数据元素或标记规则。 它允许您将数据从数据层映射到XDM，而不是从头开始填充XDM对象。</li></ul> | <ul><li>**需要映射才能将数据发送到Platform**：当您的组织准备好使用Customer Journey Analytics时，您必须将数据发送到Adobe Experience Platform中的数据集。 <p>由于此选项允许您将整个客户端数据层放入数据对象并将它发送到Adobe，这会导致大量数据被Adobe不容易解读。 要允许Adobe解释数据，您必须使用数据流映射将每个字段映射到所需的XDM字段。</p></li><li>**刚性实施**：实施受限于发送点击时数据层提供的内容。 对于具有基本数据需求的组织来说，这可能是可以接受的，但大多数组织都应当避免这种僵化的实施，而采用允许填充数据元素的更灵活的实施。</li><li>**未来的更改更难实施**：您以后添加到数据的任何字段都必须映射到数据流中的XDM。</li></ul> |

{style="table-layout:auto"}

## 基本步骤

将整个数据层发送到Customer Journey Analytics的基本步骤如下：

1. 将您的实施配置为在所需时间将数据发送到Adobe，并将JSON有效负载完全配置为您的数据层。

1. 将每个数据层元素映射到所需的XDM字段。

   任何未映射到XDM字段的数据层元素将被永久删除，因为Adobe不知道将数据存储在何处以及如何存储。



