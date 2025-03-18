---
title: 内容分析报表
description: 如何报告内容分析
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: df3a877feed82f6cbd181561da68837373bdafb8
workflow-type: tm+mt
source-wordcount: '1246'
ht-degree: 0%

---

# Content Analytics报表概述

>[!WARNING]
>
>本文是即将发布的最终版本的初步非官方草稿版本，是内容分析文档的一部分。 所有内容可能会发生更改，并且本条当前版本不承担任何法律义务。
>

{{release-limited-testing}}

Content Analytics报表是在Analysis Workspace中完成的。 特定Workspace [模板](#template)可用，因此您可以立即访问预填充了相关内容见解的Workspace项目。

要从头开始报告Content Analytics：

1. [创建新的](/help/analysis-workspace/build-workspace-project/create-projects.md)或[在Workspace中打开现有的](/help/analysis-workspace/build-workspace-project/open-projects.md)项目。
1. 请确保您[为Content Analytics报表选择数据视图](/help/analysis-workspace/c-panels/panels.md#data-view)。 Content Analytics报表仅适用于[为Content Analytics配置了](/help/content-analytics/config/configuration.md)的数据视图。
1. 将![表](/help/assets/icons/Table.svg) [自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)可视化拖动到画布上。
1. 使用[特定的Content Analytics组件](components.md)和其他通用的[组件](/help/components/overview.md)（如筛选器、日期范围、注释）来构建您的内容分析见解。 或者，使用[内容分析模板](#template)。

## 缩略图

根据您在项目中使用的Content Analytics特定维度，将显示资源和维度的缩略图。

![Content Analytics缩略图](../assets/aca-thumbnails.png)

## 预览

对于具有缩略图的维度（如资产名称、体验名称等），您可以打开预览弹出窗口。

要打开带有以下详细信息的预览，请执行以下操作：

* 选择![信息大纲](/help/assets/icons/InfoOutline.svg)。 您会看到以下详细信息。

  | 体验预览 | 资源预览 |
  |---|---|
  | ![Content Analytics体验预览](../assets/aca-experience-preview.png) | ![Content Analytics资产预览](../assets/aca-asset-preview.png) |
  | **[!UICONTROL 体验的名称]** | **[!UICONTROL 资源的名称]** |
  | **[!UICONTROL 展示次数（所有时间）]**：体验的展示次数。 | **[!UICONTROL 展示次数（所有时间）]**：资源的展示次数。 |
  | **[!UICONTROL Assets]**：此体验包含的资源数。 选择![划分](/help/assets/icons/Breakdown.svg) **[!UICONTROL 划分]**&#x200B;以检查资产。 | **[!UICONTROL 体验]**：在其中显示此资源的体验数。 ![划分](/help/assets/icons/Breakdown.svg) **[!UICONTROL 划分]**&#x200B;以检查资源。 |
  | **[!UICONTROL 首次展示]**：体验首次展示的日期。 | **[!UICONTROL 首次展示]**：资产的首次展示日期。 |
  | **[!UICONTROL 最近展示]**：体验最近展示的日期。 | **[!UICONTROL 最近展示]**：资源最近展示的日期。 |
  | **[!UICONTROL 体验属性]**：体验的属性。 | **[!UICONTROL 资产属性]**：资产的属性。 |


## 模板

内容分析[模板](/help/analysis-workspace/templates/use-templates.md)可帮助您了解哪些内容和内容属性的表现最佳。 模板是[Web渠道和参与用例](/help/analysis-workspace/templates/use-templates.md#web-engagement)的一部分，它详细说明了内容在粒度级别上的执行情况。 您可以查看单个资产的性能或特定属性。

根据您学到的内容，您可能会执行许多操作。 如在主页中推广高性能资产，为特定区段个性化内容以包括高性能属性，或轮换已开始陈旧的内容。

要使用模板，请执行以下操作：

1. 从主菜单中选择&#x200B;**[!UICONTROL Workspace]**。
1. 确保已选择为Content Analytics配置的数据视图。
1. 搜索或使用筛选器(**[!UICONTROL 渠道]**&#x200B;的&#x200B;**[!UICONTROL Web]**&#x200B;和[!UICONTROL 用例]**的**4}参与&#x200B;]**)来查找和选择**[!UICONTROL &#x200B;内容分析&#x200B;]**模板。**[!UICONTROL 
1. 选择&#x200B;**[!UICONTROL 使用模板]**。
1. 在&#x200B;**[!UICONTROL 设置模板]**&#x200B;对话框中，从&#x200B;**[!UICONTROL 选择转化量度]**&#x200B;对话框中选择量度。 例如，**[!UICONTROL 资产CTR]**。
1. 选择&#x200B;**[!UICONTROL 继续]**。

将在Workspace中打开&#x200B;**[!UICONTROL Content Analytics概述]**&#x200B;项目。 该项目由四个面板组成，每个面板都回答具体问题：

* **哪些内容的性能最佳？**
此面板可帮助您了解哪些体验以及这些体验中的哪些资产正在促进参与和转化。 体验是在特定时间捕获的完整网页。 一个体验可以同时包含文本和多个单独的图像资源。 资产是个别图像。

  该面板由以下可视化图表组成：

   * **体验**

      * **体验CTR**：摘要更改可视化图表，显示体验CTR。
      * **排名最前的转化体验**：一个水平条形图可视化图表，其中显示基于所选转化量度的排名最前的转化体验。
      * **表现最佳的体验**：表现最佳的体验的自由格式表（包括缩略图和预览）。

   * **资源**

      * **资源CTR**
显示Asset CTR的[摘要变化](/help/analysis-workspace/visualizations/summary-number-change.md)可视化图表。
      * **排名最前的转化资产**
一个[水平条形图](/help/analysis-workspace/visualizations/horizontal-bar.md)可视化图表，它根据所选的转化量度显示排名最前的转化资产。
      * **表现最佳的资产**
针对表现最好的资产的[自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)（包括[缩略图](#thumbnails)和[预览](#previews)）。
      * **Assets — 查看次数与转化率。**
[散点图](/help/analysis-workspace/visualizations/scatterplot.md)可视化图表，它显示资源视图与资源转换的散点图。

* **哪些资产属性有助于转化？**
Content Analytics使用AI和GenAI自动分配每个资源元数据，如主题、场景、前景色等。 属性是为AI分配的元数据标记，用于描述资源或体验中的内容。 例如：<code>前景色：红色</code> 是自动分配的属性。 可视化图表可帮助您识别哪些资产的属性对转化贡献最大。

  该面板由以下可视化图表组成：

   * **排名最前的转换资产属性**
一个[水平条](/help/analysis-workspace/visualizations/horizontal-bar.md)，它根据所选的转化量度显示排名最前的转化资产属性。
   * **排名最前的转化资产属性与前30天的对比**
一个[水平条形图](/help/analysis-workspace/visualizations/horizontal-bar.md)可视化图表，它根据所选的转化量度显示与前30天相比排名最前的转化资产属性。
   * **排名最前的转换资产属性数据**
一个[自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)，它根据所选的转化量度显示排名最前的转化属性。 选择表格中的一行以更新属性趋势可视化图表。
   * **属性趋势**
显示所选转化率最高的资产属性的属性趋势的[折线图](/help/analysis-workspace/visualizations/line.md)可视化图表。
   * **资源前景颜色**
示例[自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)，比较单个资源属性类别（前景颜色）中项目的性能。 您可以将此资源属性替换为其他资源属性类别维度。

* **哪些体验属性有助于转化？**
虽然资产属性侧重于图像的视觉品质，但体验属性侧重于页面的文本。 通过下面的可视化图表，您可以探索哪些体验属性有助于转化。 这些属性也使用AI和GenAI模型自动分配。

  该面板由以下可视化图表组成：

   * **排名最前的转换体验属性**
一个[水平条形图](/help/analysis-workspace/visualizations/horizontal-bar.md)可视化图表，它根据所选的转化量度显示排名最前的转化体验属性。
   * **排名最前的转化体验属性与前30天的对比**
一个[水平条形图](/help/analysis-workspace/visualizations/horizontal-bar.md)可视化图表，它根据所选的转化量度显示与前30天相比排名最前的转化体验属性。
   * **排名最前的转换体验属性数据**
一个[自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)，它根据所选的转化量度显示排名最前的转化体验。 选择表格中的一行以更新折线图可视化图表。
   * **行**
显示所选排名最前的转化体验属性趋势的[折线图](/help/analysis-workspace/visualizations/line.md)可视化图表。
   * **体验关键字**
一个[自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)，它根据所选的转化量度显示排名最前的体验关键字。

* **我的网站上的资产显示位置？**
由一个自由格式表组成的面板，该表详细说明了网站上显示视图次数最多的资源的位置。

  面板由一个可视化图表组成：

   * **查看次数最多的资源会显示在何处？**
您可以按维度划分任何资产ID，这有助于您更好地了解该图像出现的位置。

     在此示例中，[自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)（包括[缩略图](#thumbnails)和[预览](#previews)）使用了&#x200B;[!UICONTROL *资产感知ID*]，而不是&#x200B;[!UICONTROL *资产ID*]。 有时，网站上可能会使用不同的图像URL来复制完全相同的图像。 [!UICONTROL _资产感知_]&#x200B;属性有助于将这些重复项分组到单个ID下。 由于资产可以在页面上更改，因此每个资产将按&#x200B;[!UICONTROL _体验ID_]&#x200B;进行划分，以标识资产所在的页面版本。

     您可以将&#x200B;[!UICONTROL _Experience ID_]&#x200B;替换为有助于您了解网站上资产位置的其他维度。 例如，[!UICONTROL _页面名称_]、[!UICONTROL _页面URL_]&#x200B;或&#x200B;[!UICONTROL _网站区域_]。

     您还可以交换&#x200B;[!UICONTROL _感知ID_]&#x200B;和&#x200B;[!UICONTROL _资产ID_]，以获取特定图像URL被引用位置的记录。


>[!MORELIKETHIS]
>
>[Content Analytics组件](components.md)
>[使用模板](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
