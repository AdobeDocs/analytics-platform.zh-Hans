---
title: 了解您的Adobe Analytics实施以及它如何影响您升级到Customer Journey Analytics
description: 了解从Adobe Analytics升级到Customer Journey Analytics时推荐的路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: aedf7a2ad41b09521938b789dbaf1c193cdb661f
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 9%

---

# 了解您的Adobe Analytics实施以及它如何影响您升级到Customer Journey Analytics

>[!NOTE]
> 
>只有在完成所有先前的升级步骤后，才应执行本页上的步骤。 您可以按照[推荐的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)进行操作，也可以按照[Adobe Analytics为您的组织动态生成的升级步骤来Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。
>
>完成此页面上的步骤后，请继续执行建议的升级步骤或动态生成的升级步骤。

有多种升级到Customer Journey Analytics的方法，但并非所有升级路径都适用于每种类型的Adobe Analytics实施。 但是，无论Adobe Analytics在您的组织中如何实施，建议的升级路径都可用。

请通过以下信息帮助您了解当前的Adobe Analytics实施以及贵组织可用的升级路径。

如果您需要更具体的建议、指导或支持，请联系您的Adobe代表。

| 现有Adobe Analytics实施 | 描述 | 可用的升级路径 |
|---------|----------|----------|
| AppMeasurement | AppMeasurementJavaScript一直以来都是实施Adobe Analytics的常用方法。<p>有关此实现类型的更多信息，请参阅[为JavaScript实施AppMeasurement的Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)</p> | <ul><li>（推荐）使用Analytics Source Connector实现Experience PlatformWeb SDK的新实施</li><li>Experience PlatformWeb SDK的新实施</li><li>将Adobe Analytics迁移到Web SDK</li><li>Analytics Source Connector</li></ul> |
| Adobe Analytics扩展（标记） | <p>Adobe Experience Platform 中的标记是一款标记管理解决方案，可让您在满足其他标记要求的同时部署 Analytics 代码。Adobe 提供了与其他解决方案和产品的集成，并允许您部署自定义代码。无需依赖组织中的开发团队，也可以完成以下所有任务，进而更新网站上的代码。</p><p>有关此实现类型的更多信息，请参阅[使用Adobe Analytics扩展实施Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)</p> | <ul><li>（推荐）使用Analytics Source Connector实现Experience PlatformWeb SDK的新实施</li><li>Experience PlatformWeb SDK的新实施</li><li>将Adobe Analytics迁移到Web SDK</li><li>Analytics Source Connector</li></ul> |
| Experience PlatformWeb SDK (alloy.js) | Experience PlatformWeb SDK是Adobe当前推荐的实施Adobe Analytics的方法。 Adobe Experience PlatformEdge Network允许您将发送到多个产品的数据发送到一个集中的位置。 <p>有关此实现类型的更多信息，请参阅[使用Adobe Experience PlatformEdge Network实施Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>（推荐）使用Analytics Source Connector实现Experience PlatformWeb SDK的新实施</li><li>配置Adobe Analytics Web SDK实施以将数据发送到Platform</li></ul> |
| Experience PlatformWeb SDK扩展（标记） | Experience PlatformWeb SDK是Adobe当前推荐的为Web数据实施Adobe Analytics的方法。 Adobe Experience PlatformEdge Network允许您将发送到多个产品的数据发送到一个集中的位置。 <p>有关此实现类型的更多信息，请参阅[使用Adobe Experience Platform Web SDK实施Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>（推荐）使用Analytics Source Connector实现Experience PlatformWeb SDK的新实施</li><li>配置Adobe Analytics Web SDK实施以将数据发送到Platform</li></ul> |
| Experience Platform Mobile SDK | Experience Platform移动SDK是Adobe当前为移动数据实施Adobe Analytics推荐的方法。 Adobe Experience PlatformEdge Network允许您将发送到多个产品的数据发送到一个集中的位置。<p>Adobe Experience Platform Mobile SDK有助于在移动设备应用程序中支持Adobe的Experience Cloud解决方案和服务。 </p><p>有关此实施类型的更多信息，请参阅[使用Adobe Experience Platform Mobile SDK实施Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>（推荐）使用Analytics Source Connector实现Experience PlatformWeb SDK的新实施</li><li>配置Adobe Analytics Web SDK实施以将数据发送到Platform</li></ul> |

{style="table-layout:auto"}
