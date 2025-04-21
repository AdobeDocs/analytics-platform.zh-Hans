---
title: 积极增长分析
description: 确定新的、保留的、返回的或非活跃的用户。
exl-id: 53ef7485-9cae-4663-bf61-4eb77c126830
feature: Adobe Product Analytics, Guided Analysis
keywords: 产品分析
role: User
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 98%

---

# [!UICONTROL 积极增长]分析 {#active-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_activegrowth_button"
>title="积极增长"
>abstract="确定新的、保留的、返回的或非活跃的用户。"

<!-- markdownlint-enable MD034 -->


通过 ![PeopleGroup](/help/assets/icons/PeopleGroup.svg) **[!UICONTROL 积极增长]**&#x200B;分析可深入了解特定时段内用户的增长和获取情况。横轴是时间间隔，纵轴则是用户测量值。用户分为四类：

* **[!UICONTROL 新用户]**：用户在当前时段处于活跃状态，但是之前不活跃。将鼠标悬停在图表图例中的&#x200B;_[!UICONTROL 新用户]_&#x200B;上，即可查看分析所回顾的时间范围。回顾范围是根据所选的日期范围和间隔动态确定的。
* **[!UICONTROL 重复]**：该用户在当前时段和上一时段均处于活跃状态。
* **[!UICONTROL 返回用户]**：用户在当前时段处于活跃状态，在上一时段不活跃，但之前曾在某个时间点活跃过。将鼠标悬停在图表图例中的&#x200B;_[!UICONTROL 返回的用户]_&#x200B;上，即可查看分析所回顾的时间范围。回顾范围是根据所选的日期范围和间隔动态确定的。
* **[!UICONTROL 休眠用户]**：用户在上一时段内处于活跃状态，但在当前时段不活跃。休眠用户不计入活跃用户总数。

所有活跃用户（新用户 + 重复用户 + 返回用户）在横轴上方显示为青色，而所有休眠用户在横轴下方显示为橙色。


>[!VIDEO](https://video.tv.adobe.com/v/3421667/?quality=12&learn=on)

## 用例

该分析的用例包括：

* **用户保留和流失：**&#x200B;清晰地展示了用户留存率高或低的时期。识别这些高留存率或低留存率的时期，可以帮助您做出产品决策，以鼓励高留存率或帮助最大限度地减少用户流失。
* **营销活动评估**：查看特定的营销活动可以帮助您了解其产生了多少流量，以及它如何有效地帮助用户保持参与度。
* **用户生命周期分析**：分析整个用户生命周期中的活跃用户增长情况有助于识别用户参与度下降的具体阶段。例如，如果在加入阶段，个人用户中的休眠用户比例很高，则可能表明存在可用性问题或需要更好的产品内引导。

## 界面

请参阅[界面](../overview.md#interface)，了解引导分析界面的概述。以下设置专用于此分析：

### 查询边栏

查询边栏允许您配置以下组件：

* **[!UICONTROL 视图]**：在此分析和[净增长](net-growth.md)之间进行切换。
* **[!UICONTROL 活动]**：您要测量的事件。由于此分析是以用户为基础的，因此在该时间段内与该事件互动一次的用户会被视为活跃用户。您可以在查询中包含一个事件。
* **[!UICONTROL 计为]**：要应用于所选事件的计数方法。相关选项包括[!UICONTROL 用户数]和[!UICONTROL 用户百分比]。
* **[!UICONTROL 区段]**：要作为数据分段依据的区段。 您可以在查询中包含一个区段。

### 图表设置

[!UICONTROL 积极增长]分析提供以下图表设置，这些设置可在图表上方的菜单中进行调整：

* **[!UICONTROL 图表类型]**：您想要使用的可视化类型。相关选项包括[!UICONTROL 堆叠条形图]和[!UICONTROL 堆叠面积图]。

### 时间比较

{{apply-time-comparison}}

### 日期范围

您需要分析的日期范围。此设置包含两个部分：

* **[!UICONTROL 间隔]**：您想要查看趋势数据的日期粒度。有效的选项包括每小时、每天、每周、每月和每季度。相同的日期范围可以有不同的间隔，这会影响图表中的数据点数和表格中的列数。例如，以每日粒度查看跨越三天的分析仅会显示三个数据点，而以每小时粒度查看跨越三天的分析则会显示 72 个数据点。
* **[!UICONTROL 日期]**：开始和结束日期。为方便您使用，我们提供滚动日期范围预设以及之前保存的自定义范围，或者您可以使用日程表选择器选择固定的日期范围。

<!--
## Example

See below for an example of the analysis.

![Active time compare](../assets/active-growth-compare.png)

-->
