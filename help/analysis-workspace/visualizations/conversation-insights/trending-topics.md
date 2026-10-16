---
description: 使用趋势主题可视化图表来探索对话中的趋势主题。
title: 趋势主题
feature: Visualizations
role: User
hide: true
source-git-commit: 137dba69c8827f3b67d5656760d7715437c58b73
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 5%
---

# 热门话题

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_button"
>title="热门话题"
>abstract="创建一个可视化图表，该可视化图表显示启用层级向下钻取的、包含发生次数和百分比的趋势主题细分，以帮助您识别对话中的重要主题。"

>[!CONTEXTUALHELP]
>id="workspace_trendingtopics_panel"
>title="热门话题"
>abstract="根据所选排名指标分析趋势主题。 选择主题以向下钻取至最深的五个级别。 搜索特定主题并将主题与其他日期范围进行比较。"

![信息源](/help/assets/icons/Feed.svg) **[!UICONTROL 趋势主题]**&#x200B;可视化图表允许您浏览和分析趋势主题，作为对话见解的一部分。

您可以搜索特定主题，并将每个级别中每个主题的数量和百分比与其他数据范围进行比较。

## 创建和配置

创建和配置趋势主题可视化图表：

1. 添加![信息源](/help/assets/icons/Feed.svg) **[!UICONTROL 趋势主题]**&#x200B;可视化图表。 请参阅[将可视化图表添加到面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。

1. 在&#x200B;**[!UICONTROL 趋势主题]**&#x200B;可视化图表配置中：

   1. 选择&#x200B;**[!UICONTROL 排名指标]**。 例如： **[!UICONTROL 对话]**。
   1. 或者，选择&#x200B;**[!UICONTROL 设置归因]**，然后选择&#x200B;**[!UICONTROL 模型]**、**[!UICONTROL 容器]**&#x200B;和&#x200B;**[!UICONTROL 回顾窗口]**。
   1. 为&#x200B;**[!UICONTROL 限制子主题级别]**&#x200B;选择一个级别。 默认值为&#x200B;**[!UICONTROL 级别5]**。

      >[!NOTE]
      >
      >**[!UICONTROL 限制子主题级别]**&#x200B;定义了可视化图表中主题要向下钻取的最大级别数。 如果该定义的最大数量内没有其他可用主题，则![DataUnavailable](/help/assets/icons/DataUnavailable.svg) **[!UICONTROL 未找到主题]**。

1. 选择&#x200B;**[!UICONTROL 生成]**&#x200B;以生成可视化图表。 选择&#x200B;**[!UICONTROL 重置]**&#x200B;将配置值重置为默认值。

要重新配置趋势主题可视化图表，请选择&#x200B;**排名指标&#x200B;_排名指标_旁边的![编辑](/help/assets/icons/Edit.svg) |子主题级别： _x_**。

## 使用

要使用可视化图表，请执行以下操作：

* 要深入查看较低级别主题趋势子主题，请选择特定级别的主题。

* 要根据另一个日期范围比较主题，请从比较对象中选择一个日期范围。 要使用自定义日期范围，请执行以下操作：
  * 从下拉菜单中选择自定义日期范围，并在新建日期范围对话框中定义和保存自定义日期范围。
  * 选择该自定义日期范围。

* 要显示当前所选主题的线形图，请在&#x200B;**[!UICONTROL 趋势主题]**&#x200B;可视化图表中放置[线](/help/analysis-workspace/visualizations/line.md)可视化图表。 **[!UICONTROL 折线图]**&#x200B;可视化图表自动链接到&#x200B;**[!UICONTROL 趋势主题]**&#x200B;可视化图表。

## 设置

以下特定的[可视化设置](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)可用。

| 设置 | 描述 |
|---|---|
| **[!UICONTROL 显示实际值]** | 显示主题的实际值。 |
| **[!UICONTROL 显示百分比]** | 显示主题的百分比。 |



