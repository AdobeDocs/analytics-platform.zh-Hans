---
description: 计算量度管理器允许您共享、筛选、标记、批准、复制、删除和标记为收藏。
title: 计算量度管理器
feature: Calculated Metrics
exl-id: 8b257ecc-a596-4b34-ac26-eda16835f1ba
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 29%

---

# 管理计算量度

您可以从中心[!UICONTROL 计算量度]管理界面共享、筛选、标记、批准、重命名、复制、删除、导出计算量度以及将计算量度标记为收藏。 要管理计算量度，请执行以下操作：


* 在主界面中选择&#x200B;**[!UICONTROL 组件]**，然后选择&#x200B;**[!UICONTROL 计算量度]**。


## 计算量度管理器

计算量度管理器具有以下界面元素：


![过滤器界面](assets/calculated-metrics-manager.png)

### 过滤器列表

过滤器列表➊显示您拥有或已与您共享的所有计算量度。 该列表具有以下各列：

<!-- I think this table incorrectly talks about quick calculated metrics -->

| 列 | 描述 |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 选择支持![Star](/help/assets/icons/Star.svg)或取消支持![StarOutline](/help/assets/icons/StarOutline.svg)计算量度。 查看[将计算量度标记为收藏](/help/components/segments/seg-favorite.md) |
| **[!UICONTROL 标题和描述]** | 要编辑计算量度，请选择标题链接，这会打开[计算量度生成器](cm-build-metrics.md)。 共享的计算量度以![共享](/help/assets/icons/ShareAlt.svg)表示。 |
| **[!UICONTROL 数据视图]** | 此计算量度应用于的数据视图。 |
| **[!UICONTROL 所有者]** | 计算指标的所有者。 作为用户，您只能看到您拥有的注释或与您共享的注释。 |
| **[!UICONTROL 标记]** | 列出此计算指标的标记。 |
| **[!UICONTROL 共享对象]** | 列出与多少个人或组共享计算指标。 选择以打开&#x200B;**[!UICONTROL 共享计算量度]**&#x200B;对话框。 有关详细信息，请参阅[共享计算量度](cm-sharing.md)。 |
| **[!UICONTROL 修改日期]** | 上次修改计算量度的日期和时间。 |
| **[!UICONTROL 用在]** | 显示当前使用计算量度的位置以及在每个区域中使用计算量度的次数。 <p>例如，如果计算量度在40个项目和2个警报中使用，则此列的值显示为&#x200B;[!UICONTROL **42个组件**]。 <p>选择此列中的值可查看在其中使用计算量度的细分(例如，[!UICONTROL **项目(40)**]、[!UICONTROL **移动记分卡(2)**])。 此外，您还可以查看正在使用计算量度的项目列表。 例如，要查看正在使用它们的项目列表，请选择&#x200B;[!UICONTROL **项目（40）**]&#x200B;链接。</p><p>以下每个区域均显示该区域内正在使用的计算量度实例数：</p> <ul><li>[!UICONTROL **项目**]<p>包含[在计算量度生成器](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)中创建并且可用于所有项目的计算量度。</p></li><li>[!UICONTROL **临时组件**]<p>包含[创建为快速计算量度](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)且仅在单个项目中可用的计算量度。</p></li><li>[!UICONTROL **计划项目**]</li><li>[!UICONTROL **移动记分卡**]</li><li>[!UICONTROL **注释**]</li><li>[!UICONTROL **Report Builder**]<p>选择此选项可下载包含以下数据列的CSV文件：</p><ul><li>Report Builder 名称</li><li>上次访问时间</li><li>上次访问的 IMS 用户 ID</li><li>上次访问的用户名称</li></ul></li></ul><p>此信息可帮助您确定组件是否对组织中的用户有用、组件的使用位置以及是否需要删除或修改它。</p><p>查看本列时请考虑以下事项：</p><ul><li>此信息仅供系统管理员使用。</li><li>默认情况下，[!UICONTROL **用于**]&#x200B;列不显示。使用 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) 来配置此列的显示。</li><li>此信息不包括 API 或 Data Warehouse 的使用情况。</li><li>如果此列中没有给定组件的数据，但它具有&#x200B;[!UICONTROL **上次使用**]&#x200B;日期，则表示该组件可能未保存便已在分析中使用。</li><li>使用情况信息从 2023 年 9 月开始提供。</li></ul><p>可以结合[数据字典](/help/components/data-dictionary/data-dictionary-overview.md)和这些信息，帮助您跟踪并更好地了解组织中组件的使用情况。</p> |
| **[!UICONTROL 上次使用]** | 上次使用计算量度的时间。 |

{style="table-layout:auto"}

使用 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) 指定您想要显示的列。

### 操作栏

您可以使用操作栏➋对筛选器执行操作。 操作栏包含以下操作：

| 图标 | 操作 | 描述 |
|:---:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL 添加]** | 使用[计算量度生成器](cm-build-metrics.md)添加其他计算量度。 |
| ![Search](/help/assets/icons/Search.svg) | [!UICONTROL *按标题搜索*] | 在列表中未选择计算指标时，使用此搜索字段搜索筛选器。 |
| ![Label](/help/assets/icons/Label.svg) | **[!UICONTROL 标记]** | 标记所选的计算指标。 在&#x200B;**[!UICONTROL 标记计算量度]**&#x200B;对话框中，选择或取消选择所选计算量度的标记。 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存选定计算量度的标记。 有关详细信息，请参阅[标记计算量度](cm-tagging.md)。 |
| ![Share](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL 共享]** | 共享所选的计算指标。 在&#x200B;**[!UICONTROL 共享计算量度]**&#x200B;对话框中，您可以![搜索](/help/assets/icons/Search.svg) *搜索个人或组*，也可以选择&#x200B;**[!UICONTROL 组织]**&#x200B;或&#x200B;**[!UICONTROL 组]**。 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存所选计算量度的共享详细信息。 有关详细信息，请参阅[共享计算量度](cm-sharing.md)。 |
| ![Delete](/help/assets/icons/Delete.svg) | **[!UICONTROL 删除]** | 删除所选的计算指标。 系统将提示您确认。 |
| ![Edit](/help/assets/icons/Edit.svg) | **[!UICONTROL 重命名]** | 重命名单个选定的计算指标。 选中后，您可以内联重命名计算指标。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL 批准]** | 批准所选的计算指标。 请参阅[批准计算量度](cm-approving.md)。 |
| ![Copy](/help/assets/icons/Copy.svg) | **[!UICONTROL 复制]** | 复制所选的计算指标。 新计算量度是使用相同的名称和后缀`(Copy)`创建的 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL 导出至 CSV]** | 将计算量度导出到`Calculated  metric List.csv`文件。 |

### 活动过滤器栏

筛选器栏➌显示从筛选器面板应用到计算量度列表（如果有）的活动筛选器。 您可以使用 ![CrossSize75](/help/assets/icons/CrossSize75.svg) 快速移除过滤器。如果指定了多个过滤器，则可以使用&#x200B;**[!UICONTROL 全部移除]**&#x200B;来移除所有过滤器。

### 过滤器面板

您可以使用![筛选器](/help/assets/icons/Filter.svg) **[!UICONTROL 筛选器]**&#x200B;左侧面板➍来筛选计算量度列表。 过滤器面板显示过滤器的类型和遵循特定过滤器的计算量度数。 选择![过滤器](/help/assets/icons/Filter.svg)以切换过滤器面板的显示方式。

有关详细信息，请参阅[筛选计算量度列表](cm-filter.md)。


<!-- OLD CONTENT 

The Calculated metric manager shows you all the filters you own and that have been shared with you. Admin-level users can see all custom metrics in the organization. This overview presents the user interface and the capabilities of the Calculated metric manager.

![Calculated metrics window showing available filters.](assets/calc-metric-manager.png)

## Access the Calculated metrics manager

1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Calculated metrics**].

## Available actions in the Calculated metrics manager

In the Calculated metrics manager, you can:

* [Filter calculated metrics](/help/components/calc-metrics/cm-workflow/cm-filter.md)

* [Mark calculated metrics as favorites](/help/components/calc-metrics/cm-workflow/cm-favorite.md)

* [Approve calculated metrics](/help/components/calc-metrics/cm-workflow/cm-approving.md)

* [Tag calculated metrics](/help/components/calc-metrics/cm-workflow/cm-tagging.md)

* [Share calculated metrics](/help/components/calc-metrics/cm-workflow/cm-sharing.md)

* Export a calculated metric to a CSV file. 

* [Copy calculated metrics](/help/components/calc-metrics/cm-workflow/cm-copy.md)

* Delete calculated metrics

## Configure columns

You can configure the information displayed for each calculated metric in the Calculated metrics manager by configuring the columns that are displayed.

To configure the visible columns in the Calculated metrics manager:

1. In Customer Journey Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Calculated metrics]**. 

1. In the Calculated metrics manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Calculated metrics manager.

   The following columns are available:

   | Column title  | Description |
   |---|---|
   | Favorites  | Displays star icons next to each calculated metric, allowing you to mark calculated metrics as favorites. For more information, see [Mark calculated metrics as favorites](/help/components/calc-metrics/cm-workflow/cm-favorite.md). |
   | Title and description | These values are provided in the Calculated metric builder. To edit the title and description, select the title link to open the Calculated metric builder.  |
   | Report suite | Indicates in which report suite the metric was last saved.  |
   | Owner | Indicates who owns the custom metric. As a non-admin, you can see only metrics you own or those that were shared with you.  |
   | Tags | Shows tags that were applied to the metric, either by you or by people who shared the calculated metric with you.  |
   | Shared with | Lists individuals or groups (admin only) or All (admin only) that you shared the calculated metric with. <p>When a calculated metric is being shared, a share icon displays next to the calculated metric name.</p>  |
   | Date modified | Indicates the date when the custom metric was last modified.  |
   | Used in | Shows where calculated metrics are currently being used, and how many times they are being used in each area. <p>For example, if the calculated metric is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**]. <p>Select the value in this column to see the breakdown of where the calculated metrics are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Mobile Scorecards (2)**]). Furthermore, you can view the list of items where the calculated metrics are being used. For example, to see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of calculated metrics being used in that area:</p> <ul><li>[!UICONTROL **Projects**]<p>Contains calculated metrics that were [created in the calculated metric builder](/help/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains calculated metrics that were [created as quick calculated metrics ](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file, with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul><p>When viewing information for Report Builder, usage information is available starting in September 2024.</p></li></ul><p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. [Configure columns](#configure-columns) to display it.</li><li>If a calculated metric includes another calculated metric in its definition, any use of that calculated metric is not shown in the [!UICONTROL **Used in**] column. If a calculated metric is included in the definition of another type of component (such as a segment), then usage is shown in the [!UICONTROL **Used in**] column.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but it has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p> |
   | Last used | Shows the date when the calculated metric was last used in any of the following component types: <ul><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li></ul> <p>This information can help you determine whether a component is valuable to users in your organization, or whether it should be deleted.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li><li>This information is available only to system administrators.</li></ul><p>You can use the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |

   {style="table-layout:auto"}

-->