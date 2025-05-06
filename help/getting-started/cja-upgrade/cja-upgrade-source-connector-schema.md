---
title: 为 Analytics 源连接器创建一个自定义架构
description: 学习如何为 Analytics 源连接器创建一个自定义架构
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '587'
ht-degree: 100%

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
>abstract="您可以使用 Analytics 源连接器将 Adobe Analytics 报告套件数据导入到 Adobe Experience Platform。然后，这些数据可以用作 Customer Journey Analytics 中的历史数据。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## 了解 Analytics 源连接器如何将历史数据带入 Customer Journey Analytics

您可以使用 Analytics 源连接器将 Adobe Analytics 报告套件数据导入到 Adobe Experience Platform。然后，这些数据可以用作 Customer Journey Analytics 中的历史数据。

此过程假设您希望[创建一个自定义架构，以便与您的 Customer Journey Analytics Web SDK 实施一起使用](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)，因为您需要一个根据您的组织需求和您使用的特定 Platform 应用程序量身定制的精简模式。

要使用 Analytics 源连接器将历史数据引入 Customer Journey Analytics，您需要：

1. 为 Analytics 源连接器创建一个自定义架构，如下所述。

1. 如果您尚未拥有 Analytics 源连接器，请[创建 Analytics 源连接器并将字段映射到您的自定义架构](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

   或

   如果您已拥有 Analytics 源连接器，[则将字段从源连接器映射到 XDM 架构](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)。

1. [将 Analytics 源连接器数据集添加到该连接](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## 为 Analytics 源连接器创建一个自定义架构

您应该已经为您的 Experience Platform Web SDK 实施[创建了一个新的自定义架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)，以便与 Customer Journey Analytics 一起使用。该架构应包含您计划收集数据的字段的任何字段组。

现在，您需要使用 Web SDK 架构中的相同字段组，并将它们添加到可与 Analytics 源连接器一起使用的新架构中。

Analytics 源连接器的架构需要包含：

* 您为 Web SDK 实施创建的自定义架构中包含的所有字段组（包括您创建的任何自定义字段组）。（任何不属于默认字段组的自定义字段都应作为自定义字段组的一部分添加到 Web SDK 架构中。）

* Adobe Analytics ExperienceEvent 模板字段组

要创建与 Analytics 源连接器一起使用的自定义架构，请执行以下操作：

1. 在 Adobe Experience Platform 中，开始创建新的自定义架构，如[创建自定义架构以与 Customer Journey Analytics Web SDK 实施一同使用](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)中所述。

1. 添加您为 Web SDK 实施创建的架构中包含的所有字段组（包括任何自定义字段组）。

1. 添加完这些字段组后，添加 Adobe Analytics ExperienceEvent 字段组：

   在&#x200B;**[!UICONTROL 字段组]**&#x200B;部分，选择&#x200B;**[!UICONTROL 添加]**&#x200B;来添加其他字段组。

   ![将字段组添加到架构中](assets/schema-add-field-group.png)

1. 搜索并选择 **[!UICONTROL Adobe Analytics ExperienceEvent 模板]** 字段组。

   ![添加 Adobe Analytics ExperienceEvent 字段组](assets/schema-experienceevent.png)

1. 选择&#x200B;**[!UICONTROL 添加字段组]**。

1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存架构。

{{upgrade-final-step}}
