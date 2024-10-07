---
keywords: Analysis Workspace
title: Analysis Workspace 概述
description: Analysis Workspace 功能概览
feature: Workspace Basics
exl-id: 9075518e-54fe-49a6-9601-aa9468187b8f
solution: Customer Journey Analytics
role: User
source-git-commit: df0fd0af8a22c84705c3dea11065132359dd80ff
workflow-type: tm+mt
source-wordcount: '1479'
ht-degree: 13%

---

# Analysis Workspace 概述 {#analysis-workspace-overview}

Analysis Workspace允许您快速构建分析以收集见解，然后与其他人共享这些见解。 使用拖放浏览器界面，您可以进行分析、添加可视化图表以便直观地呈现数据、组织数据集，并与您选择的任何人共享和计划[项目](/help/analysis-workspace/build-workspace-project/freeform-overview.md)。


+++ 观看一段视频，其中展示了Analytics Workspace的各种可能性。

>[!VIDEO](https://video.tv.adobe.com/v/26266/?quality=12)

{{videoaa}}

+++

## 界面

下图及随附的表解释了Analysis Workspace用户界面中的主要元素：

![Analysis Workspace窗口，突出显示最左侧和最左侧面板、画布和数据视图下拉菜单。](assets/analysis-workspace-overview.png)

| 位置 | 名称和功能 |
|:---------:|----------|
| ?? | 包含项目名称、用于访问功能的菜单结构、用于返回到“项目”列表的按钮![ChevronLeft](/help/assets/icons/ChevronLeft.svg)以及用于[共享您的Workspace项目](/help/analysis-workspace/curate-share/share-projects.md)的&#x200B;**[!UICONTROL 共享]**&#x200B;按钮。 <br/>随时选择项目的名称（例如：新建项目）以更改名称。 <br/>选择![星形大纲](/help/assets/icons/StarOutline.svg)以将您的项目标记为收藏项目![星形](/help/assets/icons/Star.svg)。 |
| ?? | **按钮面板：**&#x200B;包含用于访问Analysis Workspace的[功能](#features)键的按钮：<ul><li>![网页](/help/assets/icons/WebPage.svg) [[!UICONTROL 面板]](/help/analysis-workspace/c-panels/panels.md)</li><li>![引导分析](/help/assets/icons/GuidedAnalysis.svg) [[!UICONTROL 引导分析]](/help/guided-analysis/overview.md)</li><li>![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) [[!UICONTROL 可视化图表]](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</li><li>![策划](/help/assets/icons/Curate.svg) [[!UICONTROL 组件]](/help/components/overview.md)</li><li>![ViewList](/help/assets/icons/ViewList.svg) [[!UICONTROL 目录]](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md)</li><li>![书签](/help/assets/icons/Bookmark.svg) [[!UICONTROL 数据字典]](/help/components/data-dictionary/data-dictionary-overview.md)</li></ul> |
| ?? | **左侧面板：**&#x200B;此区域包含单独的面板、可视化图表、组件或列表。 内容取决于在按钮面板中选择的按钮。 |
| ?? | **画布：**&#x200B;从左侧面板拖动内容以生成项目的主区域。 当您添加面板、向面板添加可视化图表并向可视化图表添加组件时，项目会动态更新。 您可以创建多个面板，并在每个面板中创建多个可视化图表。<br/>每个面板都基于所选的数据视图。 所选数据视图确定量度和维度等可用组件。 有关详细信息，请参阅[面板 — 数据视图](/help/analysis-workspace/c-panels/panels.md#data-view)。 |

## 功能

Analysis Workspace的主要功能可通过按钮面板使用：

| 图标 | 功能 | 描述 |
|:---:|---|---|
| ![网页](/help/assets/icons/WebPage.svg) | **[!UICONTROL 面板]** | [“面板”](/help/analysis-workspace/c-panels/panels.md)可以包含许多表格和可视化图表，用于在项目中对分析进行组织和整理。Analysis Workspace 中提供的许多面板都可以基于一些用户输入来生成整套分析。 |
| ![引导式分析](/help/assets/icons/GuidedAnalysis.svg) | **[!UICONTROL 引导式分析]** | [引导式分析](../guided-analysis/overview.md)允许您通过引导式工作流自助提供有关客户历程的高质量数据和见解。 您可以创建要包含在Workspace项目中的分析，也可以包含之前保存的现有分析。 |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | **[!UICONTROL 可视化图表]** | [可视化图表](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)（如条形图或折线图）可用于直观地呈现数据。 在最左侧的面板中，选择中间的&#x200B;**[!UICONTROL 可视化图表]**&#x200B;图标，以查看所有可用的可视化图表。 |
| ![策划](/help/assets/icons/Curate.svg) | **[!UICONTROL 组件]** | [组件](/help/components/overview.md)包含以下元素：<ul><li>![Dimension](/help/assets/icons/Dimensions.svg) [Dimension](/help/components/dimensions/overview.md)</li><li>![事件](/help/assets/icons/Event.svg) [量度](/help/components/apply-create-metrics.md)</li><li>![分段](/help/assets/icons/Segmentation.svg) [筛选器](/help/components/filters/filters-overview.md)</li><li>![日历](/help/assets/icons/Calendar.svg) [日期范围](/help/components/date-ranges/overview.md)</li></ul> |
| ![视图列表](/help/assets/icons/ViewList.svg) | **[!UICONTROL 目录]** | 目录将项目中包含的所有面板和可视化图表都整理到一个可折叠列表中，以便您快速访问特定的面板或可视化图表。 |
| ![书签](/help/assets/icons/Bookmark.svg) | **数据字典** | [数据字典](/help/components/data-dictionary/data-dictionary-overview.md)可帮助用户和管理员跟踪并更好地了解其Analytics环境中的组件。 |


##  菜单

Analysis Workspace的大多数功能都可以通过拖放以及面板、可视化图表和组件中的上下文菜单来使用。

此功能也可以通过Workspace菜单和快捷键或热键使用。 快捷键因浏览器运行的操作系统而异。 有关概述，请参阅下表。

请注意，键盘上可能使用以下符号：

- **⇧**&#x200B;用于&#x200B;**[!UICONTROL *shift *]**。
- **[!UICONTROL *cmd *]**（命令）的**⌘**。
- **[!UICONTROL *ctrl *]**（控件）的**⌃**。
- 针对&#x200B;**[!UICONTROL *⌥opt *]**（选项）的****。
- **[!UICONTROL *alt *]**的**⎇**（替代）。

有关可用菜单的概述，请参见下表。

| **[!UICONTROL 项目]** | Mac快捷键 | 快捷方式窗口 | 描述 |
|---|---|---|---|
| **[!UICONTROL 创建项目]** | **[!UICONTROL *shift+cmd+p *]** | **[!UICONTROL *shift+ctrl+p *]** | 创建新项目。 |
| **[!UICONTROL 创建移动记分卡]** | | | [创建新的移动记分卡](/help/mobile-app/create-scorecard.md)。 |
| **[!UICONTROL 打开……]** | **[!UICONTROL *cmd+o *]** | **[!UICONTROL *ctrl+o *]** | [打开现有项目](/help/analysis-workspace/build-workspace-project/save-projects.md#open-another-project)。 |
| **[!UICONTROL 打开以前的版本……]** | **[!UICONTROL *opt+cmd+o *]** | **[!UICONTROL *alt+ctrl+o *]** | [打开项目的早期版本](/help/analysis-workspace/build-workspace-project/save-projects.md#open-previous-version)。 |
| **[!UICONTROL 保存]** | **[!UICONTROL *cmd+s *]** | **[!UICONTROL *ctrl+s *]** | [保存您的项目](/help/analysis-workspace/build-workspace-project/save-projects.md#save-projects)。 |
| **[!UICONTROL 保存并添加注释……]** | **[!UICONTROL *opt+cmd+s *]** | **[!UICONTROL *alt+ctrl+s *]** | [向保存的项目版本添加注释](/help/analysis-workspace/build-workspace-project/save-projects.md#save-project-options)。 |
| **[!UICONTROL 另存为……]** | **[!UICONTROL *shift+cmd+s *]** | **[!UICONTROL *shift+ctrl+s *]** | [使用其他名称和详细信息保存项目](/help/analysis-workspace/build-workspace-project/save-projects.md#save-project-options)。 |
| **[!UICONTROL 刷新项目]** | **[!UICONTROL *opt+r *]** | **[!UICONTROL *alt+r *]** | 刷新项目。 |
| **[!UICONTROL 下载 CSV]** | **[!UICONTROL *shift+cmd+v *]** | **[!UICONTROL *shift+ctrl+v *]** | 以CSV文件格式下载项目。 |
| **[!UICONTROL 下载PDF]** | **[!UICONTROL *shift+cmd+b *]** | **[!UICONTROL *shift+ctrl+b *]** | 将项目下载为PDF文档。 |
| **[!UICONTROL 项目信息和设置]** | | | 定义项目的设置，如名称、标记、调色板等。 |
| **[!UICONTROL 用户设置]** | | | [配置首选项以使用Analysis Workspace](/help/analysis-workspace/user-preferences.md)。 |


| **[!UICONTROL 编辑]** | Mac快捷键 | 快捷方式窗口 | 描述 |
|---|---|---|---|
| **[!UICONTROL 撤消]** | **[!UICONTROL *cmd+z *]** | **[!UICONTROL *ctrl+z *]** | 撤消上一个操作。 |
| **[!UICONTROL 重做]** | **[!UICONTROL *cmd+shift+z *]** | **[!UICONTROL *ctrl+shift+z *]** | 重做上一个操作。 |
| **[!UICONTROL 全部清除]** | **[!UICONTROL *选择加w *]** | **[!UICONTROL *alt+w *]** | 清除当前项目中的所有面板。 |

| **[!UICONTROL 插入]** | Mac快捷键 | 快捷方式窗口 | 描述 |
|---|---|---|---|
| **[!UICONTROL 空白面板]** | **[!UICONTROL *opt+b *]** | **[!UICONTROL *alt+b *]** | 插入[空白面板](/help/analysis-workspace/c-panels/blank-panel.md)。 |
| **[!UICONTROL 媒体并行查看者]** | **[!UICONTROL *opt+h *]** | **[!UICONTROL *alt-h *]** | 插入[媒体并行查看者](/help/analysis-workspace/c-panels/media-concurrent-viewers.md)面板。 |
| **[!UICONTROL 媒体播放耗时]** | **[!UICONTROL *选择+i *]** | **[!UICONTROL *alt+i *]** | 插入[媒体播放耗时](/help/analysis-workspace/c-panels/media-playback-time-spent.md)面板。 |
| **[!UICONTROL 媒体平均受众访问分钟数]** | **[!UICONTROL *opt+m *]** | **[!UICONTROL *alt+m *]** | 插入[媒体平均受众访问分钟数](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)面板。 |
| **[!UICONTROL 归因]** | **[!UICONTROL *选择+e *]** | **[!UICONTROL *alt+e *]** | 插入[归因](/help/analysis-workspace/c-panels/attribution.md)面板。 |
| **[!UICONTROL 自由格式]** | **[!UICONTROL *选择+a *]** | **[!UICONTROL *alt+a *]** | 插入[自由格式](/help/analysis-workspace/c-panels/freeform-panel.md)面板。 |
| **[!UICONTROL 快速分析]** | **[!UICONTROL *opt+j *]** | **[!UICONTROL *alt+j *]** | 插入[快速分析](/help/analysis-workspace/c-panels/quickinsight.md)面板。 |
| **[!UICONTROL 正在试验]** | **[!UICONTROL *opt+x *]** | **[!UICONTROL *alt+x *]** | 插入[试验](/help/analysis-workspace/c-panels/experimentation.md)面板。 |
| **[!UICONTROL 自由格式表]** | **[!UICONTROL *opt+1 *]** | **[!UICONTROL *alt+1 *]** | 插入[自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)可视化图表。 |
| **[!UICONTROL 折线图]** | **[!UICONTROL *opt+2 *]** | **[!UICONTROL *alt+2 *]** | 插入[折线图](/help/analysis-workspace/visualizations/line.md)可视化图表。 |
| **[!UICONTROL 条形图]** | **[!UICONTROL *opt+3 *]** | **[!UICONTROL *alt+3 *]** | 插入[条形图](/help/analysis-workspace/visualizations/bar.md)可视化图表。 |
| **[!UICONTROL 组合]** | **[!UICONTROL *opt+4 *]** | **[!UICONTROL *alt+4 *]** | 插入[组合](/help/analysis-workspace/visualizations/combo-charts.md)可视化图表。 |


| **[!UICONTROL 组件]** | Mac快捷键 | 快捷方式窗口 | 描述 |
|---|---|---|---|
| **[!UICONTROL 创建筛选器……]** | **[!UICONTROL *shift+cmd+e *]** | **[!UICONTROL *shift+ctrl+e *]** | 创建新的[筛选器](/help/components/filters/create-filters.md)。 |
| **[!UICONTROL 创建指标……]** | **[!UICONTROL *shift+cmd+c *]** | **[!UICONTROL *shift+ctrl+c *]** | 创建新的[计算量度](/help/components/calc-metrics/calc-metr-overview.md)。 |
| **[!UICONTROL 创建日期范围……]** | **[!UICONTROL *shift+cmd+d *]** | **[!UICONTROL *shift+ctrl+d *]** | 创建新的[数据范围](/help/components/date-ranges/overview.md)。 |
| **[!UICONTROL 创建批注……]** | **[!UICONTROL *shift+cmd+o *]** | **[!UICONTROL *shift+ctrl+o *]** | 创建新的[批注](/help/components/annotations/overview.md)。 |
| **[!UICONTROL 创建受众……]** | **[!UICONTROL *shift+cmd+u *]** | **[!UICONTROL *shift+ctrl+u *]** | 创建新的[受众](/help/components/audiences/audiences-overview.md)。 |
| **[!UICONTROL Refewsh组件]** | **[!UICONTROL *opt+shift+r *]** | **[!UICONTROL *alt+shift+r *]** | 刷新项目中的组件。 |

| **[!UICONTROL 共享]** | Mac快捷键 | 快捷方式窗口 | 描述 |
|---|---|---|---|
| **[!UICONTROL 与Workspace用户共享]** | **[!UICONTROL *cmd+h *]** | **[!UICONTROL *ctrl+h *]** | [与其他Workspace用户共享项目](/help/analysis-workspace/curate-share/share-projects.md#share-with-customer-journey-analytics-users-and-groups-in-your-organization)。 |
| **[!UICONTROL 与任何人共享]** | **[!UICONTROL *opt+l *]** | **[!UICONTROL *alt+l *]** | [与任何人](/help/analysis-workspace/curate-share/share-projects.md#share-a-link-to-a-project)共享项目的只读版本。 |
| **[!UICONTROL 发送文件]** | **[!UICONTROL 个选择+s]** | **[!UICONTROL *alt+s *]** | [将项目作为CSV或PDF文件发送给其他收件人](/help/analysis-workspace/curate-share/send-schedule-files.md)。 |
| **[!UICONTROL 计划文件导出]** | **[!UICONTROL *shift+opt+s *]** | **[!UICONTROL *shift+alt+s *]** | [将项目以CSV或PDF文件的形式按计划发送给其他收件人](/help/analysis-workspace/curate-share/send-schedule-files.md)。 |
| **[!UICONTROL 策划项目数据]** | **[!UICONTROL *shift+cmd+g *]** | **[!UICONTROL *shift+ctrl+g *]** | [策划项目数据](/help/analysis-workspace/curate-share/curate.md)。 |

| 帮助 | Mac快捷键 | 快捷方式窗口 | 描述 |
|---|---|---|---|
| **[!UICONTROL 视频]** | | | 在新的浏览器选项卡中打开Customer Journey AnalyticsYouTube渠道。 |
| **[!UICONTROL 帮助文档]** | | | 在新的浏览器选项卡中打开文档（您现在实际上正在阅读……）。 |
| **[!UICONTROL 帮助论坛]** | | | 在新的Experience League标签页中打开Adobe Analytics浏览器社区论坛。 |
| **[!UICONTROL 热键]** | | | 显示可在Workspace中使用的热键（快捷键）的概述。 |
| **[!UICONTROL 启用调试器]** |  | | 启用调试器。 您的项目将重新加载。 |
| **[!UICONTROL 禁用调试器]** | | | 禁用调试器。 您的项目将重新加载。 |
| **[!UICONTROL 性能]** | | | 显示一个对话框，其中显示有关&#x200B;**[!UICONTROL Analysis Workspace性能]**&#x200B;的指标。 使用&#x200B;**[!UICONTROL 以CSV格式下载]**&#x200B;以下载性能度量的CSV文件。 |
| **[!UICONTROL 关于Workspace]** | | | 显示&#x200B;**[!UICONTROL 关于Analysis Workspace]**&#x200B;对话框，其中包含版本信息、功能访问级别和活动功能标志。 |

## 数据源

可同步可视化以控制哪些数据表或数据源与可视化相对应。 有关详细信息，请参阅[管理数据源](/help/analysis-workspace/visualizations/t-sync-visualization.md)。

## 使用Analysis Workspace


要开始使用Analysis Workspace，请执行以下操作：

1. 登录到[Adobe Experience Cloud](https://experience.adobe.com)。
1. 从界面右上角的应用程序切换器![应用程序](/help/assets/icons/Apps.svg)中选择&#x200B;**[!UICONTROL Customer Journey Analytics]**。
1. 默认显示Analysis Workspace的&#x200B;**[!UICONTROL 项目]**&#x200B;页面。 如果已为您选择了特定项目，或者您最近一直在处理该项目，则默认情况下将显示该项目。

### 创建项目

Analysis Workspace 中的分析被称作[项目](/help/analysis-workspace/build-workspace-project/freeform-overview.md)。

您可以在 Analysis Workspace 中创建项目，如[创建项目](/help/analysis-workspace/build-workspace-project/create-projects.md)中所述。

可以将项目组织到文件夹和子文件夹中，如 [Analysis Workspace 中的文件夹](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)中所述。

### 保存和共享项目

在 Analysis Workspace 中创建分析时，您的工作将[自动保存](/help/analysis-workspace/build-workspace-project/save-projects.md)。

当您完成项目构建并收集可操作见解时，其他人可能会希望使用该项目。 您可以与组织内的用户和组甚至组织外的人员共享项目。有关共享项目的信息，请参阅[共享项目](/help/analysis-workspace/curate-share/share-projects.md)。

## 其他资源 {#resources}

- Customer Journey Analytics中的[学习登录](/help/getting-started/landing.md#learning)页面。 本页是熟悉Analysis Workspace的绝佳方式。 特别是学习Workspace的基础知识。 此模板将指导您逐步了解在Workspace中构建首个分析的常用术语和步骤
- Adobe 提供了大量的 [Analytics 视频培训教程](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/overview)。
- 有关新功能的更新，请参阅 [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/en/docs/release-notes/experience-cloud/current)。

