---
title: 在Analysis Workspace中配置矩阵可视化
description: 了解如何在Customer Journey Analytics Analysis Workspace中配置矩阵可视化图表，包括其组件、显示选项和设置。
feature: Visualizations
role: User
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 3199a70eee577f4e283208e2c5089c05fe20ed0d
workflow-type: tm+mt
source-wordcount: '1323'
ht-degree: 4%
---

# 配置矩阵可视化

矩阵可视化图表是一个值网格，它显示两个维度中的维度项如何重叠或相互关联。 每个单元格都显示行的维度项与列的维度项的交集。

![矩阵可视化图表](assets/matrix-overview.png)

## 矩阵概述

请参阅[矩阵概述](/help/analysis-workspace/visualizations/matrix/matrix.md)，了解有关矩阵可视化图表的更多信息，包括：

* 主要功能

* 潜在洞察

* 矩阵、自由格式表、维恩图和散点图可视化图表之间的差异

## 构建矩阵可视化

1. 在项目中添加一个空白面板，选择左边栏中的&#x200B;[!UICONTROL **可视化**]&#x200B;图标，然后将&#x200B;[!UICONTROL **矩阵**]&#x200B;可视化拖动到面板中。<!-- FOLLOW-UP: add the Matrix icon before the name when it's available in help/assets/icons. -->

   或

   使用[可视化概述](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)中的[将可视化添加到面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)部分中所述的任何方式添加矩阵可视化。

   <!-- add screenshot of the Matrix configuration fields -->

1. 指定以下信息以配置矩阵可视化图表：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **行维度**] | 其项在Matrix中显示为行的维度。 |
   | [!UICONTROL **列维度**] | 其项在Matrix中显示为列的维度。 <p>如果为行维度和列维度选择相同的维度，则矩阵可视化图表会将维度项目相互进行比较。 例如，如果两个维度都是&#x200B;_设备类型_，则每个单元格会显示两种设备类型（如&#x200B;_移动电话_&#x200B;和&#x200B;_平板电脑_）之间的重叠或关联。 对角线上方和下方的值彼此镜像。</p> |
   | [!UICONTROL **量度**] | 每个单元格为其行维度项和列维度项的组合显示的指标。 |
   | [!UICONTROL **容器**] | 确定行维度项目和列维度项目之间重叠范围的容器。 （如果您的容器名称与下面显示的默认名称不同，说明它们已在您的数据视图中自定义过。）<ul><li>**人员：**（默认）对于同一人员，当行维度项和列维度项在任意数量的会话中发生重叠时。</li><li>**会话：**&#x200B;当行维度项和列维度项在同一会话中发生时，它们会重叠。</li><li>**事件：**&#x200B;当行维度项和列维度项在同一事件中发生时，它们会重叠。</li></ul><!-- SME CHECK: confirm how each container defines overlap. --> |

1. （可选）更改以下任意设置：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **行限制**] | 矩阵可视化图表显示的最大行数。 默认值为10。<!-- SME CHECK: Which items are shown (top items by the metric?)? Does the limit also apply to columns? What's the maximum? --> |
   | [!UICONTROL **重叠调色板**] | 当矩阵显示[重叠计数](#view-overlap-count-or-correlation-strength)时单元格的颜色比例。 |
   | [!UICONTROL **相关调色板**] | 当矩阵显示[关联强度](#view-overlap-count-or-correlation-strength)时单元格的颜色比例。 负关联和正关联使用不同的颜色。 |
   | [!UICONTROL **关联粒度**] | 用于计算[关联强度](#view-overlap-count-or-correlation-strength)的时间粒度，如&#x200B;**[!UICONTROL 天]**。 此值基于面板日期范围自动设置。 你不能改变它。 <p>根据面板日期范围选择以下粒度：</p><ul><li>[!UICONTROL **小时**]：已为7天或更短的日期范围选择</li><li>[!UICONTROL **天**]：为超过7天（最多3个月）的日期范围选择</li><li>[!UICONTROL **周**]：为超过3个月（最多1年）的日期范围选择</li><li>[!UICONTROL **月**]：为超过1年的日期范围选择</li></ul><!-- SME CHECK: The granularities and date range thresholds in this list are a best guess. Confirm which granularities are used for which date ranges. --> |
   | [!UICONTROL **对角线单元格值**] | 矩阵可视化图表如何显示维度项目与其自身相交的单元格。 仅当行维与列维相同时，此设置才可用。<ul><li>**[!UICONTROL 显示]：**&#x200B;显示值。</li><li>**[!UICONTROL 短划线]：**&#x200B;显示短划线而不是值。</li><li>**[!UICONTROL 空白]：**&#x200B;将单元格留空。</li></ul> |

1. 选择&#x200B;[!UICONTROL **生成**]。

   <!-- add screenshot -->

1. 继续下面的部分，[查看重叠计数或关联强度](#view-overlap-count-or-correlation-strength)。

## 查看重叠计数或关联强度

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_matrix_overlap_correlation"
>title="重叠计数与关联强度"
>abstract="<p>**重叠计数**&#x200B;是行维度项和列维度项重叠的选定量度的值。</p><p>**关联强度**&#x200B;是从–1到+1的线性关联，表示两个维度项目的量度随时间一起移动的紧密程度。 值为+1表示它们一起上升和下降，值为0表示没有关系，值为–1表示它们向相反方向移动。 相关性强度是分开计算的，因此很少重叠的维度项仍然可以具有强相关性。</p>"

<!-- markdownlint-enable MD034 -->

您可以切换矩阵可视化图表以显示重叠计数或关联强度。 默认情况下，会显示重叠计数。

1. 在Analysis Workspace中，打开Matrix可视化图表或[创建一个新可视化图表](#build-a-matrix-visualization)。

1. 在矩阵可视化图表的左上角，从以下选项中进行选择：

   * [!UICONTROL **重叠计数**]：显示每个行维度项与每个列维度项存在多少重叠。 每个单元格都会显示发生两个维度项目的人员、会话或事件（取决于容器）的所选量度的值。

   * [!UICONTROL **关联强度**]：显示每个行维度项和每个列维度项的选定指标在面板日期范围内一起移动的紧密程度，线性关联范围为–1到+1。 值为+1表示两个维度项始终一起上升和下降，值为0表示没有关系，值为–1表示它们始终以相反的方向移动。 相关性强度是分开计算的，因此很少重叠的维度项仍然可以具有强相关性。 在&#x200B;[!UICONTROL **关联粒度**]&#x200B;设置中显示的时间粒度下计算关联。<!-- SME CHECK: Confirm that the linear correlation is Pearson. -->

   矩阵可视化右上角的图例显示当前视图的颜色比例：重叠计数的颜色比例为低到高，或相关强度的颜色比例为负(-1)到正(+1)。

## 查看见解

<!-- FOLLOW-UP: Draft based on a prototype screenshot. Add a screenshot of the insight card. -->

Matrix可视化图表底部的insight信息卡描述了Matrix数据中的显着模式。

<!-- SME CHECK: How are insights generated (AI)? What does the label on the card (such as ABSOLUTE) mean, and what other labels are there? Do the insights differ between the Overlap count and Correlation strength views? Are they updated when you change the settings or the panel date range? Can you hide the card? Are any permissions, entitlements, or AI settings required? -->

要查看分析，请执行以下操作：

1. 在矩阵可视化中，查看可视化底部的insight卡。

1. 使用insight卡上的箭头可翻阅可用的见解。

## 编辑矩阵设置

构建矩阵可视化图表后，您可以更改其设置，如维度、量度或容器。

要编辑矩阵设置，请执行以下操作：

1. 在矩阵可视化中，选择可视化顶部子标题旁边的![编辑](/help/assets/icons/Edit.svg)。 子标题总结了当前设置，如量度和维度。

1. 更改[生成矩阵可视化图表](#build-a-matrix-visualization)中描述的任何设置。

1. 选择&#x200B;[!UICONTROL **生成**]。

<!-- SME CHECK: Confirm that the Edit icon reopens the build settings. Does the Matrix keep the Overlap count or Correlation strength view after you rebuild it? -->

## 查看趋势数据

您可以在[折线图可视化图表](/help/analysis-workspace/visualizations/line.md)中查看单元格的趋势数据。 折线图可视化图表显示所选量度在面板日期范围内的变化情况。 显示的行取决于Matrix显示[重叠计数还是相关强度](#view-overlap-count-or-correlation-strength)。

要查看趋势数据：

1. 在矩阵可视化中，右键单击要查看其趋势数据的单元格。

1. 选择&#x200B;[!UICONTROL **趋势**]。

   折线图可视化图表会添加到面板的“矩阵”可视化图表上方：

   * [!UICONTROL **重叠计数**]：单行显示选定的量度，该量度按行维度项和列维度项过滤。

   * [!UICONTROL **关联强度**]：两行显示所选量度，一行用于行维度项，另一行用于列维度项。 比较这两条线以了解两个维度项目的趋势结合程度。

   <!-- SME CHECK: Does the overlap count filter use the Matrix container? Is the time granularity the panel default or the Correlation granularity? Can you select multiple cells? Is the option available for diagonal cells? -->

## 在维恩图可视化图表中查看重叠

您可以在[维恩图可视化图表](/help/analysis-workspace/visualizations/venn.md)中查看单元格行维度项和列维度项之间的重叠。

有关何时使用矩阵可视化或维恩图可视化的详细信息，请参阅[矩阵概述](/help/analysis-workspace/visualizations/matrix/matrix.md)中的[在矩阵、自由格式表、维恩图或散点图可视化之间选择](/help/analysis-workspace/visualizations/matrix/matrix.md#choose-between-matrix-freeform-table-venn-or-scatter-visualizations)。

要在维恩图可视化图表中查看重叠，请执行以下操作：

1. 在矩阵可视化中，右键单击要查看其重叠的单元格。

1. Select [!UICONTROL **在维恩图表中显示**]。

   随后将向面板中添加维恩图可视化图表。 一个圆表示行维度项，另一个圆表示列维度项。 维恩图可视化图表使用与矩阵可视化图表相同的量度。<!-- SME CHECK: Where is the Venn visualization added? Are segments created for each dimension item, and do they use the Matrix container? Is the option available for diagonal cells and in the Correlation strength view? -->

## 应用细分

您可以按其他维度划分单元格的数据，以查看哪些维度项对单元格值有贡献。

要应用细分，请执行以下操作：

1. 在矩阵可视化中，右键单击要应用划分的单元格。

1. 选择&#x200B;[!UICONTROL **细分**]。

1. 选择要用于细分的维度。

   划分维度的排名最前的维度项目会显示在新的自由格式表中。<!-- SME CHECK: Where is the table added? Does the breakdown use the Matrix metric and container? Can you select multiple cells? Is the option available for diagonal cells and in the Correlation strength view? -->


