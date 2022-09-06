---
description: 让您能够轻松地在Analysis Workspace中显示比较数据，例如与上个月、去年等进行构建比较。
title: 组合图可视化图表
feature: Visualizations
role: User, Admin
exl-id: 08e49857-aa58-4527-bdfd-b1663a75a02b
source-git-commit: 5eebcccc45b9760ecc18ec94ca526f2082d089bc
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 32%

---

# 组合图表

>[!NOTE]
>
>此功能当前正在进行[小范围测试](/help/release-notes/releases.md)。

的 [!UICONTROL 组合图] 通过可视化，无需先构建表即可快速构建比较可视化。您可以通过折线图/条形图组合轻松查看数据的趋势。

使用 [!UICONTROL 组合图] to

* 将本周的订单与上个月（和去年）的同一时间的订单进行比较 — 只需点击几下即可。

* 快速分析和比较多个量度(例如 [!UICONTROL 独特访客] 和 [!UICONTROL 收入])来对齐。

* 根据函数分析量度(例如 [!UICONTROL 累积平均数])。

请记住，您可以

* 在单个中添加多个比较 [!UICONTROL 组合图].
* 如果添加一个或多个比较，则它们必须是相同类型的比较，例如 [!UICONTROL 时间比较].
* 最多可添加5个比较。
* 您最多可以对一个量度应用3个过滤器（区段）。

## 构建组合图

1. 从左边栏的“可视化”下拉列表中，将 [!UICONTROL 组合图] 可视化图表显示为空白面板。

   ![](assets/combo-chart-build.png)

1. 从下拉列表中，选择X轴的维度和Y轴的量度。

1. 选择 [!UICONTROL 折线比较] 你想用。

   | 折线比较类型 | 定义 |
   | --- | --- |
   | **[!UICONTROL 时间比较]** | 最常见的比较类型 — 例如，将此时间段与4周前进行比较。 如果已选择 [!UICONTROL 时间比较]，则对要比较的时间段进行次要选择。<p>![](assets/combo-time-period.png) |
   | **[!UICONTROL 函数]** | 你可以引入一个 [!UICONTROL 平均] 比较。 请参阅下面的支持函数列表。<p>![](assets/combo-functions.png) |
   | **[!UICONTROL 辅助指标]** | 例如，您可以比较 [!UICONTROL 收入] 到其他量度。<p>![](assets/combo-2metrics.png) |

   {style=&quot;table-layout:auto&quot;}

1. 单击&#x200B;**[!UICONTROL 生成]**。

   输出将类似于以下内容：

   ![](assets/combo-output.png)

   当前时段显示在条形图中，比较时段由折线图表示。 折线图上的圆点被称为“条形钟”。

## 支持的函数

如果您选择 **[!UICONTROL 函数]** 作为 [!UICONTROL 折线比较类型]，则将返回您选择的量度的函数。

| 函数 | 定义 |
| --- | --- |
| **[!UICONTROL 列总和]** | 添加列中某个量度的所有数值（跨维度的元素） |
| **[!UICONTROL 累积平均数]** | 返回最后 N 行的平均数。 |
| **[!UICONTROL 中间值]** | 返回列中某指标的中间值。中间值是指位于一组数字正中间的那个数字，也就是说有一半数字的值大于或等于该中间值，还有一半数字的值小于或等于该中间值。 |
| **[!UICONTROL 累积]** | N行的累积总和。 |
| **[!UICONTROL 列最大值]** | 返回某指标列的一组维度元素中的最大值。 |
| **[!UICONTROL 平均值]** | 返回量度的算术平均值或平均值。 |
| **[!UICONTROL 列最小值]** | 返回某指标列的一组维度元素中的最小值。 |

{style=&quot;table-layout:auto&quot;}

以下是收入量度的累积平均值示例：

![](assets/combo-cumul-avg.png)

以下是同时具有累积平均值和平均值函数的组合图示例：

![](assets/combo-two-functions.png)

## 组合图设置

单击组合图右上角的齿轮图标可更改其设置。

![](assets/combo-settings.png)

| 设置 | 定义 |
| --- | --- |
| **[!UICONTROL 可视化图表类型]** | 允许您切换到其他可视化图表类型。 |
| **[!UICONTROL 粒度]** | 对于趋势性的可视化图表，您可从此下拉菜单更改时间粒度（日、周、月等）。 |
| **[!UICONTROL 常规]** |  |
| **[!UICONTROL 百分比]** | 显示百分数值。 |
| **[!UICONTROL 图例可见]** | 用于隐藏组合图可视化图表的详细图例文本。 |
| **[!UICONTROL 限制最大项目数]** | 减少X轴上的项目数。 如果您有大数据集，则只能显示前10个项目（或您选择的任何值）。 |
| **[!UICONTROL 叠加]** | 在线上显示或隐藏铃铛。 |
| **[!UICONTROL 轴]** |  |
| **[!UICONTROL 显示双轴]** | 仅适用于具有两个指标的情况，可以在左（用于一个指标）、右（用于另一个指标）两边各有一个 y 轴。在所绘制指标的数量级差别很大时，此项非常有用。双轴颜色与表的颜色匹配，除非有多个比较。 在这种情况下，所有比较的颜色都是灰色的。 |
| **[!UICONTROL 标准化]** | 要求所有指标按等比例计算。在所绘制指标的数量级差别很大时，此项非常有用。 |
| **[!UICONTROL 显示x轴]** | 显示或隐藏x轴。 |
| **[!UICONTROL 显示y轴]** | 显示或隐藏y轴。 |
| **[!UICONTROL 将y轴定位为0]** | 如果图表上绘制的所有值都远远大于零，则图表默认会将 y 轴底部设置为非零值。如果选中此框，y 轴将被强制设置为零（并将重新绘制图表）。 |

{style=&quot;table-layout:auto&quot;}
