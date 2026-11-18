---
title: Analysis Workspace中的矩阵可视化概述
description: 了解Customer Journey Analytics Analysis Workspace中的矩阵可视化图表，包括它显示的内容、何时使用以及与其他可视化图表进行比较的方式。
feature: Visualizations
role: User
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 3199a70eee577f4e283208e2c5089c05fe20ed0d
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 2%
---

# 矩阵概述 {#matrix-overview}

Analysis Workspace中的矩阵可视化图表允许您查看来自两个维度的维度项目如何重叠或相互关联。

一个维度的Dimension项目显示为行（沿Y轴），而另一个维度的维度项目显示为列（沿X轴）。 每个交叉单元格都会显示重叠或关联数据，这些数据基于您选择的量度。

例如，以下矩阵可视化图表按国家/地区代码显示设备名称的事件重叠计数。

* Dimension 1（行维度）：设备名称

* Dimension 2（列维度）：国家/地区代码

* 量度：事件

![矩阵概述](assets/matrix-overview.png)

## 主要功能

* **比较两个不同的维度**：了解一个维度中的项目如何与另一个维度中的项目相关。

* **将维度与其自身进行比较**：查看同一维度中的项目如何关联。

* **重叠**：查看维度项的重叠。

* **关联**：查看维度项的趋势程度，范围从–1（始终朝着相反方向移动）到+1（始终一起移动）。

* **热图颜色**：单元格颜色显示重叠是高还是低，或者相关是正相关还是负相关以及强相关程度。 重叠和关联具有单独的调色板。

## 潜在洞察

* 跨两个维度查找阵列和间隙。 例如，您可以回答类似下面的问题：

  * 哪些营销活动在某些地区效果不错，但在其他地区则否？

  * 哪些内容类型在每种设备类型上表现最佳？

* 了解维度项彼此之间的关系趋势。 例如，您可以回答类似下面的问题：

  * 哪些营销渠道随时间推移而呈同一趋势，哪些渠道是独立移动的，哪些渠道是朝着相反的方向移动的？

  * 哪些页面的流量会同时上升和下降？

* 比较维与本身。 例如，您可以回答类似下面的问题：

  * 哪些产品通常由同一人购买？

  * 相同的人一起使用哪些设备，例如手机和平板电脑？

## 在矩阵、自由格式表、维恩图或散点图可视化图表之间进行选择

矩阵可视化图表与使用自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md)中的多个维度列的[、[维恩可视化图表](/help/analysis-workspace/visualizations/venn.md)和[散点可视化图表](/help/analysis-workspace/visualizations/scatterplot.md)具有相似之处。 每个可视化图表都会显示组件如何相互关联，但它们使用的组件以及显示结果的方式有所不同。

### 何时使用每个可视化图表

选择最适合您的分析的可视化图表：

* **矩阵：**&#x200B;对于给定的量度，查看一个维度中的每个维度项与另一个维度中的每个维度项的关系，包括差距和一起呈现趋势的维度项。

* **具有多个维度列的自由格式表：**&#x200B;您最多可以将5个维度作为单独的列添加到自由格式表中。 在表的同一行中显示的Dimension项目是连接在一起的。 向表中添加任意数量的量度，以查看每个连接的维度项目的量度数据。 对连接的维度项目进行筛选、排序和添加划分。

* **维恩图：**&#x200B;对于单个量度，查看最多3个区段的重叠。

* **散点图：**&#x200B;比较两个或三个量度中的维度项以查找模式和离群值。

### 了解这些差异

<!-- SME CHECK: Confirm the Matrix cells: segments can't be used as rows or columns. Container row: confirm what each Matrix container means for overlap, and that freeform combinations are based on the dimension items that apply to each event. -->

| 功能 | 矩阵 | 自由格式表中的多个维度列 | 维恩图 | 散点图 |
| --- | --- | --- | --- | --- |
| **组件已使用** | 2个维度；1个量度<p>比较来自2个维度的维度项目，或比较来自1个维度的维度项目。</p> | 最多5个维度；任意数量的量度<p>同一行中显示的Dimension项目是连接在一起的，其行为与单个维度项目类似。 连接的行按其量度值进行比较。</p> | 最多3个区段；1个量度<p>比较区段之间的重叠。</p> | 1个维度；最多3个量度<p>跨量度比较维度项目。</p> |
| **容器** | 在可视化图表中设置：“人员”（默认）、“会话”或“事件”<p>确定重叠是否对同一人员、同一会话或同一事件中发生的维度项目计数。</p> | 无容器设置<p>每一行将组合应用于同一事件的维度项目。 您选择的量度（如人员或会话）决定了计算的具体内容。</p> | 在每个区段中设置<p>每个区段都使用自己的[容器](/help/components/segments/seg-overview.md#containers)（人员、会话或事件）。 该量度可确定每个重叠中计入的内容。</p> | 无容器设置<p>您选择的量度将决定计算哪些内容。</p> |
| **布局** | 网格，类似于透视表<p>一个维度中的Dimension项目是行，而另一个维度中的维度项目是列。</p> | 列表<p>每行合并每个维度列中的一个维度项。</p> | 重叠的圆圈 | X轴和Y轴上的点 |
| **显示重叠** | 是<p>显示行中的每个维度项与列中每个维度项之间的重叠。</p><p>使用&#x200B;**[!UICONTROL 重叠计数]**&#x200B;视图。</p> | 是<p>显示每个维度项目组合（每行一个组合）的量度。</p> | 是<p>显示区段之间的重叠。</p> | 否 |
| **显示关联** | 是，在维度项目之间<p>显示维度项目在一段时间内的趋势程度，范围从–1（相反方向）到+1（总在一起）。</p><p>使用&#x200B;**[!UICONTROL 关联强度]**&#x200B;视图。</p> | 否 | 否 | 是，在量度之间<p>显示量度如何相互关联。 每个点是一个维度项目，由最多3个量度绘制。</p> |

{style="table-layout:auto"}

