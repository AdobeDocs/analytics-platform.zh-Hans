---
title: 净增长分析
description: 您是在获得用户还是在失去用户？
feature: Adobe Product Analytics, Guided Analysis
keywords: 产品分析
exl-id: a4f97458-9934-4a98-8005-fa1ba7831101
role: User
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 93%

---

# [!UICONTROL 净增长]分析 {#net-growth}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_netgrowth_button"
>title="净增长"
>abstract="您是在获得用户还是在失去用户？"

<!-- markdownlint-enable MD034 -->

![NetGrowth](/help/assets/icons/NetGrowth.svg)**[!UICONTROL 净增长]**&#x200B;分析有助于您洞察特定时期内用户增加或减少的速度。横轴代表时间间隔，纵轴代表增长的测量值。

每个数据点代表净增长，其计算方式如下：

`([New users] + [Return users]) / [Dormant users]`

此公式的结果是一个比率。净增长为 `1` 表示达到平衡状态；产品新增用户数与流失用户数相同。净增长大于 `1` 代表正增长；新用户 + 回访用户多于休眠用户。同样，净增长率低于 `1` 代表损失；休眠用户比新用户 + 回访用户多。

与[活跃](active-growth.md)分析类似，用户定义如下：

* **[!UICONTROL 新用户]**：用户在当前时段处于活跃状态，但是之前不活跃。将鼠标悬停在图表图例中的“[!UICONTROL 新用户]”上，即可查看分析为了确定新用户而回溯的时间范围。回顾范围是根据所选的日期范围和间隔动态确定的。
* **[!UICONTROL 返回用户]**：用户在当前时段处于活跃状态，在上一时段不活跃，但之前曾在某个时间点活跃过。将鼠标悬停在图表图例中的“[!UICONTROL 回访用户]”上，即可查看分析为了确定回访用户而回溯的时间范围。回顾范围是根据所选的日期范围和间隔动态确定的。
* **[!UICONTROL 休眠用户]**：用户在上一时段内处于活跃状态，但在当前时段不活跃。休眠用户不计入活跃用户总数。

>[!NOTE]
>
>重复用户并未被纳入此计算中，因为它们并不代表用户的任何增减。

>[!VIDEO](https://experienceleague.adobe.com/zh-hans/docs/customer-journey-analytics-learn/tutorials/guided-analysis/net-growth)


## 用例

该分析的用例包括：

* **绩效评估**：允许您评估产品在获取新用户方面的整体绩效。通过跟踪增长趋势，您可以更好地了解您的产品是否在以期望的速度吸引和留住用户。
* **用户获取分析**：允许您评估用户获取策略的有效性。分析用户增长来源（例如搜索引擎、营销活动或其他营销渠道）可以让您确定最重要的增长来源，以便相应地分配资源。
* **流失分析**：净增长公式中包含了流失用户（休眠用户）。您可以评估用户群随时间推移的总体健康状况。如果净增长率持续低于 `1`，这表明用户流失率很高，从而可能会促使实施保留策略。

## 界面

请参阅[界面](../overview.md#interface)，了解引导分析界面的概述。以下设置专用于此分析：

### 查询边栏

查询边栏允许您配置以下组件：

* **[!UICONTROL 视图]**：在此分析和[活跃增长](active-growth.md)之间进行切换。
* **[!UICONTROL 活动]**：您要测量的事件。由于此分析是以用户为基础的，因此在该时间段内与该事件互动一次的用户会被视为活跃用户。您可以在查询中包含一个事件。
* **[!UICONTROL 计为]**：要应用于所选事件的计数方法。 <ul><li>**[!UICONTROL 选项]**&#x200B;包括[!UICONTROL 用户数]和[!UICONTROL 用户百分比]。</li><li>[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}其他&#x200B;**[!UICONTROL B2B选项]**&#x200B;可用于Customer Journey Analytics B2B edition：[!UICONTROL 全球客户]、[!UICONTROL 帐户]、[!UICONTROL 购买团体]、[!UICONTROL 机会]、[!UICONTROL 全球客户百分比]、[!UICONTROL 帐户百分比]、[!UICONTROL 购买团体百分比]和[!UICONTROL 机会百分比]。</li></ul>
* **[!UICONTROL 区段]**：您要测量的区段。您可以在查询中包含一个区段。

### 时间比较

{{apply-time-comparison}}

### 日期范围

您需要分析的日期范围。此设置包含两个部分：

* **[!UICONTROL 间隔]**：您想要查看趋势数据的日期粒度。有效的选项包括每小时、每天、每周、每月和每季度。相同的日期范围可以有不同的间隔，这会影响图表中的数据点数和表格中的列数。例如，以每日粒度查看跨越三天的分析仅会显示三个数据点，而以每小时粒度查看跨越三天的分析则会显示 72 个数据点。
* **[!UICONTROL 日期]**：开始和结束日期。为方便您使用，我们提供滚动日期范围预设以及之前保存的自定义范围，或者您可以使用日程表选择器选择固定的日期范围。

<!-- 
## Example

See below for an example of the analysis.

![Net growth compare](../assets/net-growth-compare.png)

-->
