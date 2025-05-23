---
title: 为 Web SDK 扩展实施加载器标记
description: 了解如何为 Web SDK 扩展实施加载器标记
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '283'
ht-degree: 100%

---

# 为 Web SDK 扩展实施加载器标记 {#upgrade-tag-loader}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-loader"
>title="在您的网站上实施加载器标记"
>abstract="与您的网站开发团队一起在您网站的每个页面上安装加载器标记。<br><br>此任务的完成时间在很大程度上取决于与您合作部署代码的工程团队的响应时间。一些具有高度适应性的工程团队的组织可以在几天内完成这一步骤，而拥有大量积压任务的工程团队可能需要一个月甚至更长时间。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

您必须在您想要跟踪的网站上安装您的标记，这意味着将代码放在您网站模板的标题标记中。

以下过程描述了如何获取引用您的标记的代码。有关补充信息，请参阅 Experience Platform 文档中的[标记和事件转发实施指南](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/get-started/implementation-guides)。

要获取引用标记的代码，请执行以下操作：

1. 使用您的 Adobe ID 凭据登录 experience.adobe.com。

1. 在 Adobe Experience Platform 中，前往&#x200B;**[!UICONTROL 数据收集]** > **[!UICONTROL 标记]**。

1. 在&#x200B;**[!UICONTROL 标记属性]**&#x200B;页面上，从属性列表中选择您新创建的标记，以将其打开。

1. 选择左边栏中的&#x200B;**[!UICONTROL 环境]**。

1. 从环境列表中，选择正确的安装（框）按钮。

   在 [!UICONTROL Web 安装说明]对话框中，选择脚本代码旁边的复制按钮，其内容如下：

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![环境](assets/environment.png)

1. 选择&#x200B;**[!UICONTROL 关闭]**。

   您可以根据部署 Adobe Experience Platform Web SDK 的位置选择另一个环境（暂存、生产），而不是开发环境的代码。

   有关详细信息，请参阅 [环境](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=zh-Hans&)。

{{upgrade-final-step}}
