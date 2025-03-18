---
title: 了解升级到 Customer Journey Analytics 的 Web SDK 实施选项
description: 了解升级到Customer Journey Analytics时的Web SDK实施选项
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 94a2bf2f-ad84-4f35-af8f-b8a5d9e5c607
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 54%

---

# 了解升级到 Customer Journey Analytics 的 Web SDK 实施选项 {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Web SDK JavaScript 库 (alloy.js)"
>abstract="在您网站的每个页面上包含 Web SDK 库 (alloy.js)。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Web SDK 标记扩展"
>abstract="（推荐）如果您尚未使用标记，请在您的网站上安装标记加载器。如果您已经使用标记，可以将 Web SDK 扩展添加到您的标记属性。此选项包括使用 Adobe Experience Platform 数据收集和第三方标记管理系统中的标记的实施。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="NPM 包"
>abstract="使用数据收集 API 将数据直接发送到数据流。支持非身份验证（客户端到服务器）和身份验证（服务器到服务器）两种类型。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-no-selection"
>title="为给定的属性实施 Web SDK"
>abstract="在升级指南中选择所需的实施类型，以了解更多详细说明。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-third-party"
>title="将 Web SDK 库添加到您的第三方标记管理系统"
>abstract="与您的标记管理系统管理员合作，将 Web SDK 库添加到您的网站中。<br><br>此任务的完成时间在很大程度上取决于负责标记管理系统的个人的响应能力。添加 Web SDK 库可能会与相关的实施逻辑捆绑在一起，并在组织的标准发布周期内部署。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

建议的从Adobe Analytics升级到Customer Journey Analytics的过程是Experience Platform Web SDK的新实施，它是Customer Journey Analytics的首选数据收集方法。

有三种受支持的方法可以使用Adobe Experience Platform Web SDK：

* [Web SDK标记扩展](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension)： Adobe建议使用此方法。 在网站上安装标记加载器，然后使用Adobe Experience Platform数据收集UI配置实施。

* [Web SDK JavaScript库](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library)：引用CDN托管的库文件，或使用您自己的基础架构托管库文件。 调用网站上代码中的库。

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm)：使用NPM包管理器在您的站点上安装Web SDK。

有关详细信息，请参阅《Experience Platform Web SDK指南》中的[Web SDK安装概述](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview)。
