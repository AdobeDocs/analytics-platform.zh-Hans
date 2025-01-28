---
title: 从第三方分析解决方案升级到Customer Journey Analytics
description: 了解如何从第三方分析解决方案升级到Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: a462bdbff59e8d83d6948ef882e66690624c4847
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 8%

---

# 从第三方分析解决方案升级到Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="第三方分析产品"
>abstract="为第三方分析产品(如Google Analytics)收集数据的实施。 选择此选项将禁用调查表中的多个选项，当从第三方分析产品升级到Customer Journey Analytics时，这些选项不适用。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>在回答[Customer Journey Analytics升级核对清单](https://gigazelle.github.io/cja-ttv/)中的问题时，使用此页上的信息。

推荐的从第三方分析解决方案升级到Customer Journey Analytics的过程是Experience PlatformWeb SDK的新实施，该方法是Customer Journey Analytics的首选数据收集方法。 在与Web SDK结合使用时，Adobe还建议将历史数据从第三方分析解决方案摄取到Adobe Experience Platform中。

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

从第三方分析解决方案(如Google Analytics)转到Customer Journey Analytics时，请遵循以下过程：

1. ...


如果您需要更具体的建议、指导或支持，请联系您的Adobe代表。

| 现有的分析解决方案 | 描述 | 可用的升级路径 |
|---------|----------|----------|
| AppMeasurement | AppMeasurementJavaScript一直以来都是实施Adobe Analytics的常用方法。<p>有关此实现类型的更多信息，请参阅[为JavaScript实施AppMeasurement的Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)。</p> | <ul><li>[（推荐）用于持续数据收集的Experience PlatformWeb SDK的新实现；用于历史数据的Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience PlatformWeb SDK的新实现](/help/data-ingestion/aepwebsdk.md) </li><li>将Adobe Analytics迁移到Web SDK</li><li>[Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Adobe Analytics扩展（标记） | <p>Adobe Experience Platform 中的标记是一款标记管理解决方案，可让您在满足其他标记要求的同时部署 Analytics 代码。Adobe 提供了与其他解决方案和产品的集成，并允许您部署自定义代码。无需依赖组织中的开发团队，也可以完成以下所有任务，进而更新网站上的代码。</p><p>有关此实现类型的更多信息，请参阅[使用Adobe Analytics扩展实施Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)。</p> | <ul><li>[（推荐）用于持续数据收集的Experience PlatformWeb SDK的新实现；用于历史数据的Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience PlatformWeb SDK的新实现](/help/data-ingestion/aepwebsdk.md) </li><li>将Adobe Analytics迁移到Web SDK</li><li>[Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)</li></ul> |
| Experience PlatformWeb SDK (alloy.js) | Experience PlatformWeb SDK是Adobe当前推荐的实施Adobe Analytics的方法。 Adobe Experience PlatformEdge Network允许您将发送到多个产品的数据发送到一个集中的位置。 <p>有关此实现类型的详细信息，请参阅[使用Adobe Experience PlatformEdge Network实施Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)。</p> | <ul><li>[（推荐）用于持续数据收集的Experience PlatformWeb SDK的新实现；用于历史数据的Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience PlatformWeb SDK的新实现](/help/data-ingestion/aepwebsdk.md) </li><li>配置Adobe Analytics Web SDK实施以将数据发送到Platform</li></ul> |
| Experience PlatformWeb SDK扩展（标记） | Experience PlatformWeb SDK是Adobe当前推荐的为Web数据实施Adobe Analytics的方法。 Adobe Experience PlatformEdge Network允许您将发送到多个产品的数据发送到一个集中的位置。 <p>有关此实现类型的详细信息，请参阅[使用Adobe Experience Platform Web SDK实施Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[（推荐）用于持续数据收集的Experience PlatformWeb SDK的新实现；用于历史数据的Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience PlatformWeb SDK的新实现](/help/data-ingestion/aepwebsdk.md)</li><li>配置Adobe Analytics Web SDK实施以将数据发送到Platform</li></ul> |
| Experience Platform Mobile SDK | Experience PlatformMobile SDK是Adobe当前为移动数据实施Adobe Analytics推荐的方法。 Adobe Experience PlatformEdge Network允许您将发送到多个产品的数据发送到一个集中的位置。<p>Adobe Experience Platform Mobile SDK有助于在移动设备应用程序中支持Adobe的Experience Cloud解决方案和服务。 </p><p>有关此实现类型的更多信息，请参阅[使用Adobe Experience Platform Mobile SDK实施Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[（推荐）用于持续数据收集的Experience PlatformWeb SDK的新实现；用于历史数据的Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience PlatformWeb SDK的新实现](/help/data-ingestion/aepwebsdk.md) </li><li>配置Adobe Analytics Web SDK实施以将数据发送到Platform</li></ul> |
| 批量数据插入 API | 批量数据插入API (BDIA)是一种Adobe Analytics功能，允许您以文件的形式批量上传服务器调用数据，而不是使用客户端库(如AppMeasurement)。 </p><p>有关此实现类型的详细信息，请参阅[批量数据插入API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)。</p> | <ul><li>[（推荐）用于持续数据收集的Experience PlatformWeb SDK的新实现；用于历史数据的Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience PlatformWeb SDK的新实现](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Experience PlatformEdge Network服务器API和Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}