---
title: 创建标记属性并添加 Web SDK 扩展
description: 了解如何创建标记属性并添加 Web SDK 扩展
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 156df830-541d-4c92-9c49-98f346e040a7
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 100%

---

# 为您的属性创建标记 {#upgrade-tag-property}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-property"
>title="在 Adobe Experience Platform Data Collection 中创建一个标记属性。"
>abstract="使用标记是数据收集的典型标准。在 Adobe Experience Platform 界面中创建标记，您就可以随时更新数据收集变量。<br><br>只需点击几次即可创建标记属性，仅需几分钟。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

您可以使用 Adobe Experience Platform 中的“标记”功能在您的网站上实施代码，以收集数据。这一款标记管理解决方案，可让您在满足其他标记要求的同时部署代码。标签使用 Adobe Experience Platform Web SDK 扩展提供与 Adobe Experience Platform 的无缝集成。

以下信息描述了如何为您的属性创建标记。有关补充信息，请参阅 Experience Platform 文档中的[配置 Web SDK 标记扩展](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)。Web SDK 本身包含 [!UICONTROL Adobe Experience Cloud ID 服务]，因此您无需将 ID 服务扩展添加到标记中。

属性基本上是一个容器，在将标记部署到网站时可在其中填充扩展、规则、数据元素和库。很多人会为希望在其中部署同一组标记的每个网站（或一组密切相关的网站）创建一个属性。有关属性的更多信息，请参阅 Experience Platform 数据收集文档中的[属性](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/admin/companies-and-properties)。

若要为您的属性创建标记：

1. 使用您的 Adobe ID 凭据登录 experience.adobe.com。

1. 在 Adobe Experience Platform 中，前往&#x200B;**[!UICONTROL 数据收集]** > **[!UICONTROL 标记]**。

1. 选择&#x200B;**[!UICONTROL 新属性]**。

   为标签命名，选择 **[!UICONTROL Web]** 并输入域名。选择&#x200B;**[!UICONTROL 保存]**&#x200B;继续。

   ![创建资产](assets/create-property.png)

{{upgrade-final-step}}
