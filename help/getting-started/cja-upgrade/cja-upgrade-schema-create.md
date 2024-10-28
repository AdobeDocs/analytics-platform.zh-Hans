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
source-wordcount: '989'
ht-degree: 53%

---

# 创建要与Customer Journey Analytics一起使用的XDM架构

>[!NOTE]
>
>在完成[Adobe Analytics以Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)之后，应使用此文档。
> 
>只有在完成之前为您的组织动态生成的所有步骤后，才应执行此页面上的步骤。
>
>完成此页面上的步骤后，继续执行从[Adobe Analytics为您的组织动态生成的升级步骤，以Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。

>[!IMPORTANT]
>
>在开始创建XDM架构之前，请与您的数据团队和整个组织中的其他利益相关者合作，确定您组织的理想架构设计，以便用于Customer Journey Analytics和您使用的其他Adobe Experience Platform应用程序。 有关详细信息，请参阅[架构您的架构以用于Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)。

Adobe建议在升级到Customer Journey Analytics时创建Experience Data Model (XDM)架构。 XDM架构允许精简架构，根据您的组织和您使用的特定Platform应用程序的需求量身定制。 当需要对架构进行更改时，您不必在数千个未使用的字段中进行筛选，即可找到需要更新的字段。

## 创建架构

您定义的XDM架构表示您收集到Adobe Experience Platform中的数据模型。

要创建方案，请执行以下操作：

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

1. 在Adobe Experience Platform的左边栏中，选择[!UICONTROL 数据管理]中的&#x200B;**[!UICONTROL 架构]**。

1. 选择&#x200B;**[!UICONTROL 创建架构]**。

1. 在“创建模式”向导的“选择类”步骤中：

   1. 选择&#x200B;**[!UICONTROL 体验事件]**。

      ![创建突出显示Experience Event的架构](assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    体验事件架构用于为配置文件的&#x200B;_行为_&#x200B;建模（如场景名称、要添加到购物车的按钮）。 个人配置档案模式用于对个人配置档案&#x200B;_属性_（如姓名、电子邮件、性别）建模。

   1. 选择&#x200B;**[!UICONTROL 下一步]**。


1. 在[!UICONTROL 创建架构]向导的[!UICONTROL 名称和审核步骤]中：

   1. 为您的架构输入&#x200B;**[!UICONTROL 架构显示名称]**&#x200B;和（可选）**[!UICONTROL 描述]**。

      ![创建架构窗口，显示架构字段的名称名称](assets/create-ee-schema-wizard-step-2.png)

   1. 选择&#x200B;**[!UICONTROL 完成]**。

1. 在示例架构的结构选项卡中：

   1. 在[!UICONTROL 字段组]中选择&#x200B;**[!UICONTROL + 添加]**。

      ![添加字段组](assets/add-field-group-button.png)

      字段组是可重用的对象和属性集合，可让您轻松扩展模式。

   1. 在[!UICONTROL 添加字段组]对话框中，从列表中选择 **[!UICONTROL AEP Web SDK ExperienceEvent]** 字段组。

      ![AEP Web SDK ExperienceEvent 字段组](assets/select-aepwebsdk-experienceevent.png)

      您可以选择预览按钮，以查看属于该字段组的字段的预览，例如 `web > webPageDetails > name`。

      ![AEP Web SDK ExperienceEvent 字段组预览](assets/aepwebsdk-experiencevent-preview.png)

      选择&#x200B;**[!UICONTROL 返回]**&#x200B;关闭预览。

   1. 选择&#x200B;**[!UICONTROL 添加字段组]**。

1. 在[!UICONTROL 结构]面板中选择模式名称旁边的 **[!UICONTROL +]**。

   ![示例模式添加字段按钮](assets/example-schema-plus.png)

1. 在 [!UICONTROL  字段属性 ] 面板中，输入 `Identification`作为名称，**[!UICONTROL Identification]** 作为 [!UICONTROL Display name]，选择 **[!UICONTROL Object]** 作为 [!UICONTROL Type] 和选择 **[!UICONTROL ExperienceEvent Core v2.1]** 作为 [!UICONTROL Field Group]。

   >[!NOTE]
   >
   >如果该字段组不可用，请查找另一个包含标识字段的字段组。 或者[创建新的字段组](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html)和[将新的标识字段](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#define-a-identity-field)（如`ecid`、`crmId`和其他您需要的字段）添加到该字段组，并选择该新字段组。

   ![识别对象](assets/identification-field.png)

   标识对象将标识功能添加到架构中。 对于您自己的网站，您需要使用Experience CloudID和电子邮件地址来识别访问您网站的用户档案。 还有许多其他属性可用于跟踪您的人员标识（例如客户ID、忠诚度ID）。

   选择&#x200B;**[!UICONTROL 应用]**&#x200B;将此对象添加到您的模式中。

1. 选择刚刚添加的标识对象中的&#x200B;**[!UICONTROL ecid]**&#x200B;字段，选择&#x200B;**[!UICONTROL 标识]**&#x200B;和&#x200B;**[!UICONTROL 主要标识]** 和 **[!UICONTROL ECID]** 来自右侧面板中的 [!UICONTROL 标识命名空间] 列表。

   ![指定 ECID 作为身份](./assets/specify-identity.png)

   您将 Experience Cloud Identity 指定为 Adobe Experience Platform Identity 服务可用于组合（缝合）具有相同 ECID 的配置文件行为的主要身份。

   选择 **[!UICONTROL 应用]**。您会看到 ecid 属性中出现指纹图标。

1. 选择刚刚添加的标识对象中的&#x200B;**[!UICONTROL 邮件]**&#x200B;字段，选择&#x200B;**[!UICONTROL 标识]**&#x200B;和&#x200B;**[!UICONTROL 邮件]** 和 [!UICONTROL 标识命名空间] 列表中的 [!UICONTROL 字段属性] 面板。

    ![将电子邮件指定为标识](./assets/specify-email-identity.png)

   您将电子邮件地址指定为 Adobe Experience Platform Identity 服务可用于组合（拼接）配置文件行为的另一个标识。

   选择 **[!UICONTROL 应用]**。您会看到电子邮件属性中显示指纹图标。

   选择&#x200B;**[!UICONTROL 保存]**。

1. 选择显示模式名称的模式的根元素，然后选择 **[!UICONTROL 配置文件]** 开关。

   系统会提示您启用配置文件的模式。一旦启用，当数据被引入基于此模式的数据集中时，该数据将合并到实时客户配置文件。

   有关详细信息，请参阅[启用模式以在实时客户配置文件中使用](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#profile)。

   >[!IMPORTANT]
   >
   >    一旦您保存了为配置文件启用的模式，就不能再为配置文件禁用它。

   ![为配置文件启用模式](./assets/enable-for-profile.png)

1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存模式。

   您已经创建了一个最小模式，用于对您可以从您的网站捕获的数据进行建模。该模式允许使用 Experience Cloud Identity 和电子邮件地址来识别配置文件。通过启用配置文件模式，您可以确保从您的网站捕获的数据被添加到实时客户配置文件中。

   除了行为数据之外，您还可以从您的站点捕获配置文件属性数据（例如订阅时事通讯的配置文件的详细信息）。

   要捕获此配置文件数据，您需要：

   * 基于 XDM 个人配置文件类创建模式。

   * 将 Profile Core v2 字段组添加到模式中。

   * 添加基于 Profile Core v2 字段组的标识对象。

   * 将Experience CloudID定义为主标识符，将电子邮件定义为标识符。

   * 为配置文件启用模式

   请参阅[在 UI 中创建和编辑模式](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html)，了解有关向模式添加和删除字段组和单个字段的更多信息。

1. 继续执行从[Adobe Analytics为您的组织动态生成的升级步骤，以Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。

