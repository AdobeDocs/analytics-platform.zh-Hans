---
description: 使用趋势主题可视化图表来探索对话中的趋势主题。
title: 趋势主题
feature: Visualizations
role: User
hide: true
source-git-commit: ccaa957e79fba24292316c7447be786f57f03493
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 14%
---
# 热门话题

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_button"
>title="热门话题"
>abstract="创建一个可视化图表，该可视化图表显示启用层级向下钻取的、包含发生次数和百分比的趋势主题细分，以帮助您识别对话中的重要主题。"

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_panel"
>title="热门话题"
>abstract="根据所选的排名量度分析热门话题。 选择话题进行向下钻取，最多可深入五个层级。 搜索特定话题，并与其他日期范围内的话题进行比较。"

![信息源](/help/assets/icons/Feed.svg) **[!UICONTROL 趋势主题]**&#x200B;可视化图表允许您浏览和分析趋势主题，作为对话见解的一部分。

您可以搜索特定主题，并将每个级别中每个主题的数量和百分比与其他数据范围进行比较。

## 创建和配置

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_attribution"
>title="趋势主题量度归因"
>abstract="为所选量度启用非默认归因模型。"

创建和配置趋势主题可视化图表：

1. 添加![信息源](/help/assets/icons/Feed.svg) **[!UICONTROL 趋势主题]**&#x200B;可视化图表。 请参阅[将可视化图表添加到面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。

1. 在&#x200B;**[!UICONTROL 趋势主题]**&#x200B;可视化图表配置中：

   1. 选择&#x200B;**[!UICONTROL 排名指标]**。 例如： **[!UICONTROL 对话]**。
   1. 如果您要设置量度上的[归因](/help/analysis-workspace/attribution/models.md)，请选择&#x200B;**[!UICONTROL 设置归因]**，然后选择&#x200B;**[!UICONTROL 模型]**、**[!UICONTROL 容器]**&#x200B;和&#x200B;**[!UICONTROL 回顾窗口]**（可选）。
1. 选择&#x200B;**[!UICONTROL 生成]**&#x200B;以生成可视化图表。 选择&#x200B;**[!UICONTROL 重置]**&#x200B;将配置值重置为默认值。

要重新配置趋势主题可视化图表，请选择&#x200B;**排名指标&#x200B;_排名指标_旁边的![编辑](/help/assets/icons/Edit.svg) |子主题级别： _x_**。

## 使用

要使用可视化图表，请执行以下操作：

![使用趋势主题可视化图表](assets/trending-topics.png)

* 将鼠标悬停在主题上可查看包含更多详细信息的弹出窗口。➊

* 要查看较低级别主题的趋势子主题，请选择特定级别的主题。 如果在子级别没有可用的主题，您会看到![DataRemove](/help/assets/icons/DataRemove.svg) **[!UICONTROL 找不到_topic >子主题> ...]**&#x200B;的子主题。

* 使用![搜索](/help/assets/icons/Search.svg) **[!UICONTROL _搜索主题_]**&#x200B;快速搜索主题。➋

* 若要将主题与另一个日期范围进行比较，请选择日期范围，范围是&#x200B;**[!UICONTROL 比较对象]**。➌

  要使用自定义日期范围，请执行以下操作：

  * 从下拉菜单中选择&#x200B;**[!UICONTROL 自定义日期范围]**，并在&#x200B;**[!UICONTROL 新建日期范围]**&#x200B;对话框中定义和保存自定义日期范围。
  * 选择该自定义日期范围。

* 若要显示当前所选主题的线形图，请在&#x200B;**[!UICONTROL 趋势主题]**&#x200B;可视化图表中放置[线](/help/analysis-workspace/visualizations/line.md)可视化图表。 **[!UICONTROL 折线图]**&#x200B;可视化自动链接到&#x200B;**[!UICONTROL 趋势主题]**&#x200B;可视化并显示选定主题的折线图。

  ![趋势主题线可视化](assets/trending-topics-line-viz.png)

## 设置

以下特定的[可视化设置](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)可用。

| 设置 | 描述 |
|---|---|
| **[!UICONTROL 显示实际值]** | 显示主题的实际值。 |
| **[!UICONTROL 显示百分比]** | 显示主题的百分比。 |
