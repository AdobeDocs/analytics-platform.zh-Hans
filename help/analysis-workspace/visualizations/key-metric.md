---
description: 使用关键量度摘要可视化图表来比较两条时间线的量度表现。
title: 关键量度摘要
feature: Visualizations
exl-id: ef606c53-b370-419a-904b-573ee6d70a8d
role: User
source-git-commit: 1dff53e244e5d231e7075ce087705e33e0978096
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 38%

---

# 关键量度摘要 {#key-metric-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_keymetricsummary_button"
>title="关键量度摘要"
>abstract="创建折线图、汇总变化图和汇总数字图组合的可视化图表。 使用此可视化效果来比较两个时段内重要量度的趋势。"

<!-- markdownlint-enable MD034 -->


![关键量度](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL 关键量度摘要]**&#x200B;可视化让您看到重要量度在单个时间范围内的趋势如何。 它还允许您在两个时间范围内比较量度表现。 它还具备将多个可视化图表组合为一个可视化图表的优点：

* **[!UICONTROL 折线图]**&#x200B;可视化图表显示主要日期范围和比较日期范围的量度趋势

* **[!UICONTROL 摘要百分比变化]**&#x200B;显示主要日期范围和比较日期范围之间的量度增减

* 度量的当前总值（[!UICONTROL **摘要编号**]）

该可视化图表处理各种常见用例，包括：

* 一位分析师试图了解与去年同期相比，本月机会创造情况。

* 一位营销人员正在探索特定商机类型的商机开发从本月到上个月的变化。

* 一位高管想了解新预订从本季度到上季度的变化。

## 使用

1. 添加![关键量度](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL 关键量度摘要]**&#x200B;可视化图表。 请参阅[将可视化图表添加到面板](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。

1. 通过选择&#x200B;**[!UICONTROL 量度]**、**[!UICONTROL 主要日期范围]**、**[!UICONTROL 比较日期范围]**（可选）和&#x200B;**[!UICONTROL 筛选器]**（可选）来配置可视化图表：

   ![显示指标、主要日期范围、比较日期范围和区段选项的关键指标配置。](assets/key-metrics-config.png)

   | 选项 | 描述 |
   | --- | --- |
   | **[!UICONTROL 量度]** | 选择您希望检查的量度。 支持全部量度。 |
   | **[!UICONTROL 主要日期范围]** | 自由表格的当前日期范围。 |
   | **[!UICONTROL 比较日期范围。]** | 要与主日期范围进行比较的日期范围。 |
   | **[!UICONTROL 筛选器（可选）]** | 您对此摘要特别感兴趣的任何过滤器。 |

   {style="table-layout:auto"}

1. 选择&#x200B;**[!UICONTROL 生成]**。

<!--## How the Key Metric Summary visualization handles the comparison date range

(This will probably release in January. Per Jaden Howell)

* If the primary date range is set to the panel date range, there are 2-6 options that are considered 'relative' to the primary date range. These usually include the previous period (same amount of time immediately proceeding the primary date range), and 52 weeks prior to that date range.

* If the comparison date range is set to one of the 'relative' options, upon updating the primary date range, the comparison date range updates to the period immediate preceding the panel date range.

* If your comparison date range is *not* set to a 'relative' option, then updating the panel date range changes your primary date range, but has no effect on the comparison date range.

**Example 1**

Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a relative date range, one of: 'Previous day', 'Same day last week', 'Same day 4 weeks prior', 'Same day last month', 'Same day last year', or 'Same day 52 weeks prior'.
When I change the panel's date range to 'This month', the comparison date range will update to 'Previous month'.

**Example 2**
 
Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a non-relative date range, such as 'Feb 2nd, 2022', 'Highest sales day', 'Last week', etc. 

>[!NOTE]
>
>Last week is relative to the day the project is opened on, but it is not based on the panel's date range of 'Yesterday'. In other cases, such as if the panel's date range was 'This week', it may be relative.

When you change the panel's date range to '4 days ago', the comparison date range remains at the previous selection. -->

关键量度摘要的输出如下所示：

![显示量度、摘要变化、摘要数字和折线图的关键量度输出。](assets/key-metrics.png)

* **[!UICONTROL 上一时段]**&#x200B;折线图（始终以灰色显示）对应于配置步骤中的&#x200B;**[!UICONTROL 比较日期范围]**。

* 如果在配置期间未指定比较日期范围，或在可视化图表设置中隐藏比较日期范围时，则仅显示主日期范围的线形图。摘要更改已隐藏。

* 从此处，您可以将鼠标悬停在线形图上，查看各个日期的统计数据：


## 配置

构建可视化图表后，您可以编辑原始配置。

1. 在可视化图表顶部选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 配置可视化图表]**。

   您将返回到原始配置对话框。

1. 根据需要更改设置。 选择&#x200B;**[!UICONTROL 重置]**&#x200B;以重置当前设置。 选择&#x200B;**[!UICONTROL 生成]**&#x200B;以重新生成可视化图表。

## 设置

作为可视化设置的一部分，可以使用特定的关键指标摘要设置。

| 设置 | 描述 |
|---|---|
| **[!UICONTROL 摘要显示类型]** | 在&#x200B;**[!UICONTROL 强调百分比变化]**&#x200B;或&#x200B;**[!UICONTROL 强调数值]**&#x200B;之间选择。 |
| **[!UICONTROL 显示趋势线]** | 在可视化图表中显示趋势线。 |
| **[!UICONTROL 在趋势线上显示最大值和最小值]** | 在趋势线上显示最大值和最小值。 |
| **[!UICONTROL 显示比较百分比和趋势线]** | 显示与趋势线的比较百分比。 如果未选中，则两者都会隐藏。 |
| **[!UICONTROL 数值选项]** | **[!UICONTROL 显示总数]**&#x200B;或&#x200B;**[!UICONTROL 显示数字值的原始差异]**。 |
| **[!UICONTROL 缩写值]** | 选择&#x200B;**[!UICONTROL 缩写值]**&#x200B;智能缩写数值。 选中后，输入数字以定义缩写金额。 例如：<br/><table><tr><td>**原始值**</td><td>**缩写**</td><td>**结果**</td></tr><tr><td>12,011,141.25美元</td><td>未选择</td><td  align="right">12,011,141.25美元</td></tr><tr><td>12,011,141.25美元</td><td>已选定，设置为1</td><td align="right">1200万美元</td></tr><tr><td>12,011,141.25美元</td><td>已选定，设置为2</td><td  align="right">1200万美元</td></tr><tr><td>12,011,141.25美元</td><td>已选定，设置为2</td><td align="right">1201.1万美元</td></tr><tr><td>12,011,141.25美元</td><td>选择，设置为3</td><td align="right">1201.1万美元</td></tr></table> |

>[!MORELIKETHIS]
>
>[将可视化图表添加到面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[可视化设置](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[可视化上下文菜单](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
