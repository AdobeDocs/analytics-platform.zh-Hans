---
title: 创建标记属性并添加 Web SDK 扩展
description: 了解如何创建标记属性并添加 Web SDK 扩展
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 100%

---

# 将 Web SDK 扩展添加到您的标记中 {#upgrade-tag-extension}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-extension"
>title="将 Platform Web SDK 扩展添加到您的标记属性"
>abstract="将 Adobe Experience Platform Web SDK 扩展添加到您的标记属性。将 Web SDK 扩展添加到您的标记属性的过程非常简单，只需几分钟即可完成。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

您可以使用 Adobe Experience Platform 中的“标记”功能在您的网站上实施代码，以收集数据。这一款标记管理解决方案，可让您在满足其他标记要求的同时部署代码。标签使用 Adobe Experience Platform Web SDK 扩展提供与 Adobe Experience Platform 的无缝集成。

以下信息描述了如何将 Web SDK 扩展添加到您的标记中。有关补充信息，请参阅 Experience Platform 文档中的[配置 Web SDK 标记扩展](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)。Web SDK 本身包含 [!UICONTROL Adobe Experience Cloud ID 服务]，因此您无需将 ID 服务扩展添加到标记中。

[创建标记](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)后，您必须使用 Adobe Experience Platform Web SDK 扩展对其进行配置。这可确保您可以将数据发送到 Adobe Experience Platform（通过您的数据流）。

要将 Web SDK 扩展添加到您的标记中：

1. 使用您的 Adobe ID 凭据登录 experience.adobe.com。

1. 在 Adobe Experience Platform 中，前往&#x200B;**[!UICONTROL 数据收集]** > **[!UICONTROL 标记]**。

1. 从 [!UICONTROL 标签属性] 列表中选择您新创建的标签以将其打开。

1. 选择左边栏中的&#x200B;**[!UICONTROL 扩展]**。

1. 在顶部栏中选择 **[!UICONTROL 目录]**。

1. 搜索或滚动到 **[!UICONTROL Adobe Experience Platform Web SDK 扩展]**，然后选择&#x200B;**[!UICONTROL 安装]**&#x200B;进行安装。

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. 选择您的沙盒和您之前为您的[!UICONTROL 生产环境]和（可选）[!UICONTROL 暂存环境]和[!UICONTROL 创建的数据流开发环境]。

   ![AEP Web SDK 扩展配置](assets/aepwebsk-extension-datastreams.png)

1. 选择&#x200B;**[!UICONTROL 保存]**。

{{upgrade-final-step}}
