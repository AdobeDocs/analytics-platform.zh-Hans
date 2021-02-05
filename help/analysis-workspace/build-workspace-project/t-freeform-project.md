---
description: 创建一个项目并将组件（维度、量度、区段、日期范围）添加到自由格式面板。
keywords: Analysis Workspace
title: 创建工作区项目
translation-type: tm+mt
source-git-commit: 7b9a65c865a3ae8803534a10fc1a2431247be091
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 100%

---


# 创建工作区项目

创建一个项目并将组件（维度、量度、区段、日期范围）添加到自由格式面板。

在本篇文章中，您可以熟悉 Analysis Workspace 的界面元素，并了解如何创建项目。

## 创建项目

1. 指定创建和管理项目的用户权限。

   创建或组织 Analysis Workspace 项目之前，管理员必须要将您添加到具有&#x200B;**[!UICONTROL 在 Analysis Workspace 中创建/组织项目]**&#x200B;权限的组，或者添加到&#x200B;**[!UICONTROL 全部报表访问]**&#x200B;用户组。（**[!UICONTROL 管理员]** > **[!UICONTROL 用户管理]** > [群组](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/user-product-management/user-groups/groups.html)）。

1. 在 [!DNL Experience Cloud] 中，单击 **[!UICONTROL Analytics]** > **[!UICONTROL 工作区]**。

   ![](assets/analysis_workspace_menu.png)

   或者，输入正斜杠 (/) 以打开报表搜索栏，然后键入“分析工作区 *`workspace`*。

   ![](assets/analysis-app-search.png)

1. 单击&#x200B;**[!UICONTROL 新建项目]**。

   您可以选择从以下项创建项目：

* 空白项目（默认）。有关说明，请参阅下文。
* 标准模板。这些模板由 Adobe 创建并且即装即用。有关说明，请参阅[模板](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)。
* 自定义模板。这些模板由具有管理员权限的用户创建。有关说明，请参阅[模板](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)。

   ![](assets/start_modal.png)

1. 要从空白项目创建项目，请单击&#x200B;**[!UICONTROL 空白项目]**。

   * 然后单击&#x200B;**[!UICONTROL 创建]**，或
   * 只需按下 **[!UICONTROL Enter]** 键。

   屏幕上会显示空白项目，其中包括一个自由格式面板和一个数据表可视化图表。

   ![](assets/fa_project_new.png)

   >[!NOTE]
   >
   >有时候，在加载项目（或切换到报表包）时，如果该项目中的所有组件（量度/维度）并非全部包含在报表包中，将会显示“不兼容的报表包”消息。您可以看到不兼容的组件列表，这样便可以了解为什么会收到该消息。

<table id="table_3989E45D9D4241CBB2E58B29DA257B2F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/analysis-workspace-components.md"  > 组件</a> </td> 
   <td colname="col2"> <p>可拖入项目中的维度、量度、区段和日期范围。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md"  > 可视化图表</a> </td> 
   <td colname="col2"> <p>这些项目可拖至界面上的面板或项目区域中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md"  > 自由格式面板 </a> </td> 
   <td colname="col2"> <p>用于在 Analysis Workspace 中进行交互的画布或工作区。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 保存项目。为项目命名，提供描述（可选但很有用）并标记项目（可选），然后单击&#x200B;**[!UICONTROL 保存项目]**。

   ![](assets/save_project.png)

1. 现在，您可以右键单击并复制可视化图表或面板，然后将复制的可视化图表或面板粘贴（“插入”）到同一项目的其他位置或其他项目中。

   您可以利用此项功能来创建一些能够复制到其他项目中的“构建基块”（预定义的可视化图表/面板），从而更加快速地运用特定于您公司的数据。

   >[!NOTE]
   >
   >如今，当您执行“保存”或“另存为”操作后，内部链接都是一些相对于其所在项目的链接，并非相对于以往进行复制的原始项目。

## 添加组件和可视化图表 {#task_CDAC9B3007BE4A3790AFAD3746D669B1}

1. 通过将 *`components`* 和 *`visualizations`* 拖动到项目来构建项目。

   **组件**

   “组件”工具栏显示了您最常使用的一些可搜索的维度、量度、区段以及日期范围。

<table id="table_4626163E26DE46CB86391868BBA3AD32"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 组件 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 维度（橙色） </td> 
   <td colname="col2"> <p>应用于项目级别。 </p> <p><img  src="assets/dimensions.png" id="image_353BAF1A7AC04C7DB5F5CDFDE7614402" align="left" placement="break" width="300px" /> </p> <p>Prop#、eVar# 和 event# 均被附加到维度名称，您可以对这些数字编号进行搜索。示例：“Internal Campaign”在左边栏中显示为“Internal Campaign (event1)”。 </p> <p> 请注意，表中不显示 prop、eVar 和 event 编号（为了使标题保持简短）。 </p> <p>某些现有的维度在被拖到自由格式表中或在左边栏中被人查看时具有默认的排序顺序。例如，如果将“小时”放入表中或在左边栏中查看它时，它将按照从 12AM 至 11PM 的顺序进行排序。您仍然可以选择按照任何量度列进行排序。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 量度（绿色） </td> 
   <td colname="col2"> <p>应用于项目级别。 </p> <p><img  src="assets/metrics.png" id="image_7C874C72992E414CBEE6B90CEF7B9F3C" /> </p> <p> <span class="term">发生次数</span>是数据表默认的量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 区段（蓝色） </td> 
   <td colname="col2"> <p>只能在面板级别进行拖动，不过，您可以在数据表中创建内联区段。 </p> <p><img  src="assets/segments.png" id="image_5674B18BC3AB47A2B1FEE584E0FBF47C" /> </p> <p>有关更多信息，请参阅<a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  >区段</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日期范围和粒度（紫色） </td> 
   <td colname="col2"> <p>只能在面板级别进行拖动。配置日期范围时，您可以通过“日历”创建一个项目。 </p> <p><img  src="assets/date-ranges.png" id="image_A1750DA921234AD0BB02166865EB8FCC" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

**[可视化图表](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)**

[!UICONTROL 可视化]面板提供标准的 Analytics 图形、图表、圆环图、数据表、[同类群组](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)表、维恩图等等。您可以将多个可视化信息拖放到项目中。

![步骤结果](assets/visualizations.png)

![](assets/fa_full_panel.png)

1. 步骤

## 使用右键单击菜单自定义您的数据 {#concept_8117C300F21843B99F4E1B9AB7B11B6F}

右键单击菜单允许您执行以下操作，具体操作取决于您在表格中右键单击的单元格。

![步骤结果](assets/fa_data_table_actions.png)

<table id="table_0F84CC5B604D4D41BD0C9668DF525929"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 操作 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > 添加时间段列</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md"  > 比较时间段</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>复制到剪贴板 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>删除选定项 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/components/c-alerts/intellligent-alerts.md"  > 从选定范围中创建警报</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md"  > 划分</a> 
    <ul id="ul_18C83B8514AD4C1C86C071AA8402CB5C"> 
     <li id="li_6CA84ED293EA4940A7495DA9D9121264">维度 </li> 
     <li id="li_EA16EE017B2E4A6998918706938A21BF">量度 </li> 
     <li id="li_0405D339CD01405DB508A7D8D1A976B4">区段 </li> 
     <li id="li_819CE81C552F49BB9C1B83ED3B42C5F7">时间 </li> 
    </ul> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md"  > 可视化图表</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/curate-share/download-send.md"  > 下载为 CSV 格式</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/home.md"  > 趋势选择</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/components/t-freeform-project-segment.md"  > 从选定范围中创建区段</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md"  > 在区段比较中运行</a> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 只显示选定的行 </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 显示所有行 </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

有关复制和选择行的信息，请参阅[在 Analysis Workspace 中可使用键盘、鼠标交互等行为](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)。
