---
description: 面板是表格和可视化图表的集合
title: 面板概述
feature: Panels
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '2126'
ht-degree: 33%

---

# 面板概述

[!UICONTROL 面板]是表格和可视化图表的集合可从 Workspace 左上角的图标或[空白面板](/help/analysis-workspace/c-panels/blank-panel.md)访问面板。当您要根据时段、数据视图或分析用例组织您的项目时，面板非常有用。

## 面板类型

Analysis Workspace 中为 [!UICONTROL Customer Journey Analytics] 提供了以下面板类型：

| 面板名称 | 描述 |
| --- | --- |
| [空白面板](/help/analysis-workspace/c-panels/blank-panel.md) | 从可用的面板和可视化图表中选择以开始分析。 |
| [归因](attribution.md) | 使用任意维度和转化指标，快速比较和可视化任意数量的归因模型。 |
| [正在试验](experimentation.md) | 比较不同的用户体验、营销或消息变化，以确定哪些最能推动特定结果。 |
| [自由格式](freeform-panel.md) | 不受限制地执行比较和细分，然后添加可视化图表来讲述丰富的数据案例。 |
| [媒体平均受众访问分钟数](average-minute-audience-panel.md) | 分析特定内容或自定义时段内的平均受众访问分钟数。 |
| [媒体并行查看者](media-concurrent-viewers.md) | 分析一段时间内的并发查看者，了解有关并发峰值的详细信息，并且可以进行细分和比较。 |
| [媒体播放耗时](/help/analysis-workspace/c-panels/media-playback-time-spent.md) | 分析播放耗时以了解发生并发高峰或发生播放量下降的位置。 |
| [下一个或上一个项目](next-previous.md) | 显示用户转到的下一页或上一页。 |
| [快速分析](quickinsight.md) | 快速构建自由格式表和随附的可视化图表，以更快地分析和发现见解。 |


[!UICONTROL 快速见解]、[!UICONTROL 空白]和[!UICONTROL 自由格式]面板非常适合开始您的分析，而[!UICONTROL 归因]有助于进行更深入的分析。 画布底部有一个![AddCircle](/help/assets/icons/AddCircle.svg)，因此您可以随时添加空白面板。

默认开始面板是[!UICONTROL 自由格式]面板，但您也可以将[空白面板](/help/analysis-workspace/c-panels/blank-panel.md)或[快速分析面板](/help/analysis-workspace/c-panels/quickinsight.md)设置为默认值。 查看[项目与分析首选项](/help/analysis-workspace/user-preferences.md#projects--analyses-preferences)。


## 创建面板

要创建面板，请执行以下操作：

* 将面板从&#x200B;**[!UICONTROL 面板]**&#x200B;左侧面板拖放到画布上。
* 从[空白面板](blank-panel.md)中选择一个面板。
* 在Workspace中使用&#x200B;**[!UICONTROL 插入]**&#x200B;菜单并选择您的面板。 或者，您可以使用任何[快捷方式](../build-workspace-project/fa-shortcut-keys.md)插入面板。

  ![创建面板](assets/create-panel.png)

您可以：

* 选择![AddCircle](/help/assets/icons/AddCircle.svg) **within**&#x200B;任意面板以添加其他可视化图表。 此时会显示一个弹出窗口，允许您选择可视化图表。

  ![显示可能的可视化图表的弹出窗口](assets/blank-panel.png)

  | 选择…… | 创建…… |
  |---|---|
  | ![表格](/help/assets/icons/Table.svg) | [自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) |
  | ![折线图](/help/assets/icons/GraphTrend.svg) | [折线图](/help/analysis-workspace/visualizations/line.md) |
  | ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [条形图](/help/analysis-workspace/visualizations/bar.md) |
  | ![123](/help/assets/icons/123.svg) | [摘要数字](/help/analysis-workspace/visualizations/summary-number-change.md) |
  | ![文本](/help/assets/icons/Text.svg) | [文本](/help/analysis-workspace/visualizations/text.md) |
  | ![转化漏斗](/help/assets/icons/ConversionFunnel.svg) | [流失](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) |
  | ![工作流](/help/assets/icons/GraphPathing.svg) | [流](/help/analysis-workspace/visualizations/c-flow/flow.md) |
  | ![GraphAreaStacked](/help/assets/icons/GraphAreaStacked.svg) | [栈叠的面积图](/help/analysis-workspace/visualizations/area.md) |
  | ![文本编号](/help/assets/icons/TextNumbered.svg) | [同类群组表](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md) |
  | ![GraphBullet](/help/assets/icons/GraphBullet.svg) | [项目符号](/help/analysis-workspace/visualizations/bullet-graph.md) |
  | ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [圆环图](/help/analysis-workspace/visualizations/donut.md) |
  | ![上移下移](/help/assets/icons/MoveUpDown.svg) | [概要变化](/help/analysis-workspace/visualizations/summary-number-change.md) |
  | ![直方图](/help/assets/icons/Histogram.svg) | [直方图](/help/analysis-workspace/visualizations/histogram.md) |
  | ![图形散点图](/help/assets/icons/GraphScatter.svg) | [散点图](/help/analysis-workspace/visualizations/scatterplot.md) |
  | ![类型](/help/assets/icons/TwoDots.svg) | [维恩图](/help/analysis-workspace/visualizations/venn.md) |
  | ![GraphTree](/help/assets/icons/GraphTree.svg) | [树形图](/help/analysis-workspace/visualizations/treemap.md) |

* 选择![AddCircle](/help/assets/icons/AddCircle.svg) **外部**&#x200B;工作区中的最后一个面板，以添加另一个[空白面板](blank-panel.md)。


## 数据视图

每个面板都与一个[数据视图](/help/data-views/data-views.md)关联，由面板右上角的下拉菜单中的数据视图&#x200B;*]**&#x200B;的![数据](/help/assets/icons/Data.svg) **[!UICONTROL *名称标识。

创建空白Workspace项目时，初始面板的默认数据视图是您上次在Customer Journey Analytics中处理的数据视图。

创建新面板时，默认数据视图基于您上次在Workspace项目中处理的面板的数据视图。

>[!IMPORTANT]
>
>所选数据视图确定哪些维度、量度和过滤器可用于在面板中构建可视化图表。
>
>
>当您切换面板的数据视图时，某些组件可能在该新数据视图中不可用。 此更改可能会导致可视化图表无法正确呈现。 您可能会看到如下警告：
>
>* 此面板包含在选定数据视图中未启用的组件。 请更改数据视图或在数据视图中启用所需的组件。
>* 无法渲染可视化图表：请检查您的列和行以确保它们包含有效的组件。
>

## 日历

面板日历控制面板中表格和可视化图表的报告日期范围。

>[!NOTE]
>
>如果在可视化图表或面板中使用![日历](/help/assets/icons/Calendar.svg)日期范围组件（例如，作为过滤器），则日期范围组件将覆盖面板日历。
>


![显示所选日期范围的日程表窗口。](assets/panel-calendar.png)

1. 依次选择开始日期和结束日期，以选择日期范围。
或者，您也可以从[!UICONTROL *选择预设*]&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL 预设]**。

1. （可选）选择&#x200B;**[!UICONTROL 显示高级设置]**&#x200B;以：

   * 指定默认`12:00 AM` (`0:00`)和`11:59 PM` (`23:59`)以外的&#x200B;**[!UICONTROL 开始时间]**&#x200B;和&#x200B;**[!UICONTROL 结束时间]**。 结束时间始终为59秒。 对于跨越许多天的日期范围，开始时间适用于日期范围的第一天，结束时间适用于日期范围中的最后一天。 使用&#x200B;**[!UICONTROL （重置时间值）]**&#x200B;将开始和结束时间重置为默认值。
   * **[!UICONTROL 使日期范围组件相对于面板日历]**。 如果禁用，则面板中使用的日期范围组件相对于当前时间。 如果启用，则面板中使用的日期范围组件与面板日历相关。
   * **[!UICONTROL 使用滚动日期]**。 如果启用，预设日期范围（如&#x200B;**[!UICONTROL 最近7天整]**）将动态更新为当前日期和时间进度。 如果禁用，此类预设在应用后不会更新。

     ![滚动日期](assets/calendar-rolling.png)

     您可以选择括号中的文本（例如&#x200B;**[!UICONTROL 固定开始 — 每日滚动]**）以扩展面板并指定&#x200B;**[!UICONTROL 开始]**&#x200B;和&#x200B;**[!UICONTROL 结束]**&#x200B;的详细信息。

      1. 选择&#x200B;**[!UICONTROL 开始]**、**[!UICONTROL 结束]**&#x200B;或&#x200B;**[!UICONTROL 固定日期]**。
      1. 当您选择&#x200B;**[!UICONTROL Start of]**&#x200B;或&#x200B;**[!UICONTROL End of]**&#x200B;时，您可以生成完整的表达式。 例如：**[!UICONTROL 结束]** **[!UICONTROL 当前年份]** **[!UICONTROL 加]** `1` **[!UICONTROL 天]**。 为表达式的每个部分选取相应的值。
         * 选择当前值。 例如&#x200B;**[!UICONTROL 当前年份]**。
         * 选择附加计算的值。 例如，**[!UICONTROL 加]**。
         * 指定附加计算后，请指定值。 例如：`1`。
         * 指定附加计算后，选择用于计算的时段。 例如&#x200B;**[!UICONTROL 天]**。

     选择&#x200B;**[!UICONTROL 隐藏详细信息]**&#x200B;以隐藏滚动日期计算的详细信息。

1. 选择&#x200B;**[!UICONTROL 应用]**以将日期范围应用到调用日历的面板。
选择**[!UICONTROL 应用到所有面板]**&#x200B;以将日期范围应用到Workspace项目中的所有面板。


## 拖放区域 {#dropzone}

使用面板拖放区域，您可以将筛选器和下拉筛选器应用到面板中的所有表格和可视化图表。 您可以将一个或多个过滤器应用到面板。

### 过滤器

将任意筛选器从左侧面板拖放到面板拖放区域以开始筛选面板。 重复此操作可向面板添加其他过滤器。过滤器并排显示在面板顶部。

![左侧面板显示可用的量度和拖放到面板拖放区域的移动设备客户量度。](assets/segment-filter.png)

#### 快速过滤器

还可将非筛选器组件直接拖入放置区域以创建快速筛选器，从而为您节省转到[筛选器生成器](/help/components/filters/filter-builder.md)的时间和精力。 通过这种方式创建的过滤器会自动定义为事件级别过滤器。通过选择筛选器名称旁边的![编辑](/help/assets/icons/Edit.svg)，可以快速修改此定义。


有关更多信息，请参阅[快速过滤器](/help/components/filters/quick-filters.md)。

![公开并放入放置区的临时过滤器。](assets/adhoc-segment-filter.png)

### 下拉过滤器

+++ 观看视频，了解下拉过滤器的相关说明。

>[!VIDEO](https://video.tv.adobe.com/v/23877?format=jpeg)

{{videoaa}}

+++

#### 静态下拉过滤器

您还可通过静态下拉过滤器以可控方式与数据交互。例如，您可以为移动设备类型添加下拉过滤器，这样您就可以按照平板电脑、手机或台式机来筛选面板。

静态下拉过滤器也可用于将多个项目合并在一起。例如，如果您有一个项目的多个版本，每个版本具有不同的“国家/地区”过滤器，您可以将所有版本合并为一个项目并添加“国家/地区”下拉过滤器。

![突出显示营销渠道“直接”过滤器的静态下拉过滤器。](assets/dropdown-filter-intro.png)

##### 创建静态下拉过滤器

* 对于使用维度项目的下拉过滤器，请从左侧面板中选择单个维度，然后在按住⇧键(*shift*)的同时将该维度放入面板拖放区域中。 此操作创建一个下拉过滤器，其中包含与该维度关联的所有维度项。

  或者，如果您希望下拉过滤器仅包含与维度关联的特定维度项，请在左侧面板中选择所需维度旁边的右箭头图标。 此操作会公开所有可用的维度项目。使用⇧+![Select](/help/assets/icons/Select.svg) (*shift* + *select*)或^+![Select](/help/assets/icons/Select.svg) (*control* + *select*)从该列表中选择多个维度项，然后在按住&#x200B;**⇧的同时将其放到面板拖放区域**&#x200B;中。

* 对于使用单个组件类型的下拉筛选器（例如，仅维度、仅筛选器或仅量度），请在左侧面板中使用⇧+![Select](/help/assets/icons/Select.svg)或^+![Select](/help/assets/icons/Select.svg)选择同一类型的多个项。 然后，在保持&#x200B;**⇧置时将项目放入面板拖放区域**。

  使用您选择的组件创建单个下拉过滤器。

* 对于混合使用组件类型（如2个量度和3个筛选器）的下拉筛选器，请使用⇧+![Select](/help/assets/icons/Select.svg)或^+![Select](/help/assets/icons/Select.svg)选择多个组件。 按住&#x200B;**⇧将选定内容拖放到面板拖放区域**&#x200B;中。 在此上下文中，所有组件类型均被视为单独的下拉过滤器。例如，如果同时选择了量度和维度项，则会创建两个单独的下拉过滤器：一个下拉过滤器包含维度项，另一个包含量度。

下拉过滤器提供以下上下文菜单选项：

* **[!UICONTROL 删除下拉菜单]**：从面板中删除下拉过滤器。
* **[!UICONTROL 删除标签]**：删除下拉筛选器上方显示的文本。 要修改标签，请将鼠标悬停在标签上，然后选择![下拉筛选器的编辑标签](/help/assets/icons/Edit.svg)。
* **[!UICONTROL 添加标签]**：当您向一个项目添加下拉过滤器时，标签会自动设置为组件名称。如果删除标签，可以使用此选项重新添加该标签。
* **[!UICONTROL 要求选择]**：要求必须在面板上设置过滤器。

##### 使用静态下拉过滤器

用户可以通过以下任意方式使用下拉过滤器菜单来过滤面板：

* 从下拉筛选器中选择过滤器，将单个过滤器应用于面板。

* 从下拉筛选器中选择多个过滤器，将多个过滤器应用于面板。面板经过过滤，可包含任何选定的过滤器。


#### 动态下拉过滤器

动态下拉过滤器允许您根据面板报告范围内的数据和其他下拉过滤器中的值来确定可用值。例如，您可以使用国家/地区维度和城市维度创建两个动态下拉列表。 当您从&#x200B;**[!UICONTROL 国家/地区]**&#x200B;下拉列表中选择一个国家/地区时，**[!UICONTROL 城市]**&#x200B;下拉列表会动态调整以仅显示该国家/地区内的城市。

同样的概念适用于所有维度；仅出现在面板日期范围内的维度项目和选定的过滤器可见。在静态下拉过滤器中选择的维度项目会影响动态下拉过滤器中的可用值。但是，反之则不然。在动态下拉过滤器中选择的维度项目不会影响静态下拉过滤器中的可用值。

如果您预计将来会收集某个维度项目，则可以手动选择维度项目。您还可以清除动态下拉过滤器，使其不包含值，从而允许其他动态下拉过滤器包含更多值。选择&#x200B;**[!UICONTROL 全部重置]**&#x200B;以清除该面板所有下拉过滤器中的选择。

若要创建动态下拉过滤器：

* 按住&#x200B;**⇧将单个维度拖放到面板拖放区域**&#x200B;中。

请注意，动态下拉过滤器不适用于量度、过滤器或日期范围。

动态下拉过滤器提供与静态下拉过滤器相同的上下文菜单选项。


## 上下文菜单

面板的其他功能可通过面板标题上的上下文菜单（右键单击）使用。

![面板标题的右键单击选项。](assets/right-click-menu.png)

可以使用以下选项：

| 选项 | 描述 |
| --- | --- |
| **[!UICONTROL 插入复制的面板]** | 允许您将复制的面板粘贴到项目中的其他位置或其他项目中。 |
| **[!UICONTROL 插入复制的可视化图表]** | 将复制的可视化图表粘贴到面板、项目中的其他位置，或粘贴到其他项目中。 |
| **[!UICONTROL 将数据视图应用于所有面板]** | 将此面板的数据视图应用于项目中的所有其他面板。 |
| **[!UICONTROL 复制面板]** | 复制面板，以便将其插入到项目中的其他位置或其他项目中。 |
| **[!UICONTROL 复制面板]** | 生成一个与当前面板完全相同的副本，然后可对其进行修改。 |
| **[!UICONTROL 折叠所有面板]** | 折叠所有项目面板。 |
| **[!UICONTROL 展开所有面板]** | 展开所有项目面板。 |
| **[!UICONTROL 折叠面板中的所有可视化图表]** | 折叠当前面板中的所有可视化图表。 |
| **[!UICONTROL 展开面板中的所有可视化图表]** | 展开当前面板中的所有可视化图表。 |
| **[!UICONTROL 编辑描述]** | 添加（或编辑）面板的文本描述。 |
| **[!UICONTROL 获取面板链接]** | 将用户引导至项目中的特定面板。 选择链接后，收件人需要先登录，然后才能转至所链接到的那个面板。 |

## 配置

某些面板（如[!UICONTROL 归因]、[!UICONTROL 试验]、[!UICONTROL 媒体平均受众访问分钟数]等）具有配置对话框以帮助您构建可视化图表。 使用面板顶部的![编辑](/help/assets/icons/Edit.svg)来访问和更改配置。

![配置面板](/help/analysis-workspace/c-panels/assets/configure-panel.png)
