---
title: 为 Customer Journey Analytics 设置流媒体集合
description: 了解如何为Customer Journey Analytics设置流媒体收集
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b807099d-a61d-48f9-9fec-94ecc6b76213
source-git-commit: f7b06838bbe5b1a5e304c6d0da6d34635391a90b
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 20%

---

# 为 Customer Journey Analytics 设置流媒体集合 {#streaming-media-setup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-media-edge"
>title="设置并实施 Media Edge"
>abstract="如果您计划将流媒体集合与 Customer Journey Analytics 结合使用，则需要在升级过程的某些步骤中做出特定选择。例如，您需要将 MediaAnalytics 交互详情字段组添加到您的架构中，在数据流中启用 Media Analytics 等等。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

与Adobe Analytics中一样，流媒体收集可用于收集流媒体数据，以供在Customer Journey Analytics中使用。 如果将Streaming Media Collection与Adobe Analytics结合使用，则应当将其包含在Customer Journey Analytics的升级计划中。

在执行从Adobe Analytics升级到Customer Journey Analytics的步骤时，做出以下选择来考虑流媒体收集数据：

* 为Customer Journey Analytics创建架构时，请包含`MediaAnalytics Interaction Details`字段组。

  有关添加此字段组的详细信息，请参阅流媒体收集指南中的[在Adobe Experience Platform中设置架构](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)。

  有关创建架构的信息，请参阅[创建自定义架构以用于Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

* 为Customer Journey Analytics配置数据流时，启用Media Analytics。

  有关启用此选项的详细信息，请参阅《流媒体收集指南》中的[在Adobe Experience Platform中配置数据流](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)。

  有关创建数据流的信息，请参阅[创建数据流以用于Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)。

  >[!NOTE]
  >
  >如果您的Adobe Analytics实施已经在使用Experience Platform Web SDK，则无需执行此步骤。

* 为Customer Journey Analytics创建数据视图时，请包含流媒体收藏集的必需架构字段。

  确保将这些架构字段映射到XDM对象中的正确值。

  有关必填字段的更多信息，请参阅《流媒体收集指南》中的[在Customer Journey Analytics中创建数据视图](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)。

  有关创建数据视图的信息，请参阅[在Customer Journey Analytics中创建数据视图](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)。

<!--

------------------

The steps for implementing the Streaming Media Collection in Customer Journey Analytics differ depending on your current Streaming Media Collection implementation in Adobe Analytics. 

Streaming Media Collection can be implemented in Adobe Analytics in either of the following ways:

* [Edge Network implementations for the Streaming Media Collection](#edge-network-implementations)

* [Adobe Analytics-only implementations for the Streaming Media Collection](#adobe-analytics-only-implementations)

For more information about the differences between these implementation methods, see [Implement the Streaming Media Collection](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview) in the Streaming Media Collection Guide.

## Edge Network implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using the Edge Network in your Adobe Analytics implementation](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#edge-implementation-methods), this means that some steps that are required to upgrade the Streaming Media Collection to Customer Journey Analytics have already been completed as part of your Adobe Analytics implementation. Following are the completed steps:

* [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)

* [Create a dataset in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#create-a-dataset-in-adobe-experience-platform)

* [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)

The following additional steps need to be completed as part of the upgrade to Customer Journey Analytics:

>[!NOTE]
>
>As you complete the Customer Journey Analytics upgrade steps, make sure you use the schema, dataset, and datastream from your Streaming Media Collection implementation in Adobe Analytics.

* [Create a connection in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)

* [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)


## Adobe Analytics-only implementations for the Streaming Media Collection

If the Streaming Media Collection is [implemented using an Adobe Analytics-only implementation in your Adobe Analytics environment](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#adobe-analytics-only-implementation-methods), this means that Streaming Media data is not yet going to Edge Network. 

As you create the schema, dataset, datastream, connection, and data view as part of your upgrade from Adobe Analytics to Customer Journey Analytics, make the following selections to account for Streaming Media Collection data:

* When creating the schema for Customer Journey Analytics, include the `MediaAnalytics Interaction Details` field group.

  For more information about adding this field group, see [Set up the schema in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the schema, see [Create a custom schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

* When configuring the datastream for Customer Journey Analytics, enable Media Analytics. 

  For more information about enabling this option, see [Configure a datastream in Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform) in the Streaming Media Collection Guide.

  For information about creating the datastream, see [Create a datastream to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

* When creating a data view for Customer Journey Analytics, include the required schema fields for the Streaming Media Collection.

  Make sure you map these schema fieldds to the correct values in the XDM object.

  For more information about the required fields, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md) in the Streaming Media Collection Guide.

  For information about creating the data view, see [Create a data view in Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md).

  -->
