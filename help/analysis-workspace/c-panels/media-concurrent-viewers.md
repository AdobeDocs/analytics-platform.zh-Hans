---
title: “媒体并行查看者”面板
description: 了解如何使用和解读Analysis Workspace中的“媒体并行查看者”面板。
feature: Panels
exl-id: a442fb9c-165f-4136-95e2-ce92b9280c25
role: User
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '1175'
ht-degree: 98%

---

# 媒体并行查看者面板 {#media-concurrent-viewers-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_button"
>title="媒体并行查看者"
>abstract="创建一个面板来分析特定时段内的并发查看者。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_panel"
>title="媒体并行查看者"
>abstract="分析一段时间内的并发查看者，查看并发峰值，可选择使用区段、维度、维度项或日期范围进行细分和比较。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文记录了_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;_ 中的媒体并行查看者面板。<br/>_请参阅本文中_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** 版本的[媒体并行查看者](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers)。_

>[!ENDSHADEBOX]


>[!NOTE]
>
>只有购买了 Customer Journey Analytics 的流媒体收藏集附加组件的客户才能使用媒体平均受众访问分钟数面板。
>
>请联系您的 Adobe 销售代表或 Adobe 帐户团队以获取更多信息。
>

**[!UICONTROL 媒体并行查看者]**&#x200B;面板可以分析一段时间内的并发查看者，了解有关并发峰值的详细信息，并且可以进行细分和比较。

您可以分析并发查看者以了解在哪里出现了并发峰值或者在哪里出现流失，从而针对内容质量和查看者参与情况提供宝贵的洞察。并帮助进行故障排除或者容量或规模的规划。

在 Analysis Workspace 中，“并发查看者”量度是指在特定时间点查看媒体流的独特人员数量，与会话数无关。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [媒体并行查看者面板](https://video.tv.adobe.com/v/26990/?quality=12&learn=on){target="_blank"}以观看演示视频。

{{videoaa}}

>[!ENDSHADEBOX]

## 使用

要使用&#x200B;**[!UICONTROL 媒体并行查看者]**&#x200B;面板：

1. 创建&#x200B;**[!UICONTROL 媒体并行查看者]**&#x200B;面板。有关如何创建面板的信息，请参阅[创建面板](panels.md#create-a-panel)。

1. 确保为面板选择的数据视图已从流媒体集合中配置了组件。

1. 指定面板的[输入](#panel-input)。

1. 观察面板的[输出](#panel-output)。

### 面板输入

您可以使用以下输入设置来配置媒体并行查看者面板：

| 设置 | 描述 |
|---|---|
| **[!UICONTROL 面板日期范围]** | 面板日期范围的默认值为“今天”。您可以对其进行编辑以一次查看一天或几个月的数据。<br> <br>这个可视化图表限制为 1440 行数据（例如，以分钟作为粒度级别来表示 24 小时）。如果日期范围和粒度的组合产生的行数超过了 1440 行，则将自动更新粒度以适应完整的日期范围。 |
| **[!UICONTROL 粒度]** | 粒度的默认值为“分钟”。<br>这个可视化图表限制为 1440 行数据（例如，以分钟作为粒度级别来表示 24 小时）。如果日期范围和粒度的组合产生的行数超过了 1440 行，则将自动更新粒度以适应完整的日期范围。 |
| **[!UICONTROL 面板概要数字]** | 要查看并发查看者的日期或时间详细信息，可以使用摘要数字。“最大值”显示并发峰值的详细信息。**[!UICONTROL 最小值]**&#x200B;显示低谷期的详细信息。面板默认值仅显示“最大值”，不过您可以将其更改为显示“最小值”或同时显示“最大值”和“最小值”。<br><br>如果您使用细分，则会为每一项显示摘要数字。 |
| **[!UICONTROL 系列细分]** | （可选）您可以按区段、维度、维度项或日期范围细分可视化图表。<br>一次最多可以查看 10 行。细分仅限一个级别。<br>在拖动一个维度时，将根据所选面板日期范围，自动选择顶部维度项。<br>要比较日期范围，请将 2 个或更多日期范围拖到系列细分区段中。 |

下面是一个按&#x200B;**[!UICONTROL 分钟]**&#x200B;粒度配置面板的示例，**[!UICONTROL 最大值仅为]**&#x200B;摘要数字。并按&#x200B;**[!UICONTROL 其他]**、**[!UICONTROL 表]**、**[!UICONTROL 手机]**、**[!UICONTROL 游戏机]**、**[!UICONTROL 媒体播放器]**、**[!UICONTROL 机顶盒]**、**[!UICONTROL 电视]**&#x200B;进行细分。

![“媒体并行查看者系列“细分视图可显示 10 个维度、分段或日期范围中的 7 个。](assets/concurrent-viewers-series-breakdown.png)

### 面板输出

“媒体并发查看者”面板可以返回一个线形图和摘要数字，以包括最大和/或最小并发查看者的详细信息。在该面板顶部，提供了一个摘要行，用于提醒您选择的面板设置。

随时选择![编辑媒体并行查看者面板](/help/assets/icons/Edit.svg)，编辑并重建面板。

如果您选择了系列细分，则会为每一项在线形图上显示一条线以及摘要数字：

![媒体并行查看者输出。](assets/concurrent-viewers-output.png)

### 数据源

可在此面板中使用的唯一量度是&#x200B;**[!UICONTROL 并发查看者]**：

| 量度 | 描述 |
|---|---|
| **[!UICONTROL 并发查看者]** | 在特定时间点查看媒体流的独特人员数量，与会话数无关。 |

自由格式表在此视图中不可用。要查看数据源，您可以从线形图可视化图表上下文菜单中下载数据源，然后选择&#x200B;**[!UICONTROL 将数据下载为 CSV]**。其中包括系列细分。

![并发查看者输出选项，其中突出显示“将数据下载为 CSV”。](assets/concurrent-viewers-download-csv.png)

## 常见问题解答

| 问题 | 回答 |
|---|---|
| 自由格式表在什么位置？如何查看数据源？ | 自由格式表在此视图中不可用。您可以从线形图上下文菜单下载数据源，然后选择&#x200B;**[!UICONTROL 将数据下载为 CSV]**。 |
| 为什么我的粒度发生了变化？ | 这个可视化图表限制为 1440 行数据（例如，以分钟作为粒度级别来表示 24 小时）。如果日期范围和粒度的组合产生 1440 行以上，则将自动更新粒度以容纳这个完整的日期范围。<br><br>如果从较大的日期范围更改到较小的日期范围，粒度在日期范围更改后自动更新为允许的最低明细级别。要查看较高的粒度，请编辑面板并重建。 |
| 如何比较视频名称、区段、内容类型等？ | 要在单个可视化图表中比较这些项目，请将区段、维度或特定维度项拖至系列细分区段中。<br><br>视图限制为 10 个细分。要查看 10 个以上的细分，您必须使用多个面板。 |
| 如何比较日期范围？ | 要在单个可视化图表中比较日期范围，请通过拖动 2 个或更多日期范围来使用系列细分。这些日期范围覆盖面板日期范围。 |
| 如何更改可视化图表类型？ | 此面板仅允许时间系列的线形图可视化图表。 |
| 能否运行异常检测？ | 否。异常检测对此面板不可用。 |
| 为什么使用独特人员而不是活动会话？ | 使用独特人员可以消除在节目边界处（即同时结束和开始会话时）不需要的峰值。 |
| 比分钟更高的粒度下的并发查看者是什么意思？ | 使用比分钟更高的粒度，并发查看者是该时间范围内所有分钟下的独特并发查看者的总和。例如，在小时级别的粒度上，并发查看者是该小时内所有分钟下的独特并发查看者的总和。 |
| 工作区面板是否会显示与并行查看者报告相同的信息？ | 否。在 Analysis Workspace 中，“并发查看者量度”定义为在特定时间点查看媒体流的独特人员数量。与会话数无关。<br><br>此量度不同于报告部分中的并发查看者报告，该报告使用的是“并发活动会话”。使用独特人员帐户以消除在节目边界处（即同时结束和开始会话时）不需要的峰值。 |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[Create a panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>&#x200B;>[媒体播放耗时面板](media-playback-time-spent.md)
>&#x200B;>[“媒体平均受众访问分钟数”面板](average-minute-audience-panel.md)
>