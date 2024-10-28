---
title: 主动式成长分析
description: 确定新的、保留的、返回的或非活跃的用户。
exl-id: 53ef7485-9cae-4663-bf61-4eb77c126830
feature: Adobe Product Analytics, Guided Analysis
keywords: 产品分析
role: User
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 4%

---

# [!UICONTROL 活动增长]分析 {#active-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_activegrowth_button"
>title="积极增长"
>abstract="确定新的、保留的、返回的或非活跃的用户。"

<!-- markdownlint-enable MD034 -->


![PeopleGroup](/help/assets/icons/PeopleGroup.svg) **[!UICONTROL 主动增长]**&#x200B;分析提供了有关特定时间段内用户增长和获取情况的见解。 水平轴是时间间隔，而垂直轴是用户的测量值。 用户分为四个类别：

* **[!UICONTROL 新]**：用户在当前时段处于活动状态，但之前未处于活动状态。 将鼠标悬停在图表图例中的&#x200B;_[!UICONTROL 新用户]_&#x200B;上，查看分析回顾的距离。 回看范围基于所选日期范围和间隔动态确定。
* **[!UICONTROL 重复]**：用户在当前时段和上一时段处于活动状态。
* **[!UICONTROL 返回]**：用户在当前时段处于活动状态，在刚刚的上一个时段处于非活动状态，但在某个时间点以前处于活动状态。 将鼠标悬停在图表图例中的&#x200B;_[!UICONTROL 回访用户]_&#x200B;上，查看分析回顾的距离。 回看范围基于所选日期范围和间隔动态确定。
* **[!UICONTROL 休眠]**：用户在上一时段处于活动状态，但在当前时段未处于活动状态。 休眠用户不计入活动用户总数。

所有活动用户（新+重复+返回）在水平轴上方显示为蓝绿色，而所有休眠用户在水平轴下方显示为橙色。


>[!VIDEO](https://video.tv.adobe.com/v/3421667/?learn=on)

## 用例

此分析的用例包括：

* **用户保留率和流失率：**&#x200B;提供高或低用户保留率期间的清晰可视化图表。 认识到保留率高或低的时段有助于您做出产品决策，以鼓励高保留率或帮助将流失降至最低。
* **营销活动评估**：查看特定营销活动可以帮助您了解它产生了多少流量，以及它在多大程度上帮助用户保持参与。
* **用户生命周期分析**：分析用户在整个用户生命周期中的活跃用户增长可帮助确定用户参与度下降的特定阶段。 例如，如果处于入门阶段的个人的休眠用户比例很高，它可能会指示可用性问题或需要更好的产品内指导。

## 界面

有关引导式分析界面的概述，请参阅[界面](../overview.md#interface)。 以下设置特定于此分析：

### 查询边栏

利用查询边栏，可配置以下组件：

* **[!UICONTROL 视图]**：在此分析和[净增长](net-growth.md)之间切换。
* **[!UICONTROL 事件]**：要测量的事件。 由于此分析基于用户，因此在该时段内与事件交互一次的用户将被计为活动用户。 您可以在查询中包含一个事件。
* **[!UICONTROL 计为]**：要应用于选定事件的计数方法。 选项包括[!UICONTROL 用户数]和[!UICONTROL 用户百分比]。
* **[!UICONTROL 区段]**：要用作筛选数据依据的区段。 您可以在查询中包含一个区段。

### 图表设置

[!UICONTROL 活动增长]分析提供了以下图表设置，可在图表上方的菜单中调整这些设置：

* **[!UICONTROL 图表类型]**：要使用的可视化图表类型。 选项包括[!UICONTROL 栈叠条形图]和[!UICONTROL 栈叠面积图]。

### 时间比较

{{apply-time-comparison}}

### 日期范围

分析所需的日期范围。 此设置包含两个组件：

* **[!UICONTROL 时间间隔]**：要查看趋势数据的日期粒度。 有效选项包括每小时、每天、每周、每月和每季度。 同一日期范围可以有不同的时间间隔，这会影响图表中的数据点数和表中的列数。 例如，查看具有每日粒度的跨三天的分析将只显示三个数据点，而具有每小时粒度的跨三天的分析将显示72个数据点。
* **[!UICONTROL 日期]**：开始和结束日期。 您可以为方便起见，使用滚动日期范围预设和以前保存的自定义范围，也可以使用日历选择器来选择固定日期范围。

<!--
## Example

See below for an example of the analysis.

![Active time compare](../assets/active-growth-compare.png)

-->
