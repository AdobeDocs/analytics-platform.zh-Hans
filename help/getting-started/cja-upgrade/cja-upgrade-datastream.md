---
title: 为 Customer Journey Analytics 创建一个架构
description: 了解从 Adobe Analytics 升级到 Customer Journey Analytics 时的推荐路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '221'
ht-degree: 100%

---

# 创建与 Customer Journey Analytics 使用的数据流 {#upgrade-create-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-datastream-create"
>title="在 Adobe Experience Platform 中创建数据流"
>abstract="数据流是将您的数据传递到所有已配置的服务的中间位置。在 Adobe Experience Platform 中创建此位置。<br><br>在 Platform 界面中初次创建数据流只需几分钟。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

数据流表示实施 Adobe Experience Platform Web 和移动 SDK 时的服务器端配置。使用 Adobe Experience Platform SDK 收集数据时，数据会发送到 Adobe Experience Platform Edge Network。数据流决定将数据转发到哪些服务。

在您的设置中，您需要配置数据流，以便将收集到的数据发送到 Adobe Experience Platform 中的数据集。

>[!NOTE]
>
>以下步骤仅适用于使用 AppMeasurement 或 Analytics 扩展（标记）的 Adobe Analytics 实施。
>
>如果您的 Adobe Analytics 实施使用 Web SDK 或 Web SDK 扩展，则您的 Adobe Analytics 环境中已有数据流。

设置您的数据流

1. 在 Adobe Experience Platform 的左边栏中，选择[!UICONTROL 数据收藏集]中的&#x200B;**[!UICONTROL 数据流]**。

1. 选择&#x200B;**[!UICONTROL 新数据流]**。

1. 命名并描述您的数据流。从 [!UICONTROL 事件架构] 列表中选择您的架构。

   ![新数据流](assets/new-datastream.png)

1. 选择&#x200B;**[!UICONTROL 保存]**。

{{upgrade-final-step}}
