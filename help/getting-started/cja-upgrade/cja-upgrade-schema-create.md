---
title: 为 Customer Journey Analytics 创建自定义架构
description: 了解如何为 Customer Journey Analytics 创建自定义架构
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 902e5890-f970-4f1a-b091-9c3e51a987db
autotag-review: '2026-05-19T08:15:52.067Z'
TQID: 'https://experienceleague.adobe.com/RxYBLvBJnhWb-YL6HeVpTz-9dKrr5DQZhOBond8Xano'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 1294
ht-degree: 100%

---

# 创建用于 Customer Journey Analytics 的自定义架构 {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-create"
>title="在 Adobe Experience Platform 中创建所需的自定义架构"
>abstract="使用 Adobe Experience Platform UI 创建一个架构，以便 Adobe 知道正确的数据存储格式。<br><br>此步骤将实际创建您的组织已同意的架构。 在 Adobe Experience Platform 界面中创建架构的预计时间约为一周，具体取决于需要创建的维度及量度的数量。"

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-create-default-aa"
>title="使用 Adobe Analytics ExperienceEvent 字段组创建架构"
>abstract="使用 “Adobe Analytics ExperienceEvent” 字段组，在 Adobe Experience Platform 中创建包含所有 Adobe Analytics 字段的架构。<br><br>基于 Adobe Analytics ExperienceEvent 字段组创建架构非常简单，仅需几分钟即可完成。"

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-profile"
>title="为轮廓启用您的架构"
>abstract="在您的架构中启用轮廓以供 Adobe Real-time CDP 使用。 之所以出现此步骤，是因为您选择了与 Adobe Real-time CDP 集成。<br><br>由于此步骤仅需勾选一个选项，因此只需几分钟即可完成。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

>[!IMPORTANT]
>
>在开始创建自定义架构之前，请与整个组织的数据团队和其他利益相关者合作一同，确定组织针对 Customer Journey Analytics 和您使用的其他 Adobe Experience Platform 应用程序的理想架构设计。 有关详细信息，请参阅[构建用于 Customer Journey Analytics 的架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)。

以下部分介绍的是如何创建可与 Customer Journey Analytics 一起使用的架构。 可以使用以下架构选项：

* **自定义 XDM 架构：**（推荐）允许根据您组织的需求和您使用的特定 Platform 应用程序定制简化的架构。 未来所需的任何更改都很直接明了。

* **使用 Adobe Analytics ExperienceEvent 字段组的 Adobe Analytics 架构：**&#x200B;需要添加数千个不需要的字段。 未来进行任何必要的更改时都会更加困难。

有关这些架构选项的更多信息，请参阅[为 Customer Journey Analytics 选择架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)。

## 创建架构

您为 Web SDK 的实施定义的自定义架构代表了您在 Adobe Experience Platform 中收集的数据模型。

要创建自定义架构：

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

1. 在 Adobe Experience Platform 的左边栏中，选择[!UICONTROL 数据管理]中的&#x200B;**[!UICONTROL 架构]**。

1. 选择&#x200B;**[!UICONTROL 创建架构]**。

1. 在创建架构向导的&#x200B;**[!UICONTROL 选择类别]**&#x200B;步骤中：

   1. 选择&#x200B;**[!UICONTROL 体验事件]**。

      ![创建突出显示体验事件的架构](assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Experience Event 架构用于对轮廓的&#x200B;_行为_&#x200B;进行建模（如场景名称、添加到购物车的按钮）。 个人轮廓架构用于对轮廓&#x200B;_属性_（如姓名、电子邮件、性别）进行建模。

   1. 选择&#x200B;**[!UICONTROL 下一步]**。


1. 在[!UICONTROL 创建架构]向导中的[!UICONTROL 命名和审查步骤]中：

   1. 输入架构的&#x200B;**[!UICONTROL 架构显示名称]**&#x200B;和（可选）**[!UICONTROL 描述]**。

      ![创建架构窗口，其中显示架构字段的名称](assets/create-ee-schema-wizard-step-2.png)

   1. 选择&#x200B;**[!UICONTROL 完成]**。

1. 添加包含您想要在架构中包括的任何字段的所有字段组。

   字段组是可重用的对象和属性集合，以便您轻松扩展架构。

   1. 在&#x200B;**[!UICONTROL 字段组]**&#x200B;部分中，选择 **[!UICONTROL + 添加]**。

      ![添加字段组](assets/add-field-group-button.png)

   1. 在[!UICONTROL 添加字段组]对话框中，从列表中选择 **[!UICONTROL AEP Web SDK ExperienceEvent]** 字段组。

      ![AEP Web SDK ExperienceEvent 字段组](assets/select-aepwebsdk-experienceevent.png)

      您可以选择预览按钮，以查看属于该字段组的字段的预览，例如 `web > webPageDetails > name`。

      ![AEP Web SDK ExperienceEvent 字段组预览](assets/aepwebsdk-experiencevent-preview.png)

      选择&#x200B;**[!UICONTROL 返回]**&#x200B;关闭预览。

   1. （可选）选择您想要包括的任何其他字段组。

      如果您选择使用默认的 Adobe Analytics 架构，而不是创建自定义 XDM 架构，则现在可以添加 Adobe Analytics ExperienceEvent 字段组。 但是，Adobe 建议创建一个自定义的 XDM 架构，而不是添加此字段组。

      有关这些架构选项的更多信息，请参阅[为 Customer Journey Analytics 选择架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)。

   1. 选择&#x200B;**[!UICONTROL 添加字段组]**。

1. （可选）如果您有想要在架构中包含的自定义字段，请创建一个自定义字段组，并将自定义字段添加到该字段组中。

   1. 在&#x200B;**[!UICONTROL 字段组]**&#x200B;部分中，选择 **[!UICONTROL + 添加]**。

      ![添加字段组](assets/add-field-group-button.png)

   1. 在[!UICONTROL 添加字段组]对话框中，选择&#x200B;**[!UICONTROL 创建新字段组]**。

   1. 指定一个显示名称和可选描述，然后选择&#x200B;**[!UICONTROL 添加字段组]**。

1. 在[!UICONTROL 结构]面板中选择架构名称旁边的 **[!UICONTROL +]**。

   ![示例架构添加字段按钮](assets/example-schema-plus.png)

1. 在 [!UICONTROL  字段属性 ] 面板中，输入 `Identification`作为名称，**[!UICONTROL Identification]** 作为 [!UICONTROL Display name]，选择 **[!UICONTROL Object]** 作为 [!UICONTROL Type] 和选择 **[!UICONTROL ExperienceEvent Core v2.1]** 作为 [!UICONTROL Field Group]。

   >[!NOTE]
   >
   >如果该字段组不可用，请寻找另一个包含身份标识字段的字段组。 或者[创建一个新的字段组](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html)，并[将新的身份标识字段](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#define-a-identity-field)（如 `ecid`、`crmId` 以及您需要的其他字段）添加到该字段组中，并选择该新字段组。

   ![识别对象](assets/identification-field.png)

   识别对象为您的架构添加了识别功能。 在您的情况下，您希望使用 Experience Cloud ID 和电子邮件地址来识别访问您站点的轮廓。 还有许多其他属性可用于跟踪您的人员身份（例如客户 ID、忠诚度 ID）。

   选择&#x200B;**[!UICONTROL 应用]**&#x200B;将此对象添加到您的架构中。

1. 选择刚刚添加的身份标识对象中的&#x200B;**[!UICONTROL ecid]**&#x200B;字段，选择&#x200B;**[!UICONTROL 身份标识]**&#x200B;和&#x200B;**[!UICONTROL 主要身份标识]** 和 **[!UICONTROL ECID]** 来自右侧面板中的 [!UICONTROL 身份标识命名空间] 列表。

   ![指定 ECID 作为身份标识](./assets/specify-identity.png)

   您将 Experience Cloud Identity 指定为 Adobe Experience Platform 身份标识服务可用于组合（缝合）具有相同 ECID 的轮廓行为的主要身份。

   选择 **[!UICONTROL 应用]**。 您会看到 ecid 属性中出现指纹图标。

1. 选择刚刚添加的身份标识对象中的&#x200B;**[!UICONTROL 邮件]**&#x200B;字段，选择&#x200B;**[!UICONTROL 身份标识]**&#x200B;和&#x200B;**[!UICONTROL 邮件]** 和 [!UICONTROL 身份标识命名空间] 列表中的 [!UICONTROL 字段属性] 面板。

   ![将电子邮件指定为身份标识](./assets/specify-email-identity.png)

   您将电子邮件地址指定为 Adobe Experience Platform 身份标识服务可用于组合（拼接）轮廓行为的另一个身份标识。

   选择 **[!UICONTROL 应用]**。 您会看到电子邮件属性中显示指纹图标。

   选择&#x200B;**[!UICONTROL 保存]**。

1. （可选）如果您想将 Customer Journey Analytics 与 RTCDP 集成，请选择显示架构名称的架构根元素，然后选择&#x200B;**[!UICONTROL 轮廓]**&#x200B;切换按钮。

   系统会提示您为轮廓启用架构。 一旦启用，当数据被引入基于此架构的数据集中时，该数据将合并到实时客户轮廓。

   有关详细信息，请参阅[启用架构以在实时客户轮廓中使用](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#profile)。

   >[!IMPORTANT]
   >
   >为轮廓启用架构后，将无法为其禁用该架构。

   ![为轮廓启用架构](./assets/enable-for-profile.png)

1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存架构。

   您已经创建了一个最小架构，用于对您可以从您的网站捕获的数据进行建模。 该架构允许使用 Experience Cloud Identity 和电子邮件地址来识别轮廓。 通过启用轮廓架构，您可以确保从您的网站捕获的数据被添加到实时客户轮廓中。

   除了行为数据之外，您还可以从您的网站捕获轮廓属性数据（例如订阅新闻稿的轮廓的详细信息）。

   要捕获此轮廓数据，您需要：

   * 基于 XDM 个人轮廓类创建架构。

   * 将 Profile Core v2 字段组添加到架构中。

   * 添加基于 Profile Core v2 字段组的身份标识对象。

   * 将 Experience Cloud ID 定义为主要标识符，并将电子邮件定义为标识符。

   * 为轮廓启用架构

   请参阅[在 UI 中创建和编辑架构](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html)，了解有关向架构添加和删除字段组和单个字段的更多信息。

{{upgrade-final-step}}
