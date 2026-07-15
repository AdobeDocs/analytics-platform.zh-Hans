---
description: 了解如何使用直方图（与条形图类似），但将数字分组为范围（存储段）。
title: 直方图
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
autotag-review: '2026-05-19T08:31:33.712Z'
TQID: 'https://experienceleague.adobe.com/X9T4RpAiJ8uL0clPhyjffdl02kwd-k2Jv3O5t6iHfss'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 28959f1ea858dee686e6d13025621c4a6164c319
workflow-type: tm+mt
source-wordcount: 494
ht-degree: 68%

---

# 直方图 {#histogram}

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="直方图"
>abstract="创建直方图可视化图表来表示范围组中数值数据的分布。"


>[!BEGINSHADEBOX]

_本文在_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;中记录了直方图可视化图表。_<br/>_对于本文的_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**&#x200B;版本，请参阅[直方图](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/visualizations/histogram)。_

>[!ENDSHADEBOX]


![直方图](/help/assets/icons/Histogram.svg)**[!UICONTROL 直方图]**&#x200B;可视化图表类似于[!UICONTROL 条形图]可视化图表，不过它可以将数字归为几组不同的范围（存储段）。 Analytics 将数字的“存储”自动归为不同的范围，但您可以在[高级设置](#advanced-settings)中更改相关设置。

## 使用

创建直方图的步骤如下：

1. 添加![直方图](/help/assets/icons/Histogram.svg)**[!UICONTROL 直方图]**&#x200B;可视化图表。 请参阅[将可视化图表添加到面板](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。
1. 从&#x200B;**[!UICONTROL 指标]**&#x200B;组件列表中拖动一个指标，或从&#x200B;[!UICONTROL *添加指标*]&#x200B;下拉菜单中选择一个指标。
1. （可选）选择&#x200B;**[!UICONTROL 显示高级设置]**。 请参阅[高级设置](#advanced-settings)。
1. 选择&#x200B;**[!UICONTROL 生成]**。

>[!NOTE]
>
>直方图仅支持标准量度，而不支持计算量度。

在下面的示例中，直方图用于统计人数的存储段会话。 直方图显示大多数人在所选日期范围内确实有 16 至 21 次会话。

![直方图](assets/histogram.png)

## 高级设置

作为可视化图表的一部分，可以使用特定直方图设置。

| 直方图设置 | 描述 |
|---|---|
| **[!UICONTROL 开始存储段]** | 确定直方图开始的分段。 默认值为“1”。 您可以将起始数字从0设置为无限（无负数）。 |
| **[!UICONTROL 量度存储段]** | 允许您增加/减少数据范围（存储段）的数量。 存储段的最大数量为 50。 |
| **[!UICONTROL 量度存储段大小]** | 允许您设置每个分段的大小。 例如，您可以将存储段大小从1次页面查看更改为2次页面查看。 |
| **[!UICONTROL 计算方法]** | 从&#x200B;**[!UICONTROL 全局帐户]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 帐户]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 购买群]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 机会]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 人员]**、**[!UICONTROL 会话]**、**[!UICONTROL 事件]**&#x200B;或&#x200B;**[!UICONTROL 对象]**&#x200B;中选择。 例如，每个帐户 [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}的页面浏览量、每个会话的页面浏览量、每个人的页面浏览量或每个事件的页面浏览量。 选择&#x200B;**[!UICONTROL 对象]**&#x200B;时，请选择用于子事件分析的[自定义容器](/help/data-views/create-dataview.md#containers-1)。 |

<!--Russ or Meike - Check Hit Type link above. -->

**示例**：

| 开始存储段 | 量度存储段 | 量度存储段大小 | 结果 |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![直方图，开始存储段 1、量度存储段 5、量度存储段大小 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![直方图，开始存储段 0、量度存储段 3、量度存储段大小 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[将可视化图表添加到面板可视化图表设置可视化上下文菜单使用直方图识别意外数据值](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168)

