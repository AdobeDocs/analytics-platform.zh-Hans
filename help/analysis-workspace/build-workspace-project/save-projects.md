---
description: 了解不同的保存选项，包括“自动保存”、“另存为”、“另存为模板”以及“打开以前的版本”。
title: 保存项目
feature: Workspace Basics
role: User, Admin
exl-id: d751057e-6a5f-4605-abc1-9259a1f95a28
source-git-commit: ff71d21235bd37da73c0b6c628c395da6cda7659
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 100%

---

# 保存项目

Analysis Workspace 中的项目每 2 分钟自动保存一次。

您也可以手动保存项目。手动保存项目时，可以使用其他选项，例如添加标记或注释。

## 保存项目选项 {#Save}

在 Analysis Workspace 中手动保存项目时可以使用各种选项。

手动保存项目：

1. 在 Analysis Workspace 中打开您的项目，选择&#x200B;**[!UICONTROL 项目]**，然后从以下选项中进行选择：

   | 操作 | 描述 |
   |---|---| 
   | **[!UICONTROL 保存]** | 将更改保存到项目。如果项目已共享，项目的收件人也会看到所做的更改。首次保存项目时，系统会提示您提供项目的名称和（可选）描述并添加（可选）标记。 |
   | **[!UICONTROL 保存并添加注释]** | 在保存项目之前，添加有关项目中进行了哪些更改的注释。注释与项目版本一起存储，并且在[!UICONTROL 项目] > [!UICONTROL 打开以前的版本]下面可供所有编辑者使用。 |
   | **[!UICONTROL 另存为]** | 创建项目副本。原始项目不受影响。 |
   | **[!UICONTROL 另存为模板]** | 将您的项目另存为[自定义模板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=zh-Hans)，贵组织可在&#x200B;**[!UICONTROL 项目 > 新建]**&#x200B;下使用该模板。 |

## 自动保存 {#Autosave}

Analysis Workspace 中的所有项目每 2 分钟自动保存到本地计算机。这包括尚未手动保存的新创建项目。

* **新项目：**&#x200B;尽管新项目是自动保存的，但您必须在第一次手动保存每个新项目。在切换到另一个项目、关闭浏览器选项卡等时，Analysis Workspace 会提示您手动保存新项目。

  如果出于任何原因您在手动保存之前意外失去对新创建项目的访问权限，您的项目的恢复版本将保存在 Analysis Workspace 登录页面上名为`Recovered Projects (Last 7 Days)`的文件夹中。您必须恢复已恢复的项目并将其手动保存到所需位置。

  要恢复已恢复的项目：

   1. 转到 Analysis Workspace 登录页面上的&#x200B;[!UICONTROL **已恢复的项目**]&#x200B;文件夹。

      ![](assets/recovered-folder.png)

   1. 打开您的项目并将其保存到所需位置。


* **现有项目：**&#x200B;如果出于任何原因您离开的项目包含尚未自动保存的更改，Analysis Workspace 会提示您保存更改或提供警告消息。

  以下是一些常见的场景：

### 打开另一个项目

如果您在处理包含尚未自动保存的更改的项目时打开其他项目，Analysis Workspace 会提示您在离开前保存当前项目。

可以使用以下选项：

* **保存：** 用您的最新更改替换项目的最新自动保存的本地副本。
* **另存为：** 将您最近的更改另存为新项目。原始项目仅保存最新的自动保存的更改。
* **放弃更改：**&#x200B;放弃您最近的更改。该项目保留最近自动保存的更改。

![](assets/existing-save.png)

### 离开或关闭选项卡

如果您在查看包含尚未自动保存的更改的项目时离开页面或关闭浏览器选项卡，浏览器会警告您未保存的更改将丢失。您可以选择离开或取消。

![](assets/browser-image.png)

### 浏览器崩溃或会话超时

如果浏览器崩溃或会话超时，则下次访问 Analysis Workspace 时，系统会提示您恢复尚未自动保存的项目更改。

以下是您在崩溃或超时后首次访问 Analysis Workspace 时显示的项目恢复对话框。

选择&#x200B;**是**&#x200B;将从最近自动保存的副本中恢复项目。

选择&#x200B;**否**&#x200B;将删除自动保存的副本并打开项目的最后一个用户保存的版本。

![](assets/project-recovery.png)

对于从未保存的&#x200B;**新**&#x200B;项目，未保存的更改将无法恢复。

## 打开以前的版本 {#previous-version}

要打开以前的项目版本，请执行以下操作: 

1. 转到&#x200B;**[!UICONTROL 项目]** > **[!UICONTROL 打开以前的版本]**

   ![](assets/previous-versions.png)

1. 查看可用的先前版本列表。
   此时会显示[!UICONTROL 时间戳]和[!UICONTROL 编辑者]，如果在[!UICONTROL 编辑者]保存时添加了注释，还会显示[!UICONTROL 注释]。不带注释的版本会存储 90 天；带注释的版本会存储 1 年。
1. 选择以前的版本，并单击&#x200B;**[!UICONTROL 加载]**。
然后，以前的版本会加载并出现一条通知。在单击**[!UICONTROL 保存]**&#x200B;之前，以前的版本不会成为项目的当前保存版本。如果您离开加载的版本，返回时将看到上次保存的项目版本。
