---
title: 计算量度概述
description: '了解 '
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 100%

---


# 计算量度概述

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html) 略有不同。[了解更多...](/help/getting-started/cja-aa.md)

计算量度和高级计算（或派生）量度是指您可以从现有量度创建的自定义量度。我们的计算量度工具提供了一种高度灵活的方式，可用于生成、管理和组织量度。通过使用这些工具，营销人员、产品经理和分析人员不必更改 [!DNL Analytics] 实施，即可提出有关数据的问题。

您可以

* 创建在报表运行时过滤的量度，而[不必更改实施](https://youtu.be/CuQTm9RaUpY)。这些量度可以在历史记录中查看，因为它们是基于过滤器的。
* 在报表包之间共享量度。这表示所有新创建的量度都适用于同一登录公司中的所有报表包。
* （仅限高级计算量度）根据量度进行过滤。例如，您可以为“新访客”创建一个量度，其中包含首次进行会话的人员计数。
* （仅限高级计算量度）包含统计函数，以帮助您更好地描述数据。例如，您可以对报表中的项目数量进行计数，或为每个项目加入标准偏差数。

## 计算量度与高级计算量度

以下是计算量度和高级计算量度功能的比较：

| Builder 选项 | 计算量度 | 高级计算（派生）量度 |
|---|---|---|
| 格式类型（小数、时间、百分比、货币） | 是 | 是 |
| 归因更改（默认、线性、参与率等） | 是 | 是 |
| 量度类型（标准、总数） | 是 | 是 |
| 基本运算符（加、减、乘、除） | 是 | 是 |
| 应用过滤器 | 否 | 是 |
| [基本函数（计数、绝对值、平均值等）](/help/components/calc-metrics/cm-functions.md) | 否 | 是 |
| [高级函数（回归、if/then、t 分数等）](/help/components/calc-metrics/cm-adv-functions.md) | 否 | 是 |

## 工具

| 工具 | 功能 |
|--- |--- |
| 计算量度生成器 | <ul><li>使用高级分配模型创建计算量度和高级计算量度。</li><li>将内联过滤器添加到量度公式中。</li><li>比较同一报表中的过滤器。例如，比较本地访客与国际访客。</li><li>使用统计函数。</li><li> 提供详细的量度描述（显示其用途，以及何处可以使用，何处不可以使用）。</li><li>将定义复制到新量度中。</li><li>提供内联量度预览。</li><li>设置量度极性，以指示当给定的自定义事件（量度）上升时是有利还是不利。</li><li>标记量度。</li></ul> |
| 计算量度管理器 | <ul><li>与他人共享量度。</li><li>批准和管理量度。</li><li>组织（标记）量度，以方便用户查找。</li><li>删除量度。</li><li>重命名量度。</li></ul> |
| 适用于计算量度的 API | Adobe Analytics 2.0 API 集的组成部分。 |

