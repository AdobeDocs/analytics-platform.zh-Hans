---
title: 为 Web SDK 扩展实施加载器标记
description: 了解如何为 Web SDK 扩展实施加载器标记
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
autotag-review: '2026-05-19T08:19:22.813Z'
TQID: 'https://experienceleague.adobe.com/OYEIDQvTVX2GFMKWvCGuKqoyZcvWbcsnGSQwM-tsYl0'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 301
ht-degree: 100%

---

# 为 Web SDK 扩展实施加载器标记 {#upgrade-tag-loader}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-loader"
>title="在您的网站上实施加载器标记"
>abstract="与您的网站开发团队一起在您网站的每个页面上安装加载器标记。<br><br>此任务的完成时间在很大程度上取决于与您合作部署代码的工程团队的响应时间。 一些具有高度适应性的工程团队的组织可以在几天内完成这一步骤，而拥有大量积压任务的工程团队可能需要一个月甚至更长时间。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

您必须在您想要跟踪的网站上安装您的标记，这意味着将代码放在您网站模板的标头标记中。

以下过程描述了如何获取引用您的标记的代码。 有关补充信息，请参阅 Experience Platform 文档中的[标记和事件转发实施指南](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/get-started/implementation-guides)。

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

   您可以根据自己在部署 Adobe Experience Platform Web SDK 过程中的阶段，选择另一个环境（暂存、生产），而不是开发环境的代码。

   有关详细信息，请参阅 [环境](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?)。

{{upgrade-final-step}}
