---
title: 了解升级到 Customer Journey Analytics 的 Web SDK 实施选项
description: 了解升级到 Customer Journey Analytics 的 Web SDK 实施选项
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 94a2bf2f-ad84-4f35-af8f-b8a5d9e5c607
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '350'
ht-degree: 100%

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
>abstract="在升级指南中选择所需的实施类型，以获取更详细的说明。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-third-party"
>title="将 Web SDK 库添加到您的第三方标记管理系统"
>abstract="与您的标记管理系统管理员合作，将 Web SDK 库添加到您的网站中。<br><br>此任务的完成时间在很大程度上取决于负责标记管理系统的个人的响应能力。添加 Web SDK 库可能会与相关的实施逻辑捆绑在一起，并在组织的标准发布周期内部署。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

从 Adobe Analytics 升级到 Customer Journey Analytics 的推荐流程是对 Experience Platform Web SDK 进行新的实施，这是 Customer Journey Analytics 的首选数据收集方法。

使用 Adobe Experience Platform Web SDK 有三种受支持的方式：

* [Web SDK 标记扩展](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/web-sdk/install/extension)：Adobe 建议使用此方法。在您的网站上安装一个标记加载器，然后使用 Adobe Experience Platform 数据收集 UI 来配置您的实施。

* [Web SDK JavaScript 库](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/web-sdk/install/library)：引用 CDN 托管的库文件，或者使用您自己的基础架构托管库文件。在您网站的代码内调用该库。

* [NPM](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/web-sdk/install/npm)：使用 NPM 包管理器在您的网站上安装 Web SDK。

有关详细信息，请参阅 Experience Platform Web SDK 指南中的 [Web SDK 安装概述](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/web-sdk/install/overview)。
