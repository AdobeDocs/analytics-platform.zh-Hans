---
title: 管理数据视图
description: 了解如何管理数据视图。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c5cf15ab-3eb1-4e6b-93a3-3d89694ca0ea
source-git-commit: c7cf7250f30e2f6023aa7690391aea149ba12eff
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 10%

---

# 管理数据视图


在您[创建或编辑一个或多个数据视图](/help/data-views/create-dataview.md)后，您可以在&#x200B;**[!UICONTROL 数据视图]**&#x200B;中管理它们。

从Customer Journey Analytics中的主菜单栏选择&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 数据视图]**。

**[!UICONTROL 数据视图]**&#x200B;界面显示所有可用数据视图的表。

![数据视图界面](/help/data-views/assets/data-views.png)

表中提供以下列和图标：

| 列或图标 | 描述 |
| --- | --- |
| **[!UICONTROL 名称]** | 数据视图的名称。 |
| ![信息](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | 要查看有关数据视图的信息，请选择数据视图名称旁边的![信息大纲](/help/assets/icons/InfoOutline.svg)。<br/>弹出窗口显示有关数据视图的详细信息。 |
| ![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | 选择![更多](/help/assets/icons/More.svg)，打开上下文菜单。您可以选择：<br/>![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**&#x200B;到[编辑](#edit-data-views)数据视图。<br/>![复制](/help/assets/icons/Copy.svg) **[!UICONTROL 复制]**&#x200B;到[复制数据视图](#copy-data-views)。<br/>![删除](/help/assets/icons/Delete.svg) **[!UICONTROL 删除]**&#x200B;以[删除](#delete-data-views)数据视图。<br/>![文件CSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 导出到CSV]**&#x200B;以[将数据视图的详细信息导出到CSV文件](#export-data-views-to-csv)。<br/>![项目添加](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL 创建项目]**&#x200B;以[为数据视图创建新的Workspace项目](#create-project-from-data-views)。<br/>![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 启用Data Insights Agent]**&#x200B;以启用Data Insights Agent的数据视图。<br/>![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL 禁用Data Insights Agent]**&#x200B;以禁用Data Insights Agent的数据视图。 |
| **[!UICONTROL 连接]** | 与数据视图关联的连接的名称。 |
| **[!UICONTROL 沙盒]** | 与数据视图关联的沙盒的名称。 |
| **[!UICONTROL 所有者]** | 数据视图的所有者。 |
| **[!UICONTROL Data Insights Agent]** ![信息大纲](/help/assets/icons/InfoOutline.svg) | 指示数据视图的[Data Insights Agent](/help/data-analysis-ai.md)是&#x200B;**[!UICONTROL 已启用]**&#x200B;还是&#x200B;**[!UICONTROL 已禁用]**。 <br/>选择![信息大纲](/help/assets/icons/InfoOutline.svg)以在数据视图中显示包含&#x200B;**[!UICONTROL Data Insights Agent状态]**&#x200B;的弹出窗口。 <br/>![Data Insights Agent使用情况](/help/data-views/assets/data-views-dia-status.png) |
| **[!UICONTROL 集成]** | 列出与其他解决方案的集成。 例如：Adobe Audience Analysis、Content Analytics、Brand Concierge、Journey Optimizer、GenStudio和使用情况分析。 |
| **[!UICONTROL 在 CJA 中使用]** | 指示是否在Customer Journey Analytics中使用数据视图。 对于在Adobe Journey Optimizer集成中自动生成的数据视图，此值仅为&#x200B;**[!UICONTROL Off]**。 |
| **[!UICONTROL 创建日期]** | 创建数据视图时的时间戳。 |
| **[!UICONTROL 上次修改时间]** | 最近修改数据视图时的时间戳。 |

要配置要在表中显示的列，请选择![ColumnSetting](/help/assets/icons/ColumnSetting.svg)。 在&#x200B;**[!UICONTROL 自定义表]**&#x200B;对话框中，选择要显示的列。 然后选择&#x200B;**[!UICONTROL 应用]**。


## 搜索数据视图

您可以使用![搜索](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg)框快速搜索数据视图。

## 筛选数据视图

要将筛选器应用于数据视图列表，请选择![筛选器](/help/assets/icons/Filter.svg)图标，然后从以下筛选器选项中选择：

| 筛选选项 | 描述 |
|---------|----------|
| **[!UICONTROL 连接]** | 仅显示与您选择的连接相关联的数据视图。 |
| **[!UICONTROL 所有者]** | 仅显示由您选择的人员拥有的数据视图。 |
| **[!UICONTROL 沙盒]** | 仅显示您选择的沙盒中可用的数据视图。 |
| **[!UICONTROL 集成]** | 仅显示具有选定集成的数据视图。 |
| **[!UICONTROL 在 CJA 中使用]** | 选择&#x200B;**[!UICONTROL On]**&#x200B;以仅显示允许与Customer Journey Analytics一起使用的数据视图。 选择&#x200B;**[!UICONTROL 关闭]**&#x200B;可仅显示尚未启用与Customer Journey Analytics配合使用的数据视图。 |


选择![筛选器](/help/assets/icons/Filter.svg) **[!UICONTROL 隐藏筛选器]**&#x200B;以隐藏筛选器窗格。

## 创建数据视图

要[创建新数据视图](/help/data-views/create-dataview.md)，请选择&#x200B;**[!UICONTROL 创建新数据视图]**。


## 编辑数据视图

如果要[编辑数据视图](/help/data-views/create-dataview.md)：

1. 选择数据视图名称旁边的![更多](/help/assets/icons/More.svg)。
1. 从上下文菜单中选择![编辑](/help/assets/icons/Edit.svg)**[!UICONTROL 编辑]**。

或者，您可以：

1. 选择数据视图行。
1. 选择蓝色操作栏中的![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**。


## 复制数据视图

如果要复制数据视图：

1. 选择数据视图名称旁边的![更多](/help/assets/icons/More.svg)。
1. 从上下文菜单中选择![复制](/help/assets/icons/Copy.svg) **[!UICONTROL 复制]**。

或者，您可以：

1. 选择一个或多个数据视图行。
1. 从蓝色操作栏中选择![复制](/help/assets/icons/Copy.svg) **[!UICONTROL 复制]**。

数据视图已复制并添加到列表，其中在名称后附加了&#x200B;**[!UICONTROL （复制）]**。


## 删除数据视图

如果要删除数据视图：

1. 选择数据视图名称旁边的![更多](/help/assets/icons/More.svg)。
1. 从上下文菜单中选择![删除](/help/assets/icons/Delete.svg) **[!UICONTROL 删除]**。

或者，您可以：

1. 选择一个或多个数据视图行。
1. 选择蓝色操作栏中的![删除](/help/assets/icons/Delete.svg) **[!UICONTROL 删除]**。

当您删除一个或多个数据视图时，**[!UICONTROL 删除数据视图]**&#x200B;面板指示受影响的项目。

![删除数据视图](/help/data-views/assets/delete-data-view.png)


* 在➊ **[!UICONTROL 确认]**&#x200B;中，显示了删除数据视图的后果。
* 选择&#x200B;**[!UICONTROL 删除]**&#x200B;以永久删除数据视图。 选择&#x200B;**[!UICONTROL 取消]**&#x200B;即可取消。


## 将数据视图导出到CSV

您可以将数据视图导出到CSV文件。

1. 选择数据视图名称旁边的![更多](/help/assets/icons/More.svg)。
1. 从上下文菜单中选择![文件CSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 导出到CSV]**。

或者，您可以：

1. 选择一个或多个数据视图行。
1. 从蓝色操作栏中选择![文件CSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 导出到CSV]**。

所选数据视图的详细信息将导出到浏览器Downloads文件夹中名为`Data views List (x).csv`的CSV文件。


## 从数据视图创建项目

您可以直接从数据视图界面创建Workspace项目。

1. 选择数据视图名称旁边的![更多](/help/assets/icons/More.svg)。
1. 从上下文菜单中选择![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL 创建项目]**。

或者，您可以：

1. 选择数据视图行。
1. 从蓝色操作栏中选择![ProjectAdd](/help/assets/icons/ProjectAdd.svg) **[!UICONTROL 创建项目]**。


## 启用或禁用Data Insights Agent的数据视图

您可以启用或禁用[Data Insights Agent](/help/data-analysis-ai.md)的数据视图。

1. 选择数据视图名称旁边的![更多](/help/assets/icons/More.svg)。
1. 从上下文菜单中选择![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 为Data Insights Agent启用]**&#x200B;或![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL 为Data Insights Agent禁用]**。

或者，您可以：

1. 选择一个或多个已为Data Insights Agent禁用或启用的数据视图行。
1. 从蓝色操作栏中选择![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 为Data Insights Agent]**&#x200B;启用![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL 为Data Insights Agent]**&#x200B;禁用。
