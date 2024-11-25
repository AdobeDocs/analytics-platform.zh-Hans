---
title: 为Analytics源连接器创建自定义架构
description: 了解如何为Analytics源连接器创建自定义架构
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: 45f2097d2f0657f623b825acb8d06ec6972f757f
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 3%

---

# 为Analytics源连接器创建自定义架构

>[!NOTE]
> 
>只有在完成所有先前的升级步骤后，才应执行本页上的步骤。 您可以按照[推荐的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)进行操作，也可以按照[Adobe Analytics为您的组织动态生成的升级步骤来Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。
>
>完成此页面上的步骤后，请继续执行建议的升级步骤或动态生成的升级步骤。

## 了解Analytics Source Connector可怎样将历史数据引入Customer Journey Analytics

您可以使用Analytics Source Connector将Adobe Analytics报表包数据引入Adobe Experience Platform。 然后，此数据可用作Customer Journey Analytics中的历史数据。

此过程假定您希望[创建一个自定义架构以用于您的Customer Journey AnalyticsWeb SDK实施](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)，因为您需要一个针对您的组织需求以及您使用的特定Platform应用程序量身定制的简化架构。

要使用Analytics Source Connector将历史数据纳入Customer Journey Analytics，您需要：

1. 为Analytics源连接器创建自定义架构，如下所述。

1. 如果您还没有Analytics源连接器，请[创建Analytics源连接器并将字段映射到您的自定义架构](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

   或

   如果您已有Analytics源连接器，请将源连接器中的[字段映射到XDM架构](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)。

1. [将 Analytics 源连接器数据集添加到连接](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## 为Analytics源连接器创建自定义架构

您应该已经[为Experience PlatformWeb SDK实现创建了新的自定义架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)以用于Customer Journey Analytics。 此架构应包含您计划收集其数据的字段的任何字段组。

您现在需要使用Web SDK架构中的这些相同的字段组，并将其添加到可以与Analytics Source Connector一起使用的新架构中。

Analytics Source Connector的此架构需要包含：

* 您为Web SDK实施创建的自定义架构中包含的所有字段组（包括您创建的任何自定义字段组）。 （任何不属于默认字段组的自定义字段都应作为自定义字段组的一部分添加到您的Web SDK架构中。）

* “Adobe Analytics ExperienceEvent模板”字段组

要创建与Analytics Source Connector一起使用的自定义架构，请执行以下操作：

1. 在Adobe Experience Platform中，开始创建新的自定义架构，如[创建自定义架构以用于Customer Journey AnalyticsWeb SDK实施](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)中所述。

1. 添加您为Web SDK实施创建的架构中包含的所有字段组（包括任何自定义字段组）。

1. 添加完这些字段组后，添加Adobe Analytics ExperienceEvent字段组：

   在&#x200B;**[!UICONTROL 字段组]**&#x200B;部分中，选择&#x200B;**[!UICONTROL 添加]**&#x200B;以添加其他字段组。

   ![将字段组添加到架构](assets/schema-add-field-group.png)

1. 搜索并选择&#x200B;**[!UICONTROL Adobe Analytics ExperienceEvent模板]**&#x200B;字段组。

   ![添加Adobe Analytics ExperienceEvent字段组](assets/schema-experienceevent.png)

1. 选择&#x200B;**[!UICONTROL 添加字段组]**。

1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存模式。

1. 继续执行[建议的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[动态生成的升级步骤](https://gigazelle.github.io/cja-ttv/)。
