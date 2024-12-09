---
description: Workspace 中的项目共享和项目角色
keywords: Analysis Workspace 共享
title: 共享项目
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
role: User
source-git-commit: 4942c83e34b129e3718084601d5a733bcebf4de9
workflow-type: tm+mt
source-wordcount: '2042'
ht-degree: 64%

---

# 共享项目 {#share-projects}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_shareprojects"
>title="共享项目"
>abstract="您可以与组织中的其他用户共享这些项目角色中的任何一个。"

<!-- markdownlint-enable MD034 -->


可与以下类型的人员共享 Analysis Workspace 项目：

* 组织中有权访问Adobe Customer Journey Analytics的用户和组

  可共享“编辑”、“复制”或“查看”访问权限

* 您组织中无权访问Customer Journey Analytics的用户和组

  收件人具有只读访问权限

* 您组织之外的人员

  收件人具有只读访问权限

当收件人打开项目时，将反映您在分享前应用的任何[策划](curate.md)。

+++ 观看视频，了解如何使用项目共享。

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)

{{videoaa}}

+++

## 与组织中的Customer Journey Analytics用户和组共享 {#Add}

您可以与组织中的现有Customer Journey Analytics用户或组共享项目。 在按本节所述共享项目时，与您共享的用户必须已具有Customer Journey Analytics帐户。

您可以与用户或组共享特定角色，也可以共享链接。

* [共享特定的项目角色](#share-a-specific-project-role)

* [共享项目链接](#share-a-link-to-a-project)

## 共享特定的项目角色

与组织中的用户和组共享特定项目角色时，请考虑以下事项：

* 项目角色（**[!UICONTROL 编辑原件]**、**[!UICONTROL 编辑副本]**&#x200B;和&#x200B;**[!UICONTROL 只读]**）与用户和特定项目 ID 关联。项目角色与 [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) 中管理的用户权限无关。

* 在Customer Journey Analytics中，组由[Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html)中的产品配置文件定义。 管理员可以共享到任何组，包括“全部”组。 除“全部”组外，非管理员可以共享到其所属的任何组。

* 如果用户分配到了多个角色，将始终获得权限最高的角色体验。 如果同时将用户添加为个人和组成员，则可能发生这种情况。 例如，如果作为个人授予用户&#x200B;**[!UICONTROL 编辑原件]**&#x200B;角色，并作为组成员授予用户&#x200B;**[!UICONTROL 只读]**&#x200B;角色，则该用户将获得&#x200B;**[!UICONTROL 编辑原件]**&#x200B;项目体验。

* 归入&#x200B;**[!UICONTROL 编辑副本]**&#x200B;或&#x200B;**[!UICONTROL 只读]**&#x200B;角色的管理员在打开项目时获得这些有限的体验。管理员可通过与自己共享项目并为自己授予“编辑”角色而将其角色更改为&#x200B;**[!UICONTROL 编辑原件]**，如以下过程所述。

* 如果选择共享多个项目，则会将收件人添加到每个项目的现有收件人列表中。

  例如，已与收件人 1、2 和 3 共享项目 A，同时已与收件人 4、5 和 6 共享项目 B。

  之后，与收件人 4 和 7 共享项目 A 和 B。项目 A 的新共享列表现在为 1、2、3、4 和 7，项目 B 的新共享列表为 4、5、6 和 7。

要与组织中的用户或组共享特定的项目角色，请执行以下操作：

1. 在Customer Journey Analytics中，选择&#x200B;[!UICONTROL **Workspace**]&#x200B;选项卡，然后在左侧面板中选择&#x200B;[!UICONTROL **项目**]。

1. 选中要共享的一个或多个项目旁边的复选框，然后选择&#x200B;[!UICONTROL **共享**]。

   或

   要仅共享单个项目，您可以打开要共享的项目，然后选择&#x200B;**[!UICONTROL 共享]** > **[!UICONTROL 与 Workspace 用户共享]**。
如果存在未保存的更改，则将提示您首先保存您的项目。

   此时会显示“共享项目”对话框。该对话框的&#x200B;[!UICONTROL **通过链接分享**]&#x200B;和&#x200B;[!UICONTROL **设置**]&#x200B;部分仅在共享单个项目时可见。

   ![共享项目窗口。](assets/share-proj-modal.png)

1. 在提供的角色字段之一中添加收件人或收件人组：

   **编辑原件：**&#x200B;收件人可将更改&#x200B;**[!UICONTROL 保存]**&#x200B;到项目，并作为共有人行使权力。如果您希望与其他同事共同管理项目，则此角色很有用；这包括编辑、删除和修改共享项目的收件人列表。<br>注意：Analysis Workspace 当前不支持实时协作，因此建议在给定时间只让一个用户编辑项目。如果同时保存多个项目，则将保留最后一个版本。

   **编辑副本：**&#x200B;收件人可以&#x200B;**[!UICONTROL 另存为]**&#x200B;并有权访问左侧面板。 在此角色中，项目交互不受限。如果您希望将项目共享给了解您组织数据以及知道如何使用 Analysis Workspace 的用户，但不希望更改项目，则此角色非常有用。

   **只读：**&#x200B;收件人无法&#x200B;**[!UICONTROL 保存]**&#x200B;或&#x200B;**[!UICONTROL 另存为]**，并且无权访问左侧面板。 项目交互受到限制。如果您希望将项目共享给不太熟悉您组织的数据结构(通常情况下是Analysis Workspace或Customer Journey Analytics)的用户，则此角色非常有用。 但是，您可能仍然希望这些用户在一个安全的环境中使用数据和信息分析。详细了解[只读角色项目体验](/help/analysis-workspace/curate-share/view-only-projects.md)。

1. （条件）如果要共享单个项目，请选择在共享项目时是否启用以下选项：

   * **与所有收件人共享嵌入的项目组件：**&#x200B;共享筛选器、计算量度和日期范围。 共享后，这些组件将显示在接收人工作区的“组件”下拉菜单中。此设置不具有持续性，属于分享时的一次性操作。

   * **设置为收件人的登陆页面：** 将此页面设置为收件人的登陆页面。 此设置不具有持续性，属于分享时的一次性操作。

1. 选择&#x200B;**[!UICONTROL 共享]**。（如果已共享该项目，请选择&#x200B;[!UICONTROL **更新**]。）

   或

   选择&#x200B;**[!UICONTROL 策划和共享]**&#x200B;以自动应用项目策划。（如果项目已共享，请选择&#x200B;**[!UICONTROL 策划和更新]**。）了解有关[项目策划](curate.md)的更多信息。

## 共享项目链接

按本节所述共享链接时，请考虑以下事项：

* 使用该链接的收件人需要先登录Customer Journey Analytics，然后才能访问项目。

* 如果收件人未分配角色，并收到指向项目的[链接](/help/analysis-workspace/curate-share/shareable-links.md)（**[!UICONTROL 共享] > [!UICONTROL 获取项目链接]**），则他们会获得默认角色。 管理员获得&#x200B;**[!UICONTROL 编辑原件]**&#x200B;角色，非管理员获得&#x200B;**[!UICONTROL 编辑副本]**&#x200B;角色。

要与您组织中的用户共享项目链接，请执行以下操作：

1. 保存该项目。如果存在未保存的更改，则在分享链接前将提示您首先保存您的项目。

1. 选择&#x200B;**[!UICONTROL 共享]** > **[!UICONTROL 与 Workspace 用户共享]**，然后在&#x200B;**[!UICONTROL 通过链接分享]**&#x200B;字段旁选择&#x200B;**[!UICONTROL 复制]**。

   ![突出显示“共享方式”链接字段的共享项目。](assets/share-proj-modal.png)

1. 与组织中的用户共享项目链接。 例如，您可以将其粘贴到电子邮件、内部网站等。

## 与任何人共享项目（无需登录） {#share-public-link}

您可以将对Analysis Workspace项目的[只读访问权限](/help/analysis-workspace/curate-share/view-only-projects.md)授予无权访问Customer Journey Analytics的人员。 其中可包括：

* 您组织之外的人员

* 您组织内无权访问Customer Journey Analytics的人员

>[!NOTE]
>
>与无权访问Customer Journey Analytics的用户共享Analysis Workspace项目时，请考虑以下事项：
>
>* Customer Journey Analytics管理员可以禁用通过这种方式共享项目的功能，如[首选项](/help/analysis-workspace/user-preferences.md)中所述。 如果您无法按本节所述共享项目，则Customer Journey Analytics管理员已禁用此功能。
>
>* 扩展的可视化图表超过50个的项目不能与无权访问Customer Journey Analytics的用户共享。
>
>* 与您共享的用户可以查看在[策划](curate.md)期间应用于项目的任何筛选器。
> 
>* 您与其共享的用户可更改项目日期范围。默认情况下显示您为项目设置的日期范围。
>
>* 如果许多用户尝试同时访问给定的链接，则项目可能会变得无法访问。默认情况下，每 5 分钟可有超过 190 人访问单个链接。如果您的组织达到此限制，请等待 5 分钟，然后再重试访问链接。
>
>* Healthcare Shield和Privacy &amp; Security Shield许可证的[!UICONTROL 与任何人共享]功能都被阻止。

以下视频演示和随附文档描述与任何人共享链接相关的选项：

>[!VIDEO](https://video.tv.adobe.com/v/3420093/?learn=on)

要与任何人共享Analysis Workspace项目，请执行以下操作：

1. 打开要共享的 Analysis Workspace 项目。

1. 选择&#x200B;**[!UICONTROL 共享]** > **[!UICONTROL 与任何人共享]**。

   如果存在未保存的更改，则将提示您保存您的项目。

   <!-- Add screen shot of new modal -->

1. 如果尚未启用&#x200B;**[!UICONTROL 链接活动]**&#x200B;选项，请启用该选项。

   选择此选项将创建可与任何人共享的项目链接。随时可通过禁用此选项而禁止访问项目。

   项目的所有者也是此链接的所有者。仅在项目所有权转移时才能将链接所有权转移给另一个用户，如Analytics管理员指南中的[转移用户资产](/help/tools/asset-transfer/transfer-assets.md)中所述。

1. 选择是否启用以下安全选项(此选项可由您的Customer Journey Analytics管理员控制)：

   * **[!UICONTROL 要求进行 Experience Cloud 身份验证]：**

     启用此选项后，只有那些能够访问项目的用户才能登录到创建您共享的项目的Adobe Experience Cloud组织。 但是，与您共享的用户不需要具有访问Customer Journey Analytics的权限。

     Customer Journey Analytics管理员可以为公司配置此首选项，如[首选项](/help/analysis-workspace/user-preferences.md)中所述。 根据管理员如何配置此选项，您可能会遇到以下情况：

      * 如果此选项不可见，则Customer Journey Analytics管理员未启用此功能。

      * 如果启用了此选项但无法禁用它，则意味着您的Customer Journey Analytics管理员要求对访问Analysis Workspace项目的任何人进行Experience Cloud身份验证。 对于许可Healthcare Shield的组织来说，情况始终如此。

1. 在&#x200B;**[!UICONTROL 与任何人共享（无需登录）]**&#x200B;字段旁边，选择![链接](/help/assets/icons/Link.svg)以将链接复制到系统剪贴板。

1. 与您希望其有权访问该项目的人员共享该链接。例如，可将该链接粘贴到电子邮件中。

   您与其共享该链接的任何人均可查看该 Analysis Workspace 项目。

1. （可选）您可以选择![生成新链接图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg)以移除先前收到项目链接的用户的访问权限。 随后将生成一个可与您希望其访问该项目的用户共享的新链接。

1. 选择&#x200B;**[!UICONTROL 关闭]**&#x200B;以关闭共享对话框。随后自动保存您的更改。

## 查看与您共享的项目

当有人通过[共享特定项目角色](#share-a-specific-project-role)与您共享项目时，您可以从 [Analytics 登陆页面上的“项目”选项卡](/help/getting-started/landing.md#navigate-the-projects-tab)访问共享项目。

当有人通过共享链接与您共享项目时（通过[共享项目选项卡](#share-a-link-to-a-project)或通过[与任何人共享链接](#share-a-project-with-anyone-no-login-required)），您必须使用与您共享的链接才能访问该项目。 例如，该链接可能已在电子邮件、内部网站等中共享。

## 共享嵌入的组件

以下是一段关于该主题的视频：

>[!VIDEO](https://video.tv.adobe.com/v/24713/?quality=12)

## 常见问题解答 {#FAQs}

| 问题 | 回答 |
|---|---|
| 如果两位编辑者同时保存一个项目，会发生什么情况？ | 将不会合并更改，并将保留最后保存的项目版本。Analysis Workspace 当前不支持实时协作。 |
| 作为管理员，我将获得什么样的项目体验？ | 处于&#x200B;**[!UICONTROL 编辑副本]**&#x200B;或&#x200B;**[!UICONTROL 只读]**&#x200B;角色的管理员，在打开项目时将获得这些有限的体验。 如有需要，管理员可以随时通过&#x200B;**[!UICONTROL 组件] > [!UICONTROL 项目]**&#x200B;将其角色增加到&#x200B;**[!UICONTROL 编辑原始项目]**。 |
| 如果一位收件人作为个人和作为小组成员分别有不同的角色，会发生什么情况？ | 如果收件人同时具有多个角色，他们将始终获得权限最高的角色体验。例如，如果收件人以个人身份获得&#x200B;**[!UICONTROL 编辑原始]**&#x200B;角色，并且以组成员身份获得&#x200B;**[!UICONTROL 可以查看]**&#x200B;角色，他们将获得&#x200B;**[!UICONTROL 编辑原始]**&#x200B;项目体验。 |
| 如果收件人打开项目链接，他们会获得什么体验？ | 收件人将获得您在共享模式中为其分配的角色。如果没有为收件人分配角色，并且收件人收到项目的链接（**[!UICONTROL 共享]** > **[!UICONTROL 与 Workspace 用户共享]**，然后在&#x200B;**[!UICONTROL 通过链接共享]**&#x200B;字段旁选择&#x200B;**[!UICONTROL 复制]**），则为其授予默认角色。管理员获得&#x200B;**[!UICONTROL 编辑原件]**&#x200B;角色，非管理员获得&#x200B;**[!UICONTROL 编辑副本]**&#x200B;角色。 |
