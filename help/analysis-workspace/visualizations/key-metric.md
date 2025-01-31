---
description: 使用关键量度摘要可视化图表来比较两条时间线的量度表现。
title: 关键量度摘要
feature: Visualizations
exl-id: ef606c53-b370-419a-904b-573ee6d70a8d
role: User
source-git-commit: 55b312552d32070875714a77e1177bf0da5f9d87
workflow-type: tm+mt
source-wordcount: '959'
ht-degree: 36%

---

# 关键量度摘要 {#key-metric-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="关键量度摘要"
>abstract="创建由线条、概要变化和摘要数字图表组合而成的可视化效果。使用此可视化效果来比较两个时段内重要量度的趋势。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文记录了_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;中的关键指标摘要可视化。_<br/>_查看本文的_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;版本的[关键量度摘要](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/key-metric)。_

>[!ENDSHADEBOX]


![关键量度](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL 关键量度摘要]**&#x200B;可视化让您看到重要量度在单个时间范围内的趋势如何。 它还允许您在两个时间范围内比较量度表现。 它还具备将多个可视化图表组合为一个可视化图表的优点：

* **[!UICONTROL 折线图]**&#x200B;可视化图表显示主要日期范围和比较日期范围的量度趋势

* **[!UICONTROL 摘要百分比变化]**&#x200B;显示主要日期范围和比较日期范围之间的量度增减

* 度量的当前总值（[!UICONTROL **摘要编号**]）

## 用例

此可视化图表处理各种常见用例，包括：

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
   | **[!UICONTROL 主要日期范围]** | 自由表格的当前日期范围。<p>从数据视图中的任何可用日期范围中进行选择。</p> <p>如果要使用在可视化图表所在的面板上使用的相同日期范围，请选择&#x200B;[!UICONTROL **面板日期范围**]。</p> |
   | **[!UICONTROL 比较日期范围。]** | 要与主要日期范围进行比较的日期范围。 |
   | **[!UICONTROL 筛选器（可选）]** | 您对此摘要感兴趣的任何过滤器。 |

   {style="table-layout:auto"}

   >[!NOTE]
   >
   >当&#x200B;[!UICONTROL **主日期范围**]&#x200B;字段设置为&#x200B;[!UICONTROL **面板日期范围**]&#x200B;时，**[!UICONTROL 比较日期范围]**&#x200B;将自动更新，具体取决于您选择的&#x200B;**[!UICONTROL 比较日期范围]**&#x200B;选项是相对于主日期范围还是固定的。
   >
   >* **相对：**&#x200B;如果将&#x200B;**[!UICONTROL 比较日期范围]**&#x200B;字段设置为与主日期范围相关的选项（如&#x200B;[!UICONTROL **前一天**]、[!UICONTROL **上周同日**]、[!UICONTROL **前第4周同日**]&#x200B;等），则对&#x200B;[!UICONTROL **主日期范围**]&#x200B;字段的任何更新都会导致&#x200B;**[!UICONTROL 比较日期范围]**&#x200B;自动更新为紧跟面板日期范围的时段。
   >* **固定：**&#x200B;如果&#x200B;[!UICONTROL **比较日期范围**]&#x200B;字段设置为固定日期范围（如&#x200B;**2023年2月3日**），则对&#x200B;[!UICONTROL **主要日期范围**]&#x200B;字段或面板日期范围所做的更改不会对&#x200B;[!UICONTROL **比较日期范围**]&#x200B;产生影响。 但是，对面板日期范围的任何更新都会导致&#x200B;[!UICONTROL **主日期范围**]&#x200B;自动更新。

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

查看输出时，请考虑以下事项：

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
| --- | --- |
| **[!UICONTROL 强调百分比变化]** | 在可视化图表中心以突出的粗体显示摘要更改 |
| **[!UICONTROL 强调数值]** | 在可视化图表中心以突出的粗体显示摘要编号 |
| **[!UICONTROL 图例可见]** | 显示或隐藏可视化图表底部的图例 |
| **[!UICONTROL 显示注释]** | 显示或隐藏管理员添加的注释 |
| **[!UICONTROL 隐藏标题]** | 隐藏可视化图表的标题。 |
| **[!UICONTROL 百分比]** | 以百分比而非数字显示可视化图表。 |
| **[!UICONTROL 显示趋势线]** | 在可视化图表中显示趋势线。 |
| **[!UICONTROL 在趋势线上显示最大值和最小值]** | 在主线形图和比较线形图上显示或隐藏最小值和最大值 |
| **[!UICONTROL 显示比较百分比和趋势线]** | 显示或隐藏比较数据。 隐藏时，比较线形图和汇总更改对象将从视图中隐藏。 |
| **[!UICONTROL 显示总数]** | 显示或隐藏摘要编号 |
| **[!UICONTROL 显示原始差异]** | 显示或隐藏主要日期范围和次要日期范围中量度的总值之间的原始差异 |
| **[!UICONTROL 缩写值]** | 选择&#x200B;**[!UICONTROL 缩写值]**&#x200B;智能缩写数值。 选中后，输入数字以定义缩写金额。 例如：<br/><table><tr><td>**原始值**</td><td>**缩写**</td><td>**结果**</td></tr><tr><td>12,011,141.25美元</td><td>未选择</td><td align="right">12,011,141.25美元</td></tr><tr><td>12,011,141.25美元</td><td>已选定，设置为1</td><td align="right">1200万美元</td></tr><tr><td>12,011,141.25美元</td><td>已选定，设置为2</td><td align="right">1200万美元</td></tr><tr><td>12,011,141.25美元</td><td>已选定，设置为2</td><td align="right">1201.1万美元</td></tr><tr><td>12,011,141.25美元</td><td>选择，设置为3</td><td align="right">1201.1万美元</td></tr></table> |

## 编辑可视化图表

构建可视化图表后，您仍然可以编辑原始配置。

1. 单击可视化右上角的铅笔图标（设置齿轮图标旁边）。

   ![可视化编辑图标](assets/edit-icon.png)

   现在，您将返回到原始配置视图。

1. 根据需要更改量度、主要日期范围、比较日期范围或过滤器。

>[!MORELIKETHIS]
>
>[将可视化图表添加到面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[可视化设置](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[可视化上下文菜单](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
