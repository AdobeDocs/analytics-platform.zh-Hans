---
title: 为Analytics源连接器创建XDM架构
description: 了解如何为Analytics源连接器创建XDM架构
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 8e51e97b0616a5406c5c3a29431fde87a551ab9f
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 2%

---

# 为Analytics源连接器创建XDM架构

>[!NOTE]
> 
>只有在完成所有先前的升级步骤后，才应执行本页上的步骤。 您可以按照[推荐的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)进行操作，也可以按照[Adobe Analytics为您的组织动态生成的升级步骤来Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。
>
>完成此页面上的步骤后，请继续执行建议的升级步骤或动态生成的升级步骤。

您应该已经[为Experience PlatformWeb SDK实现创建了新的XDM架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)以用于Customer Journey Analytics。 此架构应包含您计划收集其数据的字段的任何字段组。

除了已为Web SDK实施创建的XDM架构之外，您现在还需要创建第二个XDM架构以与Analytics源连接器一起使用，将历史数据导入Customer Journey Analytics。

第二个架构需要包含：

* 为Web SDK实施创建的架构中包含的所有字段组（包括任何自定义字段组）。 （任何不属于默认字段组的自定义字段都应作为自定义字段组的一部分添加到您的Web SDK架构中。）

* “Adobe Analytics ExperienceEvent模板”字段组

要创建用于Analytics源连接器的XDM架构，请执行以下操作：

1. 在Adobe Experience Platform中，开始创建新的XDM架构，如[创建要与Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)一起使用的XDM架构中所述。

1. 添加您为Web SDK实施创建的架构中包含的所有字段组（包括任何自定义字段组）。

1. 添加完这些字段组后，添加Adobe Analytics ExperienceEvent字段组：

   在&#x200B;**[!UICONTROL 字段组]**&#x200B;部分中，选择&#x200B;**[!UICONTROL 添加]**&#x200B;以添加其他字段组。

   ![将字段组添加到架构](assets/schema-add-field-group.png)

1. 搜索并选择&#x200B;**[!UICONTROL Adobe Analytics ExperienceEvent模板]**&#x200B;字段组。

   ![添加Adobe Analytics ExperienceEvent字段组](assets/schema-experienceevent.png)

1. 选择&#x200B;**[!UICONTROL 添加字段组]**。

1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存模式。

1. 继续执行[建议的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[动态生成的升级步骤](https://gigazelle.github.io/cja-ttv/)。

