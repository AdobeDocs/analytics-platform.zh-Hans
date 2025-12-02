---
description: 了解如何在 Analysis Workspace 中使用和管理项目。使用项目管理器可对项目进行创建、删除、移动、共享、审批、固定、复制和添加标记等管理操作。
keywords: Analysis Workspace
title: 项目概述
feature: Workspace Basics
exl-id: 2eeb615c-57a1-4469-8d4a-8a61956bd6e6
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1684'
ht-degree: 100%

---

# 项目概述

通过 Workspace 项目，可将面板、可视化图表和组件组合起来，以得出您的分析结果，并与您组织中的任何人共享。在开始您的第一个项目之前，请了解如何访问、浏览和管理您的项目。

要访问 Customer Journey Analytics 中的项目，请选择&#x200B;**[!UICONTROL 工作区]**。**[!UICONTROL 项目]**&#x200B;管理器列出了您拥有的所有项目或与您共享的项目。带有项目列表的项目管理器也是 Customer Journey Analytics 的默认登录页面，除非您在“偏好设置”中另有配置。

![显示项目列表的项目登陆页面。](assets/projects.png)


## 标题区

在标题区域 ➊ 内，您可以创建一个项目，创建一个文件夹，编辑您的偏好设置以及显示或隐藏带有附加图块的面板。

* 要显示或隐藏左侧面板，以便您在&#x200B;**[!UICONTROL 项目]**&#x200B;和&#x200B;**[!UICONTROL 学习]**&#x200B;之间进行选择，请选择![边栏](/help/assets/icons/Rail.svg)。
* 标题会显示“项目”，并可选择性地带有您所选文件夹的路径。例如[!UICONTROL 项目] > **[!UICONTROL 公司文件夹]**。您可以选择单个子文件夹部分，以直接跳转到特定文件夹。
* 要显示[**[!UICONTROL 空白项目]**](create-projects.md)、[**[!UICONTROL 空白移动记分卡]**](/help/mobile-app/create-scorecard.md)、[**[!UICONTROL 引导式分析]**](/help/guided-analysis/overview.md)、**[!UICONTROL 打开文档]**&#x200B;和&#x200B;**[!UICONTROL 打开发行说明]**&#x200B;的图块，请选择 ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 显示更多]**。要隐藏带有图块的区域，请选择 ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 显示更少]**。
* 根据您使用[显示选择器](#show-selector)选择要显示的内容，您可以编辑偏好设置，并对&#x200B;**[!UICONTROL 项目]**&#x200B;中当前可见的文件夹执行操作：

  | 操作 | 描述 |
  |---|---|
  | **[!UICONTROL 创建项目]** | 选择以[创建新项目](create-projects.md)。 |
  | **[!UICONTROL 创建文件夹]** | 选择以[创建新文件夹](workspace-folders/create-folders.md)。 |
  | ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL 编辑偏好设置]** | 为所有项目[编辑偏好设置](/help/analysis-workspace/user-preferences.md)。当痕迹导航导致空间有限时，此操作会作为![更多](/help/assets/icons/More.svg)子菜单的一部分。 |
  | **[!UICONTROL 添加项目]** | 选择以在当前文件夹中[添加项目](workspace-folders/add-projects.md)。当痕迹导航导致空间有限时，此操作会作为![更多](/help/assets/icons/More.svg)子菜单的一部分。 |
  | **[!UICONTROL 重命名文件夹]** | [重命名](workspace-folders/manage-folders.md#rename-folders)当前文件夹。 |
  | **[!UICONTROL 移动文件夹]** | [移动](workspace-folders/manage-folders.md#move-folders)当前文件夹。 |
  | **[!UICONTROL 删除文件夹]** | [删除](workspace-folders/manage-folders.md#delete-folders)当前文件夹。 |




## 项目列表


项目列表 ➋ 显示您拥有的所有项目，以及与您共享的所有项目。该列表具有以下各列：

| 列 | 描述 |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | 当选择一个或多个项目时，项目界面底部会出现一个蓝色的操作栏。有关更多详细信息，请参阅[操作](#actions)。 |
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 选择以加入收藏 ![Star](/help/assets/icons/Star.svg) 或取消收藏 ![StarOutline](/help/assets/icons/StarOutline.svg) 一个项目。 |
| **[!UICONTROL 标题和描述]** | 要编辑项目，请选择标题链接，这会打开[工作区项目](/help/analysis-workspace/home.md)。与您共享的项目会以 ![分享](/help/assets/icons/ShareAlt.svg) 标示。选择 ![InfoOutline](/help/assets/icons/InfoOutline.svg) 以显示一个弹出菜单，其中包含有关该项目的更多详细信息。选择![更多](/help/assets/icons/More.svg)以打开带有操作选项的上下文菜单。有关更多详细信息，请参阅[操作](#actions)。 |
| **[!UICONTROL Type]** | 工作区项目，![FolderUser](/help/assets/icons/FolderUser.svg) 文件夹，或者[移动记分卡](/help/mobile-app/home.md)。 |
| **[!UICONTROL 标记]** | 应用于项目的标记。 |
| **[!UICONTROL 已计划]** | 是否计划通过电子邮件将项目发送给收件人。相关选项包括 ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 开启]**&#x200B;或者 ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 关闭]**。请参阅[向其他人发送项目数据](/help/analysis-workspace/export/t-schedule-report.md)。 |
| **[!UICONTROL 共享链接（任何人）]** | 是否与任何人共享项目，包括无权访问 Analysis Workspace 的人员。相关选项包括 ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 有效]**&#x200B;或者 ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 无效]**。有关详细信息，请参阅[共享项目](/help/analysis-workspace/curate-share/share-projects.md)中的[与任何人共享项目（无需登录）](/help/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required)。 |
| **[!UICONTROL 项目角色]** | 您在项目中的角色。相关选项包括：编辑、复制、查看。有关更多信息，请参阅[项目角色](/help/analysis-workspace/curate-share/curate.md)。 |
| **[!UICONTROL 数据视图]** | 与项目关联的数据视图。 |
| **[!UICONTROL 所有者]** | 创建此项目的人员（您或与您共享此项目的人员）。 |
| **[!UICONTROL 共享对象]** | 已与其共享该项目的用户。 |
| **[!UICONTROL 上次修改时间]** | 项目上次修改的日期和时间。 |
| **[!UICONTROL 上次打开时间]** | 项目上次打开的日期和时间。 |
| **[!UICONTROL 项目 ID]** | 项目的 ID。 |
| **[!UICONTROL 最长日期范围]** | 项目中任何面板或可视化图表的最长日期范围。 |
| **[!UICONTROL 查询次数]** | 项目中包含的查询总数。 |
| **[!UICONTROL 位置]** | 项目所在的文件夹。 |

将鼠标悬停在任意列标题上即可显示 ![ChevronDown](/help/assets/icons/ChevronDown.svg)，并从上下文菜单中选择：

* **[!UICONTROL 升序排序]**
* **[!UICONTROL 降序排序]**
* **[!UICONTROL 调整列大小]**。一条蓝线会显示，以帮助您调整列的大小。

### 操作

您可以使用上下文菜单![更多](/help/assets/icons/More.svg)或蓝色操作栏对一个或多个项目执行操作。

| 图标 | 操作 | 描述 |
|:---:| ---|---|
| ![CrossSize75](/help/assets/icons/Close.svg) | **[!UICONTROL *x *已选择]** | 取消选择您选择的项目和文件夹，并移除蓝色操作栏。 |
| ![Delete](/help/assets/icons/Delete.svg) | **[!UICONTROL 删除]** | 删除一个或多个项目或文件夹。系统将提示您确认。<p>您要删除的项目：</p><ul><li>无法恢复</li><li>从项目列表中移除</li><li>无法再通过其 URL 访问</li><li>不再包含在计划交付中（如果之前已配置为计划交付）<br/>有关计划交付的信息，请参阅 [计划项目](/help/components/scheduled-projects-manager.md)。  </p> |
| ![Share](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL 共享]** | 共享项目。请参阅[共享项目](/help/analysis-workspace/curate-share/share-projects.md)，以了解更多信息。 |
| ![Edit](/help/assets/icons/Edit.svg) | **[!UICONTROL 重命名]** | 重命名项目。打开&#x200B;**[!UICONTROL 重命名：*项目名称对话框&#x200B;*]**。输入新名称并选择**[!UICONTROL 保存&#x200B;]**。 |
| ![Copy](/help/assets/icons/Copy.svg) | **[!UICONTROL 复制]** | 复制一个或多个项目。相关会获得相同的名称和后缀 `(Copy)`。 |
| ![PinOnff](/help/assets/icons/PinOff.svg) | **[!UICONTROL 固定]**&#x200B;或者&#x200B;**[!UICONTROL 取消固定]** | 固定或取消固定一个或多个项目或文件夹。固定的项目和文件夹会在列表顶部显示，并忽略您指定的排序顺序。 |
| ![ArrowUp](/help/assets/icons/ArrowUp.svg) | **[!UICONTROL 上移]** | 将固定的项目或文件夹在项目列表中上移。 |
| ![ArrowDown](/help/assets/icons/ArrowDown.svg) | **[!UICONTROL 下移]** | 将固定的项目或文件夹在项目列表中下移。 |
| ![Label](/help/assets/icons/Label.svg) | **[!UICONTROL 标记]** | 标记一个或多个项目或文件夹。**[!UICONTROL 标记组件]**&#x200B;对话框会显示，以选择一个或多个标记。选择&#x200B;**[!UICONTROL 保存]**&#x200B;来保存所选项目或文件夹的标记。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL 批准]**&#x200B;或者&#x200B;**[!UICONTROL 拒绝]** | 批准或拒绝项目。只有管理员可以批准项目。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL 导出 CSV]** | 将选定的项目导出到名为 `Project List.csv` 的 CSV 文件中。 |
| ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) | **[!UICONTROL 添加项目]** | 将一个或多个项目添加到选定文件夹。在&#x200B;**[!UICONTROL 添加项目]**&#x200B;中，您可以选择一个或多个项目。选择&#x200B;**[!UICONTROL 添加]**，将这些项目添加到文件夹中。请参阅[在文件夹中添加项目](workspace-folders/add-projects.md#from-inside-a-folder)，以了解更多信息。 |
| ![FolderAddTo](/help/assets/icons/FolderAddTo.svg) | **[!UICONTROL 移动到]** | 将一个或多个选定的项目移动到文件夹。在&#x200B;**[!UICONTROL 选择文件夹]**&#x200B;中，选择要将选定项目移动到的文件夹，然后选择&#x200B;**[!UICONTROL 移动]**。请参阅[在文件夹中添加项目](workspace-folders/add-projects.md#from-the-project-list)，以了解更多信息。 |



## 显示选择器

您可以使用&#x200B;**[!UICONTROL 显示]**&#x200B;选择器 ➌ 来切换项目界面的外观。**[!UICONTROL 显示]**&#x200B;选择器定义了[标题区域](#title-area)中可用的选项，以及[项目列表](#project-list)中显示的列。

* 要更改[标题区域](#title-area)可用的选项，请选择&#x200B;**[!UICONTROL 显示]****[!UICONTROL 所有项目]**&#x200B;或&#x200B;**[!UICONTROL 显示]****[!UICONTROL 文件夹和项目]**。

* 要定义在[项目列表](#project-list)中显示哪些列，请选择 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg)，然后从&#x200B;**[!UICONTROL 自定义表格]**&#x200B;对话框中选择或取消选择列。选择&#x200B;**[!UICONTROL 应用]**&#x200B;以应用自定义设置。有关列的更多详细信息，请参阅[项目列表](#project-list)。

## 过滤器面板

您可以使用过滤器面板 ➍ 过滤[项目列表](#project-list)中的项目和文件夹。要显示或隐藏过滤器面板，请使用![过滤器](/help/assets/icons/Filter.svg)。

过滤器面板由以下部分组成。

### 标记

| 标记 | 描述 |
|---|---|
| ![标记](/help/analysis-workspace/build-workspace-project/assets/projects-filters-tags.png){width="300"} | 您可以使用&#x200B;**[!UICONTROL 标记]**&#x200B;部分按标记进行过滤。 <ul><li>您可以使用 ![搜索](/help/assets/icons/Search.svg) *搜索标记*&#x200B;来搜索您想要用于过滤的标记。</li><li>您可以选择多个标记。可用的标记取决于在过滤器面板中对其他部分的选择。</li><li>这些数字表明：<ul><li>**2︎⃣**：当前过滤器生成的项目可用的标记数量。</li><li>7︎⃣：与特定标记相关的项目数量。</li></ul></li></ul> |


### 数据视图

| 数据视图 | 描述 |
|---|---|
| ![数据视图](/help/analysis-workspace/build-workspace-project/assets/projects-filters-dataviews.png){width="300"} | 您可以使用&#x200B;**[!UICONTROL 数据视图]**&#x200B;部分来过滤数据视图。 <ul><li>您可以使用 ![搜索](/help/assets/icons/Search.svg) *搜索数据视图*&#x200B;来搜索您想要用于过滤的数据视图。</li><li>您可以选择多个数据视图。可用的数据视图取决于在过滤器面板中对其他部分的选择。</li><li>这些数字表明：<ul><li>**3︎⃣**：当前过滤器生成的项目可用的数据视图数量。</li><li>4︎⃣：与特定数据视图相关的项目数量。</li></ul></li></ul> |


### 所有者

| 所有者 | 描述 |
|---|---|
| ![所有者](/help/analysis-workspace/build-workspace-project/assets/projects-filters-owners.png){width="300"} | **[!UICONTROL 所有者]**&#x200B;部分允许您过滤所有者。 <ul><li>您可以使用 ![搜索](/help/assets/icons/Search.svg) *搜索所有者*&#x200B;来搜索您想要用于过滤的所有者。</li><li>您可以选择多个所有者。可用的所有者取决于在过滤器面板中对其他部分的选择。</li><li>这些数字表明：<ul><li>**3︎⃣**：当前过滤器生成的项目可用的所有者数量。</li><li>4︎⃣：与特定所有者相关的项目数量。</li></ul></li></ul> |


### 类型

| 类型 | 描述 |
|---|---|
| ![Type](/help/analysis-workspace/build-workspace-project/assets/projects-filters-type.png){width="300"} | **[!UICONTROL 类型]**&#x200B;部分允许您根据项目或文件夹的类型进行筛选。<ul><li>您可以选择以下一个或多个选项：<ul><li> **[!UICONTROL 文件夹]**</li><li>**[!UICONTROL 工作区项目]**</li><li>**[!UICONTROL 移动记分卡]**</li></ul> <li>您可以选择多个其他过滤器。可用的其他过滤器取决于在过滤器面板中对其他部分的选择。</li><li>这些数字表明：<ul><li>**5︎⃣**：当前过滤器生成的项目可用的其他过滤器数量。</li><li>4︎⃣：与特定其他过滤器相关的项目数量。</li></ul></li></ul> |


### 其他过滤器

| 其他过滤器 | 描述 |
|---|---|
| ![其他过滤器](/help/analysis-workspace/build-workspace-project/assets/projects-filters-others.png){width="300"} | 您可以使用&#x200B;**[!UICONTROL 其他过滤器]**&#x200B;部分按其他预定义过滤器进行过滤。<ul><li>您可以选择以下一个或多个选项：<ul><li> **[!UICONTROL 显示所有]**</li><li>**[!UICONTROL 与我共享]**</li><li>**[!UICONTROL 我的]**</li><li>**[!UICONTROL 已批准]**</li><li>**[!UICONTROL 收藏夹]**</li></ul> 您可以选择的内容取决于您的角色和权限。</li><li>您可以选择多个其他过滤器。可用的其他过滤器取决于在过滤器面板中对其他部分的选择。</li><li>这些数字表明：<ul><li>**5︎⃣**：当前过滤器生成的项目可用的其他过滤器数量。</li><li>4︎⃣：与特定其他过滤器相关的项目数量。</li></ul></li></ul> |

## 搜索

您可以使用搜索区域 ➎ 通过![搜索](/help/assets/icons/Search.svg)字段来搜索项目和文件夹。开始输入后，[项目列表](#project-list)将会自动过滤您的搜索输入。

搜索区域还会显示从过滤器面板中应用的过滤器。

* 要移除过滤器，请选择过滤器中的 ![CrossSize75](/help/assets/icons/CrossSize75.svg)。
* 要移除所有过滤器，请选择“全部清除”。

如果空间有限，无法显示单个过滤器，您会看到&#x200B;**[!UICONTROL 按 *x* 分段的过滤器]**。

* 要移除过滤器：

   1. 使用 **[!UICONTROL *x *过滤器]**![ChevronDown](/help/assets/icons/ChevronDown.svg) 顶部打开一个上下文菜单，其中列有过滤器的类型和单个过滤器。
   1. 使用 ![CrossSize75](/help/assets/icons/CrossSize75.svg) 来移除过滤器。


<!--

The Projects page contains the following information: 

>[!NOTE]
>
>Some columns are not displayed by default. To customize the columns you see, click the **Customize table** icon ![Customize table](assets/projects-page-customize-columns-icon.png).

|  Element  | Description  |
|---|---|
| [Edit preferences](/help/analysis-workspace/user-preferences.md) | Manage settings for Analysis Workspace and its related components for all new projects or panels that you create.  |
| [Create folder](/help/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)  | Add a new folder or subfolder to the list of projects and folders. |
| [Create project](/help/analysis-workspace/build-workspace-project/create-projects.md)  | Start a new project from scratch.  |
|  Show more  |Reveals options for creating a blank project or mobile scorecard, [viewing training tutorials](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction.html?lang=zh-Hans), or [viewing release notes](/help/release-notes/latest.md).  |
| Show Folders & Projects| Choose whether to show the folder structure of projects. For more information, see [About Folders in Analytics](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
|  Customize table (icon)  | Allows you to customize the information that shows for each project on the Projects page.  |
|  Name  | Name of the Workspace project.  |
| Type | Indicates whether this is a Workspace Project, a folder, or a [Mobile Scorecard](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html?lang=zh-Hans). |
|  Tags  |Tags that were applied to the project.  |
| Scheduled | Indicates whether projects are scheduled to be emailed to recipients on a schedule. See [Send project data to others](/help/analysis-workspace/export/t-schedule-report.md). |
| Shared link (anyone) | Projects can be shared with anyone--even with people who don't have access to Analysis Workspace. This column shows whether projects have been shared in this way. See [Share a project with anyone (no login required)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Share projects](/help/analysis-workspace/curate-share/share-projects.md) for more information. |
| Data view | The data view that the project is associated with. |
| [Project Role](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=zh-Hans) | Indicates your role for the project - owners, edit, duplicate, view. |
|  Owner  | The person who created this project (either you or someone who shared the project with you.)  |
|  Shared with  | Users that the project has been shared with.  |
|  Last Modified  | Date and time when the project was last modified.  |
|  Last Opened  | Date and time when the project was last opened.  |
|  Project ID  | The ID of the project.  |
|  Longest Date Range  | The longest date range of the project.  |
|  Number of Queries  | The total number of queries contained in the project.  |
|  Location  | The folder where the project resides.  |

## Menu bar {#menu-bar}

Within a project, the menu provides options for managing your project, adding components, finding help, and more. Each menu option can also be accessed by keyboard [shortcuts](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![New Project options including the Project, Edit, Insert, Components, Share, and Help options.](assets/menu.png)

|  Menu item  | Description  |
|---|---|
|  Project  | Includes common actions for project management, including New, Open, Save, and Save As. You can also refresh the entire project to retrieve the most recent data and definitions by clicking Refresh Project. [Download project data](/help/analysis-workspace/export/download-send.md) options enable you to export data from Workspace. **Project Info & Settings** (see below) offers many options for managing your project.  |
|  Edit  | Undo or redo your last action. Clear All will reset your project to a blank starting point. |
|  Insert  | Insert new panels or visualizations from this menu. You can also insert new panels and visualizations from the left panel.  |
|  [Components](/help/components/overview.md)  | Create new segments, calculated metric, date range, or alert components from your project. You can also create new components from the left panel. If your component definitions have recently changed, Refresh Components will retrieve the latest definitions. |
|  [Share](/help/analysis-workspace/curate-share/send-schedule-files.md)  | Curate, share and schedule PDF/CSV projects to recipients in your organization.  |
|  Help  | Access help documentation, videos, and the Analytics [Experience League community](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community). Manage the visibility of Workspace tips as well as the [debugger](https://experienceleague.adobe.com/zh-hans/docs/analytics-learn/tutorials/apis/using-analysis-workspace-to-build-api-2-requests). Find details about Workspace and factors that impact project [performance](/help/technotes/optimizing-performance.md).  |
|  Share button or Owner  | If you are in an Own or Edit for the project, the Share button in the top-right gives you one-click access to manage your project recipients. If you are in a Duplicate or View role for the project, you will see the project owner's name. |

### Project Info & Settings {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project info & settings]** provides project-level information on the currently active project.

![The Project Info & Settings window.](assets/projectinfo.png)

Settings include:

|  Setting  | Description  |
|---|---|
|  Project Name  | The name given to the project. You can double-click the name to edit it.  |
|  Created By  | Project owner name  |
|  Last Modified  | Date of last modification to the project.  |
|  Tags  |Lists any tags applied to a project for easier categorization.  |
|  Description  | A description is useful for clarifying the purpose of a project. You can double-click the description to edit it.  |
|  Count repeat instances in project  | Specifies whether repeat instances are counted in reports. Note: this setting does not apply to Flow or Fallout visualizations.  |
|  [Project color palette](/help/analysis-workspace/build-workspace-project/color-palettes.md)  | You can change the categorical color palette used in Workspace, by choosing from out-of-the-box palettes that have been optimized for color blindness, or by specifying your custom palette. This feature affects many things in Workspace, including most visualizations.  |
| [View Density](/help/analysis-workspace/build-workspace-project/view-density.md) | Lets you see more data on the screen by reducing the vertical padding of the left panel, freeform tables and cohort tables. |

## Left panel

Within a project, various icons are available in the left panel, and each represents important parts of a project:

* [Panels](/help/analysis-workspace/c-panels/panels.md) ![panels icon](assets/panels-icon.png)

* [Visualizations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)![visualizations icon](assets/visualizations-icon.png)

* [Components](/help/components/overview.md)![components icon](assets/components-icon.png)

* [Data dictionary](/help/components/data-dictionary/data-dictionary-overview.md)![data dictionary icon](assets/data-dictionary-icon.png)

* [Table of contents](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md) ![toc icon](assets/toc-icon.png)

Components (Dimensions, Metrics, Segments, Date Ranges) in the left panel relate to the active panel data view. The active panel is identified by the blue border that surrounds it, and the active data view is listed at the top of the component panel.

![The components relating to the active panel data view for Cross-Industry Demo Data data view.](assets/left-rail.png)

## Project canvas {#canvas}

The project canvas is where you bring together panels, tables, visualizations, and components to build your analysis. A project can contain many panels, and each panel can contain many tables and visualizations.

Panels are helpful when you want to organize your projects according to time periods, data views, or analysis use case. The active panel will have a blue border around it, and determines what components are available in the left panel.

Depending on the starting point you chose for your projects, you will either have a [freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) or a [blank panel](/help/analysis-workspace/c-panels/blank-panel.md) in the canvas to begin with. The quickest way to start analyzing is to select one or many components and simply drag & drop them into the project canvas. A table of data will automatically be rendered for you. [Learn more](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) about the different options for building a table, or leverage our [training tutorial](/help/analysis-workspace/home.md) for more guidance on building your first project.

![A Freeform Table for the project.](assets/canvas.png)

## Project Manager {#manager}

Analysis Workspace projects can be managed under **Analytics > Components >  Projects**. The Project Manager shows the projects that a specific user created. You can transfer project ownership to a new user under Admin > Analytics Users & Assets > Transfer Assets.

In Projects Manager, you can add, tag, share, duplicate/copy, and more. Search for a project in the search bar or by using the filter options in the left panel. You can filter by tag, owners, project type and more.

![Project Manager Tags search field and Title search field.](assets/project-manager.png)

The following are common actions in the Projects manager, and can be taken on one or many projects at once:

|  Action  | Description  |
|---|---|
|  Add  | Create a new project from scratch.  |
|  Tag or Approve  | Choose "Tag" or "Approve" to organize your projects and make them easier to search for.  |
|  [Share](/help/analysis-workspace/curate-share/share-projects.md)  | Make a project available to other Analysis Workspace users in your organization.  |
|  Delete  | Delete your project.  |
|  Rename  | Edit the name of your project.  |
|  Copy  | Create a duplicate copy of your project. This creates a new project and project ID. Any shares or schedules tied to the original project will not be copied. |
|  Export to CSV  | Download your project as a CSV file, which includes plain-text data.  |

-->

