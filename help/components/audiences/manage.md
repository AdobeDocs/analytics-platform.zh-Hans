---
title: 了解如何管理在Customer Journey Analytics中创建的受众
description: 了解如何管理 Customer Journey Analytics 中的受众
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: 8676497c9341e3ff74d1b82ca79bc1e73caf514f
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 20%

---

# 管理受众

可以使用&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 受众]**&#x200B;在Customer Journey Analytics中管理受众。

通过管理以前创建的受众，您可以：

* **计划或取消计划**&#x200B;自动受众刷新/更新。计划的最长有效期为 1 年。
* 即将到期时&#x200B;**续订受众刷新计划**。针对即将过期的受众的处理方式与针对即将过期的计划报告的处理方式类似 - 管理员会在计划过期前一个月收到一封电子邮件。
* 查看&#x200B;**刷新间隔**&#x200B;和上次更新受众的&#x200B;**时间**
* 深入了解从Customer Journey Analytics生成受众&#x200B;**所花费的**&#x200B;时间。 以及为激活目的而让受众显示在Real-time Customer Platform中所需的时间。
* 查看Customer Journey Analytics中的受众是否被Real-time Customer Platform **主动使用**。 或者（理想情况下）任何使用Customer Journey Analytics创建的Experience Platform的受众应用程序。

如果您有[受众视图](/help/technotes/access-control.md#user-level-access)访问权限，则可以查看受众。 如果您有[受众创建](/help/technotes/access-control.md#user-level-access)权限，则可以编辑和删除受众。 [受众列表](#audiences-list)显示受众。

## “受众”列表

受众列表➊会显示以下列：

| 栏目 | 描述 |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | 选择一个或多个受众后，“受众”界面的底部会显示一个蓝色操作栏。 有关详细信息，请参阅[操作](#actions)。 |
| **[!UICONTROL 标题和描述]** | 创建受众时输入的标题和描述。 |
| **[!UICONTROL 数据视图]** | 创建此受众的数据视图。 |
| **[!UICONTROL 受众规模]** | 该受众中的总人数。 |
| **[!UICONTROL 所有者]** | 受众的所有者，即受众创建者。 |
| **[!UICONTROL 刷新频率]** | 创建受众时配置的刷新间隔。 |
| **[!UICONTROL 标记]** | 应用于此受众的所有标记。 |
| **[!UICONTROL 发布状态]** | 可以显示![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 就绪]**、![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 正在进行]**&#x200B;或![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL 错误]**。 |
| **[!UICONTROL 上次刷新时间]** | 受众上次刷新的时间戳。 |
| **[!UICONTROL 上次修改时间]** | 上次编辑或修改受众的时间戳。 |

您可以使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)来配置要显示的列。 使用![搜索](/help/assets/icons/Search.svg)搜索受众。

要编辑受众，请执行以下操作：

1. 选择受众的标题。 使用&#x200B;**[!UICONTROL 编辑受众项目]**&#x200B;对话框更新受众。 有关详细信息，请参阅[受众生成器](publish.md#audience-builder)。

1. 选择&#x200B;**[!UICONTROL 重新发布]**&#x200B;以重新发布受众。


## 操作

以下是计划项目管理器中的常见操作。 您可以从上下文菜单中选择操作：

| 图标 | 操作 | 描述 |
|:---:|---|---|
| ![标签](/help/assets/icons/Labels.svg) | **[!UICONTROL 标记]** | 标记所选受众。 在&#x200B;**[!UICONTROL 更新标记：*受众名称&#x200B;*]**对话框中，从下拉菜单中选择标记或键入一个或多个新标记。 选择**[!UICONTROL 保存&#x200B;]**以进行保存。 |
| ![删除](/help/assets/icons/Delete.svg) | **[!UICONTROL 删除]** | 删除所选受众。 |
| ![编辑](/help/assets/icons/Edit.svg) | **[!UICONTROL 重命名]** | 重命名所选受众。 使用&#x200B;**[!UICONTROL 重命名： *受众名称&#x200B;*]**对话框重命名受众，并选择**[!UICONTROL 保存&#x200B;]**进行保存。 |

选择一个或多个计划项目时，可从蓝色操作栏执行以下操作。

| 图标 | 操作 | 描述 |
|:---:|---|---|
| ![关闭](/help/assets/icons/Close.svg) | 已选择&#x200B;**[!UICONTROL *x *]** | 选择以取消选择您选择的受众。 |
| ![删除](/help/assets/icons/Delete.svg) | **[!UICONTROL 删除]** | 删除所选受众。 |
| ![文件CSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL 导出到 CSV]** | 将所选受众导出到名为`audiences.csv`的文件。 |

## 筛选

您可以使用筛选器面板筛选[受众列表](#audiences-list)➋。 若要显示或隐藏筛选器面板，请使用![筛选器](/help/assets/icons/Filter.svg)。

过滤器面板由以下部分组成。

### 数据视图

| 数据视图 | 描述 |
|---|---|
| ![所有者](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | **[!UICONTROL 数据视图]**&#x200B;部分允许您筛选数据视图。 <ul><li>您使用![搜索](/help/assets/icons/Search.svg)来搜索要用于筛选的数据视图。</li><li>您可以选择多个数据视图。</li></ul> |

### 所有者

| 所有者 | 描述 |
|---|---|
| ![所有者](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | 通过&#x200B;**[!UICONTROL 所有者]**&#x200B;部分，可筛选所有者。 <ul><li>您使用![搜索](/help/assets/icons/Search.svg)来搜索要用于筛选的所有者。</li><li>您可以选择多个所有者。 </li></ul> |

## 刷新频率

| 刷新频率 | 描述 |
|---|---|
| ![刷新频率](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | 通过&#x200B;**[!UICONTROL 刷新频率]**&#x200B;部分，可根据刷新频率进行过滤。 <ul><li>您使用![搜索](/help/assets/icons/Search.svg)来搜索要用于过滤的刷新频率。</li><li>只有在[受众列表](#audiences-list)中为受众<br/>定义的刷新频率才显示为可用选项。</li></ul> |


### 标记

| 标记 | 描述 |
|---|---|
| ![标记](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | **[!UICONTROL 标记]**&#x200B;部分允许您根据标记进行筛选。 <ul><li>您使用![搜索](/help/assets/icons/Search.svg)来搜索要用于过滤的标记。 |
