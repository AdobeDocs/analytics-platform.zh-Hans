---
title: 创建用于Customer Journey Analytics的架构
description: 了解从Adobe Analytics升级到Customer Journey Analytics时推荐的路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 29%

---

# 创建要用于Customer Journey Analytics的数据集 {#upgrade-create-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-create"
>title="在Adobe Experience Platform中创建数据集"
>abstract="数据集是收集的数据所在的位置。 在Adobe Experience Platform中创建此位置。<br><br>创建包含架构的数据集只需要几分钟。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>只有在完成所有先前的升级步骤后，才应执行本页上的步骤。 您可以按照[推荐的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)进行操作，也可以按照[Adobe Analytics为您的组织动态生成的升级步骤来Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。
>
>完成此页面上的步骤后，请继续执行建议的升级步骤或动态生成的升级步骤。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

数据集是用于存储和管理收集到Adobe Experience Platform中的数据的结构。

要创建数据集，请执行以下操作：

1. 在Adobe Experience Platform的左边栏中，选择[!UICONTROL 数据管理]中的&#x200B;**[!UICONTROL 数据集]**。

1. 选择&#x200B;**[!UICONTROL 创建数据集]**。

   ![创建数据集](assets/create-dataset.png)

1. 选择&#x200B;**[!UICONTROL 使用架构创建数据集]**。

   ![使用架构创建数据集](assets/create-dataset-from-schema.png)。

1. 选择您之前创建的架构，然后选择 **[!UICONTROL 下一个]**。

1. 为您的数据集命名并（可选）提供描述。

   ![数据集名称](assets/name-your-datatest.png)

1. 选择&#x200B;**[!UICONTROL 完成]**。

1. 选择&#x200B;**[!UICONTROL 轮廓]**&#x200B;开关

   系统会提示您启用轮廓的数据集。启用后，数据集会使用其摄取的数据丰富实时客户轮廓。

   >[!IMPORTANT]
   >
   >    只有当数据集所依附的架构也为轮廓启用时，您才能为轮廓启用数据集。

   ![为轮廓启用架构](assets/aepwebsdk-dataset-profile.png)

   有关如何查看、预览、创建和删除数据集的详细信息，请参阅[数据集UI指南](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=zh-Hans)。 您还可以了解如何为Real-time Customer Profile启用数据集。

1. 继续执行[建议的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[动态生成的升级步骤](https://gigazelle.github.io/cja-ttv/)。
