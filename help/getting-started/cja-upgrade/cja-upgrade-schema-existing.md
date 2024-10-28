---
title: 创建用于Customer Journey Analytics的架构
description: 了解从Adobe Analytics升级到Customer Journey Analytics时推荐的路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---

# 在Customer Journey Analytics中使用Adobe Analytics架构

>[!NOTE]
>
>此文档应该用作[Adobe AnalyticsCustomer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)的一部分。

<!-- this page exists as the "Learn more" link in the info icon for the option "I am comfortable using my Adobe Analytics schema as a basis" -->

只有使用Adobe Analytics Web SDK配置了Adobe Analytics实施时，用于将Customer Journey Analytics应用于现有Adobe Experience Platform架构的选项才可用。<!-- correct? Or can you do this with an AppMeasurement implementation?-->

考虑将Adobe Analytics架构与Customer Journey Analytics结合使用的以下优缺点：

| 优势 | 缺点 |
|----------|---------|
| <p>使用Adobe Analytics架构的优势包括：</p><ul><li>易于升级<p>如果您已使用Adobe Experience Platform Web SDK将数据发送到Adobe Analytics，则可以将其他服务添加到您的数据流以将数据发送到Adobe Experience Platform(然后可以在您的Customer Journey Analytics配置中使用)。</p></li></ul> | <p>使用Adobe Analytics架构的缺点包括：</p><ul><li>虽然使用Adobe Analytics架构不会限制您如何将其与其他Platform应用程序一起使用，但它的确会导致架构比不使用该架构时复杂得多。 这是因为Adobe Analytics架构包含许多特定于Adobe Analytics的对象，您的组织不太可能使用这些对象。<p>当需要对架构进行更改时，您必须筛选成千上万个未使用的字段以查找需要更新的字段。</p></li></ul> |

<!-- Not sure about any of this: 

If you plan to use your Adobe Analytics schema, the following steps are required:

For Adobe Analytics implementations using AppMeasurement:

1. Datastream mapping

For Adobe Analytics implementations using the Web SDK:

1. 



the upgrade steps provided by the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).

If you want to create an XDM schema to use with Customer Journey Analytics, continue with [Create an XDM schema to use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).


Tags: (All 3 require data prep mapping. Would need to go into the datastream and map every single field to its appropriate place in XDM. Because whenever you use the data object, it always requires mapping. If you send something in the data object and it doesn't get mapped, the it is permanently lost and can't be recovered.)

1. Shim - Intercepts and instead of sending data to a report suite, it sends it to a Data View. (Data object)

1. Russ special - convert current implementation to a Web SDK implementation - put everything in the data object. 

1. Plop entire data layer into the data object and send that to the datastream. (not documented. Might be the Web SDK docs.)

-->