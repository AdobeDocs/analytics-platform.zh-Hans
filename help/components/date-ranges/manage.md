---
title: 管理日期范围
description: 在 Analysis Workspace 中共享、重命名或删除日期范围。
feature: Calendar
exl-id: 694758c4-d740-4fd7-9fb0-3ff7f6b25a3d
role: User
source-git-commit: 19d2130f4fae736a8553c1a3dd573706d4fb8083
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 9%

---

# 管理日期范围


您可以从中心[!UICONTROL 日期范围]管理界面中共享、筛选、标记、批准、复制、共享和删除日期范围，并将日期范围标记为收藏。 要管理日期范围，请执行以下操作：

* 在主界面中选择&#x200B;**[!UICONTROL 组件]**，然后选择&#x200B;**[!UICONTROL 日期范围]**。


## 日期范围管理器

日期范围管理器具有以下界面元素：

![日期范围界面](assets/date-ranges-manager.png)

### 日期范围列表

日期范围列表显➊示所有日期范围。 该列表具有以下列：

| 栏目 | 描述 |
| --- | --- | 
| ![星形大纲](/help/assets/icons/StarOutline.svg) | 选择支持![星型](/help/assets/icons/Star.svg)或取消支持![星型大纲](/help/assets/icons/StarOutline.svg)日期范围。 |
| **[!UICONTROL 标题和描述]** | 要编辑标题和描述，请选择标题链接，这将打开[日期范围生成器](/help/components/date-ranges/create.md#date-range-builder)。 |
| **[!UICONTROL 所有者]** | 日期范围的所有者。 |
| **[!UICONTROL 标记]** | 此日期范围的标记。 |
| **[!UICONTROL 共享对象]** | 您与其共享日期范围的个人或组。 选择以打开&#x200B;**[!UICONTROL 共享日期范围]**&#x200B;对话框。 |
| **[!UICONTROL 修改日期]** | 显示上次修改日期范围的日期和时间。 |

{style="table-layout:auto"}

使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)指定要显示的列。

### 操作栏

您可以使用操作栏➋对日期范围执行操作。 操作栏包含以下操作：

| 操作 | 描述 |
|---|---|
| ![添加圆圈](/help/assets/icons/AddCircle.svg) **[!UICONTROL 添加]** | 使用[日期范围生成器](create.md#date-range-builder)添加另一个日期范围。 |
| ![搜索](/help/assets/icons/Search.svg) [!UICONTROL *按标题搜索*] | 在列表中未选择日期范围时，使用此搜索字段搜索日期范围。 |
| ![标签](/help/assets/icons/Label.svg) **[!UICONTROL 标签]** | 标记选定的日期范围。 在&#x200B;**[!UICONTROL 标记日期范围]**&#x200B;对话框中，选择或取消选择选定日期范围的标记。 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存选定日期范围的标记。 |
| ![共享](/help/assets/icons/ShareLight.svg) **[!UICONTROL 共享]** | 共享选定的日期范围。 在&#x200B;**[!UICONTROL 共享日期范围]**&#x200B;对话框中，您可以![搜索](/help/assets/icons/Search.svg) *搜索个人或组*，也可以选择&#x200B;**[!UICONTROL 组织]**&#x200B;或&#x200B;**[!UICONTROL 组]**。 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存所选日期范围的共享详细信息。 |
| ![删除](/help/assets/icons/Delete.svg) **[!UICONTROL 删除]** | 删除选定的日期范围。 系统会提示您进行确认。 |
| ![编辑](/help/assets/icons/Edit.svg)**[!UICONTROL 重命名]** | 重命名单个选定的日期范围。 选中后，您可以内联重命名日期范围。 |
| ![复选标记Circle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 批准]** | 批准选定的日期范围。 |
| ![副本](/help/assets/icons/Copy.svg) **[!UICONTROL 副本]** | 复制选定的日期范围。 将使用相同的名称和后缀创建新日期范围（复制） |
| ![文件CSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 导出到CSV]** | 将选定的日期范围导出到`Date ranges List.csv`文件。 |

### 活动筛选栏

筛选器栏➌显示活动的筛选器（如果有）。 您可以使用![CrossSize75](/help/assets/icons/CrossSize75.svg)快速删除筛选器。 如果指定了多个筛选器，请使用&#x200B;**[!UICONTROL 全部删除]**&#x200B;删除所有筛选器。

### 过滤器面板

您可以使用&#x200B;**[!UICONTROL 筛选器]**&#x200B;左侧面板筛选日期范围➍。 过滤器面板显示过滤器的类型和遵循该过滤器的日期范围的数量。 选择![筛选器](/help/assets/icons/Filter.svg)以切换筛选器面板的显示。

要筛选筛选器列表，请执行以下操作：

1. 选择![筛选器](/help/assets/icons/Filter.svg)以打开筛选器面板。 如果筛选器列表需要更多空间，您可以再次选择![筛选器](/help/assets/icons/Filter.svg)以关闭面板。
1. 您可以使用任何可用的[过滤分区](#filter-sections)来过滤日期范围。

   >[!INFO]
   >
   >*项*&#x200B;是指[日期范围列表](#date-ranges-list)中显示的日期范围项。
   > 

#### 筛选区域

{{tagfiltersection}}
{{ownerfiltersection}}
{{otherfiltersfiltersection}}


[日期范围列表](#date-ranges-list)会根据您的筛选器配置自动更新。 您可以在[活动筛选器栏](#active-filter-bar)中查看配置的筛选器。


## 编辑日期范围

您可以通过两种方式编辑日期范围：

* 在Workspace项目中，使用[组件信息](/help/components/use-components-in-workspace.md#component-info)图标。

* 在[[!UICONTROL 日期范围]列表](#date-ranges-list)中，选择日期范围的标题。

您使用[日期范围生成器](/help/components/date-ranges/create.md#date-range-builder)编辑日期范围。




使用日期范围管理器共享、重命名或删除日期范围。进入日期管理器：

1. 使用您的 Adobe ID 凭据登录 [analytics.adobe.com](https://analytics.adobe.com)。
1. 依次转到[!UICONTROL 组件] > [!UICONTROL 日期范围]。


<!--

## Interface

![Date Ranges with Example range highlighted.](../assets/date-range-ui.png)

The date range manager includes the following options:

* **Add**: Create a new date range. See [create a date range](create.md) for more information.
* **Search by title**: Search for a date range by title. Results are filtered based on text entered here.
* **Filter**: Filter date ranges using the left column. You can filter by custom tag, owner, created by you, your favorites, approved, or shared with you. You can also search for desired filters.
* **Favorite**: Click the ![star](../assets/star.png) icon next to a date range to add it to your favorites.
* **Customize columns**: Click the ![columns](../assets/columns.png) icon to show or hide columns in the date range manager.

Click the checkbox next to one or more date ranges for more options.

* **Tag**: Apply a tag to all selected date ranges. Tags help you organize date ranges, and let you filter them using the left column.
* **Share**: Share a date range to other Experience Cloud users. If you are a product administrator, you can also share to the entire organization or groups. Date ranges that are shared to other users in your organization include a ![shared](../assets/shared.png) icon next to the title.
* **Delete**: Permanently delete the selected date range(s).
* **Rename**: If a single date range is selected, you can change its title.
* **Approve**: If you are a product admin, you can add a stamp of approval to a date range. Approved date ranges inform users in your organization that they are 'official', differentiating them from date ranges created by other users in your organization. Approved date ranges include a ![approved](../assets/approved.png) icon next to the title.
* **Unapprove**: If you are a product admin and select a date range that is already approved, you can unapprove it.
* **Copy**: Create a copy of the selected date range(s). Copying date ranges appends `(Copy)` to the end of the title of the newly copied date range(s).
* **Export to CSV**: Exports all selected date ranges into a CSV file. Columns in the resulting CSV file include all visible columns in the date range manager.
-->