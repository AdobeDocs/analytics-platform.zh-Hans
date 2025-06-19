---
description: 了解如何评论Analysis Workspace中的项目
title: 在项目中添加和查看注释
feature: Workspace Basics
role: User
exl-id: 05f69a1c-31c2-40d8-ae8b-a084169897b1
source-git-commit: 91ac84764a186d81f3270bb3ec9673d93b11bd38
workflow-type: tm+mt
source-wordcount: '1857'
ht-degree: 0%

---

# 在项目中添加和管理注释 {#comment-on-projects}

{{release-limited-testing}}

Analysis Workspace中的评论允许您在Analysis Workspace项目的上下文中共享见解和提问。 这可以简化有关数据的讨论，使对话与正在讨论的数据保持同步。

>[!NOTE]
>
>可以在项目级别或组织级别禁用在项目中添加和管理注释的功能。 如果您无法按本节所述添加和管理注释，则Customer Journey Analytics管理员或项目所有者已禁用此功能。
>
>* **项目：**&#x200B;项目所有者可以为项目禁用此功能，如[创建项目](/help/analysis-workspace/build-workspace-project/create-projects.md)中所述。
>* **组织：** Customer Journey Analytics管理员可以为组织禁用此功能，如[首选项](/help/analysis-workspace/user-preferences.md)中所述。

## 查看评论

您可以在右边栏的注释区域或注释标记（如果存在）中查看注释。

>[!NOTE]
>
>必须先保存项目，才能在右边栏中显示注释区域。 如果项目以前未保存，您需要[保存项目](/help/analysis-workspace/build-workspace-project/save-projects.md)才能添加注释。


![在Analysis Workspace中查看评论](assets/workspace-comments-view.png)

### 在注释区域查看注释

在Analysis Workspace项目中所做的所有注释都将显示在右边栏的注释区域中。 现有注释的总数将显示在注释图标上。

1. 默认情况下，当您首次打开项目时，Analysis Workspace中每个项目的注释区域都会展开。

   选择项目右边栏中的注释区域图标以打开或关闭注释区域。

   ![评论区域已关闭](assets/comments-area-closed.png)

   每个评论都显示一个时间戳，表明发表评论的日期。 如果评论是在当天发布，则显示当天的时间。 将鼠标悬停在显示发表评论的完整日期和时间的日期或时间上。

1. （可选）要搜索注释区域，请选择搜索图标![搜索图标](assets/comments-search-icon.png)，然后键入单词或短语。 过滤注释区域以仅包含那些包括该单词或短语的注释。

### 在项目中查看评论徽章

在项目](#comment-on-a-specific-area-of-the-project)的特定区域上作出[的评论具有在评论所属的项目区域上显示的&#x200B;**评论徽章** ![评论徽章](assets/comment-indicator.svg)。 选择徽章以查看评论。 选择徽章后，您可以选择注释本身以在右边栏的注释区域中突出显示注释。

编号显示在项目中的每个徽章上，并且按照其创建顺序排序。 如果在项目的同一区域中有多个评论，则该徽章显示3个点![评论徽章多个](assets/comment-indicator-multiple.svg)。 选择3点徽章以显示该区域中的所有注释。

<!-- Insert screeshot-->

要从项目中隐藏所有评论徽章，请执行以下操作：

1. 在Analysis Workspace中打开项目后，选择Analysis Workspace右边栏中的注释区域图标![注释区域图标](/help/assets/icons/Comment.svg)。

1. 在注释区域底部，启用选项&#x200B;**[!UICONTROL 隐藏置入的徽章]**。

## 添加评论

您可以添加引用项目特定区域的注释，也可以添加常规注释。

### 对项目特定区域的评论

要评论项目的特定区域（如自由格式表中的量度值），请执行以下操作：

1. 在Analysis Workspace中打开项目后，右键单击要插入注释的项目区域。

   所有可视化都支持在可视化标题上使用评论徽章，但只有以下可视化支持在可视化中的特定数据点上使用评论徽章：

   * 自由格式表
   * 同类群组表
   * 线形图

   <!--add screenshot-->

1. 选择&#x200B;**[!UICONTROL 添加评论]**。

1. 在&#x200B;**[!UICONTROL 新评论]**&#x200B;字段中，指定您的评论。

   注释最多可包含15,000个字符，可包括基本标记、超链接、项目符号和编号列表以及表情符号。

1. （可选）通过键入@符号后跟其名称，将您的评论通知其他人。 有关使用@符号通知其他人的详细信息，请参阅[在评论中包含其他人](#include-others-in-a-comment)。

1. 选择&#x200B;**[!UICONTROL 提交]**。

   **评论徽章** ![评论徽章](assets/comment-indicator.png)位于您添加评论的Workspace项目的区域，如[查看项目中的评论徽章](#view-comment-badges-in-a-project)中所述。 该注释也显示在右边栏的注释区域顶部。

### 添加有关项目的一般注释

要在Analysis Workspace中的项目中添加注释，请执行以下操作：

1. 在Analysis Workspace中打开项目后，选择Analysis Workspace右边栏中的注释区域图标![注释区域图标](/help/assets/icons/Comment.svg)。<!-- add screen shot -->

1. 在&#x200B;**[!UICONTROL 新评论]**&#x200B;字段中，指定您的评论。

   注释最多可包含15,000个字符，可包括基本标记、超链接、项目符号和编号列表以及表情符号。

1. （可选）通过键入@符号后跟其名称，将您的评论通知其他人。 有关使用@符号通知其他人的详细信息，请参阅[在评论中包含其他人](#include-others-in-a-comment)。

1. 选择&#x200B;**[!UICONTROL 提交]**。

   评论显示在评论区域的顶部，如[在评论区域](#view-comments-in-the-comments-area)中查看评论中所述。

## 在评论中包含其他人

Analysis Workspace中的评论功能使与他人协作更加容易。

当使用@符号在评论中包含人时，请考虑以下事项：

* 您包括的用户将根据其Adobe Experience Cloud通知设置接收通知。

  有关详细信息，请参阅[接收有关评论的通知](#receive-notifications-about-comments)。

* 您可以在评论中包含组织中有权访问Customer Journey Analytics的任何人，但这样做不会自动授予他们编辑项目的权限。

要在您的评论中包含其他人，请执行以下操作：

1. 键入@符号，然后开始键入要包括的人员的名字、姓氏或电子邮件地址。

   ![标记用户](assets/comments-tag-user.png)

1. 当人员出现在下拉菜单中时，选择该人员的姓名。

## 回复评论

1. 在Analysis Workspace中，打开要添加注释的项目。

1. 选择Analysis Workspace右边栏中的评论区域图标![评论区域图标](/help/assets/icons/Comment.svg)，然后选择您要回复的评论旁边的&#x200B;**[!UICONTROL 回复]**。

   要包含要回复的注释的文本，并将原始文本包裹在引号标记中，请选择要回复的特定注释或回复旁边的3点图标，然后选择&#x200B;**[!UICONTROL 引号回复]**。 引用回复是指示您的评论所引用的评论或回复的好方法。

   或

   在做出评论的面板或可视化图表上选择评论图标，然后选择&#x200B;**[!UICONTROL 回复]**。

1. 在&#x200B;**[!UICONTROL 新评论]**&#x200B;字段中，指定您的评论。

   注释最多可包含15,000个字符，可包括基本标记、超链接、项目符号和编号列表以及表情符号。

1. （可选）通过键入@符号后跟其名称，将您的评论通知其他人。 有关使用@符号通知其他人的详细信息，请参阅[在评论中包含其他人](#include-others-in-a-comment)。

1. 选择&#x200B;**[!UICONTROL 提交]**。

## 接收有关评论的通知

您提及的项目所有者和[特定用户](#include-others-in-a-comment)将根据其Adobe Experience Cloud通知设置接收通知。 默认情况下，这些用户会收到应用程序内通知，该通知显示在Customer Journey Analytics中的[Experience Cloud通知](https://experienceleague.adobe.com/en/docs/core-services/interface/features/account-preferences#view-notifications)图标![Experience Cloud通知图标](assets/experience-cloud-notification.svg)中。

此外，用户还可以通过[订阅电子邮件通知](https://experienceleague.adobe.com/en/docs/core-services/interface/features/account-preferences#subscribe-to-in-app-and-email-notifications)和[订阅Experience Cloud通知](https://experienceleague.adobe.com/en/docs/core-services/interface/features/account-preferences#slack)，将其Slack通知设置配置为接收电子邮件通知和Slack通知。

## 为现有评论放置徽章

如果右侧边栏的评论区域中有评论，但该评论在项目中还没有徽章，则可以添加该徽章。

1. 在Analysis Workspace中打开项目后，选择Analysis Workspace右边栏中的注释区域图标![注释区域图标](/help/assets/icons/Comment.svg)。

1. 选择您要为其放置徽章的评论旁边的更多图标![更多图标](/help/assets/icons/MoreSmallList.svg)，然后选择&#x200B;**[!UICONTROL 放置徽章]**。

1. 选择要为现有评论放置徽章的项目区域。

   **评论徽章** ![评论徽章](assets/comment-indicator.png)放置在您选择的Workspace项目的区域中。 该注释也显示在右边栏的注释区域顶部。

   有关详细信息，请参阅[查看项目中的评论徽章](#view-comment-badges-in-a-project)。

要删除徽章，请执行以下操作：

1. 选择要删除的徽章，然后选择&#x200B;**[!UICONTROL 删除徽章]**。

   徽章将被删除，但仍可在右边栏的注释区域找到注释。

## 移动现有评论的徽章

您可以移动已经为现有评论设置的评论徽章。

1. 在Analysis Workspace中打开项目后，找到要移动的评论的徽章。

1. 右键单击该徽章，然后选择&#x200B;**[!UICONTROL 移动版面]**。

1. 选择要放置徽章的项目区域。

<!-- add section about adding images to comments. will be available at GA. Include that "you can have a maximum of 5 images per comment, and each image can be up to 2 MB." -->

## 复制指向评论的链接

您可以将链接复制到评论并与他人共享该链接。 只有已经拥有项目访问权限的用户才能通过链接访问项目。

要将链接复制到评论，请执行以下操作：

1. 在Analysis Workspace中打开项目后，选择Analysis Workspace右边栏中的注释区域图标![注释区域图标](/help/assets/icons/Comment.svg)。

1. 选择要复制其链接的评论旁边的更多图标![更多图标](/help/assets/icons/MoreSmallList.svg)，然后选择&#x200B;**[!UICONTROL 复制链接]**。

   该链接将会复制到您的系统剪贴板中。 您可以将链接粘贴到电子邮件或其他类型的消息中。

## 复制评论的文本

您可以复制评论的正文并与他人共享。

要复制评论的正文，请执行以下操作：

1. 在Analysis Workspace中打开项目后，选择Analysis Workspace右边栏中的注释区域图标![注释区域图标](/help/assets/icons/Comment.svg)。

1. 选择包含要复制的文本的评论旁边的更多图标![更多图标](/help/assets/icons/MoreSmallList.svg)，然后选择&#x200B;**[!UICONTROL 复制正文文本]**。

   注释的正文文本已复制到系统剪贴板中。

## 喜欢评论

1. 在Analysis Workspace中打开项目后，选择Analysis Workspace右边栏中的注释区域图标![注释区域图标](/help/assets/icons/Comment.svg)。

1. 在要认可的评论下选择&#x200B;**[!UICONTROL 赞]**。

## 删除评论

删除注释时，原始注释以及任何回复或附件也会被删除。

无法恢复已删除的评论。

要删除注释，请执行以下操作：

1. 在Analysis Workspace中打开项目后，选择Analysis Workspace右边栏中的注释区域图标![注释区域图标](/help/assets/icons/Comment.svg)。

1. 选择要删除的评论旁边的更多图标![更多图标](/help/assets/icons/MoreSmallList.svg)，然后选择&#x200B;**[!UICONTROL 删除]**。

1. 再次选择&#x200B;**[!UICONTROL 删除]**&#x200B;以确认删除。

## 解决评论

解析注释时，注释会在注释区域标记为已解析和隐藏。 如果评论有关联的徽章，则该徽章将从项目中移除。

要解决评论，请执行以下操作：

1. 在Analysis Workspace中打开项目后，选择Analysis Workspace右边栏中的注释区域图标![注释区域图标](/help/assets/icons/Comment.svg)。

1. 选择要解析的评论旁边的更多图标![更多图标](/help/assets/icons/MoreSmallList.svg)，然后选择&#x200B;**[!UICONTROL 解析]**。

1. 再次选择&#x200B;**[!UICONTROL 解析]**&#x200B;以确认。

默认情况下，已解决的注释在注释区域中处于隐藏状态。 要显示已解决的注释，请执行以下操作：

1. 选择注释区域中的过滤器图标，然后取消选择&#x200B;**[!UICONTROL 隐藏已解析的注释]**&#x200B;选项。
