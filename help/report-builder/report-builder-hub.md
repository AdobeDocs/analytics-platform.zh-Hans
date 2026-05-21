---
title: Report Builder 中心
description: 了解Report Builder中心。
role: User
feature: Report Builder
type: Documentation
exl-id: 119bd0b5-0d07-407f-b6e9-ef43352bad31
solution: Customer Journey Analytics
TQID: https://experienceleague.adobe.com/lXd4Z4gvGpgmdUbmtV-e0rkmt4r4NvlBHX5Np-HWEFY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
  - id: f2ef16dc-055a-4bb7-baa5-7039653f3966
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 535
ht-degree: 25%

---

# Report Builder 中心

Report Builder中心是从Excel功能区栏选择![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]**&#x200B;时显示在Excel工作簿中的右侧窗格。

使用 Report Builder 中心创建、更新和管理数据块。

Report Builder中心包含![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**、![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]**&#x200B;和![Calendar](/help/assets/icons/Calendar.svg) **[!UICONTROL 计划]**&#x200B;按钮、**[!UICONTROL 命令]**&#x200B;面板和&#x200B;**[!UICONTROL 快速编辑]**&#x200B;面板。

![Report Builder中心](assets/hub51.png){zoomable="yes"}


选择

* ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 创建]**&#x200B;以[创建新数据块](create-a-data-block.md)。
* ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL 管理]**&#x200B;以[管理现有的数据块](manage-reportbuilder.md)。
* ![日历](/help/assets/icons/Calendar.svg) **[!UICONTROL 计划]**&#x200B;至[管理计划以通过电子邮件发送工作簿](schedule-reportbuilder.md)。

## “命令”面板

使用&#x200B;**[!UICONTROL 命令]**&#x200B;面板访问与所选单元格兼容的命令或上一个操作。

| 命令 | 可用的时间… | 用途 |
|------|------------------|--------|
| ![编辑](/help/assets/icons/Edit.svg)**[!UICONTROL 编辑数据块]** | 所选一个或多个单元格仅属于一个数据块。 | 用于编辑数据块。 |
| ![刷新](/help/assets/icons/Refresh.svg) **[!UICONTROL 刷新数据块]** | 选区至少包含一个数据块。 该命令仅刷新选区中的数据块。 | 用于刷新一个或多个数据块。 |
| ![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL 刷新所有数据块]** | 工作簿包含一个或多个数据块。 | 用于刷新工作簿中的所有数据块 |
| ![发送](/help/assets/icons/Send.svg) **[!UICONTROL 发送工作簿]** | 工作簿包含一个或多个数据块。 | 使用以电子邮件的形式[发送工作簿](schedule-reportbuilder.md)。 |
| ![复制](/help/assets/icons/Copy.svg) **[!UICONTROL 复制数据块]** | 所选单元格或单元格属于一个或多个数据块。 | 用于复制数据块。 |
| ![剪切](/help/assets/icons/Cut.svg) **[!UICONTROL 剪切数据块]** | 所选单元格或单元格属于一个或多个数据块。 | 设置以剪切数据块。 |
| ![删除](/help/assets/icons/Delete.svg) **[!UICONTROL 删除数据块]** | 所选一个或多个单元格仅属于一个数据块。 | 用于删除数据块 |

## 快速编辑面板

在电子表格中选择一个或多个数据块时，Report Builder会显示&#x200B;**[!UICONTROL 快速编辑]**&#x200B;面板。 您可以使用&#x200B;**[!UICONTROL 快速编辑]**&#x200B;面板同时更改一个或多个数据块中的参数。

使用&#x200B;**[!UICONTROL 快速编辑]**&#x200B;分区时所做的更改将应用于所有选定的数据块。

### 数据视图

数据块从选定数据视图提取数据。 如果在一个工作表中选择了多个数据块并且它们不从同一数据视图提取数据，则&#x200B;**数据视图**&#x200B;链接显示&#x200B;**[!UICONTROL _多个_]**。

更改数据视图时，选区中的所有数据块将采用新的数据视图。 数据块中的组件根据ID与新的数据视图匹配。 如果在数据块中未找到某个组件，则会删除该组件并将其替换为&#x200B;**[!UICONTROL 无效值]**&#x200B;或为特定组件显示![AlertRed](/help/assets/icons/AlertRed.svg)。

若要更改数据视图，请从&#x200B;**[!UICONTROL 数据视图]**&#x200B;下拉菜单中选择新的数据视图。


### 日期范围

**日期范围**&#x200B;显示所选数据块的日期范围。 如果选择具有多个日期范围的多个数据块，则&#x200B;**[!UICONTROL 日期范围]**&#x200B;链接显示&#x200B;**[!UICONTROL _多个_]**。

### 区段

**区段**&#x200B;链接显示所选数据块使用的区段的摘要列表。 如果选择应用了多个区段的多个数据块，则&#x200B;**区段**&#x200B;链接显示&#x200B;**[!UICONTROL _多个_]**。

>[!MORELIKETHIS]
>
>[选择数据视图](select-data-view.md)
>[选择一个日期范围](select-date-range.md)
>[使用筛选器](work-with-filters.md)
>
