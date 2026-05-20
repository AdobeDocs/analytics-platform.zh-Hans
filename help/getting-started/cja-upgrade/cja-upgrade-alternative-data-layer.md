---
title: 升级到Customer Journey Analytics时的备用方法
description: 了解升级到Customer Journey Analytics时的替代方法
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 3a0d03d1-def0-45e6-8eb2-115b88497e6d
autotag-review: '2026-05-19T08:09:26.880Z'
TQID: 'https://experienceleague.adobe.com/IsYrCVRcY1cd2xSYV7A-iJ2jx8Ku-oZ-BtHu8If-55Y'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 696
ht-degree: 54%

---

# 升级替代方案：将数据层发送到 Customer Journey Analytics {#data-collection-data-layer}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer"
>title="将数据层发送到 Adobe"
>abstract="您可以通过数据对象将整个数据层发送到 Adobe，而不是通过 XDM 对象发送数据。<br><br>此选项允许您将数据层映射到 XDM，而不是从头开始填充 XDM 对象，从而节省实施时间。 不过，这种映射的工作量很大，因为会有大量数据 Adobe 无法轻易解释。 随着时间的推移，此选项还会带来更多的复杂性，因为您将来添加到数据中的任何字段都必须映射到数据流中的 XDM。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-send-data-layer"
>title="将您的数据层发送到 Adobe"
>abstract="配置实施以在所需时间将数据发送到 Adobe，并将 JSON 负载配置为完整的数据层。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer-map"
>title="将每个数据层元素分配给 XDM"
>abstract="将每个数据层元素映射到所需的 XDM 字段。 任何未映射到 XDM 字段的数据层元素都将被永久删除，因为 Adobe 不知道在哪里或如何存储该数据。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

当升级到 Customer Journey Analytics 时，Adobe [建议重新实施 Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。 但是，根据时间和资源限制等多种因素，推荐的升级步骤可能不适合您组织。

您可以将整个数据层发送到Customer Journey Analytics，而不是使用XDM对象收集数据。 但是，这种替代方法会随着时间的推移而增加复杂性。

## 优点和缺点

此方法与[在Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)中使用AppMeasurement数据收集逻辑是互斥的，因为这两种方法都完成相同的任务。

以下是使用此升级替代方案的优缺点：

| 优点 | 缺点 |
|----------|---------|
| <ul><li>**提供在 Experience Edge Network 中托管数据的所有优点**： <p>这些优点包括：</p><ul><li>Adobe Experience Platform 专为支持[实时个性化用例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)而构建，因此具有高性能报告和数据可用性</li><li>整合其他CX Enterprise产品（AJO、RTCDP等）之间的Adobe CX Enterprise数据收集实施</li><li>不依赖于 Adobe Analytics 命名法（属性、eVar、事件等）</li></ul><li>**使用当前数据层逻辑**：此方法使用当前数据层逻辑代替传统的Web SDK实施。 虽然此方法需要一些配置，但它不需要从头开始的全新实施，并且不需要填充数据元素或标记规则。 它允许您将数据从数据层映射到XDM，而不是从头开始填充XDM对象。</li></ul> | <ul><li>**需要映射才能将数据发送到 Platform**：当您的组织准备好使用 Customer Journey Analytics 时，您必须将数据发送到 Adobe Experience Platform 中的数据集。 <p>由于此选项允许您将整个客户端数据层放入数据对象并将它发送到Adobe，这会导致大量数据被Adobe不容易解读。 要允许Adobe解释数据，您必须使用数据流映射将每个字段映射到所需的XDM字段。</p></li><li>**刚性实施**：实施受限于发送点击时数据层提供的内容。 对于具有基本数据需求的组织来说，这可能是可以接受的，但大多数组织都应当避免这种僵化的实施，而采用允许填充数据元素的更灵活的实施。</li><li>**未来的更改更难实施**：您以后添加到数据的任何字段都必须映射到数据流中的XDM。</li></ul> |

{style="table-layout:auto"}

## 基本步骤

将整个数据层发送到Customer Journey Analytics的基本步骤如下：

1. 配置实施以在所需时间将数据发送到 Adobe，并将 JSON 负载配置为完整的数据层。

1. 将每个数据层元素映射到所需的 XDM 字段。

   任何未映射到 XDM 字段的数据层元素都将被永久删除，因为 Adobe 不知道在哪里或如何存储该数据。
