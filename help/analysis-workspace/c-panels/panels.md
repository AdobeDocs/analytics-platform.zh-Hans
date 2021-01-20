---
description: 面板是表和可视化的集合
title: 面板概述
translation-type: tm+mt
source-git-commit: 7b9a65c865a3ae8803534a10fc1a2431247be091
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 8%

---


# 面板概述

[!UICONTROL 面板]是表和可视化的集合。 您可以从Workspace中左上角的图标或[空白面板](/help/analysis-workspace/c-panels/blank-panel.md)访问面板。 当您希望根据时段、报表包或分析用例组织项目时，面板会很有帮助。 Analysis Workspace提供以下面板类型：

| 面板名称 | 描述 |
| --- | --- |
| [空白面板](/help/analysis-workspace/c-panels/blank-panel.md) | 从可用的面板和可视化中进行选择，以开始分析。 |
| [“快速分析”面板](quickinsight.md) | 快速构建自由格式表和随附的可视化图表，以便更快地分析和发现见解。 |
| [归因面板](attribution.md) | 使用任何维度和转化量度快速比较和可视化任意数量的归因模型。 |
| [自由格式面板](freeform-panel.md) | 执行无限制的比较和细分，然后添加可视化以讲述丰富的数据故事。 |

![](assets/panel-overview.png)

[!UICONTROL Quick Insights]、Blank  和Freeformpanels是开始您的  分析的绝佳 [!UICONTROL 场所，而Analytics for ]目标、 [!UICONTROL Attribution IQ]    、Ching Media Viewer和Ching细分相比较可以提供更高级的分析。项目中有一个 `"+"` 按钮，通过该按钮，您可以随时添加空白面板。

默认的起始面板是[!UICONTROL Freeform]面板，但您也可以将[空白面板](/help/analysis-workspace/c-panels/blank-panel.md)设置为默认面板。

## 日历 {#calendar}

面板日历控制面板中表格和可视化的报告范围。

注意：如果在表、可视化或面板拖放区中使用（紫色）日期范围组件，它将覆盖面板日历。

![](assets/panel-calendar.png)

## 拖放区{#dropzone}

面板拖放区允许您将区段和下拉过滤器应用于面板中的所有表和可视化。 您可以对面板应用一个或多个过滤器。 可通过单击编辑铅笔来修改每个滤镜上方的标题，也可以右键单击以完全删除它。

### 细分过滤器

将左边栏中的任何过滤器拖放到面板拖放区，开始筛选面板。

![](assets/segment-filter.png)

### 临时过滤器

还可以将非区段组件直接拖动到拖放区中以创建临时过滤器，从而节省转到Filter Builder的时间和精力。 以这种方式创建的过滤器会自动定义为命中级过滤器。 可以通过单击滤镜旁边的信息图标(i)，然后单击铅笔形编辑图标，并在滤镜生成器中编辑来修改此定义。

临时过滤器是项目的本地，除非您公开，否则不会显示在左边栏中。

![](assets/adhoc-segment-filter.png)

### 下拉过滤器{#dropdown-filter}

除细分过滤器外，下拉过滤器还允许您以受控方式与数据交互。 例如，您可以为移动设备类型添加下拉筛选器，以便按平板电脑、手机或桌面对面板进行分段。

下拉式过滤器还可用于将多个项目合并到一个项目中。 例如，如果应用了不同国家／地区段的同一项目的多个版本，您可以将所有版本合并到单个项目中并添加国家／地区下拉列表筛选器。

![](assets/dropdown-filter-intro.png)

要创建下拉过滤器，请执行以下操作：

1. 要使用[!UICONTROL Dimension项]创建下拉筛选器，如[!UICONTROL 营销渠道]维中的值，请单击左边栏中您的维旁边的右箭头图标。 这将显示所有可用项。 从左边栏中选择一个或多个组件项，并将它们拖放到面板拖放区&#x200B;**中，同时按住Shift键**。 这会将组件转换为下拉筛选器，而不是单个区段。
1. 要使用度量、段或日期范围等其他组件创建下拉筛选器，请从左边栏中的一个组件类型中进行选择，并在按住Shift键的同时放入面板拖放区&#x200B;**。**
1. 从下拉列表中选择一个选项以更改面板中的数据。 您也可以选择&#x200B;**[!UICONTROL 无过滤器]**&#x200B;来选择不过滤任何面板数据。

![](assets/create-dropdown.png)

[观看视](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html) 频以进一步了解如何向项目添加下拉过滤器。

## 右键单击菜单{#right-click}

右击面板标题即可获得面板的其他功能。

![](assets/right-click-menu.png)

可以使用以下设置：

| 设置 | 描述 |
| --- | --- |
| [!UICONTROL 插入复制的面板／可视化] | 允许您将复制的面板或可视化粘贴（“插入”）到项目中的其他位置，或粘贴到完全不同的项目中。 |
| [!UICONTROL 复制面板] | 允许您右键单击并复制面板，以便将其插入项目中的其他位置，或插入完全不同的项目。 |
| [!UICONTROL 重复面板] | 精确重复当前面板，然后可以修改该面板。 |
| [!UICONTROL 折叠／展开所有面板] | 折叠并展开所有项目面板。 |
| [!UICONTROL 折叠／展开面板中的所有可视化] | 折叠并展开当前面板中的所有可视化。 |
| [!UICONTROL 编辑描述] | 添加（或编辑）面板的文本描述。 |
| [!UICONTROL 获取面板链接] | 此设置允许您将人员引导至项目中的特定面板。单击链接后，收件人需要先登录，然后才能被定向到链接的确切面板。 |
