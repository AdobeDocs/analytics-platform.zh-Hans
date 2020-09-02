---
description: 使用线条可视化描述趋势（基于时间）数据集
title: 折线图
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: 4f163e32787a732526511aeda5f6c1e32becb490
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 20%

---


# 折线图

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html) 略有不同。[了解更多...](/help/getting-started/cja-aa.md)

“行”可视化使用行表示度量，以显示值在一段时间内的变化情况。 仅当使用时间作为维度时，才可以使用折线图。

![线条可视化](assets/line-viz.png)

>[!IMPORTANT]
>
>某些线条可视化设置，如 [!UICONTROL 显示趋势线]，当前处于有限测试中。 [了解更多](https://docs.adobe.com/content/help/zh-Hans/analytics/landing/an-releases.html)

单击“线条”可视化右上角的齿轮图标可访问 [**可视化设置**](freeform-analysis-visualizations.md) 。 设置分为：

* **常规**:在各种可视化类型中通用的设置
* **轴**:影响线可视化的x或y轴的设置
* **叠加**:用于向显示在线条可视化中的系列添加其他上下文的选项。

![“可视化图表”设置 ](assets/viz-settings-modal.png)

## 更改粒度

通过[可视化设置](freeform-analysis-visualizations.md)中的粒度下拉列表，可以将趋势可视化（例如折线图、条形图）从每日更改为每周、每月等。此粒度也会在数据源表中更新。

## 显示最小或最大

下 **[!UICONTROL 可视化设置]** > **[!UICONTROL 叠加]** > **[!UICONTROL 显示最小／最大]**，您可以叠加最小值和最大值标签以快速突出显示度量中的峰值和谷值。 注意：最小值／最大值是从可视化中的可见数据点派生的，而不是从维中的完整值集。

![显示最小／最大](assets/min-max-labels.png)

## 显示趋势线叠加

下 **[!UICONTROL 可视化设置]** > **[!UICONTROL 叠加]** > **[!UICONTROL 显示趋势线]**，您可以选择向行系列添加回归趋势线。 趋势线有助于在数据中描绘更清晰的图案。

![线性趋势线](assets/show-linear-trendline.png)

所有模型都采用普通最小二乘拟合：

| 模型 | 描述 |
| --- | --- |
| 线性 | 为简单的线性数据集创建最适合的直线，当数据以稳定速率增加或减少时，该直线很有用。 等式： `y = a + b * x` |
| 对数 | 创建最适合的曲线，当数据更改率快速增加或减少，然后平铺时，该曲线很有用。 对数趋势线可使用负值和正值。 等式： `y = a + b * log(x)` |
| 指数 | 创建一条曲线，当数据以不断增加的速度上升或下降时，它非常有用。 如果数据包含零值或负值，则不应使用此选项。 等式： `y = a + e^(b * x)` |
| 幂 | 创建一条曲线，对于比较以特定速率增加的测量值的数据集非常有用。 如果数据包含零值或负值，则不应使用此选项。 等式： `y = a * x^b` |
| 二次方程式 | 找到最适合抛物线（上下凹）形状的数据集。 等式： `y = a + b * x + c * x^2` |
