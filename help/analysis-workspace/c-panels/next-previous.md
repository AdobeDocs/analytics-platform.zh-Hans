---
description: 显示特定维度的下一项或上一项维度面板。
title: “下一项或上一项”面板
feature: Panels
role: User, Admin
exl-id: a5f6ce97-6720-4129-9ece-e2e834289d45
source-git-commit: c94e97723a4ed30e675144e02196c93016b13235
workflow-type: ht
source-wordcount: '457'
ht-degree: 100%

---

# “下一项或上一项”面板 {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_button"
>title="下一项或上一项"
>abstract="创建面板来了解人们来自的上一项维度或人们要去的下一项维度。"

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="下一项或上一项"
>abstract="分析访客之前最常来自何处或后续最常访问的地方是什么。指定用于可视化图表的维度、维度项、方向和容器。"



<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_本文记录了_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_ 中的“下一项或上一项”面板。<br/>_请参阅本文中_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** 版本的[下一项或上一项面板](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/panels/next-previous)。_

>[!ENDSHADEBOX]

**[!UICONTROL 下一项或上一项]**&#x200B;面板包含许多表格和可视化图表，用于识别特定维度的下一项或上一项维度。例如，您可能想要浏览客户访问主页后最常访问哪些页面。

## 使用 {#use}

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_container"
>title="容器"
>abstract="选择容器来确定您的查询范围。"

要使用&#x200B;**[!UICONTROL 下一项或上一项]**&#x200B;面板：

1. 创建&#x200B;**[!UICONTROL 下一项或上一项]**&#x200B;面板。有关如何创建面板的信息，请参阅[创建面板](panels.md#create-a-panel)。

1. 指定面板的[输入](#panel-input)。

1. 观察面板的[输出](#panel-output)。

### 面板输入

您可以使用以下输入设置配置[!UICONTROL 下一项或上一项]面板：

![下一项或上一项面板](assets/next-or-previous-item.png)

| 输入 | 描述 |
| --- | --- |
| **[!UICONTROL 维度]** | 选择您想要浏览下一项或上一项的维度。 |
| **[!UICONTROL 维度项]** | 选择位于下一项/上一项查询中心的特定维度项。 |
| **[!UICONTROL 方向]** | 请指定您是否正在寻找[!UICONTROL 下一项]或[!UICONTROL 上一项]维度。 |
| **[!UICONTROL 容器]** | 选择容器、**[!UICONTROL 全球帐户]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 帐户]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 购买群组]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 机会]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 会话]**&#x200B;或&#x200B;**[!UICONTROL 人员]**，以确定您的查询范围。 |

{style="table-layout:auto"}

选择&#x200B;**[!UICONTROL 生成]**&#x200B;以生成面板。

### 面板输出

[!UICONTROL 下一项或上一项]面板返回一组丰富的数据和可视化图表，帮助您更好地了解特定维度项之后或之前的发生次数。


![下一项/上一项面板输出](assets/next-or-previous-item-output.png)


| 可视化图表 | 描述 |
| --- | --- |
| **[!UICONTROL 水平条]** | 根据您选择的维度项列出下一项（或上一项）维度。将光标悬停在单个条形图上可突出显示自由格式表中相应的项。 |
| **[!UICONTROL 摘要数字]** | 当前月份（迄今为止）所有下一项或上一项维度发生次数的高级摘要数字。 |
| **[!UICONTROL 自由格式表]** | 根据您选择的维度项以表的格式列出下一项（或上一项）维度。例如，人们在主页或工作区页面之后（或之前）访问的最受欢迎的页面是哪些（按发生次数计算）。 |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[创建一个面板](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
