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
source-wordcount: '229'
ht-degree: 35%

---

# 创建数据流以用于Customer Journey Analytics

>[!NOTE]
>
>在完成[Adobe Analytics以Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)之后，应使用此文档。
> 
>只有在完成之前为您的组织动态生成的所有步骤后，才应执行此页面上的步骤。
>
>完成此页面上的步骤后，继续执行从[Adobe Analytics为您的组织动态生成的升级步骤，以Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

数据流表示实施 Adobe Experience Platform Web 和移动 SDK 时的服务器端配置。使用 Adobe Experience Platform SDK 收集数据时，数据会发送到 Adobe Experience Platform Edge Network。它是确定数据转发到哪些服务的数据流。

在您的设置中，您希望将从网站收集的数据发送到 Adobe Experience Platform 中的数据集。

设置您的数据流

1. 在Adobe Experience Platform中，从左边栏中的[!UICONTROL 数据收集]中选择&#x200B;**[!UICONTROL 数据流]**。

1. 选择&#x200B;**[!UICONTROL 新数据流]**。

1. 命名并描述您的数据流。从 [!UICONTROL 事件模式] 列表中选择您的模式。

   ![新数据流](assets/new-datastream.png)

1. 选择&#x200B;**[!UICONTROL 保存]**。

1. 继续执行从[Adobe Analytics为您的组织动态生成的升级步骤，以Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。

