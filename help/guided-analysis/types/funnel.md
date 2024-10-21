---
title: 漏斗分析
description: 比较步骤之间的转化率。
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: 产品分析
role: User
source-git-commit: 7ccc9f28acf08fb49d86005abb7fbb648a1564ce
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 2%

---

# [!UICONTROL 漏斗]分析

![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg)**[!UICONTROL Funnel ]**分析提供了产品中关键用户历程的可视表示形式。 水平轴表示用户必须执行的每个步骤。 垂直轴表示每个步骤中用户或会话的百分比。 所有步骤必须按最终顺序完成，但可以在报告窗口内的任何时间执行。

>[!VIDEO](https://video.tv.adobe.com/v/3421663/?learn=on){width="90%"}

## 用例

此分析的用例包括：

* **转化分析**：您可以分析漏斗每个阶段的转化，如零售结账、帐户注册、订阅流程或产品体验中的其他关键历程。 通过跟踪从一个步骤进展到下一个步骤的用户数量，您可以识别具有异常或不需要的转化率的瓶颈。 此信息对于了解您可以在何处改进产品历程以立即获得结果非常有价值。
* **试验分析**：您可以对运行A/B试验的可选步骤或步骤的漏斗中的转化率进行比较。 此信息可帮助您确定漏斗的哪个变化会导致最高转化率，以便鼓励更多用户沿着该路径前进。
* **入门优化**：通过检查关键事件的用户行为来优化产品的入门流程。 您可以确定用户难以完成或无法完成的步骤。
* **功能采用和参与**：了解用户如何与您的产品中的特定功能进行交互。 通过与功能相关的步骤分析用户进度，您可以查看采用率，并识别用户可能未充分使用某些功能的区域。 然后，您可以使用此信息专注于功能改进以提高采用率。
* **营销渠道有效性**：衡量营销渠道的有效性。 您可以创建一个区段，重点关注与不同营销渠道（例如，付费搜索、显示、免费搜索或直接）交互的用户。 然后，您可以比较其历程，以了解哪个渠道可带来最佳产品结果。

## 界面

有关引导式分析界面的概述，请参阅[界面](../overview.md#interface)。 以下设置特定于此分析：

### 查询边栏

利用查询边栏，可配置以下组件：

* **[!UICONTROL 视图]**：在此分析和[转化趋势](conversion-trends.md)之间切换。
* **[!UICONTROL 步骤]**：要跟踪的事件接触点。 图表中的每个条形表示一个步骤。 您最多可以包含十个步骤。
   * [!UICONTROL 比较]：每个步骤都提供一个选项，用于比较单个漏斗步骤中的多个事件，从而创建一个“分支漏斗”。 此功能允许您并排比较两个历程的摩擦力，而无需创建两个单独的分析。 当存在步骤选项或在漏斗内运行A/B试验时，此插件非常有用。 请参阅Customer Journey Analytics教程中的[漏斗](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/funnel)，观看介绍如何比较漏斗的视频。
* **[!UICONTROL 计为]**：要应用于漏斗的范围。 选项包括[!UICONTROL 会话]和[!UICONTROL 用户]。
   * [!UICONTROL 会话]：所有步骤必须发生在同一会话中才能被计数。
   * [!UICONTROL 用户]：所有步骤都必须在选定的报表时段内执行才能被计数。
* **[!UICONTROL 区段]**：要与其比较漏斗的区段。 所选的每个区段会将每个步骤拆分为多个条。 每种颜色代表不同的区段。 您最多可以包含三个区段。

### 图表设置

[!UICONTROL 漏斗]分析提供了以下图表设置，可以在图表上方的菜单中调整这些设置：

* **[!UICONTROL 图表类型]**：要使用的可视化图表类型。 选项包括[!UICONTROL 步骤]。
* **[!UICONTROL 转换自]**：确定从步骤到步骤的百分比计算。 选项包括从[!UICONTROL 第一步]或[!UICONTROL 上一步]计算转换。

### 时间比较

{{apply-time-comparison}}



### 日期范围

分析所需的日期范围。 此设置包含两个组件：

* **[!UICONTROL 时间间隔]**：要查看趋势数据的日期粒度。 此设置不会影响非趋势分析，如[漏斗](funnel.md)。
* **[!UICONTROL 日期]**：开始和结束日期。 您可以为方便起见，使用滚动日期范围预设和以前保存的自定义范围，也可以使用日历选择器来选择固定日期范围。

<!--
## Example

See below for an example of the analysis.

![Funnel time compare](../assets/funnel-compare.png)

-->
