---
title: Customer Journey Analytics 的数据摄取选项
description: 了解将数据摄取到 Customer Journey Analytics 的不同方式
translation-type: ht
source-git-commit: 4ea06ca1f13255c570ccc9f69cb328d57bf975b2
workflow-type: ht
source-wordcount: '487'
ht-degree: 100%

---


# Customer Journey Analytics 的数据摄取选项

在将数据摄取到 Customer Journey Analytics 时，有多种选项供您选择。其中的有些选项假定您要转移传统 Adobe Analytics 的数据，而另一些选项则假定您直接从 Adobe Experience Platform 中摄取数据。本参考提供了要遵循的高级步骤以及指向更多详细信息的链接。

## 从传统 Adobe Analytics 中摄取数据

此工作流利用 Adobe Analytics Data Connector，会因您选择 DTM 还是 Launch 作为标签管理器而有所不同。

### 通过 Dynamic Tag Management (DTM)

1. [创建数据层](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/prepare/data-layer.html)（如果尚未创建）。数据层是网站上 JavaScript 对象的框架，其中包含实施中使用的所有变量值。它让您可以在实施中拥有更大的控制力且更便于维护。
1. 使用 [DTM](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/other/dtm/dtm-implementation-overview.html) 在您的站点上实施代码以收集数据（如果尚未实施）。Dynamic Tag Management 可提供一个用于从多个数据源提取数据的单一数据层。
1. 在 Adobe Experience Platform 中创建一个 [Adobe Analytics 源连接器](https://docs.adobe.com/content/help/zh-Hans/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)。该源连接器将会在名为[体验数据模型 (XDM) 系统](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/home.html)的标准化框架中，将 Analytics 数据摄取到 Experience Platform。
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/zh-Hans/analytics-platform/using/cja-overview/cja-getting-started.html) 创建一个或多将纳入您的跨渠道报表的连接和数据视图。

### 通过 Launch

1. [创建数据层](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/prepare/data-layer.html)（如果尚未创建）。数据层是网站上 JavaScript 对象的框架，其中包含实施中使用的所有变量值。它让您可以在实施中拥有更大的控制力且更便于维护。
1. 使用 [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/launch/overview.html) 在您的站点上实施代码以收集数据（如果尚未实施）。Launch 是一款标签管理解决方案，可让您在满足其他标记要求的同时部署 Analytics 代码。Launch 提供了与其他解决方案和产品的集成，并允许您部署自定义代码。无需依赖组织中的开发团队，也可以完成以下所有任务，进而更新网站上的代码。
1. 在 Adobe Experience Platform 中创建一个 [Adobe Analytics 源连接器](https://docs.adobe.com/content/help/zh-Hans/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)。该源连接器将会在名为[体验数据模型 (XDM) 系统](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/home.html)的标准化框架中，将 Analytics 数据摄取到 Experience Platform。
1. 使用 [Customer Journey Analytics](https://docs.adobe.com/content/help/zh-Hans/analytics-platform/using/cja-overview/cja-getting-started.html) 创建一个或多将纳入您的跨渠道报表的连接和数据视图。
