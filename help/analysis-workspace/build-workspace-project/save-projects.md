---
description: 了解不同的保存选项，包括“自动保存”、“另存为”、“另存为模板”以及“打开以前的版本”。
title: 保存项目
feature: Workspace Basics
role: User, Admin
exl-id: e8206956-6e24-4a3a-8c3f-8acf1fb9d800
source-git-commit: 1c19c8cb9cad7b4b7938915d04396cc4646a1f32
workflow-type: ht
source-wordcount: '461'
ht-degree: 100%

---

# 保存项目

要保存对项目所做的更改，请转到工作区的&#x200B;**[!UICONTROL 项目]**&#x200B;菜单。在某些情况下，工作区还会自动保存项目。

## 保存项目选项 {#Save}

在&#x200B;**[!UICONTROL 项目]**&#x200B;菜单下，您可以执行不同的保存操作，具体取决于您希望未来以何种方式访问分析。

| 操作 | 描述 |
|---|---|
| **[!UICONTROL 保存]** | 将更改保存到项目。如果项目已共享，项目的收件人也会看到所做的更改。首次保存项目时，系统会提示您提供项目的名称和（可选）描述并添加（可选）标记。 |
| **[!UICONTROL 保存并添加注释]** | 在保存项目之前，添加有关项目中进行了哪些更改的注释。注释与项目版本一起存储，并且在[!UICONTROL 项目] > [!UICONTROL 打开以前的版本]下面可供所有编辑者使用。 |
| **[!UICONTROL 另存为]** | 创建项目副本。原始项目不受影响。 |
| **[!UICONTROL 另存为模板]** | 将您的项目另存为[自定义模板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=zh-Hans)，贵组织可在&#x200B;**[!UICONTROL 项目 > 新建]**&#x200B;下使用该模板 |

![](assets/save-project.png)

## 自动保存 {#Autosave}

每两分钟会将现有项目（即，以前至少保存过一次的项目）自动保存到本地计算机。目前，不会自动保存从未保存过的新项目。

有一些情形可能会使您离开项目而未保存所做的更改，从而导致不同的可用操作。

### 打开另一个工作区项目

Adobe 提供了在离开页面之前进行保存的选项。离开现有项目后，将删除自动保存的本地副本。

![](assets/existing-save.png)

### 离开或关闭选项卡

浏览器会警告“未保存的更改将会丢失”。您可以选择离开或取消。

![](assets/browser-image.png)

### 浏览器崩溃或会话超时

对于&#x200B;**现有**&#x200B;项目，在返回到工作区时，您将会看到&#x200B;**项目恢复**&#x200B;模式。选择“是”将从自动保存的本地副本中恢复项目。选择“否”将删除自动保存的本地副本并打开用户保存的最近项目版本。

![](assets/project-recovery.png)

对于从未保存的&#x200B;**新**&#x200B;项目，未保存的更改将无法恢复。

## 打开以前的版本 {#previous-version}

>[!NOTE]
>
>以前的项目版本当前属于受限制版本。

要打开以前的项目版本，请执行以下操作: 

1. 转到&#x200B;**[!UICONTROL 项目]** > **[!UICONTROL 打开以前的版本]**

   ![](assets/previous-versions.png)

1. 查看可用的先前版本列表。
   此时会显示[!UICONTROL 时间戳]和[!UICONTROL 编辑者]，如果在[!UICONTROL 编辑者]保存时添加了注释，还会显示[!UICONTROL 注释]。不带注释的版本会存储 90 天；带注释的版本会存储 1 年。
1. 选择以前的版本，并单击&#x200B;**[!UICONTROL 加载]**。
然后，以前的版本会加载并出现一条通知。在单击**[!UICONTROL 保存]**&#x200B;之前，以前的版本不会成为项目的当前保存版本。如果您离开加载的版本，返回时将看到上次保存的项目版本。
