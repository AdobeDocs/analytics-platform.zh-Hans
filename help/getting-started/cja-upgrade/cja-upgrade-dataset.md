---
title: 为 Customer Journey Analytics 创建一个架构
description: 了解从 Adobe Analytics 升级到 Customer Journey Analytics 时的推荐路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
autotag-review: '2026-05-19T08:12:18.647Z'
TQID: 'https://experienceleague.adobe.com/ti9UiQzAa9wBCCH-44dmUxTzojuh5ZHu9YJ9HNC8OHI'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d00e9f03-e50b-4162-b143-0c0817c937c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 100%

---

# 创建与 Customer Journey Analytics 使用的数据集 {#upgrade-create-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-create"
>title="在 Adobe Experience Platform 中创建数据集"
>abstract="数据集是已收集数据所在的位置。 在 Adobe Experience Platform 中创建此位置。<br><br>基于既定架构创建数据集仅需几分钟。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

数据集是用于存储和管理您在 Adobe Experience Platform 中收集的数据的结构。

要创建数据集：

1. 在 Adobe Experience Platform 的左边栏中，选择[!UICONTROL 数据管理]中的&#x200B;**[!UICONTROL 数据集]**。

1. 选择&#x200B;**[!UICONTROL 创建数据集]**。

   ![创建数据集](assets/create-dataset.png)

1. 选择&#x200B;**[!UICONTROL 使用架构创建数据集]**。

   ![使用架构创建数据集](assets/create-dataset-from-schema.png)。

1. 选择您之前创建的架构，然后选择 **[!UICONTROL 下一个]**。

1. 为您的数据集命名并（可选）提供描述。

   ![数据集名称](assets/name-your-datatest.png)

1. 选择&#x200B;**[!UICONTROL 完成]**。

1. 选择&#x200B;**[!UICONTROL 轮廓]**&#x200B;开关

   系统会提示您启用轮廓的数据集。 启用后，数据集会使用其摄取的数据丰富实时客户轮廓。

   >[!IMPORTANT]
   >
   >    只有当数据集所依附的架构也为轮廓启用时，您才能为轮廓启用数据集。

   ![为轮廓启用架构](assets/aepwebsdk-dataset-profile.png)

   有关如何查看、预览、创建和删除数据集的更多信息，请参阅[数据集 UI 指南](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html)。 您还可以了解如何为实时客户轮廓启用数据集。

{{upgrade-final-step}}
