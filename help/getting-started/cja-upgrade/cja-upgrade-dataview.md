---
title: 在Customer Journey Analytics中创建数据视图
description: 了解从Adobe Analytics升级到Customer Journey Analytics时推荐的路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 832f3f9a-1836-43ac-8185-f22ae0ded3aa
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 20%

---

# 在Customer Journey Analytics中创建数据视图 {#upgrade-create-dataview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataview"
>title="在Customer Journey Analytics中创建数据视图"
>abstract="数据视图是Customer Journey Analytics专属的容器，通过它，可决定如何解释来自连接的数据。<br><br>虽然数据视图的初始创建需要几分钟时间，但为每个维度和量度配置所需的组件设置可能需要几天时间。 调整这些设置可追溯应用，以便您的组织可以在一段时间内优化它们。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>只有在完成所有先前的升级步骤后，才应执行本页上的步骤。 您可以按照[推荐的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)进行操作，也可以按照[Adobe Analytics为您的组织动态生成的升级步骤来Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。
>
>完成此页面上的步骤后，请继续执行建议的升级步骤或动态生成的升级步骤。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-views/create-dataview.md -->

创建数据视图涉及从架构元素创建量度和维度或利用标准组件。大多数架构元素既可以是维度，也可以是量度，具体取决于您的业务要求。 将架构元素拖入数据视图后，右侧即显示选项，从中可调整维度或量度在 Customer Journey Analytics 中的操作方式。

要创建数据视图，请执行以下操作：

1. 登录到 [Customer Journey Analytics](https://analytics.adobe.com)，然后转到&#x200B;**[!UICONTROL “数据视图”]**&#x200B;选项卡。

1. 选择&#x200B;**[!UICONTROL 创建新数据视图]**。 或者，您可以从数据视图列表中选择现有数据视图进行编辑。

1. 在&#x200B;[!UICONTROL **配置**]&#x200B;选项卡上，指定数据视图的名称，并配置其基本设置、组件和日历选项。

   有关每个字段的详细信息，请参阅[创建或编辑数据视图](/help/data-views/create-dataview.md)中的[配置](/help/data-views/create-dataview.md#configure)。

   ![配置数据视图](assets/dataview-configure.png)

1. 选择&#x200B;[!UICONTROL **“组件”**]&#x200B;选项卡。

   在&#x200B;[!UICONTROL **组件**]&#x200B;选项卡中，您可以设置数据视图的组件，这意味着您可以从架构元素创建量度和维度。 您也可以使用标准组件。

   ![“组件”选项卡](assets/dataview-components.png)

1. 从&#x200B;[!UICONTROL **组件**]&#x200B;选项卡，将架构元素从左边栏拖入&#x200B;[!UICONTROL **Dimension**]&#x200B;部分或&#x200B;[!UICONTROL **量度**]&#x200B;部分。 您添加的架构元素将成为数据视图中的量度或维度。

   有关向数据视图添加组件时可用的选项的详细信息，请参阅[创建或编辑数据视图](/help/data-views/create-dataview.md)中的[组件](/help/data-views/create-dataview.md#components)。

1. 选择&#x200B;[!UICONTROL **设置**]&#x200B;选项卡。在此处，您可以配置要应用于整个数据视图的过滤器，以及配置会话超时和量度。

   有关配置数据视图设置时可用的选项的详细信息，请参阅[创建或编辑数据视图](/help/data-views/create-dataview.md)中的[设置](/help/data-views/create-dataview.md#settings)。

1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存数据视图的配置。

1. 指定所有所需设置后，选择&#x200B;**[!UICONTROL 保存并完成]**。

1. 继续执行[建议的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[动态生成的升级步骤](https://gigazelle.github.io/cja-ttv/)。
