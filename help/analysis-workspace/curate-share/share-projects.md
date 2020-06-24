---
description: Workspace中的项目共享和项目角色
keywords: Analysis Workspace sharing
title: 共享Workspace项目
translation-type: tm+mt
source-git-commit: 92dfb091a004ca7403f67e3f16527ea1e39cd01a
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 7%

---


# 共享Workspace项目

>[!NOTE] 您正在查看Customer Journey Analytics中的Analysis Workspace文档。 其功能集与传统Adobe [Analytics的Analysis Workspace略有不同](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html)。 [了解更多...](/help/getting-started/cja-aa.md)

共享使项目可供组织中的其他Analysis Workspace用户使用。 在收件人 [打开](curate.md) 项目时，您所应用的任何特选内容都会反映出来。

## 项目角色 {#Roles}

您可以向三个项目角色中的一个添加收件人。 项目角色与用户和特定项目ID关联。 项目角色独立于在Adobe Experience Cloud管理控制台 [中管理的用户权限](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/manage-users-and-products/admin-getting-started.html)。

| 角色 | 项目控制 |
|---|---|
| 可以编辑 | 收件人可以对项目的变更执行“保存”操作，并且可以行使共有人的权力。如果您希望与其他同事共同编辑项目，此角色非常有用。<br>注意： Analysis Workspace当前不支持实时协作，因此建议在给定时间只有一个用户编辑项目。 如果同时保存项目，则保留最后一个版本。 |
| 可以复制 | 收件人可以另存为并有权访问左边栏。 项目交互不限于此角色。 如果您希望将项目共享给了解组织数据以及如何使用Analysis Workspace的用户，但不希望更改项目，则此角色非常有用。 |
| 可以查看 | 收件人不能另存为，也无权访问左边栏。 项目交互也很有限。 如果您希望将项目共享给不太熟悉您组织的数据结构、Analysis Workspace或AdobeAnalytics的用户，则此角色非常有用。 但是，您仍希望他们在一个安全的环境中使用数据和洞察。<br>进一步了解 [Can视图项目体验](/help/analysis-workspace/curate-share/view-only-projects.md)。 |

### 未分配角色

如果收件人未分配角色，并收到指向项目的链接(“共&#x200B;**[!UICONTROL 享]”>“获[!UICONTROL 取项目链接]**”)，则默认情况下，这些视图将被置于“ **** Can”角色中。

### 分配了多个角色

如果收件人被置于多个角色，他们将始终获得最高体验。 如果将用户添加为个人和组的一部分，则可能会发生这种情况。 例如，如果用户以个人身份 **[!UICONTROL 获得]** “可以编辑”角色， **[!UICONTROL 以组成员身份获得]** “可以视图 **[!UICONTROL ”角色，则用户将获得“可以]** 编辑”项目体验。

### 管理员和角色

处于Can重复 **[!UICONTROL 或]** Can视图 **[!UICONTROL 角色的管理员在打开项目时]** ，将会收到这些有限的体验。 如果需要，管理员可以通过“组件”>“项 **[!UICONTROL 目”]** ，随时将 **[!UICONTROL 其角色增]加到Can[!UICONTROL edit]**（可编辑）。

## 向共享项目添加收件人 {#Add}

向共享项目添加收件人:

1. 单击 **[!UICONTROL 共享]** > **[!UICONTROL 共享项目]**。
如果存在未保存的更改，将提示您先保存项目。
1. 添加收件人或用户组。
有关每个角色的说明，请参考顶部的帮助图标。
1. （可选）与所有收件人共享嵌入式项目组件（区段、计算指标和日期范围）。
共享后，这些组件将显示在收件人工作区的“组件”下拉框中。 请注意，此设置不会持续存在——它在共享时是单个操作。
1. （可选）将此页设置为收件人的登陆页。
此设置不具有持续性，在分享时，它是独立的操作。
1. 单击共享。您还可以单击“特 **[!UICONTROL 选”和“共享]** ”以自动应用项目特选。 如果某个项目已共享，则这些按钮将显示“ **[!UICONTROL 更新]** ” **[!UICONTROL 和“特选和更新”]**。 进一步了解 [项目特选](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/curate-share/curate.html)。

![](assets/share-proj-modal.png)

## 共享到收件人组 {#Groups}

所有用户都可以将项目共享到组，组是收件人的集合。 在AdobeAnalytics，组由Adobe Experience Cloud管理控制台中的产 [品用户档案定义](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/manage-users-and-products/admin-getting-started.html)。

* 管理员可以共享到任何组，包括“全部”。
* 除“全部”外，非管理员可以共享给他们所属的组。

## 在项目经理中共享项目 {#Manager}

还可以从“组件”>“项 **[!UICONTROL 目”]共[!UICONTROL 享项目]**。 可以按照上述相同步骤共享单个项目。

如果选择共享多个项目，则会将收件人添加到每个项目的现有收件人列表。 例如：

* 项目A共享给用户1、2、3
* 项目B共享给用户4、5、6
* 选择项目A和B后，用户4和7将添加到收件人列表。 现在，每个项目的新收件人列表为：
   * 项目A: 1, 2, 3, 4, 7
   * 项目B: 4, 5, 6, 7

   ![](assets/mult-proj-sharing.png)

## 常见问题解答 {#FAQs}

| 问题 | 回答 |
|---|---|
| 如果两个编辑同时保存一个项目，会发生什么情况？ | 更改不会合并，并保留上次保存的项目版本。 Analysis Workspace当前不支持实时协作。 |
| 作为管理员，我将看到哪些项目体验？ | 处于Can重复 **[!UICONTROL 或]** Can视图 **[!UICONTROL 角色的管理员在打开项目时]** ，将会收到这些有限的体验。 如果需要，管理员可以通过“组件”>“项 **[!UICONTROL 目”]** ，随时将 **[!UICONTROL 其角色增]加到Can[!UICONTROL edit]**（可编辑）。 |
| 如果用户以个人身份被置于一个角色中而以组成员身份被置于另一个角色，会出现什么情况？ | 如果收件人被置于多个角色，他们将始终获得更高的体验。 例如，如果用户以个人身份 **[!UICONTROL 获得]** “可以编辑”角色， **[!UICONTROL 以组成员身份获得]** “可以视图 **[!UICONTROL ”角色，则用户将获得“可以]** 编辑”项目体验。 |
| 当用户获得项目链接时，为何会获得仅视图体验？ | 如果收件人未分配角色，并收到指向项目的链接(“共&#x200B;**[!UICONTROL 享]”>“获[!UICONTROL 取项目链接]**”)，则默认情况下，这些视图将被置于“ **** Can”角色中。 如果用户希望增加项目角色，项目所有者或编辑者可以通过项目共享模式将其添加到“可以”重复或“可以”编辑角色。 |
