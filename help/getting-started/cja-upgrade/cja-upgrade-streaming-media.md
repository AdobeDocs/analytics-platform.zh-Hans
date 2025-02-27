---
title: 为Customer Journey Analytics设置流媒体收集
description: 了解如何为Customer Journey Analytics设置流媒体收集
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 68ce73ddf805ec377fdb2c539683507f191c9249
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 2%

---

# 为Customer Journey Analytics设置流媒体收集 {#streaming-media-setup}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-media-edge"
>title="设置和实施Media Edge"
>abstract="您可以将Adobe流媒体收集配置为使用Experience Platform Edge在Customer Journey Analytics中提供数据。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

在Customer Journey Analytics中实施流媒体收集的步骤因您当前在Adobe Analytics中实施流媒体而异。

可通过以下任一方式在Adobe Analytics中实施流媒体收集：

* [适用于流媒体收集的Edge Network实施](#edge-network-implementations)

+++ 查看信息图

  ![Edge上的流媒体](assets/streaming-media-edge.png)

+++

* [适用于流媒体收集的仅限Adobe Analytics的实施](#adobe-analytics-only-implementations)

+++ 查看信息图

  ![仅限Analytics的实施](assets/analytics-implementation.png)

+++

有关这些实施方法之间的差异的更多信息，请参阅《流媒体收集指南》中的[实施流媒体收集](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview)。

## 适用于流媒体收集的Edge Network实施

如果在Adobe Analytics实施中使用Edge Network [实施了流媒体收集](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#edge-implementation-methods)，则意味着将流媒体收集升级到Customer Journey Analytics所需的一些步骤已经作为Adobe Analytics实施的一部分完成。 以下是已完成的步骤：

* [在Adobe Experience Platform中设置架构](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)

* [在Adobe Experience Platform中创建数据集](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#create-a-dataset-in-adobe-experience-platform)

* [在Adobe Experience Platform中配置数据流](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)

在升级到Customer Journey Analytics时，需要完成以下附加步骤：

>[!NOTE]
>
>完成Customer Journey Analytics升级步骤后，请确保使用来自Adobe Analytics中的流媒体收集实施的架构、数据集和数据流。

* [在 Customer Journey Analytics 中创建连接](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)

* [在 Customer Journey Analytics 中创建数据视图](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)


## 适用于流媒体收集的仅限Adobe Analytics的实施

如果在您的Adobe Analytics环境中](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/overview#adobe-analytics-only-implementation-methods)使用仅用于Adobe Analytics的实施来实施流媒体收集[，则意味着流媒体数据尚未发送到Edge Network。

在从Adobe Analytics升级到Customer Journey Analytics的过程中创建架构、数据集、数据流、连接和数据视图时，做出以下选择以考虑流媒体收集数据：

* 为Customer Journey Analytics创建架构时，请包含`MediaAnalytics Interaction Details`字段组。

  有关添加此字段组的详细信息，请参阅流媒体收集指南中的[在Adobe Experience Platform中设置架构](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#set-up-the-schema-in-adobe-experience-platform)。

  有关创建架构的信息，请参阅[创建自定义架构以用于Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

* 为Customer Journey Analytics配置数据流时，启用Media Analytics。

  有关启用此选项的详细信息，请参阅《流媒体收集指南》中的[在Adobe Experience Platform中配置数据流](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge#configure-a-datastream-in-adobe-experience-platform)。

  有关创建数据流的信息，请参阅[创建数据流以用于Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)。

* 为Customer Journey Analytics创建数据视图时，请包含流媒体收藏集的必需架构字段。

  确保将这些架构字段映射到XDM对象中的正确值。

  有关必填字段的更多信息，请参阅《流媒体收集指南》中的[在Customer Journey Analytics中创建数据视图](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)。

  有关创建数据视图的信息，请参阅[在Customer Journey Analytics中创建数据视图](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)。


