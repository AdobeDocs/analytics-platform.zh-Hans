---
title: 升级到Customer Journey Analytics时监视数据集摄取
description: 了解在升级到Customer Journey Analytics时如何监测数据集摄取
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: f71f5b863a024d882a116a5fd3bf0fc433e5fe99
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# 升级到Customer Journey Analytics时监视数据集摄取

>[!NOTE]
> 
>只有在完成所有先前的升级步骤后，才应执行本页上的步骤。 您可以按照[推荐的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)进行操作，也可以按照[Adobe Analytics为您的组织动态生成的升级步骤来Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。
>
>完成此页面上的步骤后，请继续执行建议的升级步骤或动态生成的升级步骤。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

配置Web SDK实施后，您需要检查各个批次的状态，以验证数据是否已摄取到数据集中。

1. 在Experience PlatformUI的左侧导航中选择&#x200B;**[!UICONTROL 监视]**。

   此时将显示监控仪表板。 利用此仪表板，可查看来自批次或流式摄取的集客数据状态。

   <!-- insert screenshot -->

1. 选择&#x200B;**[!UICONTROL 批次端对端]**&#x200B;以查看批次列表。

   如果未显示批次，请检查您的Web SDK实施，以确保正确地向Adobe发送数据。

   <!-- insert screenshot -->

1. 为给定数据集选择批次ID，然后验证&#x200B;**[!UICONTROL 状态]**&#x200B;字段中是否显示&#x200B;**[!UICONTROL 成功]**。

   如果&#x200B;**[!UICONTROL 失败]**&#x200B;显示在&#x200B;**[!UICONTROL 状态]**&#x200B;字段中，请检查您的Web SDK实施，以确保其向Adobe正确发送数据。

   重复此步骤以验证每个批次的状态。

1. 继续执行[建议的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[动态生成的升级步骤](https://gigazelle.github.io/cja-ttv/)。

