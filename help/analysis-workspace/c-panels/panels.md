---
description: 面板是表格和可视化图表的集合
title: 面板概述
feature: Panels
exl-id: be3e34a0-06c1-4200-b965-96084c2912fd
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '851'
ht-degree: 100%

---

# 面板概述

[!UICONTROL 面板]是表格和可视化图表的集合可从工作区左上角的图标或[空白面板](/help/analysis-workspace/c-panels/blank-panel.md)访问面板。当您要根据时段、数据视图或分析用例组织您的项目时，面板非常有用。

## 面板类型

Analysis Workspace 中为 [!UICONTROL Customer Journey Analytics] 提供了以下面板类型：

| 面板名称 | 描述 |
| --- | --- |
| [空白面板](/help/analysis-workspace/c-panels/blank-panel.md) | 从可用的面板和可视化图表中选择以开始分析。 |
| [“快速分析”面板](quickinsight.md) | 快速构建自由格式表和随附的可视化图表，以便更快地分析和发现见解。 |
| [归因面板](attribution.md) | 使用任意维度和转化指标，快速比较和可视化任意数量的归因模型。 |
| [自由格式面板](freeform-panel.md) | 不受限制地执行比较和细分，然后添加可视化图表来讲述丰富的数据案例。 |

![](assets/panel-overview.png)

[!UICONTROL 快速见解]、[!UICONTROL 空白]和[!UICONTROL 自由格式]面板非常适合开始您的分析，而[!UICONTROL 归因 IQ] 本身有助于进行更深入的分析。项目中有一个 `"+"` 按钮，通过该按钮，您可以随时添加空白面板。

默认开始面板是[!UICONTROL 自由格式]面板，但您也可以将[空白面板](/help/analysis-workspace/c-panels/blank-panel.md)设置为默认值。

## 日历 {#calendar}

面板日历控制面板中表格和可视化报表的报告范围。

注意：如果在表格、可视化报表或面板拖放区域中使用了某个（紫色）日期范围组件，则该组件会覆盖面板日历。

![](assets/panel-calendar.png)

您可以在面板日历的高级设置下应用分钟级日期范围。如果报告的日期范围跨越许多天，则开始时间适用于范围内的第一天，结束时间适用于最后一天。

## 拖放区域 {#dropzone}

使用面板拖放区域，您可以将筛选器和下拉筛选器应用到面板中的所有表格和可视化图表。您可以将一个或多个过滤器应用到面板。各个过滤器上方的标题可以通过单击铅笔图标进行修改，您也可以右键单击以将其全部删除。

### 筛选器

将任意筛选器从左边栏拖放到面板拖放区域以开始筛选面板。

![](assets/segment-filter.png)

### 临时筛选器

还可将非筛选器组件直接拖入放置区域以创建临时筛选器，从而节省转到筛选器生成器的时间和精力。通过这种方式创建的筛选器自动定义为点击级别筛选器。通过单击筛选器旁的信息图标 (i)、单击铅笔形状编辑图标并在筛选器生成器中进行编辑，可以修改此定义。

临时筛选器在项目本地，除非将其公开，否则此类筛选器不会出现在左边栏中。

![](assets/adhoc-segment-filter.png)

### 下拉筛选器 {#dropdown-filter}

除了筛选器，您还可通过下拉筛选器以可控方式与数据交互。例如，您可以为移动设备类型添加下拉筛选器，这样您就可以按照平板电脑、手机或台式机来筛选面板。

下拉筛选器也可用于将多个项目合并在一起。例如，如果您有一个项目的多个版本，每个版本具有不同的“国家/地区”筛选器，您可以将所有版本合并为一个项目并添加“国家/地区”下拉筛选器。

![](assets/dropdown-filter-intro.png)

要创建下拉过滤器，请执行以下操作：

1. 要使用[!UICONTROL 维度项]创建下拉过滤器，例如[!UICONTROL 营销渠道]维度，请在左边栏中单击该维度旁边的右箭头图标。这会打开所有可用项。从左边栏中选择一个或多个组件项，然后&#x200B;**在按住 Shift 键的同时**&#x200B;将其放到面板拖放区域中。这会将组件转换为下拉筛选器，而不是转换为单个筛选器。
1. 要使用量度、筛选器或日期范围等其他组件创建下拉筛选器，请在左边栏中选择一种组件类型，然后&#x200B;**在按住 Shift 键的同时**&#x200B;将其放到面板拖放区域中。
1. 从下拉过滤器中选择以下选项之一来更改面板中的数据。您也可以通过选择&#x200B;**[!UICONTROL 无过滤器]**&#x200B;来不过滤任何面板数据。

![](assets/create-dropdown.png)

[观看视频](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html?lang=zh-Hans)以详细了解如何将下拉过滤器添加到项目中。

## 右键单击菜单 {#right-click}

面板的其他功能可通过在面板的标题上右键单击来使用。

![](assets/right-click-menu.png)

其中提供了以下设置：

| 设置 | 描述 |
| --- | --- |
| [!UICONTROL 插入复制的面板/可视化图表] | 使用此设置，您可以将复制的面板或可视化图表粘贴（“插入”）到项目中的其他位置或完全不同的项目中。 |
| [!UICONTROL 复制面板] | 使用此设置，您可以右键单击并复制面板，以便将其插入到项目中的其他位置或完全不同的项目中。 |
| [!UICONTROL 复制面板] | 生成一个与当前面板完全相同的副本，然后可对其进行修改。 |
| [!UICONTROL 折叠/展开所有面板] | 折叠和展开所有项目面板。 |
| [!UICONTROL 折叠/展开面板中的所有可视化图表] | 折叠和展开当前面板中的所有可视化图表。 |
| [!UICONTROL 编辑描述] | 添加（或编辑）面板的文本描述。 |
| [!UICONTROL 获取面板链接] | 此设置允许您将人员引导至项目中的特定面板。单击该链接时，收件人需要先登录，然后才能转至所链接到的那个面板。 |
