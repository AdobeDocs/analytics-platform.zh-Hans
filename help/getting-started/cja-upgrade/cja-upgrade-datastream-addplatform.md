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
source-wordcount: '318'
ht-degree: 29%

---

# 将Platform作为服务添加到您的数据流

>[!NOTE]
>
>在完成[Adobe Analytics以Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)之后，应使用此文档。
> 
>只有在完成之前为您的组织动态生成的所有步骤后，才应执行此页面上的步骤。
>
>完成此页面上的步骤后，继续执行从[Adobe Analytics为您的组织动态生成的升级步骤，以Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

在完成此部分中的步骤之前，应该已经存在数据流。 数据流的创建时间和方式取决于您的Adobe Analytics实施，如下所示：

* 如果您的Adobe Analytics实施使用的是Web SDK或Web SDK扩展，则在升级过程开始之前，数据流可用于Adobe Analytics环境。

* 对于其他Adobe Analytics实施，创建数据流是升级过程的一部分，如[创建数据流以用于Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)中所述。

在数据流可用时，您需要添加Platform即服务：

1. 在 Adobe Experience Platform UI 的左边栏中，选择 [!UICONTROL 数据收藏集] 中的 **[!UICONTROL 数据流]**。

1. 选择之前配置的数据流。<!--true?-->

1. 选择 **[!UICONTROL 添加服务]**。

1. 在 [!UICONTROL 添加服务屏幕]：

   1. 从 [!UICONTROL 服务] 列表中选择 **[!UICONTROL Adobe Experience Platform]**。

   1. 确保选择 **[!UICONTROL Enabled]**。

   1. 从 [!UICONTROL 事件数据集] 列表中选择您的数据集。

      ![数据流 AEP 服务](./assets/datastream-aep-service.png)

   1. 保留其他设置并选择 **[!UICONTROL 保存]** 以保存数据流。

   您的数据流现已配置为将从您的网站收集的数据转发到 Adobe Experience Platform 中的数据集。

   有关如何配置数据流和如何处理敏感数据的更多信息，请参阅[数据流概述](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html)。

1. 继续执行从[Adobe Analytics为您的组织动态生成的升级步骤，以Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。