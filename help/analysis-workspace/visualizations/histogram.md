---
description: 直方图类似于条形图，不过它可以将数字归为几组不同的范围（存储段）。
title: 直方图
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
source-git-commit: c94e97723a4ed30e675144e02196c93016b13235
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 81%

---

# 直方图 {#histogram}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="直方图"
>abstract="创建直方图可视化图表来表示范围组中数值数据的分布。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文记录了_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** 中的直方图可视化。_<br/>_请参阅本文中_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** 版本的[直方图](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/visualizations/histogram)。_

>[!ENDSHADEBOX]


![直方图](/help/assets/icons/Histogram.svg)**[!UICONTROL 直方图]**&#x200B;可视化图表类似于[!UICONTROL 条形图]可视化图表，不过它可以将数字归为几组不同的范围（存储段）。Analytics 将数字的“存储”自动归为不同的范围，但您可以在[高级设置](#advanced-settings)中更改相关设置。

## 使用

创建直方图的步骤如下：

1. 添加![直方图](/help/assets/icons/Histogram.svg)**[!UICONTROL 直方图]**&#x200B;可视化图表。请参阅[将可视化图表添加到面板](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。
1. 从&#x200B;**[!UICONTROL 量度]**&#x200B;组件列表中拖动量度，或从&#x200B;[!UICONTROL *添加量度*]&#x200B;下拉菜单中选择量度。
1. （可选）选择&#x200B;**[!UICONTROL 显示高级设置]**。请参阅[高级设置](#advanced-settings)。
1. 选择&#x200B;**[!UICONTROL 生成]**。

>[!NOTE]
>
>直方图仅支持标准量度，而不支持计算量度。

在下面的示例中，直方图用于统计人数的存储段会话。直方图显示大多数人在所选日期范围内确实有 16 至 21 次会话。

![直方图](assets/histogram.png)

## 高级设置

作为可视化图表的一部分，可以使用特定直方图设置。

| 直方图设置 | 描述 |
|---|---|
| **[!UICONTROL 开始存储段]** | 确定直方图从哪个存储段开始。“1”为默认值。您可以在 0 到无穷大（非负数）的范围内设置开始数量。 |
| **[!UICONTROL 量度存储段]** | 您可以增加/减少数据范围（存储段）的数量。存储段的最大数量为 50。 |
| **[!UICONTROL 量度存储段大小]** | 您可以设置每个存储段的大小。例如，您可以将存储段大小从 1 次页面查看更改为 2 次页面查看。 |
| **[!UICONTROL 计算方法]** | 从&#x200B;**[!UICONTROL 全局帐户]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}、**[!UICONTROL 帐户]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}、**[!UICONTROL 购买群]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}、**[!UICONTROL 机会]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}、**[!UICONTROL 人员]**、**[!UICONTROL 会话]**&#x200B;或&#x200B;**[!UICONTROL 活动]**&#x200B;中进行选择。 例如，每个帐户[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}的页面查看次数、每个会话的页面查看次数、每个人的页面查看次数、或每个事件的页面查看次数。 |

<!--Russ or Meike - Check Hit Type link above. -->

**示例**：

| 开始存储段 | 量度存储段 | 量度存储段大小 | 结果 |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![直方图，开始存储段 1、量度存储段 5、量度存储段大小 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![直方图，开始存储段 0、量度存储段 3、量度存储段大小 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[将可视化图表添加到面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[可视化图表设置](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[可视化图表上下文菜单](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>[使用直方图识别意外数据值](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168)

