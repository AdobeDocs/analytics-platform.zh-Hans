---
title: 为 Analytics 源连接器创建一个自定义架构
description: 了解如何为Analytics源连接器创建自定义架构
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: ac3ec479938acf509bbd26be282b75e75dd49c33
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 23%

---

# 为 Analytics 源连接器创建一个自定义架构 {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create-schema"
>title="为 Analytics 源连接器创建一个架构"
>abstract="此架构是 Adobe Analytics ExperienceEvent 字段组与构成您组织的自定义架构的所有字段组的组合。通过它，您可以将 Analytics 源连接器使用的字段映射到您组织的架构，并且此架构仅用于历史数据。<br><br>虽然具有技术性质，但创建此架构可以在几个小时内完成，如果您确切知道哪些字段组构成了组织的自定义架构，速度可能会更快。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-historical"
>title="为历史数据创建 Analytics 源连接器"
>abstract="您可以使用Analytics Source Connector将Adobe Analytics报表包数据引入Adobe Experience Platform。 然后，此数据可以用作Customer Journey Analytics中的历史数据。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## 了解Analytics Source Connector如何将历史数据引入Customer Journey Analytics

您可以使用Analytics Source Connector将Adobe Analytics报表包数据引入Adobe Experience Platform。 然后，此数据可以用作Customer Journey Analytics中的历史数据。

此过程假定您希望[创建一个自定义架构以用于您的Customer Journey Analytics Web SDK实施](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)，因为您需要一个针对贵组织和您使用的特定Platform应用程序的需求而定制的简化架构。

要使用Analytics Source Connector将历史数据引入Customer Journey Analytics，您需要：

1. 为Analytics源连接器创建自定义架构，如下所述。

1. 如果您还没有Analytics源连接器，请[创建Analytics源连接器并将字段映射到您的自定义架构](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

   或

   如果您已有Analytics源连接器，请将源连接器中的[字段映射到XDM架构](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)。

1. [将 Analytics 源连接器数据集添加到连接](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## 为 Analytics 源连接器创建一个自定义架构

您应该已经[为Experience Platform Web SDK实施创建了新的自定义架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)以便与Customer Journey Analytics一起使用。 此架构应包含您计划收集其数据的字段的任何字段组。

现在，您需要使用Web SDK架构中的这些相同的字段组，并将其添加到可以与Analytics Source Connector一起使用的新架构中。

Analytics Source Connector的此架构需要包含：

* 您为Web SDK实施创建的自定义架构中包含的所有字段组（包括您创建的任何自定义字段组）。 (任何不属于默认字段组的自定义字段都应作为自定义字段组的一部分添加到您的Web SDK架构中。)

* “Adobe Analytics ExperienceEvent模板”字段组

要创建与Analytics Source Connector一起使用的自定义架构，请执行以下操作：

1. 在Adobe Experience Platform中，开始创建新的自定义架构，如[创建自定义架构以用于Customer Journey Analytics Web SDK实施](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)中所述。

1. 添加您为Web SDK实施创建的架构中包含的所有字段组（包括任何自定义字段组）。

1. 添加完这些字段组后，添加Adobe Analytics ExperienceEvent字段组：

   在&#x200B;**[!UICONTROL 字段组]**&#x200B;部分中，选择&#x200B;**[!UICONTROL 添加]**&#x200B;以添加其他字段组。

   ![将字段组添加到架构](assets/schema-add-field-group.png)

1. 搜索并选择&#x200B;**[!UICONTROL Adobe Analytics ExperienceEvent模板]**&#x200B;字段组。

   ![添加Adobe Analytics ExperienceEvent字段组](assets/schema-experienceevent.png)

1. 选择&#x200B;**[!UICONTROL 添加字段组]**。

1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存架构。

{{upgrade-final-step}}
