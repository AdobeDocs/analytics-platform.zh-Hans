---
title: 创建用于Customer Journey Analytics的架构
description: 了解从Adobe Analytics升级到Customer Journey Analytics时推荐的路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: 41965bcd5ae8252fbf2ceda0d2b633ec6dc0e9a3
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 23%

---

# 创建数据流以用于Customer Journey Analytics

>[!NOTE]
> 
>只有在完成所有先前的升级步骤后，才应执行本页上的步骤。 您可以按照[推荐的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)进行操作，也可以按照[Adobe Analytics为您的组织动态生成的升级步骤来Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。
>
>完成此页面上的步骤后，请继续执行建议的升级步骤或动态生成的升级步骤。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

数据流表示实施 Adobe Experience Platform Web 和移动 SDK 时的服务器端配置。使用 Adobe Experience Platform SDK 收集数据时，数据会发送到 Adobe Experience Platform Edge Network。它是确定数据转发到哪些服务的数据流。

在您的设置中，您希望配置数据流以将收集的数据发送到Adobe Experience Platform中的数据集。

>[!NOTE]
>
>只有使用AppMeasurement或Analytics扩展（标记）的Adobe Analytics实施才需要执行以下步骤。
>
>如果您的Adobe Analytics实施使用Web SDK或Web SDK扩展，则您的Adobe Analytics环境中已存在数据流。

设置您的数据流

1. 在Adobe Experience Platform中，从左边栏中的[!UICONTROL 数据收集]中选择&#x200B;**[!UICONTROL 数据流]**。

1. 选择&#x200B;**[!UICONTROL 新数据流]**。

1. 命名并描述您的数据流。从 [!UICONTROL 事件架构] 列表中选择您的架构。

   ![新数据流](assets/new-datastream.png)

1. 选择&#x200B;**[!UICONTROL 保存]**。

1. 继续执行[建议的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[动态生成的升级步骤](https://gigazelle.github.io/cja-ttv/)。
