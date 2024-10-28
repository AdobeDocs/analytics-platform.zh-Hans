---
title: 创建用于Customer Journey Analytics的架构
description: 了解从Adobe Analytics升级到Customer Journey Analytics时推荐的路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 30%

---

# 创建要用于Customer Journey Analytics的数据集

>[!NOTE]
>
>在完成[Adobe Analytics以Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)之后，应使用此文档。
> 
>只有在完成之前为您的组织动态生成的所有步骤后，才应执行此页面上的步骤。
>
>完成此页面上的步骤后，继续执行从[Adobe Analytics为您的组织动态生成的升级步骤，以Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

创建XDM架构后，现在必须定义构建来存储和管理该数据，此操作通过数据集在Adobe Experience Platform中完成。

要创建数据集，请执行以下操作：

1. 在Adobe Experience Platform的左边栏中，选择[!UICONTROL 数据管理]中的&#x200B;**[!UICONTROL 数据集]**。

1. 选择&#x200B;**[!UICONTROL 创建数据集]**。

   ![创建数据集](assets/create-dataset.png)

1. 选择&#x200B;**[!UICONTROL 使用模式创建数据集]**。

   ![使用模式创建数据集](assets/create-dataset-from-schema.png)。

1. 选择您之前创建的模式，然后选择 **[!UICONTROL 下一个]**。

1. 为您的数据集命名并（可选）提供描述。

   ![数据集名称](assets/name-your-datatest.png)

1. 选择&#x200B;**[!UICONTROL 完成]**。

1. 选择&#x200B;**[!UICONTROL 配置文件]**&#x200B;开关

   系统会提示您启用配置文件的数据集。启用后，数据集会使用其摄取的数据丰富实时客户配置文件。

   >[!IMPORTANT]
   >
   >    只有当数据集所依附的模式也为配置文件启用时，您才能为配置文件启用数据集。

   ![为配置文件启用模式](assets/aepwebsdk-dataset-profile.png)

   有关如何查看、预览、创建和删除数据集的详细信息，请参阅[数据集UI指南](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=zh-Hans)。 您还可以了解如何为Real-time Customer Profile启用数据集。

1. 继续执行从[Adobe Analytics为您的组织动态生成的升级步骤，以Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。

