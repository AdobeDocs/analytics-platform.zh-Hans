---
keywords: Analysis Workspace
title: Analysis Workspace 概述
description: 了解Adobe Analytics的首要分析工具Analysis Workspace。 使用项目、面板、表格、可视化和其他组件使数据形象化，并策划和共享您的分析。
feature: Workspace Basics
exl-id: 9075518e-54fe-49a6-9601-aa9468187b8f
solution: Customer Journey Analytics
role: User
source-git-commit: 9056b8b172ae7a2267bf12de4b2355d1a1364b32
workflow-type: tm+mt
source-wordcount: '1490'
ht-degree: 97%

---

# Analysis Workspace 概述 {#analysis-workspace-overview}

利用 Analysis Workspace，可以快速生成分析以收集洞察，然后与其他人共享这些洞察。可以使用拖放浏览器界面进行分析、添加可视化内容以便直观地呈现数据、梳理数据集以及与您选定的任何人员共享和安排[项目](/help/analysis-workspace/build-workspace-project/freeform-overview.md)。

>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace 概述](https://video.tv.adobe.com/v/26266/?quality=12&learn=on){target="_blank"}以获取演示视频。

{{videoaa}}

>[!ENDSHADEBOX]

## 界面

下面的图像和附表解释了 Analysis Workspace 用户界面中的主要元素：

![Analysis Workspace 窗口突出显示了界面的各个部分](assets/analysis-workspace-overview.png)

| 位置 | 名称和功能 |
|:---------:|----------|
| A | 包含项目名称、用于访问功能的菜单结构、返回项目列表的按钮![“返回”按钮](/help/assets/icons/ChevronLeft.svg)，以及[分享 Workspace 项目](/help/analysis-workspace/curate-share/share-projects.md)的&#x200B;**[!UICONTROL 分享]**&#x200B;按钮。<br/>随时选择您的项目名称（例如：新项目）即可更改名称。<br/>选择![取消收藏](/help/assets/icons/StarOutline.svg)将您的项目标记为收藏的项目![收藏](/help/assets/icons/Star.svg)。 |
| B | **按钮面板：**&#x200B;包含用于访问Analysis Workspace的[功能](#features)键的按钮：<ul><li>![WebPage](/help/assets/icons/WebPage.svg) [[!UICONTROL 面板]](/help/analysis-workspace/c-panels/panels.md)</li><li>![引导式分析](/help/assets/icons/GuidedAnalysis.svg) [[!UICONTROL 引导式分析]](/help/guided-analysis/overview.md)</li><li>![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) [[!UICONTROL 可视化]](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</li><li>![策划](/help/assets/icons/Curate.svg) [[!UICONTROL 组件]](/help/components/overview.md)</li><li>![ViewList](/help/assets/icons/ViewList.svg) [[!UICONTROL 目录]](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md)</li><li>![书签](/help/assets/icons/Bookmark.svg) [[!UICONTROL 数据字典]](/help/components/data-dictionary/data-dictionary-overview.md)</li></ul> |
| C | **左侧面板：**&#x200B;该区域包含单独的面板、可视化内容、组件或列表。相关内容取决于按钮面板中选择的按钮。 |
| D | **画布：**&#x200B;从左侧面板拖动内容以构建项目的主要区域。当您添加面板、向面板添加可视化效果以及向可视化效果添加组件时，项目会动态更新。您可以创建多个面板，并且在每个面板内可以创建多个可视化效果。<br/>每个面板均基于选定的数据视图。所选的数据视图决定了可用的组件，例如量度和维度。请参阅[面板：数据视图](/help/analysis-workspace/c-panels/panels.md#data-view)，了解更多信息。 |

## 功能

Analysis Workspace 的主要功能可通过按钮面板使用：

| 图标 | 功能 | 描述 |
|:---:|---|---|
| ![WebPage](/help/assets/icons/WebPage.svg) | **[!UICONTROL 面板]** | [面板](/help/analysis-workspace/c-panels/panels.md)可以包含许多表格和可视化内容，用于在项目中对分析进行组织和整理。Analysis Workspace 中提供的许多面板都可以基于一些用户输入来生成整套分析。 |
| ![Guided Analysis](/help/assets/icons/GuidedAnalysis.svg) | **[!UICONTROL 引导式分析]** | [引导式分析](../guided-analysis/overview.md)允许您通过引导式工作流自助获取有关客户历程的高质量数据和洞察。您可以创建一个分析，以将其纳入您的 Workspace 项目中，或包含之前保存的现有分析。 |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | **[!UICONTROL 可视化内容]** | [可视化内容](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)（例如条形图或折线图）可用于直观地呈现数据。在最左侧面板中，选择中间的&#x200B;**[!UICONTROL 可视化内容]**&#x200B;图标可查看所有可用的可视化内容。 |
| ![Curate](/help/assets/icons/Curate.svg) | **[!UICONTROL 组件]** | [组件](/help/components/overview.md)包括以下元素：<ul><li>![Dimensions](/help/assets/icons/Dimensions.svg) [维度](/help/components/dimensions/overview.md)</li><li>![Event](/help/assets/icons/Event.svg) [量度](/help/components/apply-create-metrics.md)</li><li>![分段](/help/assets/icons/Segmentation.svg) [区段](/help/components/segments/seg-overview.md)</li><li>![Calendar](/help/assets/icons/Calendar.svg) [日期范围](/help/components/date-ranges/overview.md)</li></ul> |
| ![ViewList](/help/assets/icons/ViewList.svg) | **[!UICONTROL 目录]** | 目录会将项目中包含的所有面板和可视化内容组织成一个可折叠列表，以便您能够快速访问特定的面板或可视化内容。 |
| ![Bookmark](/help/assets/icons/Bookmark.svg) | **数据字典**  | [数据字典](/help/components/data-dictionary/data-dictionary-overview.md)可以帮助用户和管理员跟踪并更好地理解 Analytics 环境中的组件。 |


## 菜单

Analysis Workspace 的大部分功能可通过拖放以及面板、可视化内容和组件内的上下文菜单实现。

还可以通过 Workspace 菜单和快捷方式或热键使用相关功能。快捷键根据浏览器所运行的操作系统而有所不同。概述见下表。

请注意，您的键盘上可能会使用以下符号：

- **⇧** 表示 **[!UICONTROL *shift *]**&#x200B;键。
- **⌘** 表示 **[!UICONTROL *cmd *]**（命令）。
- **⌃** 表示 **[!UICONTROL *ctrl *]**（控制）。
- **⌥** 表示 **[!UICONTROL *opt *]**（选项）。
- **⎇** 表示 **[!UICONTROL *alt *]**（备选）。

请参阅下表以了解可用菜单的概述。

| **[!UICONTROL 项目]** | Mac 快捷方式 | Windows 快捷方式 | 描述 |
|---|---|---|---|
| **[!UICONTROL 创建项目]** | **[!UICONTROL *Shift+cmd+p *]** | **[!UICONTROL *shift+ctrl+p *]** | 创建一个新项目。 |
| **[!UICONTROL 创建移动记分卡]** | | | [创建新的移动记分卡](/help/mobile-app/create-scorecard.md)。 |
| **[!UICONTROL 打开……]** | **[!UICONTROL *cmd+o *]** | **[!UICONTROL *ctrl+o *]** | [打开现有项目](/help/analysis-workspace/build-workspace-project/save-projects.md#open-another-project)。 |
| **[!UICONTROL 打开以前的版本……]** | **[!UICONTROL *opt+cmd+o *]** | **[!UICONTROL *alt+ctrl+o *]** | [打开项目的早期版本](/help/analysis-workspace/build-workspace-project/save-projects.md#open-previous-version)。 |
| **[!UICONTROL 保存]** | **[!UICONTROL *cmd+s *]** | **[!UICONTROL *ctrl+s *]** | [保存项目](/help/analysis-workspace/build-workspace-project/save-projects.md#save-projects)。 |
| **[!UICONTROL 保存并添加注释……]** | **[!UICONTROL *opt+cmd+s *]** | **[!UICONTROL *alt+ctrl+s *]** | [为您保存的项目版本添加注释](/help/analysis-workspace/build-workspace-project/save-projects.md#save-project-options)。 |
| **[!UICONTROL 另存为……]** | **[!UICONTROL *shift+cmd+s *]** | **[!UICONTROL *shift+ctrl+s *]** | [使用不同的名称和详细信息保存项目](/help/analysis-workspace/build-workspace-project/save-projects.md#save-project-options)。 |
| **[!UICONTROL 刷新项目]** | **[!UICONTROL *opt+r *]** | **[!UICONTROL *alt+r *]** | 刷新项目。 |
| **[!UICONTROL 下载 CSV]** | **[!UICONTROL *shift+cmd+v *]** | **[!UICONTROL *shift+ctrl+v *]** | 将项目下载为 CSV 文件。 |
| **[!UICONTROL 下载 PDF]** | **[!UICONTROL *shift+cmd+b *]** | **[!UICONTROL *shift+ctrl+b *]** | 以 PDF 文档的形式下载项目。 |
| **[!UICONTROL 项目信息和设置]**  | | | 定义项目的设置，例如名称、标记、调色板等。 |
| **[!UICONTROL 用户设置]** | | | [配置使用 Analysis Workspace 的偏好设置](/help/analysis-workspace/user-preferences.md) 。 |


| **[!UICONTROL 编辑]** | Mac 快捷方式 | Windows 快捷方式 | 描述 |
|---|---|---|---|
| **[!UICONTROL 撤销]** | **[!UICONTROL *cmd+z *]** | **[!UICONTROL *ctrl+z *]** | 撤消上一个操作。 |
| **[!UICONTROL 重做]** | **[!UICONTROL *cmd+shift+z *]** | **[!UICONTROL *ctrl+shift+z *]** | 重新执行上一个操作。 |
| **[!UICONTROL 全部清除]** | **[!UICONTROL *opt+w *]** | **[!UICONTROL *alt+w *]** | 清除当前项目中的所有面板。 |

| **[!UICONTROL 插入]** | Mac 快捷方式 | Windows 快捷方式 | 描述 |
|---|---|---|---|
| **[!UICONTROL 空白面板]** | **[!UICONTROL *opt+b *]** | **[!UICONTROL *alt+b *]** | 插入[空白面板](/help/analysis-workspace/c-panels/blank-panel.md)。 |
| **[!UICONTROL 媒体并行观众]** | **[!UICONTROL *opt+h *]** | **[!UICONTROL *alt-h *]** | 插入[媒体并行观众](/help/analysis-workspace/c-panels/media-concurrent-viewers.md)面板。 |
| **[!UICONTROL 媒体播放耗时]** | **[!UICONTROL *opt+i *]** | **[!UICONTROL *alt+i *]** | 插入[媒体播放耗时](/help/analysis-workspace/c-panels/media-playback-time-spent.md)面板。 |
| **[!UICONTROL 媒体平均分钟观众数]** | **[!UICONTROL *opt+m *]** | **[!UICONTROL *alt+m *]** | 插入[媒体平均分钟观众数](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)面板。 |
| **[!UICONTROL 归因]** | **[!UICONTROL *opt+e *]** | **[!UICONTROL *alt+e *]** | 插入[归因](/help/analysis-workspace/c-panels/attribution.md)面板。 |
| **[!UICONTROL 自由格式表]** | **[!UICONTROL *opt+a *]** | **[!UICONTROL *alt+a *]** | 插入[自由格式](/help/analysis-workspace/c-panels/freeform-panel.md)面板。 |
| **[!UICONTROL 快速洞察]** | **[!UICONTROL *opt+j *]** | **[!UICONTROL *alt+j *]** | 插入[快速洞察](/help/analysis-workspace/c-panels/quickinsight.md)面板。 |
| **[!UICONTROL 试验]** | **[!UICONTROL *opt+x *]** | **[!UICONTROL *alt+x *]** | 插入[试验](/help/analysis-workspace/c-panels/experimentation.md)面板。 |
| **[!UICONTROL 自由格式表]** | **[!UICONTROL *opt+1 *]** | **[!UICONTROL *Alt + 1 *]** | 插入[自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)可视化内容。 |
| **[!UICONTROL 折线图]** | **[!UICONTROL *opt+2 *]** | **[!UICONTROL *Alt + 2 *]** | 插入[折线图](/help/analysis-workspace/visualizations/line.md)可视内容。 |
| **[!UICONTROL 条形图]** | **[!UICONTROL *opt+3 *]** | **[!UICONTROL *Alt + 3 *]** | 插入[条形图](/help/analysis-workspace/visualizations/bar.md)可视化内容。 |
| **[!UICONTROL 组合]** | **[!UICONTROL *opt+4 *]** | **[!UICONTROL *Alt + 4 *]** | 插入[组合](/help/analysis-workspace/visualizations/combo-charts.md)可视化内容。 |


| **[!UICONTROL 组件]** | 快捷方式 Mac | Windows 快捷方式 | 描述 |
|---|---|---|---|
| **[!UICONTROL 创建区段……]** | **[!UICONTROL *shift+cmd+e *]** | **[!UICONTROL *shift+ctrl+e *]** | 创建新的[区段](/help/components/segments/seg-create.md)。 |
| **[!UICONTROL 创建量度……]** | **[!UICONTROL *shift+cmd+c *]** | **[!UICONTROL *shift+ctrl+c *]** | 创建新的[计算量度](/help/components/calc-metrics/calc-metr-overview.md)。 |
| **[!UICONTROL 创建日期范围……]** | **[!UICONTROL *shift+cmd+d *]** | **[!UICONTROL *shift+ctrl+d *]** | 创建新的[日期范围](/help/components/date-ranges/overview.md)。 |
| **[!UICONTROL 创建注释……]** | **[!UICONTROL *shift+cmd+o *]** | **[!UICONTROL *shift+ctrl+o *]** | 创建新的[注释](/help/components/annotations/overview.md)。 |
| **[!UICONTROL 创建受众……]** | **[!UICONTROL *shift+cmd+u *]** | **[!UICONTROL *shift+ctrl+u *]** | 创建新的[受众](/help/components/audiences/audiences-overview.md)。 |
| **[!UICONTROL 刷新组件]** | **[!UICONTROL *opt+shift+r *]** | **[!UICONTROL *alt+shift+r *]** | 刷新项目中的组件。 |

| **[!UICONTROL 共享]** | Mac 快捷方式 | Windows 快捷方式 | 描述 |
|---|---|---|---|
| **[!UICONTROL 与 Workspace 用户共享]** | **[!UICONTROL *cmd+h *]** | **[!UICONTROL *ctrl+h *]** | [与其他 Workspace 用户共享项目](/help/analysis-workspace/curate-share/share-projects.md#share-with-customer-journey-analytics-users-and-groups-in-your-organization)。 |
| **[!UICONTROL 与任何人共享]** | **[!UICONTROL *opt+l *]** | **[!UICONTROL *alt+l *]** | [与任何人共享项目的只读版本](/help/analysis-workspace/curate-share/share-projects.md#share-a-link-to-a-project)。 |
| **[!UICONTROL 发送文件]** | **[!UICONTROL opt+s]** | **[!UICONTROL *alt+s *]** | [将项目作为 CSV 或 PDF 文件发送给其他收件人](/help/analysis-workspace/curate-share/send-schedule-files.md)。 |
| **[!UICONTROL 安排文件导出]** | **[!UICONTROL *shift+opt+s *]** | **[!UICONTROL *shift+alt+s *]** | [按计划将项目作为 CSV 或 PDF 文件发送给其他收件人](/help/analysis-workspace/curate-share/send-schedule-files.md)。 |
| **[!UICONTROL 策划项目数据]** | **[!UICONTROL *shift+cmd+g *]** | **[!UICONTROL *shift+ctrl+g *]** | [策划项目数据](/help/analysis-workspace/curate-share/curate.md)。 |

| 帮助 | 描述 |
|---|---|
| **[!UICONTROL 视频]** | 在新浏览器选项卡中打开 Customer Journey Analytics YouTube 频道。 |
| **[!UICONTROL 帮助文档]** | 在新浏览器选项卡中打开（您刚才实际上正在阅读的…）文档。 |
| **[!UICONTROL 帮助论坛]** | 在新浏览器选项卡中打开 Adobe Analytics Experience League 社区论坛。 |
| **[!UICONTROL 热键]** | 显示您可以在 Workspace 中使用的热键（快捷方式）的概述。 |
| **[!UICONTROL 启用调试器]** | 启用调试器。您的项目将重新加载。 |
| **[!UICONTROL 禁用调试器]** | 禁用调试器。您的项目将重新加载。 |
| **[!UICONTROL 绩效]** | 显示一个对话框，其中显示有关 **[!UICONTROL Analysis Workspace 绩效]**&#x200B;的量度。使用&#x200B;**[!UICONTROL 下载为 CSV]**&#x200B;以下载绩效量度的 CSV 文件。 |
| **[!UICONTROL 关于 Workspace]** | 显示 **[!UICONTROL 关于 Analysis Workspace]** 对话框，其中包含版本信息、功能访问级别和活动功能标志。 |

## 数据源

您可以同步可视化内容，以控制哪个数据表或数据源对应于某项可视化内容。请参阅[管理数据源](/help/analysis-workspace/visualizations/t-sync-visualization.md)，以了解详细信息。

## 使用 Analysis Workspace 


要开始使用 Analysis Workspace：

1. 登录到 [Adobe Experience Cloud](https://experience.adobe.com)。
1. 从界面右上角的应用切换器&#x200B;**[!UICONTROL 应用程序]**&#x200B;中选择 ![Customer Journey Analytics](/help/assets/icons/Apps.svg)。
1. 默认情况下将显示 Analysis Workspace 的&#x200B;**[!UICONTROL 项目]**&#x200B;页面。如果已为您选择了特定项目，或者您最近一直在处理该项目，则默认情况下会显示该项目。

### 创建项目

Analysis Workspace 中的分析被称作[项目](/help/analysis-workspace/build-workspace-project/freeform-overview.md)。

您可以在 Analysis Workspace 中创建项目，如[创建项目](/help/analysis-workspace/build-workspace-project/create-projects.md)中所述。

可以将项目组织到文件夹和子文件夹中，如 [Analysis Workspace 中的文件夹](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)中所述。

### 保存和共享项目

在 Analysis Workspace 中创建分析时，您的工作将[自动保存](/help/analysis-workspace/build-workspace-project/save-projects.md)。

当您完成项目的构建并收集到可操作洞察时，其他人可能会想要使用这个项目。您可以与组织内的用户和组甚至组织外的人员共享项目。有关共享项目的信息，请参阅[共享项目](/help/analysis-workspace/curate-share/share-projects.md)。

## 其他资源 {#resources}

- Customer Journey Analytics 中的[“学习”登录](/help/getting-started/landing.md#learning)页面。该页面是熟悉 Analysis Workspace 的好方法。特别是对于学习 Workspace 的基础内容。此模板将可指导您逐步了解在 Workspace 中构建第一个分析时通常会用到的术语和步骤
- Adobe 提供大量的 [Analytics 视频培训教程](https://experienceleague.adobe.com/zh-hans/docs/analytics-learn/tutorials/overview)。
- 有关新功能的更新，请参阅 [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/zh-hans/docs/release-notes/experience-cloud/current)。

