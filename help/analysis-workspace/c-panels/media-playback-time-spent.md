---
title: “媒体播放耗时”面板
description: 了解如何在Analysis Workspace中使用和解释“Media Playback耗时”面板。
feature: Panels
exl-id: de0fdbea-71f0-445b-a1e4-c7e895f142d4
role: User
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 96%

---

# “媒体播放耗时”面板 {#media-playback-time-spent-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaplaybacktimespent_button"
>title="媒体播放耗时"
>abstract="创建面板来分析一段时间内的视频消耗情况，其中具有不同级别的粒度，以及细分和比较的能力。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaplaybacktimespent_panel"
>title="媒体播放耗时"
>abstract="分析一段时间内的视频使用情况，选择各种粒度，并可选择使用区段、维度、维度项或日期范围进行细分和比较。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文记录了_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;_ 中的媒体播放耗时面板。<br/>_请参阅本文中_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** 版本的[媒体播放耗时面板](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/panels/media-playback-time-spent)。_

>[!ENDSHADEBOX]


>[!NOTE]
>
>只有购买了 Customer Journey Analytics 的流媒体收藏集附加组件的客户才能使用媒体平均受众访问分钟数面板。
>请联系您的 Adobe 销售代表或 Adobe 帐户团队以获取更多信息。
>

**[!UICONTROL 媒体播放耗时]**&#x200B;面板支持长期分析播放，其中提供关于并发高峰的详细信息，并可进行细分和比较。

在 Analysis Workspace 中，播放耗时是指在特定时间点查看媒体流的耗时。它包括暂停、缓冲和开始时间。

已购买流媒体集合附加组件的客户可以分析播放耗时，从而深入洞察内容质量和查看者参与度。并在故障排除或规划容量或规模时提供帮助。

播放耗时可以帮助您了解：

* 发生并发峰值的地方。

* 发生流失的地方。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [媒体播放耗时](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/media-analytics/measuring-media-analytics/media-playback-time-spent-panel){target="_blank"}以观看演示视频。

{{videoaa}}

>[!ENDSHADEBOX]


## 使用

要使用&#x200B;**[!UICONTROL 媒体播放耗时]**&#x200B;面板：

1. 创建&#x200B;**[!UICONTROL 媒体播放耗时]**&#x200B;面板。有关如何创建面板的信息，请参阅[创建面板](panels.md#create-a-panel)。

1. 确保为面板选择的数据视图已从流媒体集合中配置了组件。

1. 指定面板的[输入](#panel-input)。

1. 观察面板的[输出](#panel-output)。


### 面板输入

您可以使用以下输入设置来配置“媒体播放耗时”面板：

| 设置 | 描述 |
|---|---|
| 面板日期范围 | 面板日期范围的默认值为“今天”。您可以对其进行编辑以一次查看一天或几个月的数据。<br>这个可视化图表限制为 1440 行数据（例如，以分钟作为粒度级别来表示 24 小时）。如果日期范围和粒度的组合产生的行数超过了 1440 行，则将自动更新粒度以适应完整的日期范围。 |
| 粒度 | 粒度的默认值为“分钟”。<br>这个可视化图表限制为 1440 行数据（例如，以分钟作为粒度级别来表示 24 小时）。如果日期范围和粒度的组合产生的行数超过了 1440 行，则将自动更新粒度以适应完整的日期范围。 |
| 面板摘要数字 | 要查看播放耗时的日期或时间详细信息，可以使用摘要数字。“最大值”显示并发峰值的详细信息。“最小值”显示低谷期的详细信息。“总和”将计算用于选择的播放耗时的总和。面板默认值仅显示“最大值”，不过您可以将其更改为显示“最小值”、“总和”或这三个值的任意组合。<br>如果您使用细分，则会为每一项显示摘要数字。 |
| 系列细分 | （可选）您可以按区段、维度、维度项或日期范围细分可视化图表。<p>– 一次最多可以查看 10 行。细分仅限一个级别。</p><p>- 在拖动一个维度时，将根据所选面板日期范围，自动选择顶部维度项。</p>- 要比较日期范围，请将 2 个或更多日期范围拖到系列细分区段中。 |
| 时间格式 | 您可以按 `Hours:Minutes:Seconds`（默认）或 `Minutes`（以整数显示，四舍五入到 0.5）格式查看播放耗时。 |
| 日期序列显示 | 如果您已放置至少两个日期范围区段作为系列细分，您将看到用于选择叠加（默认）或顺序的选项。“叠加”显示具有公共 x 轴起点的线，以便它们并行运行，而“顺序”显示具有特定 x 轴起点的线。如果数据对齐（例如，区段1于晚上8:44结束，区段2于晚上8:45开始），则这些线将按顺序显示。 |


![媒体播放耗时的默认视图。](assets/mpts_default_view.png)

### 面板输出

“媒体播放耗时”面板可以返回一个线形图和摘要数字，以包括播放耗时的最大值、最小值和/或总和。在该面板顶部，提供了一个摘要行，用于提醒您选择的面板设置。

随时选择![编辑媒体播放耗时面板](/help/assets/icons/Edit.svg)以编辑并重建面板。

如果您选择系列细分，则会为每一项在线形图上显示一条线以及摘要数字：

![媒体播放耗时输出显示线形图和摘要。](assets/mpts_outputs1.png)

### 数据源

可在此面板中使用的唯一量度是“播放耗时”。

| 量度 | 描述 |
|---|---|
| 播放耗时 | 所选粒度期间查看内容所耗的总时间（`hours:minutes:seconds` 或 `minutes`），其中包括暂停、缓冲和开始时间。 |

## 常见问题解答

| 问题 | 回答 |
|---|---|
| 自由格式表在什么位置？如何查看数据源？ | <p></p><p>自由格式表在此视图中不可用。要下载数据源，请从线形图的上下文菜单中选择下载 CSV 文件选项。</p> |
| <p>为什么我的粒度发生了变化？</p> | <p>这个可视化图表限制为 1440 行数据（例如，以分钟作为粒度级别来表示 24 小时）。如果日期范围和粒度的组合产生 1440 行以上，则将自动更新粒度以容纳这个完整的日期范围。</p><p></p><p>如果从较大的日期范围更改到较小的日期范围，粒度在日期范围更改后自动更新为允许的最低明细级别。要查看较高的粒度，请编辑面板并重建。</p> |
| <p></p><p>如何比较视频名称、区段、内容类型等？</p> | <p>要在单个可视化图表中比较这些内容，请将区段、维度或特定维度项拖放到系列细分区段中。</p><p></p><p>视图限制为 10 个细分。要查看 10 个以上的细分，您必须使用多个面板。</p> |
| 如何比较日期范围？ | 要在单个可视化图表中比较日期范围，请通过拖动 2 个或更多日期范围来使用系列细分。这些日期范围覆盖面板日期范围。 |
| 如何更改可视化图表类型？ | <p></p><p>此面板仅允许时间系列的线形图可视化图表。</p> |
| 能否运行异常检测？ | <p></p><p>否。异常检测对此面板不可用。</p> |


>[!MORELIKETHIS]
>
>[Create a panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>[“媒体平均受众访问分钟数”面板](average-minute-audience-panel.md)
>[媒体并行查看者面板](media-concurrent-viewers.md)
>
