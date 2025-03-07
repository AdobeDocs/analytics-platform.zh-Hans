---
description: 直方图类似于条形图，不过它可以将数字归为几组不同的范围（存储段）。
title: 直方图
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
source-git-commit: 0859a35bb0f34800b970ff256bc9b740ffe424c9
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 39%

---

# 直方图 {#histogram}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="直方图"
>abstract="创建直方图可视化图表来表示范围组中数值数据的分布。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文记录了_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;中的直方图可视化图表。_<br/>_查看本文的_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;版本的[直方图](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/histogram)。_

>[!ENDSHADEBOX]


![直方图](/help/assets/icons/Histogram.svg) **[!UICONTROL 直方图]**&#x200B;可视化与[!UICONTROL 条形图]可视化类似，但它将数字分组为范围（存储桶）。 Analytics 将数字的“存储”自动归为不同的范围，但您可以在[高级设置](#advanced-settings)中更改相关设置。

## 使用

创建直方图的步骤如下：

1. 添加![直方图](/help/assets/icons/Histogram.svg) **[!UICONTROL 直方图]**&#x200B;可视化图表。 请参阅[将可视化图表添加到面板](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。
1. 从&#x200B;**[!UICONTROL 指标]**&#x200B;组件列表中拖动一个指标，或从&#x200B;[!UICONTROL *添加指标*]&#x200B;下拉菜单中选择一个指标。
1. （可选）选择&#x200B;**[!UICONTROL 显示高级设置]**。 请参阅[高级设置](#advanced-settings)。
1. 选择&#x200B;**[!UICONTROL 生成]**。

>[!NOTE]
>
>直方图仅支持标准量度，而不支持计算量度。

在下面的示例中，直方图用于为人员数存储会话。 直方图显示，大多数人在所选日期范围内有16-21个会话。

![直方图](assets/histogram.png)

## 高级设置

在可视化中，可以使用特定的直方图设置。

| 直方图设置 | 描述 |
|---|---|
| **[!UICONTROL 正在启动存储桶]** | 确定直方图从哪个存储段开始。“1”为默认值。您可以在 0 到无穷大（非负数）的范围内设置开始数量。 |
| **[!UICONTROL 指标桶]** | 允许您增加/减少数据范围（存储段）的数量。 存储段的最大数量为50。 |
| **[!UICONTROL 量度存储段大小]** | 您可以设置每个存储段的大小。例如，您可以将存储段大小从 1 次页面查看更改为 2 次页面查看。 |
| **[!UICONTROL 计数方法]** | 从&#x200B;**[!UICONTROL 人员]**、**[!UICONTROL 会话]**&#x200B;或&#x200B;**[!UICONTROL 事件]**&#x200B;中选择。 例如，每个会话的页面查看次数，或每个人的页面查看次数，或每个事件的页面查看次数。 |

<!--Russ or Meike - Check Hit Type link above. -->

**示例**：

| 起始分段 | 量度分段 | 量度存储段大小 | 结果 |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![直方图，起始存储桶1，量度存储桶5，量度存储桶大小2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![直方图，起始存储桶0，量度存储桶3，量度存储桶大小5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[在面板中添加可视化效果](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[可视化设置](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[可视化上下文菜单](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>[使用直方图识别意外的数据值](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168)

