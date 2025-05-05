---
description: 轻松地在 Analysis Workspace 中进行数据的可视化比较，例如构建与上个月、去年等的比较。
title: 组合图表可视化
feature: Visualizations
exl-id: 06faa997-3a4e-4c41-b64e-64a15ada6552
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 97%

---

# 组合 {#combo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_combo_button"
>title="组合"
>abstract="快速创建组合图可视化图表，无需先创建自由格式表。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文记录了_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** 中的组合可视化图表。_

_请参阅本文中_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** 版本的[组合](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/visualizations/combo-charts)。_

>[!ENDSHADEBOX]


通过![组合图表](/help/assets/icons/ComboChart.svg)**[!UICONTROL 组合]**&#x200B;可视化，可轻松快速地构建比较可视化图表，而无需先构建表格。您可以通过线条/条形组合轻松查看数据趋势。

使用[!UICONTROL 组合]：

* 将本周的订单与上个月（和去年）同一时间的订单进行比较。
* 在同一张图表上快速分析和比较多个量度（例如[!UICONTROL 人数]和[!UICONTROL 收入]）。
* 在一段时间内针对某个函数（例如[!UICONTROL 累积平均数]）分析量度。

请记住以下事项：

* 您可以在单个[!UICONTROL 组合图表]中添加多个比较。
* 如果添加一个或多个比较，则它们必须是同一类型，例如[!UICONTROL 时间比较]。
* 最多可添加 5 个比较。
* 您最多可以为一个量度应用 3 个区段。
* 组合图表中不支持计算量度。

## 使用

1. 添加![注释](/help/assets/icons/ComboChart.svg) [!UICONTROL 组合]可视化。请参阅[将可视化添加到面板](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)

1. 从下拉菜单中，选择X轴的维和Y轴的量度。

1. 选择您要使用的[!UICONTROL 线形比较]的类型。

   | 线形比较类型 | 定义 |
   | --- | --- |
   | **[!UICONTROL 时间比较]** | 最常见的比较类型 – 例如，将此时间段与 4 周前进行比较。如果您选择了[!UICONTROL 时间比较]，则对要比较的时间段进行二次选择。<p>![与所选时段以及时段的二次选择字段进行线形比较。](assets/combo-time-period.png) |
   | **[!UICONTROL 函数]** | 您可以在比较中引入函数（例如[!UICONTROL 平均值]）。请参阅[受支持的函数](#supported-functions)列表。<p>![线形比较下拉菜单显示所选功能以及可用的支持功能列表。](assets/combo-functions.png) |
   | **[!UICONTROL 辅助量度]** | 例如，您可以将[!UICONTROL 收入]与另一个量度进行比较。<p>![比较两个量度的组合图表。](assets/combo-2metrics-settings.png) |

   {style="table-layout:auto"}

1. 选择&#x200B;**[!UICONTROL 生成]**。

   输出类似于：

   ![组合图表以条形图显示当前时段，以线形图显示比较时段](assets/combo-output.png)

   当前时段显示在条形图中。线形图表示比较时段。线形图上的点被称为&#x200B;*条形铃*。

## 支持的函数

如果您选择&#x200B;**[!UICONTROL 函数]**&#x200B;作为[!UICONTROL 线形比较类型]，则会返回已选择量度的函数。

| 函数 | 定义 |
| --- | --- |
| **[!UICONTROL 列总和]** | 添加列中某量度的所有数值（某一维度的各个元素） |
| **[!UICONTROL 累积平均数]** | 返回最后 N 行的平均数。 |
| **[!UICONTROL 中间值]** | 返回列中某量度的中间值。中间值是位于一组数字中间的数字。一半的数字大于或等于中间值，一半的数字小于或等于中间值。 |
| **[!UICONTROL 累积数]** | N 行的累积总和。 |
| **[!UICONTROL 列最大值]** | 返回某量度列的一组维度元素中的最大值。 |
| **[!UICONTROL 平均值]** | 返回某度量的算术平均值或平均值。 |
| **[!UICONTROL 列最小值]** | 返回某量度列的一组维度元素中的最小值。 |

{style="table-layout:auto"}

以下是“收入”量度的累积平均值的示例：

![显示累计平均值的组合图表](assets/combo-cumul-avg.png)

以下是使用了累积平均值和均值函数的组合图表的示例：

![显示累积平均值和均值函数的组合图表。](assets/combo-three-functions.png)

>[!MORELIKETHIS]
>
>[在面板中添加可视化效果](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[可视化图表设置](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[可视化图表上下文菜单](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
