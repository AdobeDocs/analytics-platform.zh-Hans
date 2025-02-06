---
title: 了解升级到Customer Journey Analytics时的Web SDK实施选项
description: 了解升级到Customer Journey Analytics时的Web SDK实施选项
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# 了解升级到Customer Journey Analytics时的Web SDK实施选项 {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Web SDK JavaScript库(alloy.js)"
>abstract="在网站的每个页面上包含Web SDK库(alloy.js)。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Web SDK标记扩展"
>abstract="（推荐）如果尚未使用标记，请在网站上安装标记加载器。 如果您已在使用标记，则可以将Web SDK扩展添加到标记属性中。 此选项包括使用Adobe Experience Platform数据收集和第三方标记管理系统中的标记的实施。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="NPM包"
>abstract="使用数据收集API将数据直接发送到数据流。 同时支持未经身份验证的（客户端到服务器）和经过身份验证的（服务器到服务器）类型。"

<!-- markdownlint-enable MD034 -->

建议的从Adobe Analytics升级到Customer Journey Analytics的过程是Experience PlatformWeb SDK的新实施，该方法是Customer Journey Analytics的首选数据收集方法。

有三种受支持的方法可以使用Adobe Experience Platform Web SDK：

* [Web SDK标记扩展](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension)：Adobe建议使用此方法。 在网站上安装标记加载器，然后使用Adobe Experience Platform数据收集UI配置实施。

* [Web SDK JavaScript库](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library)：引用CDN托管的库文件，或使用您自己的基础架构托管库文件。 调用网站上代码中的库。

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm)：使用NPM包管理器在您的站点上安装Web SDK。

有关详细信息，请参阅Experience PlatformWeb SDK指南中的[Web SDK安装概述](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview)。



