---
title: 净增长分析
description: 您是在获得用户还是在失去用户？
feature: Adobe Product Analytics, Guided Analysis
keywords: 产品分析
exl-id: a4f97458-9934-4a98-8005-fa1ba7831101
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 6%

---

# [!UICONTROL 净增长]分析 {#net-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_netgrowth_button"
>title="净增长"
>abstract="您是在获得用户还是在失去用户？"

<!-- markdownlint-enable MD034 -->

![NetGrowth](/help/assets/icons/NetGrowth.svg) **[!UICONTROL Net Growth]**&#x200B;分析提供有关特定时间段内用户增减速率的见解。 水平轴是时间间隔，垂直轴是生长测量值。

每个数据点表示净增长，使用下列公式计算净增长：

`([New users] + [Return users]) / [Dormant users]`

此公式的结果是比率。 `1`的净增长代表均衡；该产品获得的用户数与其失去的用户数相同。 大于`1`的净增长表示正增长；新+回访用户多于休眠用户。 同样，净增长低于`1`意味着损失；休眠用户多于新回访用户。

与[活动](active-growth.md)分析类似，用户定义如下：

* **[!UICONTROL 新]**：用户在当前时段处于活动状态，但之前未处于活动状态。 将鼠标悬停在图表图例中的“[!UICONTROL 新用户]”上，查看分析回顾到多远以确定新用户。 回看范围基于所选日期范围和间隔动态确定。
* **[!UICONTROL 返回]**：用户在当前时段处于活动状态，在刚刚的上一个时段处于非活动状态，但在某个时间点以前处于活动状态。 查看分析在图表图例中通过将鼠标悬停在“[!UICONTROL 回访用户]”上来确定回访用户的回顾范围。 回看范围基于所选日期范围和间隔动态确定。
* **[!UICONTROL 休眠]**：用户在上一时段处于活动状态，但在当前时段未处于活动状态。 休眠用户不计入活动用户总数。

>[!NOTE]
>
>重复用户不计入此计算，因为它们不表示用户的任何收益或损失。

>[!VIDEO](https://video.tv.adobe.com/v/3421664/?quality=12&learn=on)


## 用例

此分析的用例包括：

* **性能评估**：允许您评估产品在获取新用户方面的整体性能。 通过跟踪增长趋势，您可以更好地了解您的产品是否以所需的速度吸引和留住用户。
* **用户获取分析**：允许您评估用户获取策略的有效性。 通过分析用户增长的来源（如搜索引擎、促销活动或其他营销渠道），您可以确定最重要的增长来源，以便相应地分配资源。
* **流失分析**：净增长在其公式中包含减少（休眠用户）。 您可以随着时间的推移评估用户群的整体运行状况。 如果净增长始终低于`1`，则表示存在大量流失现象，这可能会促使实施保留策略。

## 界面

有关引导式分析界面的概述，请参阅[界面](../overview.md#interface)。 以下设置特定于此分析：

### 查询边栏

利用查询边栏，可配置以下组件：

* **[!UICONTROL 视图]**：在此分析和[活动增长](active-growth.md)之间切换。
* **[!UICONTROL 事件]**：要测量的事件。 由于此分析基于用户，因此在该时段内与事件交互一次的用户将被计为活动用户。 您可以在查询中包含一个事件。
* **[!UICONTROL 计为]**：要应用于所选事件的计数方法。选项包括[!UICONTROL 用户数]和[!UICONTROL 用户百分比]。
* **[!UICONTROL 区段]**：要测量的区段。 您可以在查询中包含一个区段。

### 时间比较

{{apply-time-comparison}}

### 日期范围

分析所需的日期范围。 此设置包含两个组件：

* **[!UICONTROL 时间间隔]**：要查看趋势数据的日期粒度。 有效选项包括每小时、每天、每周、每月和每季度。 相同日期范围可以有不同的时间间隔，这会影响图表中的数据点数和表中的列数。 例如，查看具有每日粒度的跨三天的分析将只显示三个数据点，而具有每小时粒度的跨三天的分析将显示72个数据点。
* **[!UICONTROL 日期]**：开始和结束日期。 您可以为方便起见，使用滚动日期范围预设和以前保存的自定义范围，也可以使用日历选择器来选择固定日期范围。

<!-- 
## Example

See below for an example of the analysis.

![Net growth compare](../assets/net-growth-compare.png)

-->
