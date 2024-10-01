---
description: 了解如何在 Analysis Workspace 中创建项目
title: 创建项目
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: 383fad799944f7405af6de1754aa2e0af83e2cab
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 40%

---

# 创建项目

Analysis Workspace中的[项目](/help/analysis-workspace/build-workspace-project/freeform-overview.md)允许您创建和查看业务关键型分析。  这些分析可与组织内部或外部的利益相关者共享。

1. 在Customer Journey Analytics中，选择&#x200B;**[!UICONTROL Workspace]**。

1. 在左侧面板中选择&#x200B;**[!UICONTROL 项目]**，然后选择&#x200B;**[!UICONTROL 创建项目]**。

1. 选择&#x200B;**空白Workspace项目**&#x200B;以使用浏览器创建您的Workspace项目。

   有关如何创建移动记分卡项目的更多信息，请参阅[空白移动记分卡](/help/mobile-app/curator.md)，您可以使用移动应用程序与其他利益相关者共享该项目。 有关创建引导式分析项目时可用的各种选项的更多信息，请参阅[引导式分析](/help/guided-analysis/overview.md)。

1. 选择&#x200B;[!UICONTROL **创建**]。


现在您已创建一个空白Workspace项目，请确保您熟悉[Analysis Workspace](/help/analysis-workspace/home.md)用户界面。 一旦完成，您就可以构建项目。 为此，请执行以下操作：

![示例项目](assets/example-project.png)

* 将[面板](/help/analysis-workspace/c-panels/panels.md)添加到您的项目中。 例如，**[!DNL Example Panel]**➊。

* 将[可视化图表](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)添加到您的面板。 例如：
   * **[!DNL Line Graph]** [折线图](/help/analysis-workspace/visualizations/line.md)可视化➋
   * **[!DNL Countries]** [自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)可视化➌
* 将[组件](/help/components/overview.md)添加到您的可视化图表中。 例如：
   * **[!DNL Store Country]** [维度](/help/components/dimensions/overview.md)➍
   * **[!DNL People]** [指标](/help/components/apply-create-metrics.md)➎
   * **[!DNL Avg Order Value]** [计算量度](/help/components/calc-metrics/calc-metr-overview.md)➏
   * **[!DNL Mobile App Sessions]** [筛选器](/help/components/filters/filters-overview.md)➐
   * **[!DNL Last Month]** [日期范围](/help/components/date-ranges/overview.md)➑
   * **[!DNL Example]** [批注](/help/components/annotations/overview.md)➒


## 项目信息和设置 {#project-info-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_project_repeatinstances"
>title="计数重复实例"
>abstract="指定是否将重复实例计入报表中。<br/>注意：此设置不适用于“流”或“流失”可视化。"

<!-- markdownlint-enable MD034 -->


项目设置提供有关当前活动项目的项目级信息。

![项目信息和设置窗口。](./assets/projectinfo.png)

这些设置包括：

| 设置 | 描述 |
|---|---|
| 项目名称 | 给项目起的名称。您可以双击该名称以编辑它。 |
| 所有者 | 项目所有者名称。 |
| 最近修改 | 项目上次修改日期。 |
| 标记 | 列出应用于项目以方便分类的所有标记。 |
| 描述 | 描述有助于明确项目的目的。您可以双击描述以编辑它。 |
| 计数重复实例 | 指定是否将重复实例计入报表中。 注意：此设置不适用于“流”或“流失”可视化。 |
| 显示注释 | 指定是否显示此项目的注释。 |
| [项目调色板](/help/analysis-workspace/build-workspace-project/color-palettes.md) | 通过从已为色盲优化过的现成调色板中进行选择或通过指定您的自定义调色板，可更改在 Workspace 中使用的类别调色板。此功能影响 Workspace 中的许多内容，包括大多数可视化。 |
| [视图密度](/help/analysis-workspace/build-workspace-project/view-density.md) | 通过减小左侧面板、自由格式表和同类群组表的垂直边距，让您可在屏幕上查看更多数据。 |



