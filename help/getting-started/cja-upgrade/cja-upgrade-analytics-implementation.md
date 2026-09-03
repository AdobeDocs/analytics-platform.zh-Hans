---
title: 了解您的 Adobe Analytics 实施情况及其对升级到 Customer Journey Analytics 的影响
description: 了解从 Adobe Analytics 升级到 Customer Journey Analytics 时的推荐路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
autotag-review: '2026-05-19T08:10:04.372Z'
TQID: 'https://experienceleague.adobe.com/DYm1jOVvaGGgUpz51TEXYPNyqvJdMMY-clhvSEiEEyw'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5eid: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 994
ht-degree: 98%

---

# 了解您的 Adobe Analytics 实施情况及其对升级到 Customer Journey Analytics 的影响 {#implementation-affects-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement"
>title="AppMeasurement（手动 JS 文件）"
>abstract="JavaScript 实施，在页面上加载 AppMeasurement.js，并使用 s 对象（例如，s.eVar1）向 Adobe 发送数据。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-analyticsextension"
>title="Adobe Analytics 扩展（标记）"
>abstract="标记实施，加载 Adobe Experience Platform 数据收集（以前称为 Launch）。 标记已安装 Adobe Analytics 扩展。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk"
>title="Web SDK（alloy.js）"
>abstract="JavaScript 实施，在页面上加载 Web SDK 库（alloy.js），并使用 JSON 负载向 Adobe 发送数据。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdkextension"
>title="Web SDK 扩展（标记）"
>abstract="标记实施，加载 Adobe Experience Platform 数据收集（以前称为 Launch）。 标记已安装 Web SDK 扩展。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-api"
>title="数据插入 API"
>abstract="使用数据插入 API 或批次数据插入 API 的实施。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-mobilesdk"
>title="Mobile SDK"
>abstract="使用 Adobe Experience Platform Mobile SDK 的实施。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-third-party"
>title="使用第三方标记管理工具的 AppMeasurement"
>abstract="使用第三方标记管理工具的实施。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-unknown"
>title="未知实施"
>abstract="如果您不是管理实施的人员，可以暂时选择此选项。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-determine-implementation"
>title="确定现有的实施类型"
>abstract="在您的组织内部开展工作，确定您当前使用哪种类型的实施来将数据发送到 Adobe Analytics。 当您升级到 Customer Journey Analytics 时，请与了解此信息的个人或团队合作。<br><br>确定您的组织所使用的实施类型后，修改 Customer Journey Analytics 升级指南中的答案。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Adobe Analytics 可以通过多种方式实施。 升级到 Customer Journey Analytics 时，并非所有升级路径都适用于所有 Adobe Analytics 实施。 但是，无论您的组织如何实施 Adobe Analytics，都可以使用推荐的升级路径。

使用以下信息了解您当前的 Adobe Analytics 实施，以及您的组织可用的升级途径。

如果您需要更具体的建议、指导或支持，请联系您的 Adobe 代表。

| 现有的 Adobe Analytics 实施 | 描述 | 可用的升级路径 |
|---------|----------|----------|
| AppMeasurement | AppMeasurement for JavaScript 一直以来都是实施 Adobe Analytics 的常用方法。<p>有关此实施类型的详细信息，请参阅[使用 AppMeasurement for JavaScript 实施 Adobe Analytics](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/js/overview)。</p> | <ul><li>[（推荐）对 Experience Platform Web SDK 进行新的实施，以持续收集数据；使用 Analytics 源连接器收集历史数据](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK 的新实施 ](/help/data-ingestion/aepwebsdk.md) </li><li>[将 Adobe Analytics 迁移到 Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Analytics 源连接器](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Adobe Analytics 扩展（标记） | <p>Adobe Experience Platform 中的 Tags 是一种标记管理解决方案，可让您在满足其他标记要求的同时部署 Analytics 代码。 Adobe 提供了与其他解决方案和产品的集成，并允许您部署自定义代码。 所有这些任务都可以在不依赖组织中的任何开发团队更新您网站上的代码的情况下完成。</p><p>有关此实施类型的详细信息，请参阅[使用 Analytics 扩展实施 Adobe Analytics](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/launch/overview)。</p> | <ul><li>[（推荐）对 Experience Platform Web SDK 进行新的实施，以持续收集数据；使用 Analytics 源连接器收集历史数据](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK 的新实施 ](/help/data-ingestion/aepwebsdk.md) </li><li>[将 Adobe Analytics 迁移到 Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[Analytics 源连接器](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li></ul> |
| Experience Platform Web SDK (alloy.js) | Experience Platform Web SDK 是 Adobe 目前推荐的实施 Adobe Analytics 的方法。 Adobe Experience Platform Edge Network 允许您将发送到多个产品的数据发送到一个集中的位置。 <p>有关该实施类型的更多信息，请参阅[使用 Adobe Experience Platform Edge Network 实施 Adobe Analytics](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/aep-edge/overview)。</p> | <ul><li>[（推荐）对 Experience Platform Web SDK 进行新的实施，以持续收集数据；使用 Analytics 源连接器收集历史数据](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK 的新实施 ](/help/data-ingestion/aepwebsdk.md) </li><li>[配置 Adobe Analytics Web SDK 实施，以将数据发送到 Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Experience Platform Web SDK 扩展（标记） | Experience Platform Web SDK 是 Adobe 目前推荐的针对 Web 数据实施 Adobe Analytics 的方法。 Adobe Experience Platform Edge Network 允许您将发送到多个产品的数据发送到一个集中的位置。 <p>有关此实施类型的详细信息，请参阅[使用 Adobe Experience Platform Web SDK 实施 Adobe Analytics](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>[（推荐）对 Experience Platform Web SDK 进行新的实施，以持续收集数据；使用 Analytics 源连接器收集历史数据](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK 的新实施 ](/help/data-ingestion/aepwebsdk.md)</li><li>[配置 Adobe Analytics Web SDK 实施，以将数据发送到 Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| Experience Platform Mobile SDK | Experience Platform Mobile SDK 是 Adobe 目前推荐的针对 Mobile 数据实施 Adobe Analytics 的方法。 Adobe Experience Platform Edge Network 允许您将发送到多个产品的数据发送到一个集中的位置。<p>Adobe Experience Platform Mobile SDK有助于在您的移动应用程序中支持Adobe的CX企业解决方案和服务。 </p><p>有关此实施类型的详细信息，请参阅[使用 Adobe Experience Platform Mobile SDK 实施 Adobe Analytics](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>[（推荐）对 Experience Platform Web SDK 进行新的实施，以持续收集数据；使用 Analytics 源连接器收集历史数据](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK 的新实施 ](/help/data-ingestion/aepwebsdk.md) </li><li>[配置 Adobe Analytics Web SDK 实施，以将数据发送到 Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)</li></ul> |
| 批量数据插入 API | 批量数据插入 API（BDIA）是一种 Adobe Analytics 功能，允许您以文件的形式批量上传服务器调用数据，而不是使用客户端库（如 AppMeasurement）。 </p><p>有关此实施类型的详细信息，请参阅[批量数据插入 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/)。</p> | <ul><li>[（推荐）对 Experience Platform Web SDK 进行新的实施，以持续收集数据；使用 Analytics 源连接器收集历史数据](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</li><li>[Experience Platform Web SDK 的新实施 ](/help/data-ingestion/aepwebsdk.md)</li><li>[Adobe Experience Platform Edge Network 服务器 API 和 Edge Network](/help/data-ingestion/serverapi.md)</li></ul> |

{style="table-layout:auto"}


