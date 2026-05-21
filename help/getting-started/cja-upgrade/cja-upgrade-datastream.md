---
title: 为 Customer Journey Analytics 创建一个架构
description: 了解从 Adobe Analytics 升级到 Customer Journey Analytics 时的推荐路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
autotag-review: '2026-05-19T08:13:03.106Z'
TQID: 'https://experienceleague.adobe.com/vzavQGq0OyhXTpSkqe3nnXQEW0Nax9RXt4SwTRwa4UU'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 100%

---

# 创建与 Customer Journey Analytics 使用的数据流 {#upgrade-create-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-datastream-create"
>title="在 Adobe Experience Platform 中创建数据流"
>abstract="数据流是将您的数据传递到所有已配置的服务的中间位置。 在 Adobe Experience Platform 中创建此位置。<br><br>在 Platform 界面中首次创建数据流仅需几分钟。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

数据流表示实施 Adobe Experience Platform Web 和移动 SDK 时的服务器端配置。 使用 Adobe Experience Platform SDK 收集数据时，数据会发送到 Adobe Experience Platform Edge Network。 数据流决定将数据转发到哪些服务。

在您的设置中，您需要配置数据流，以便将收集到的数据发送到 Adobe Experience Platform 中的数据集。

>[!NOTE]
>
>以下步骤仅适用于使用 AppMeasurement 或 Analytics 扩展（标记）的 Adobe Analytics 实施。
>
>如果您的 Adobe Analytics 实施使用 Web SDK 或 Web SDK 扩展，则您的 Adobe Analytics 环境中已有数据流。

设置您的数据流

1. 在 Adobe Experience Platform 的左边栏中，选择[!UICONTROL 数据收藏集]中的&#x200B;**[!UICONTROL 数据流]**。

1. 选择&#x200B;**[!UICONTROL 新数据流]**。

1. 命名并描述您的数据流。 从 [!UICONTROL 事件架构] 列表中选择您的架构。

   ![新数据流](assets/new-datastream.png)

1. 选择&#x200B;**[!UICONTROL 保存]**。

{{upgrade-final-step}}
