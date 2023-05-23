---
description: Workspace 中的项目共享和项目角色
keywords: Analysis Workspace 共享
title: 共享项目
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
source-git-commit: ec8760cf9984d4e962992f613c4a58a52fa29d47
workflow-type: tm+mt
source-wordcount: '1814'
ht-degree: 52%

---

# 共享项目

您可以與下列人員型別共用Analysis Workspace專案：

* 您組織中有權存取Adobe Customer Journey Analytics的使用者和群組

   您可以共用編輯、複製或檢視存取權

* 您組織中無權存取Customer Journey Analytics的使用者和群組

   收件者具有唯讀存取權

* 組織外部的人員

   收件者具有唯讀存取權

任何 [組織](curate.md) 收件者開啟專案時，會反映您在共用前套用的內容。

下面是项目共享的视频概述：

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)


## 與您組織中的Customer Journey Analytics使用者和群組共用 {#Add}

您可以與組織中的現有Customer Journey Analytics使用者或群組共用專案。 如本節所述，當您共用專案時，與您共用的使用者必須已擁有Customer Journey Analytics帳戶。

您可以与用户或组共享特定角色，也可以共享链接。

* [共享特定的项目角色](#share-a-specific-project-role)

* [共享项目链接](#share-a-link-to-a-project)

## 共享特定的项目角色

与组织中的用户和组共享特定项目角色时，请考虑以下事项：

* 项目角色（**[!UICONTROL 可以编辑]**，**[!UICONTROL 可以复制]**，**[!UICONTROL 可以查看]**）与用户和特定项目 ID 相关联。 项目角色与 [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) 中管理的用户权限无关。

* 在 Customer Journey Analytics 中，组由 [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) 中的产品配置文件定义。管理员可以共享到任何组，包括“全部”组。 除“全部”组外，非管理员可以共享到其所属的任何组。

* 如果用户分配到了多个角色，将始终获得权限最高的角色体验。 如果同时将用户添加为个人和组成员，则可能发生这种情况。 例如，如果作为个人用户获得&#x200B;**[!UICONTROL 可以编辑]**&#x200B;角色，而作为小组成员获得&#x200B;**[!UICONTROL 可以查看]**&#x200B;角色，则用户将获得&#x200B;**[!UICONTROL 可以编辑]**&#x200B;项目体验。

* 具有&#x200B;**[!UICONTROL 可以复制]**&#x200B;或&#x200B;**[!UICONTROL 可以查看]**&#x200B;角色的管理员在打开项目时会获得有限的项目体验。 如有需要，管理员可以随时通过“**[!UICONTROL 组件]”>“[!UICONTROL 项目]**”将其角色提升为&#x200B;**[!UICONTROL 可以编辑]**。

与组织中的用户或组共享特定项目角色：

1. 前往您要共用的專案，然後按一下 **[!UICONTROL 共用]** > **[!UICONTROL 與工作區使用者共用]**.

如果存在未保存的更改，系统将提示您先保存项目。

   ![](assets/share-proj-modal.png)

   有关如何同时共享多个项目的信息，请参阅[在“项目”管理器中共享项目](#share-projects-in-the-project-manager)。

1. 在提供的角色字段之一中添加收件人或收件人组：

   **可以编辑：**&#x200B;收件人可以&#x200B;**[!UICONTROL 保存]**&#x200B;对项目的变更，并且可以行使共有人的权力。 如果您希望与其他同事共同管理项目，则此角色很有用；这包括编辑、删除和修改共享项目的收件人列表。<br>注意：Analysis Workspace 当前不支持实时协作，因此建议在给定时间只让一个用户编辑项目。如果同时保存多个项目，则将保留最后一个版本。

   **可以复制：**&#x200B;收件人可以执行&#x200B;**[!UICONTROL 另存为]**&#x200B;操作，并有权访问左边栏。 在此角色中，项目交互不受限。如果您希望将项目共享给了解您组织数据以及知道如何使用 Analysis Workspace 的用户，但不希望更改项目，则此角色非常有用。

   **可以查看：**&#x200B;收件人无法执行&#x200B;**[!UICONTROL 保存]**&#x200B;或&#x200B;**[!UICONTROL 另存为]**&#x200B;操作，并且不具有访问左边栏的权限。 项目交互受到限制。如果您想要與整體上較不熟悉您的組織資料結構、Analysis Workspace或Customer Journey Analytics的使用者共用專案，此角色會很有用。 但是，您可能仍然希望这些用户在一个安全的环境中使用数据和信息分析。详细了解[“可以查看”角色提供的项目体验](/help/analysis-workspace/curate-share/view-only-projects.md)。

1. 选择共享项目时是否启用以下选项：

   * **共享嵌入的项目组件：**&#x200B;与所有接收人共享区段、计算量度和日期范围。 共享后，这些组件将显示在接收人工作区的“组件”下拉菜单中。此设置不具有持续性，属于分享时的一次性操作。

   * **设置为收件人的登陆页面：** 将此页面设置为收件人的登陆页面。 此设置不具有持续性，属于分享时的一次性操作。

1. 单击&#x200B;**[!UICONTROL 共享]**。(如果專案已共用，請按一下 [!UICONTROL **更新**].)

   或

   按一下 **[!UICONTROL 組織與共用]** 以自動套用專案組織。 (如果專案已共用，請按一下 **[!UICONTROL 監管與更新]**.) 了解有关[项目策划](curate.md)的更多信息。

## 共享项目链接

按本节所述共享链接时，请考虑以下事项：

* 使用連結的收件者必須先登入Customer Journey Analytics，才能存取專案。

* 如果收件人未分配角色，并收到指向项目的[链接](/help/analysis-workspace/curate-share/shareable-links.md)（**[!UICONTROL 共享] > [!UICONTROL 获取项目链接]**），则他们会获得默认角色。 管理員接收 **[!UICONTROL 可以編輯]** 和非管理員會收到 **[!UICONTROL 可以複製]**.

与组织中的用户共享项目链接：

1. 保存项目。如果有未儲存的變更，系統會提示您先儲存專案，然後再共用連結。

1. 選取 **[!UICONTROL 共用]** > **[!UICONTROL 與工作區使用者共用]**，然後選取 **[!UICONTROL 複製]** 旁邊 **[!UICONTROL 透過連結共用]** 欄位。

   ![](assets/share-proj-modal.png)

1. 与组织中的用户共享项目链接。 例如，您可以将其粘贴到电子邮件、内部网站等。

## 與任何人共用專案（不需要登入） {#share-public-link}

{{release-limited-testing-section}}

您可以授予 [唯讀存取](/help/analysis-workspace/curate-share/view-only-projects.md) Analysis Workspace專案給無法存取Customer Journey Analytics的使用者。 這可能包括：

* 組織外部的人員

* 貴組織內未布建Customer Journey Analytics的人員

>[!NOTE]
>
>與無法存取CJA的人共用Analysis Workspace專案時，請考慮下列事項：
>
>* CJA管理員可以停用以這種方式共用專案的功能，如中所述 [偏好設定](/help/analysis-workspace/user-preferences.md). 如果您無法依照本節所述共用專案，您的CJA管理員已停用此功能。
>
>* 超過50個展開視覺效果的專案無法與無法存取CJA的人共用。
>
>* 您共用的使用者可以檢視期間套用到專案的任何篩選器 [組織](curate.md).
> 
>* 您共用的使用者可以變更專案日期範圍。 預設會顯示您為專案設定的日期範圍。
>
>* 如果許多使用者同時嘗試存取指定的連結，專案可能會變成無法存取。 根據預設，每5分鐘可以存取單一連結的人數超過190人。 如果您的組織達到此限制，請等待5分鐘，然後再次嘗試存取連結。


若要與任何人共用Analysis Workspace專案：

1. 開啟您要共用的Analysis Workspace專案。

1. 按一下 **[!UICONTROL 共用]** > **[!UICONTROL 與任何人共用]**.

   如果有未儲存的變更，系統會提示您儲存專案。

   <!-- Add screen shot of new modal -->

1. 啟用 **[!UICONTROL 連結作用中]** 選項（如果尚未啟用）。

   選取此選項會建立專案的連結，可供任何人共用。 您可以隨時停用此選項來停用對專案的存取。

   專案的所有者也是此連結的所有者。 只有在專案所有權轉移時，才能將連結所有權轉移給其他使用者，如中所述 [轉移使用者資產或設定帳戶有效期](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/user-product-management/users-assets.html?lang=en) （在Analytics管理指南中）。

1. 選擇是否啟用以下安全性選項（此選項可由您的CJA管理員控制）：

   * **[!UICONTROL 需要 Experience Cloud 身份验证]:**

      啟用此選項後，只有可登入您共用專案所在的Adobe Experience Cloud組織的使用者才能存取該專案。

      CJA管理員可以為公司設定此偏好設定，如中所述 [偏好設定](/help/analysis-workspace/user-preferences.md). 您可能會遇到以下情況，具體取決於管理員如何設定此選項：

      * 如果未顯示此選項，您的CJA管理員未啟用此功能。

      * 如果此選項已啟用且變暗，您的CJA管理員需要對存取Analysis Workspace專案的任何人進行Experience Cloud驗證。

1. 旁邊 **[!UICONTROL 與任何人共用（不需要登入）]** 欄位，按一下 **複製連結** 圖示 ![複製連結圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Link_18_N.svg))，以將連結複製到您的系統剪貼簿。

1. 與您要存取專案的人共用連結。 例如，您可以貼上電子郵件中的連結。

   您共用連結的任何人都可以檢視Analysis Workspace專案。

1. （可選）您可以按一下 **產生新連結** 圖示 ![產生連結圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) 移除先前收到專案連結之使用者的存取權。 系統會產生新連結，您可將其與您要存取專案的使用者共用。

1. 選取 **[!UICONTROL 關閉]** 關閉「共用」對話方塊。 您的變更會自動儲存。

## 在项目管理器中共享项目 {#Manager}

还可以通过&#x200B;**[!UICONTROL 组件] > [!UICONTROL 项目]**&#x200B;来共享项目。可以按照上述相同步骤共享单个项目。如果选择共享多个项目，则会将收件人添加到每个项目的现有收件人列表中。

例如：

* 项目 A 共享给收件人 1、2、3
* 项目 B 共享给收件人 4、5、6

选择项目 A 和 B 后，将收件人 4 和 7 添加到共享列表。现在，每个项目的新共享列表为：

* 项目 A：1、2、3、4、7
* 项目 B：4、5、6、7

![](assets/mult-proj-sharing.png)

## 共享嵌入的组件

以下是一段关于该主题的视频：

>[!VIDEO](https://video.tv.adobe.com/v/24713/?quality=12)

## 常见问题解答 {#FAQs}

| 问题 | 回答 |
|---|---|
| 如果两位编辑者同时保存一个项目，会发生什么情况？ | 将不会合并更改，并将保留最后保存的项目版本。Analysis Workspace 当前不支持实时协作。 |
| 作为管理员，我将获得什么样的项目体验？ | 具有&#x200B;**[!UICONTROL 可以复制]**&#x200B;或&#x200B;**[!UICONTROL 可以查看]**&#x200B;角色的管理员在打开项目时将获得有限的项目体验。如有需要，管理员可以随时通过&#x200B;**[!UICONTROL 组件] > [!UICONTROL 项目]**&#x200B;将其角色提升为&#x200B;**[!UICONTROL 可以编辑]**。 |
| 如果一位收件人作为个人和作为小组成员分别有不同的角色，会发生什么情况？ | 如果收件人同时具有多个角色，他们将始终获得权限最高的角色体验。例如，如果作为个人收件人获得&#x200B;**[!UICONTROL 可以编辑]**&#x200B;角色，而作为小组成员获得&#x200B;**[!UICONTROL 可以查看]**&#x200B;角色，则收件人将获得&#x200B;**[!UICONTROL 可以编辑]**&#x200B;项目体验。 |
| 如果收件人打开项目链接，他们会获得什么体验？ | 收件人将获得您在共享模式中为其分配的角色。收件者若未被指派任何角色，且收到專案的連結(**[!UICONTROL 共用]** > **[!UICONTROL 與工作區使用者共用]**，然後選取 **[!UICONTROL 複製]** 旁邊 **[!UICONTROL 透過連結共用]** 欄位)，則預設會將其置於角色中。 管理员将获得&#x200B;**[!UICONTROL 可以编辑]**&#x200B;角色，非管理员将获得&#x200B;**[!UICONTROL 可以复制]**&#x200B;角色。 |
