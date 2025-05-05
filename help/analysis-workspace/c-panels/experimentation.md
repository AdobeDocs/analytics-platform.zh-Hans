---
description: 了解如何在 Customer Journey Analytics 试验面板中分析 A/B 测试结果。
title: 试验性面板
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
role: User
source-git-commit: 7e32ae7aa757a8ca47732416f0f883033611ea94
workflow-type: tm+mt
source-wordcount: '2179'
ht-degree: 96%

---

# 试验性面板 {#experimentation-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_experimentation_button"
>title="试验"
>abstract="创建一个面板来比较不同的用户体验、营销或消息变化。并确定哪种变化最能产生特定的结果。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_experimentation_panel"
>title="试验"
>abstract="比较不同的用户体验、营销或消息变化，确定哪种变化最能推动特定结果。指定试验、要比较的控制变量、成功量度和标准化量度。可选择设置置信度的上限和下限。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文记录了_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** 中的试验面板。_<br/>_有关如何在_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** 中分析 Adobe Target 活动和体验的信息，请参阅 [Analytics for Target 面板](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/panels/a4t-panel)。_

>[!ENDSHADEBOX]


通过&#x200B;**[!UICONTROL 试验]**&#x200B;面板，分析师可以比较不同的用户体验、营销或消息传递方面的变化，以确定哪一种变化最能推动特定结果。您可以从任何试验平台评估任何 A/B 试验的提升度和置信度：在线、离线、来自 Target 或 Adobe Journey Optimizer 等 Adobe 解决方案、甚至是 BYO（自带）数据。

详细了解有关 [Adobe Customer Journey Analytics 与 Adobe Target](https://experienceleague.adobe.com/zh-hans/docs/target/using/integrate/cja/target-reporting-in-cja) 之间的集成。

## 访问控制 {#access}

试验面板可供所有 Customer Journey Analytics 用户使用。不需要管理员权限或其他权限。但是，这些先决条件需要采取只有管理员才能执行的操作。

## 计算量度中的函数

提供两项高级函数：升力和置信度。有关详细信息，请参阅[参考——高级函数](/help/components/calc-metrics/cm-adv-functions.md)。

## 先决条件

要使用实验面板，请确保遵循以下先决条件：

### 创建与试验数据集的连接

推荐的数据架构是将实验数据存储在一个[对象数组](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/ui/fields/array)中，该数组包含两个独立维度的实验数据和变量数据。两个维度都需要位于&#x200B;**单个**&#x200B;对象数组中。如果您的试验数据只有一个维度（试验数据和变量数据以分隔符字符串的形式存在），您可以在数据视图中使用[子字符串](/help/data-views/component-settings/substring.md)设置，将该维度拆分为两个，以便在面板中使用。


在 Adobe Experience Platform [摄取](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/ingestion/home)您的试验数据后，[在 Customer Journey Analytics 中创建与一个或多个试验数据集的连接](/help/connections/create-connection.md)。

### 在数据视图中添加上下文标签

在 Customer Journey Analytics 数据视图设置中，管理员可以向维度或量度添加[上下文标签](/help/data-views/component-settings/overview.md)，并且 Customer Journey Analytics 服务（如[!UICONTROL 试验]面板）可以使用这些标签来实现其目的。试验面板使用两个预定义标签：

* [!UICONTROL 试验试验]
* [!UICONTROL 试验变量]

在包含试验数据的数据视图中，选择两个维度，一个包含试验数据，另一个包含变量数据。然后用&#x200B;**[!UICONTROL 实验试验]**&#x200B;和&#x200B;**[!UICONTROL 实验变量]**&#x200B;标签标注这些维度。

![实验和实验变量的上下文标签选项。](assets/context-label.png)

如果没有这些标签，则由于没有试验可使用，因此“试验”面板不起作用。

## 使用

要使用&#x200B;**[!UICONTROL 实验]**&#x200B;面板：

1. 创建一个&#x200B;**[!UICONTROL 实验]**&#x200B;面板。有关如何创建面板的信息，请参阅[创建面板](panels.md#create-a-panel)。


1. 指定面板的[输入](#panel-input)。

1. 观察面板的[输出](#panel-output)。

   >[!IMPORTANT]
   >
   >如果尚未完成 Customer Journey Analytics 数据视图中的必要设置，则在可继续操作之前将收到此消息：[!UICONTROL 请配置数据视图中的试验维度和变量维度]。
   >

### 面板输入

要使用实验面板：

1. 配置面板输入设置：

   ![将实验面板拖入项目中。](assets/experiment-input.png)

   | 设置 | 定义 |
   | --- | --- |
   | **[!UICONTROL 日期范围]** | 根据 Customer Journey Analytics 中收到的所选试验的第一个事件，实验面板的日期范围会自动设置。如果需要，可以将日期范围限制或扩展到更具体的时间范围。 |
   | **[!UICONTROL 试验]** | 向最终用户展示的某项体验的一组变体，以确定哪一种体验最适合永久保存。试验由两个或多个变量组成，其中一个变量会被视为控制变量。该设置预先填充了数据视图中已标记为&#x200B;**[!UICONTROL 试验]**&#x200B;标签的维度，以及过去 3 个月的实验数据。 |
   | **[!UICONTROL 控制变量]** | 最终用户体验中的两种或多种变化中的一种，并会为了确定更好的替代方案而对其进行比较。必须选择一个变量作为控制变量，并且只能将一个变量视为控制变量。该设置预先填充了数据视图中已标记为&#x200B;**[!UICONTROL 变量]**&#x200B;标签的维度。此设置将会调出与此试验相关的变量数据。 |
   | **[!UICONTROL 成功量度]** | 用户正在与变量进行比较的一个或多个量度。可产生最理想的转化量度结果（最高或最低）的变量会成为某项试验中具有&#x200B;*最佳性能的变量*。最多可添加 5 个量度。 |
   | **[!UICONTROL 标准化量度]** ➋ | 运行测试的基础(**[!UICONTROL 全局帐户]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}、**[!UICONTROL 帐户]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}、**[!UICONTROL 机会]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}、**[!UICONTROL 购买群]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}、**[!UICONTROL 人员]**、**[!UICONTROL 会话]**&#x200B;或&#x200B;**[!UICONTROL 事件]**)。 例如，测试可能会比较几种变体的转化率，其中&#x200B;**[!UICONTROL 转化率]**&#x200B;计算为“页面查看”。 |
   | **[!UICONTROL 包括置信上限/下限]** | 启用此选项可以显示置信度的上限和下限。 |


1. 选择&#x200B;**[!UICONTROL 生成]**。

### 面板输出

试验面板会返回一组丰富的数据和可视化图表，以帮助您更好地了解试验的执行情况。在该面板顶部，提供了一个[摘要更改](../visualizations/summary-number-change.md)可视化图表，用于提醒您选择的面板设置。在任何时候，您都可以通过选择右上角的编辑铅笔来编辑面板。

您还可以获得一份文本摘要，其中会指出试验是否具有结论性，并会总结结果。结论性取决于统计显著性（参见[统计方法](#adobes-statistical-methodology)）。您可以看到表现最佳、提升幅度最大且置信度最高的变体的汇总数据。

对于您选择的每个成功量度，都会显示一个[自由格式表](../visualizations/freeform-table/freeform-table.md)可视化图表和一个转化率[线型](../visualizations/line.md)可视化图表。

![实验输出，其中显示一个自由格式表和一个转化率趋势。](assets/experiment-output.png)


>[!NOTE]
>
>此面板当前不支持分析 A/A 测试。

#### 解释结果

1. **试验具有结论性**：每次查看实验报告时，都会对到目前为止实验中积累的数据进行分析。当&#x200B;*至少有一个*&#x200B;变量的&#x200B;*随时*&#x200B;有效置信度超过 95% 的阈值时，分析会宣布实验具有结论性。当臂数超过两个时，需应用 Benjamini-Hochberg 校正法来校正多重假设验证测试。

2. **最佳性能变量**：当一项试验被宣布为具有结论性时，具有最高转化率的变量会被标记为“最佳性能变量”。请注意，该变量必须是对照变量或基准变量，或者是超过 95% *随时*&#x200B;有效置信阈值的变量之一（应用 Benjamini-Hochberg 校正）。

3. **转换率**：显示的转换率是成功量度值 ➊ 与标准化量度值 ➋ 的比率。注意，如果量度不是二进制的（实验中的每个单位为 1 或 0），则该值可能大于 1

4. **提升**：试验报告摘要显示超过基线的部分，这是对给定变量转换率超过基线的改进百分比的衡量。精确地来说，它是给定变量与基线之间的性能差异除以基线的性能，并以百分比表示。

5. **置信度**：所示的随时有效置信度是一种概率度量，可表明有多少证据能够表明给定变量与控制变量相同。置信度越高，表明支持控制变量和非控制变量具有相同性能的假设的证据越少。置信度是指您观察到给定变量与控制变量之间转化率差异较小的概率（以百分比表示）。而实际上，真正的潜在转化率并无差异。就 *p* 值而言，显示的置信度为1-*p*-值。

>[!NOTE]
>
>对结果的全面描述应考虑所有可用证据（如试验设计、样本量、转化率、置信度等），而不仅仅是声明是否具有结论性。即使结果尚未具有结论性，但仍可能有令人信服的证据（例如，置信区间几乎不重叠）表明一个变体与另一个变体不同。理想情况下，在连续范围上诠释的所有统计证据都应为决策提供信息。

## Adobe 的统计方法 {#statistics}

为了提供易于解释且安全的统计推断，Adobe 采用了基于[随时有效置信序列（Anytime Valid Confidence Sequences）](https://arxiv.org/abs/2103.06476)的统计方法。

置信度序列是置信区间的&#x200B;*顺序*&#x200B;模拟。要理解置信度序列是什么，请想象一下您重复试验一百次。并为&#x200B;*每位参与实验的新用户*&#x200B;计算平均业务量度（例如电子邮件的打开率）的估计值及其相关的 95% 置信度序列。

95% 置信度序列将包括您运行的 100 次实验中的 95 次实验中业务量度的“真”值。（每个试验只能计算一次 95% 置信区间，以提供相同的 95% 覆盖率保证；而不是计算每个新用户）。因此，通过使用置信序列，您可以连续监控试验，而不会增加假阳性错误率，即这些序列允许“窥视”结果。

## 解释非随机维度 {#non-randomized}

 Customer Journey Analytics 允许分析师选择任何维度作为实验。但是，如果所选的实验维度不是对人员进行随机分组的，那么该如何解释分析呢？

例如，考虑一个人看到的广告。如果您决定向人员展示&#x200B;*广告 B* 而非&#x200B;*广告 A*，您可能对衡量某些量度（例如平均收入）的变化感兴趣。展示广告 B 而不是广告 A 的因果效应对于做出营销决策至关重要。如果用展示广告 B 的替代策略取代展示广告 A 的现状，那么这种因果效应可以用整个人群的平均收入来衡量。

A/B 测试是业内客观衡量此类干预效果的黄金标准。A/B 测试之所以能够产生因果估计，关键原因在于人们会随机接收其中的一种可能变量。

现在，考虑一个并非通过随机化实现的维度，例如，该人所在的美国州。人们主要来自两个州，即纽约和加利福尼亚。由于存在地区气候差异，冬季服装品牌在两个州的平均销售收入可能会有所不同。在这种情况下，天气可能是冬季服装销售的真正影响因素，而不是人们的地理位置不同。

使用 Customer Journey Analytics 中的实验面板可以分析不同人员所在州的平均收入差异数据。在这种情况下，输出没有因果解释。然而，这样的分析可能仍然具有吸引力。它提供了各州平均收入差异的估计值（以及不确定性指标）。该值也称为&#x200B;*统计假设验证测试*。这种分析的结果可能具有吸引力，但并不一定具有可操作性。这仅仅是因为您尚未进行随机化，并且有时无法将人们随机分配到维度的某一可能值。

下列插图对比了这些情况：

![显示观察数据和随机实验的图表。](assets/randomize.png)

当您想衡量干预措施 X 对结果 Y 的影响时，很可能两者的真正原因都是混杂因素 C。如果数据不是通过对 X 进行随机分组而获得的，那么影响就更难衡量，而分析会明确考虑到 C。随机化打破了 X 对 C 的依赖，让我们可以衡量 X 对 Y 的影响，而不必担心其他变量。

## 在实验中使用计算量度。 {#use-in-experimentation}

>[!NOTE]
>
>对于同时使用 Customer Journey Analytics 和 Adobe Journey Optimizer 的组织，本节中的信息也适用于 Journey Optimizer 中的实验功能。

并非所有计算量度都与实验面板兼容。

包含以下任何量度或常量的计算量度均与实验面板不兼容：

* [摘要数据集](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/summary-data)的基本量度
* 基础指标之间进行相除或相乘（例如，`Revenue`/`Orders`）
* 在基础量度上增加或减少的常数（例如，`Revenue+50`）
* 以下任何基础量度：
   * 人员

在创建计算量度时，与“实验”面板不兼容的计算量度在&#x200B;[!UICONTROL **产品兼容性**]&#x200B;字段中显示为 Customer Journey Analytics （不包括实验）中的&#x200B;[!UICONTROL **所有位置**]&#x200B;值。有关创建计算量度的信息，请参阅[建立量度](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)。

## 在实验面板中使用计算量度

请参阅此博客文章，了解有关[使用实验面板中的计算量度](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119)的信息。

>[!MORELIKETHIS]
>[掌握 Adobe Customer Journey Analytics 实验](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/mastering-adobe-customer-journey-analytics-experimentation-your/ba-p/732338)
>
