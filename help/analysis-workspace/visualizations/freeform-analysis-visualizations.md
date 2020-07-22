---
description: 了解 Analysis Workspace 中的可视化图表和可视化图表设置。
keywords: Analysis Workspace
title: 可视化图表概述
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 98%

---


# 可视化图表概述

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html) 略有不同。[了解更多...](/help/getting-started/cja-aa.md)

工作区提供了许多可视化图表，使您能够生成数据的可视化表示形式，如条形图、圆环图、直方图、折线图、地图、散点图等。每个可视化图表都有其自身的设置，您可以管理这些设置。单击可视化图表的名称可了解更多详细信息。

YouTube 视频：[Analysis Workspace 中的可视化图表类型](https://www.youtube.com/watch?v=b1zLEywRa6w&amp;index=39&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (2:57)

| 可视化图表名称 | 描述 |
|---|---|
| [面积图](/help/analysis-workspace/visualizations/area.md) | 与折线图类似，只是线条下方显示了彩色区域。当您有多个量度并且希望显示两个或更多量度相交的区域时，可使用面积图。 |
| [条形图](/help/analysis-workspace/visualizations/bar.md) | 显示一些垂直条，这些垂直条表示一个或多个量度中的各种值。 |
| [项目符号图表](/help/analysis-workspace/visualizations/bullet-graph.md) | 显示您感兴趣的值与其他性能范围（目标）进行比较或衡量的结果。 |
| [同类群组表](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | *`cohort`* 是指一组在特定期限内共享相同特性的人员。例如，在您想了解如何让一个同类群组喜欢某个品牌时，同类群组分析就能派上用场。您可以轻松识别趋势中的变化，然后相应地采取回应 |
| [圆环](/help/analysis-workspace/visualizations/donut.md) | 此可视化图表与饼图类似，它将数据显示为整体的一部分或区段。 |
| [流失](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | 流失报表显示访客从何处离开（流失）或继续通过（流过）预定义的页面序列。 |
| [流量](/help/analysis-workspace/visualizations/c-flow/flow.md) | 显示客户在您的网站和应用程序中的浏览路径。 |
| [自由格式表](/help/analysis-workspace/visualizations/freeform-table.md) | 自由格式表不仅可以作为数据表，而且还是一个交互式可视化图表。 |
| [直方图](/help/analysis-workspace/visualizations/histogram.md) | 直方图类似于条形图，不过它可以将数字归为几组不同的范围（存储段）。 |
| [水平条](/help/analysis-workspace/visualizations/horizontal-bar.md) | 显示一些水平条，这些水平条表示一个或多个量度中的各种值。 |
| [折线图](/help/analysis-workspace/visualizations/line.md) | 使用线条来表示量度，以显示一段时间内值的变化情况。仅当使用时间作为维度时，才可以使用折线图。 |
| [散点图](/help/analysis-workspace/visualizations/scatterplot.md) | 显示维度项目与最多三个指标之间的关系。 |
| [概要数字](/help/analysis-workspace/visualizations/summary-number-change.md) | 根据所选的单元格，此可视化图表显示总计和概要。 |
| [概要变化](/help/analysis-workspace/visualizations/summary-number-change.md) | 根据所选的单元格，此可视化图表会比较单元格。 |
| [文本](/help/analysis-workspace/visualizations/text.md) | 允许您将用户定义的文本添加至您的工作区。 |
| [树图](/help/analysis-workspace/visualizations/treemap.md) | 将分层（树结构）数据显示为一组嵌套的矩形。 |
| [维恩图](/help/analysis-workspace/visualizations/venn.md) | 允许您最多拖入 3 个区段（从“组件”中）和一个量度来构建维恩图。 |

## “可视化图表”面板 {#section_DC07F032FBEF4046A40F7B95C28DA018}

要显示“可视化”面板，请单击侧边面板中的&#x200B;**[!UICONTROL 可视化]**。

![步骤结果](assets/visualizations.png)

大部分可视化图表类型（例如面积图、条形图、圆环图和折线图）都是 Adobe Analytics 用户非常熟悉的。但是，Analysis Workspace 提供了可视化图表设置，以及许多全新或独特的具有交互功能的可视化图表类型。

## “可视化”设置 {#section_D3BB5042A92245D8BF6BCF072C66624B}

要访问[!UICONTROL 可视化设置]，请将一个可视化拖到[!UICONTROL 自由格式面板]中，然后单击[!UICONTROL 可视化设置]齿轮图标。

>[!IMPORTANT]
>
>可视化决定了哪些可视化设置可见。并非所有设置都适用于所有可视化图表。此外，某些高级设置&#x200B;**仅**&#x200B;可对特定可视化图表显示，例如[直方图设置](/help/analysis-workspace/visualizations/histogram.md#section_09D774C584864D4CA6B5672DC2927477)。

![](assets/visualization_settings.png)

| 设置 | 描述 |
|--- |--- |
| 百分数 | 显示百分数值。 |
| 100% 堆叠 | 堆叠的面积、堆叠的条形或堆叠的水平条形可视化图表上的此设置将图表变为“100% 堆叠”可视化图表。示例：![](assets/stacked_100_percent.png) |
| 图例可见 | 让您可以隐藏概要数字/概要变化可视化图表的过滤器详细信息文本。 |
| 限制最大项目数 | 允许您限制可视化图表显示的项目数量。 |
| 将 Y 轴定位为 0 | 如果图表上绘制的所有值都远远大于零，则图表默认会将 y 轴底部设置为非零值。如果选中此框，y 轴将被强制设置为零（并将重新绘制图表）。 |
| 标准化 | 要求所有量度按等比例计算。 |
| 显示双轴 | 仅适用于具有两个量度的情况，可以在左（用于一个量度）、右（用于另一个量度）两边各有一个 y 轴。 |
| 显示异常 | 增强了折线图和自由格式表以显示数据异常。 |

## “创建可视化”图标 {#section_9C11D9DEDC42413AA53E69A71A509DFC}

如果不确定应选取哪个可视化，请单击任意表行中的&#x200B;**[!UICONTROL 创建可视化]**&#x200B;图标。将光标悬停在表行上时，将显示此图标。单击此图标将提示 Analysis Workspace 针对哪种可视化图表最适合您的数据做出有根据的推测。例如，如果最多选择了 3 个区段，系统将创建维恩图。如果选择了 3 个以上的区段，系统将创建条形图。对于其他类型的数据，系统可能会创建折线图，等等。

![](assets/create-visual.png)

## 右键单击“可视化图表”/“面板”菜单 {#section_05B7914D4C9E443F97E2BFFDEC70240C}

在可视化图表或面板标头旁单击鼠标右键后，可以访问图形的上下文设置。以下部分或全部设置将可用：

![](assets/right-click_menu.png)

| 设置 | 描述 |
|--- |--- |
| 插入已复制的可视化图表/面板 | 此设置允许您将已复制的可视化图表/面板粘贴（“插入”）到同一项目的其他位置，或另一个完全不同的项目中。 |
| 复制可视化图表/面板 | 此设置允许您右键单击并复制可视化图表或面板。 |
| 生成可视化图表/面板副本 | 生成一个与当前可视化图表完全相同的副本，然后可对其进行修改。 |
| 折叠所有面板 | 折叠所有项目面板。 |
| 折叠面板中的所有可视化图表 | 折叠此项目面板中的所有可视化图表。 |
| 展开所有面板 | 展开所有项目面板。 |
| 展开面板中的所有可视化图表 | 展开此项目面板中的所有可视化图表。 |
| 编辑描述 | 添加（或编辑）可视化图表/面板的文本描述。此描述会显示在项目 > 项目信息和设置中。 |
| 获取面板链接 | 此设置允许您将人员引导至项目中的特定面板。 |
| 获取可视化图表链接 | 此设置允许您复制并共享该链接，从而让其他人直接访问这个可视化图表。需要用户登录。 |
| 重新开始 | （适用于流量、维恩、直方图）删除当前可视化图表的配置，并打开一个新面板，您可以在此处重新配置该可视化图表。 |

## 编辑图例标签 {#section_94F1988CB4B9434BA1D9C6034062C3DE}

您可以对可视化图表图例（流失、面积图、堆叠的面积图、条形图、堆叠的条形图、圆环图、直方图、水平条形图、堆叠的水平条形图、折线图、散点图和维恩图）中的系列名称进行重命名，从而让可视化图表变得更方便使用。

图例编辑&#x200B;**不**&#x200B;适用于以下可视化图表：树状图、项目符号、概要变化或数字、文本、自由格式、直方图、同类群组或流量。

要编辑图例标签，例如在折线图中编辑图例标签，请执行以下操作：

1. 右键单击某个图例标签。
1. 单击&#x200B;**[!UICONTROL 编辑标签]**。

   ![](assets/edit-label.png)

1. 输入新的标签文本。
1. 按 **[!UICONTROL Enter]** 键保存。

下面是一个[指向该主题相关视频的链接](https://www.youtube.com/watch?v=mry3vDrTml0&amp;index=61&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)。
