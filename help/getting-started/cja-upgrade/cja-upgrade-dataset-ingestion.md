---
title: 升级到 Customer Journey Analytics 时监控数据集摄取
description: 了解如何在升级到 Customer Journey Analytics 时监控数据集摄取
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
TQID: https://experienceleague.adobe.com/1YL4BpmedZdyaoP7S-ZignAlucl9WsRrNBKjOO3p1TQ
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 224
ht-degree: 100%

---

# 升级到 Customer Journey Analytics 时监控数据集摄取 {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="验证数据集中的数据"
>abstract="现在您已经配置了实施，可以使用数据集活动管理器查看已摄取和失败的批次。 如果您主要看到的是已摄取的批次，那么这一步就完成了。 如果您主要看到的是失败的批次或没有批次，请检查您的实施，以确保它正确地将数据发送到 Adobe。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

在配置 Web SDK 或实施 API 后，您需要检查各个批次的状态，以验证数据是否已被摄取到数据集中。

1. 在 Experience Platform UI 中，选择左侧导航中的&#x200B;**[!UICONTROL 监控]**。

   监控仪表板会显示。 使用该仪表板可查看批量或流式摄取的入站数据的状态。

   <!-- insert screenshot -->

1. 选择&#x200B;**[!UICONTROL 批次端到端]**&#x200B;来查看批次列表。

   如果没有显示批次，请检查您的实施情况，以确保其正确地将数据发送到 Adobe。

   <!-- insert screenshot -->

1. 选择给定数据集的批次 ID，然后验证&#x200B;**[!UICONTROL 状态]**&#x200B;字段中是否显示&#x200B;**[!UICONTROL 成功]**。

   如果&#x200B;**[!UICONTROL 状态]**&#x200B;字段中显示&#x200B;**[!UICONTROL 失败]**，请检查您的实施情况，以确保其正确地将数据发送给 Adobe。

   重复此步骤以验证每个批次的状态。

{{upgrade-final-step}}

