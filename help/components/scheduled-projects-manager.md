---
description: 可通过两种方式在 Analysis Workspace 中使用量度。
title: 量度
feature: Components
exl-id: fa7c5a0f-4983-40ee-b9c1-3e10aab3fc28
role: User
source-git-commit: 8676497c9341e3ff74d1b82ca79bc1e73caf514f
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 16%

---

# 计划项目

可以使用&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 计划项目]**&#x200B;在Customer Journey Analytics中管理计划的Analysis Workspace项目。

在&#x200B;**[!UICONTROL 计划项目]**&#x200B;中，您可以编辑和删除重复的项目计划。  [计划项目列表](#scheduled-project-list)显示特定用户已创建的项。 如果应用程序中禁用该用户帐户，则将停止所有计划的提交。

![计划项目界面](assets/scheduled-projects.png)

## 计划项目列表

计划项目列表会➊显示以下列：

| 栏目 | 描述 |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | 选择一个或多个计划项目时，“计划项目”界面的底部会显示一个蓝色操作栏。 有关详细信息，请参阅[操作](#actions)。 |
| ![颗星](/help/assets/icons/Star.svg) | 选择支持![Star](/help/assets/icons/Star.svg)或取消支持![StarOutline](/help/assets/icons/StarOutline.svg)计划项目。 |
| **[!UICONTROL 计划 ID]** | 主要用于调试的ID。 |
| **[!UICONTROL 名称]** | 此项目的名称。<br/>选择![信息大纲](/help/assets/icons/InfoOutline.svg)以查看计划项目的更多详细信息。<br/>选择![更多](/help/assets/icons/More.svg)打开上下文菜单。 通过此菜单，您可以：<ul><li>![删除](/help/assets/icons/Delete.svg) **[!UICONTROL 删除]**&#x200B;计划项目。</li><li>![标签](/help/assets/icons/Labels.svg) **[!UICONTROL 标记]**&#x200B;计划项目。</li><li>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 批准]**&#x200B;计划项目。</li><li>![文件CSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 导出CSV]**：将计划项目导出到CSV文件。</li></ul> |
| **[!UICONTROL 所有者]** | 创建并拥有此项目的人。 |
| **[!UICONTROL 标记]** | （可选）标记是一种用于排列项目的好方法。 所有用户均可创建标记，并将一个或多个标记应用到项目。 但是，您只能查看自己拥有或者与您共享的项目的标记。 |
| **[!UICONTROL 已传送至]** | 此计划项目的收件人。 |
| **[!UICONTROL 过期日期]** | 您可以将到期日期设置为最多一年，而不考虑调度频率。 |
| **[!UICONTROL 频率]** | 您希望将此计划项目发送给一个或多个收件人的频率。 |
| **[!UICONTROL 执行时间]** | 在一天中发送此计划项目的时间。 |
| **[!UICONTROL 查询次数]** | 查询此项目的次数。 |
| **&#x200B;**&#x200B;| 为计划项目定义的最长日期范围。 该值可能与调查性能问题相关。 有关详细信息，请参阅[报告活动管理器](/help/reporting-activity-manager/reporting-activity-overview.md)。 |
| **[!UICONTROL 查询次数]** | 为计划项目执行的查询数。 该值可能与调查性能问题相关。 有关详细信息，请参阅[报告活动管理器](/help/reporting-activity-manager/reporting-activity-overview.md)。 |


您可以使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)来配置要显示的列。

使用![搜索](/help/assets/icons/Search.svg)搜索计划项目。 您还可以查看是否从“筛选器”面板应用了任何筛选器。 要删除筛选器，请为筛选器选择![CrossSize75](/help/assets/icons/CrossSize75.svg)。 要删除所有筛选器，请选择&#x200B;**[!UICONTROL 全部清除]**。

要编辑计划项目，请选择计划项目的标题。 使用&#x200B;**[!UICONTROL 编辑计划项目]**&#x200B;对话框更新计划详细信息。

![编辑计划项目](assets/edit-scheduled-project.png)

选择&#x200B;**[!UICONTROL 更新]**&#x200B;以更新计划。




## 操作

以下是计划项目管理器中的常见操作。 选择一个或多个计划项目时，您可以从上下文菜单或蓝色操作栏中选择操作。

| 图标 | 操作 | 描述 |
|:---:|---|---|
| ![关闭](/help/assets/icons/Close.svg) | 已选择&#x200B;**[!UICONTROL *x *]** | 选择以取消选择您选择的计划项目。 |
| ![删除](/help/assets/icons/Delete.svg) | **[!UICONTROL 删除]** | 为项目删除选定的计划项目；不会删除这些项目。 |
| ![标签](/help/assets/icons/Labels.svg) | **[!UICONTROL 标记]** | 标记所选的计划项目。 在&#x200B;**[!UICONTROL 标记计划项目]**&#x200B;中选择标记并选择&#x200B;**[!UICONTROL 保存]**&#x200B;以进行保存。 |
| ![复选标记圆](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL 批准]** | 批准所选的计划项目。 |
| ![文件CSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL 导出到 CSV]** | 将所选计划项目导出到名为`Export Scheduled Projects List.csv`的文件。 |


## 筛选

您可以使用筛选器面板筛选计划项目[计划项目列表](#scheduled-project-list)➌。 若要显示或隐藏筛选器面板，请使用![筛选器](/help/assets/icons/Filter.svg)。

过滤器面板由以下部分组成。

### 标记

| 标记 | 描述 |
|---|---|
| ![标记](/help/components/assets/scheduledprojects-filter-tags.png){width="300"} | **[!UICONTROL 标记]**&#x200B;部分允许您根据标记进行筛选。 <ul><li>您使用![搜索](/help/assets/icons/Search.svg) **[!UICONTROL 搜索标记]**&#x200B;来搜索要用于过滤的标记。</li><li>您可以选择多个标记。 可用的标记取决于在过滤器面板的其他部分中所做的选择。</li><li>这些数字表示：<ul><li>⃣7︎：与特定标记关联的计划项目数。</li></ul></li></ul> |


### 所有者

| 所有者 | 描述 |
|---|---|
| ![所有者](/help/components/assets/scheduledprojects-filter-owners.png){width="300"} | 通过&#x200B;**[!UICONTROL 所有者]**&#x200B;部分，可筛选所有者。 <ul><li>您使用![搜索](/help/assets/icons/Search.svg) *搜索所有者*&#x200B;来搜索要用于筛选的所有者。</li><li>您可以选择多个所有者。 可用的所有者取决于在筛选器面板的其他部分中所做的选择。</li><li>这些数字表示：<ul><li>⃣4︎：与特定所有者关联的计划项目数。</li></ul></li></ul> |


### 其他筛选器

| 其他筛选器 | 描述 |
|---|---|
| ![其他筛选条件](/help/components/assets/scheduledprojects-filter-otherfilters.png){width="300"} | 通过&#x200B;**[!UICONTROL 其他筛选器]**&#x200B;部分，可筛选其他预定义筛选器。<ul><li>您可以选择以下一个或多个选项：<ul><li> **[!UICONTROL 已过期]**：筛选已过期的计划项目。</li><li>**[!UICONTROL 失败]**：筛选计划失败的计划项目。</li></ul>具体选择内容取决于您的角色和权限。</li><li>您可以选择多个其他过滤器。 可用的其他筛选器取决于在筛选器面板的其他部分中所做的选择。</li><li>这些数字表示：<ul><li>⃣4︎：与特定其他过滤器关联的计划项目数。</li></ul></li></ul> |
