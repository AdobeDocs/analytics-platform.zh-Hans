---
description: 了解如何在 Analysis Workspace 中创建项目。
title: 创建项目
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: 518bebc18611136873fce5c23dd7041afafe1220
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 100%

---

# 创建项目 {#create-projects}


使用 Analysis Workspace 中的[项目](/help/analysis-workspace/build-workspace-project/freeform-overview.md)可以创建和查看业务关键分析。这些分析可以与组织内部或外部的利益相关者共享。

1. 在 Customer Journey Analytics 中，选择 **[!UICONTROL Workspace]**。

1. 选择左侧面板中的&#x200B;**[!UICONTROL 项目]**，然后选择&#x200B;**[!UICONTROL 创建项目]**。

1. 选择&#x200B;**空白 Workspace 项目**，以使用浏览器创建您的 Workspace 项目。

   有关如何创建可使用移动应用程序与其他利益相关者共享的移动记分卡项目的更多信息，请参阅[空白移动记分卡](/help/mobile-app/curator.md)。请参阅[引导式分析](/help/guided-analysis/overview.md)，了解有关创建引导式分析项目的各种可用选项的更多信息。

1. 选择&#x200B;[!UICONTROL **创建**]。


现在您已经创建了一个空白 Workspace 项目，请确保您熟悉 [Analysis Workspace](/help/analysis-workspace/home.md) 用户界面。完成后，您就可以构建您的项目了。操作方法：

![Example project](assets/example-project.png)

* 将[面板](/help/analysis-workspace/c-panels/panels.md)添加到您的项目中。例如，**[!DNL Example Panel]** ➊。

* 在您的面板中添加[可视化效果](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)。例如：
   * **[!DNL Line Graph]** [线形图](/help/analysis-workspace/visualizations/line.md)可视化图表➋
   * **[!DNL Countries]** [自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)可视化图表➌
* 在可视化效果中添加[组件](/help/components/overview.md)例如：
   * **[!DNL Store Country]** [维度](/help/components/dimensions/overview.md) ➍
   * **[!DNL People]** [量度](/help/components/apply-create-metrics.md) ➎
   * **[!DNL Avg Order Value]** [计算量度](/help/components/calc-metrics/calc-metr-overview.md) ➏
   * **[!DNL Mobile App Sessions]** [区段](/help/components/segments/seg-overview.md) ➐
   * **[!DNL Last Month]** [日期范围](/help/components/date-ranges/overview.md) ➑
   * **[!DNL Example]** [注释](/help/components/annotations/overview.md) ➒


## 项目信息和设置 {#project-info-settings}

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="计数重复实例"
>abstract="指定是否将重复实例计入报告中。<br/><br/>注意：此设置不适用于“流”或“流失”可视化。"

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="计数重复实例"
>abstract="指定是否将重复实例计入报告中。<br/>注意：此设置不适用于“流”或“流失”可视化。"


>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="允许评论"
>abstract="启用后，Analysis Workspace 中项目的右侧栏中会显示一个评论区域。"


项目设置提供有关当前活动项目的项目级信息。

![The Project Info &amp; Settings window.](./assets/projectinfo.png)

这些设置包括：

| 设置 | 描述 |
|---|---|
| 项目名称 | 给项目起的名称。您可以双击该名称以编辑它。 |
| 所有者 | 项目所有者名称。 |
| 最近修改 | 项目上次修改日期。 |
| 标记 | 列出应用于项目以方便分类的所有标记。 |
| 描述 | 描述有助于明确项目的目的。您可以双击描述以编辑它。 |
| 计数重复实例 | 指定是否将重复实例计入报告中。注意：此设置不适用于“流”或“流失”可视化。 |
| 显示注释 | 指定是否显示该项目的注释。 |
| [项目调色板](/help/analysis-workspace/build-workspace-project/color-palettes.md) | 通过从已为色盲优化过的现成调色板中进行选择或通过指定您的自定义调色板，可更改在 Workspace 中使用的类别调色板。此功能影响 Workspace 中的许多内容，包括大多数可视化。 |
| [视图密度](/help/analysis-workspace/build-workspace-project/view-density.md) | 通过减小左侧面板、自由格式表和同类群组表的垂直边距，让您可在屏幕上看到更多数据。 |
| 允许评论 | 该选项启用后，Analysis Workspace 中项目的右侧栏中会显示一个评论区域。有关详细信息，请参阅[在项目中添加和管理评论](/help/analysis-workspace/build-workspace-project/comment-projects.md)。 |



