---
description: 了解如何在Customer Journey Analytics试验面板中分析A/B测试结果。
title: 试验性面板
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
role: User
source-git-commit: 3e2d92003f8b89a20edfcfb8358854c7fbd15577
workflow-type: tm+mt
source-wordcount: '2144'
ht-degree: 20%

---

# 试验性面板 {#experimentation-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_experimentation_button"
>title="试验"
>abstract="创建一个面板来比较不同的用户体验、营销或消息变化。并确定哪种变化最能产生特定的结果。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_experimentation_panel"
>title="试验"
>abstract="比较不同的用户体验、营销或消息变化，以确定哪些最能推动特定结果。<br/><br/>**参数&#x200B;**<br/>**试验**：分析的试验。<br>**控制变量**：所选试验的控制变量。<br/>**成功量度**：最多 5 个标准（非计算）成功量度来分析试验。<br/>**标准化量度**：人员、会话或事件。 此指标（也称为计数方法）将作为提升计算的分母。该量度也会在应用置信度计算之前影响数据汇总的方式。"

<!-- markdownlint-enable MD034 -->



通过&#x200B;**[!UICONTROL 试验]**&#x200B;面板，分析师可以比较不同的用户体验、营销或消息传递变化，以确定哪一种最能推动特定结果。 您可以从任何试验平台评估任何A/B试验的提升和置信度：在线、离线、Target或Journey Optimizer等Adobe解决方案，甚至BYO（自带）数据。

详细了解Adobe Customer Journey Analytics与Adobe Target之间的[集成](https://experienceleague.adobe.com/zh-hans/docs/target/using/integrate/cja/target-reporting-in-cja)。

## 访问控制 {#access}

试验面板可供所有Customer Journey Analytics用户使用。 不需要管理员权限或其他权限。但是，前提条件要求只有管理员才能执行的操作。

## 计算量度中的函数

提供了两个高级函数：提升和置信度。 有关详细信息，请参阅[参考 - 高级函数](/help/components/calc-metrics/cm-adv-functions.md)。

## 先决条件

要使用试验面板，请确保遵循以下先决条件：

### 创建与试验数据集的连接

建议的数据架构将试验数据放在[对象数组](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/array)中，该数组在两个单独的维度中包含试验数据和变体数据。 两个维度都必须位于&#x200B;**单个**&#x200B;对象数组中。 如果您的试验数据位于单个维度中（试验数据和变体数据位于分隔字符串中），则可在数据视图中使用[子字符串](/help/data-views/component-settings/substring.md)设置将该维度一分为二以用于面板中。


将试验数据[引入Adobe Experience Platform后，[在Customer Journey Analytics](/help/connections/create-connection.md)中创建与一个或多个试验数据集的连接。](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home)

### 在数据视图中添加上下文标签

在Customer Journey Analytics数据视图设置中，管理员可以将[上下文标签](/help/data-views/component-settings/overview.md)添加到维度或量度，并且Customer Journey Analytics服务（如[!UICONTROL 试验]面板）可以使用这些标签。 试验面板使用两个预定义标签：

* [!UICONTROL 试验试验]
* [!UICONTROL 试验变体]

在包含试验数据的数据视图中，选择两个维度，一个包含试验数据，另一个包含变量数据。 然后用&#x200B;**[!UICONTROL 试验试验]**&#x200B;和&#x200B;**[!UICONTROL 试验变体]**&#x200B;标签标记这些维度。

试验变体和试验变体的![上下文标签选项。](assets/context-label.png)

如果没有这些标签，则由于没有试验可使用，因此“试验”面板不工作。

## 使用

要使用&#x200B;**[!UICONTROL 试验]**&#x200B;面板：

1. 创建&#x200B;**[!UICONTROL 试验]**&#x200B;面板。 有关如何创建面板的信息，请参阅[创建面板](panels.md#create-a-panel)。


1. 指定面板的[输入](#panel-input)。

1. 观察面板的[输出](#panel-output)。

   >[!IMPORTANT]
   >
   >如果尚未完成Customer Journey Analytics数据视图中的必要设置，则在可以继续操作之前会收到此消息： [!UICONTROL 请在数据视图中配置试验维度和变体维度]。
   >

### 面板输入

要使用“试验”面板，请执行以下操作：

1. 配置面板输入设置：

   ![实验面板被拖入项目中。](assets/experiment-input.png)

   | 设置 | 定义 |
   | --- | --- |
   | **[!UICONTROL 日期范围]** | 根据在所选试验的Customer Journey Analytics中收到的第一个事件，自动设置试验面板的日期范围。 如果需要，可以将日期范围限制或扩展到更具体的时间范围。 |
   | **[!UICONTROL 试验]** | 向最终用户展示的一组体验变体，用于确定哪一种变体最好永久保留。 试验由两个或多个变量组成，其中一个变量视为控制变量。该设置预先填充了数据视图中已标记为&#x200B;**[!UICONTROL 试验]**&#x200B;标签的维度，以及过去3个月的试验数据。 |
   | **[!UICONTROL 控件变体]** | 最终用户体验中的两种或多种变化中的一种，并会为了确定更好的替代方案而对其进行比较。必须选择一个变量作为控制变量，并且只能将一个变量视为控制变量。 该设置预先填充了数据视图中已标记为&#x200B;**[!UICONTROL 变量]**&#x200B;标签的维度。 此设置将会调出与此试验相关的变量数据。 |
   | **[!UICONTROL 成功量度]**➊ | 用户正在与变量进行比较的一个或多个量度。转换量度（最高或最低）具有最理想结果的变量被声明为试验的&#x200B;*最佳性能变量*。 最多可添加 5 个量度。 |
   | **[!UICONTROL 标准化量度]**➋ | 运行测试的基础（[!UICONTROL 人员]、[!UICONTROL 会话]或[!UICONTROL 事件]）。 例如，测试可能会比较几种变体的转化率，其中&#x200B;**[!UICONTROL 转化率]**&#x200B;计算为“页面查看” |
   | **[!UICONTROL 包含置信度上/下限]** | 启用此选项可显示置信水平的上限和下限。 |


1. 选择&#x200B;**[!UICONTROL 生成]**。

### 面板输出

试验面板会返回一组丰富的数据和可视化图表，帮助您更好地了解试验的执行情况。在面板顶部，提供了[摘要更改](../visualizations/summary-number-change.md)可视化图表以提醒您选择的面板设置。 您可以随时通过选择右上方的编辑铅笔来编辑面板。

您还可以获得一份文本摘要，其中会指出试验是否具有结论性，并会总结结果。结论性基于统计显着性（请参阅[统计方法](#adobes-statistical-methodology)。） 您可以看到具有最高提升和置信度的最佳性能变量的摘要数字。

对于您选择的每个成功量度，将显示[自由格式表](../visualizations/freeform-table/freeform-table.md)可视化图表和转化率[折线图](../visualizations/line.md)可视化图表。

![试验输出显示一个自由格式表和一个转化率趋势。](assets/experiment-output.png)


>[!NOTE]
>
>此面板当前不支持分析 A/A 测试。

#### 解释结果

1. **试验有结论**：每次查看试验报告时，都会分析到目前为止在试验中积累的数据。 当&#x200B;*anytime*&#x200B;的有效置信度超过&#x200B;*至少一个*&#x200B;变量的95%阈值时，分析将宣布试验具有结论性。 对于双臂以上的情况，采用Benjamini-Hochberg校正方法对多重假设检验进行校正。

2. **最佳性能变量**：当一项试验被宣布为具有结论性时，具有最高转化率的变量会被标记为最佳性能变量。 请注意，此变量必须是控制变量或基线变量，或者是超过95% *anytime*&#x200B;有效置信阈值的变量之一（应用Benjamini-Hochberg校正）。

3. **转化率**：显示的转化率是成功量度值➊与标准化量度值的比➋率。 请注意，如果量度不是二进制的（试验中的每个单位为1或0），则此值可以大于1

4. **提升**：试验报告摘要显示超过基线的部分，这是对给定变量转换率超过基线的改进百分比的衡量。 精确地来说，它是给定变量与基线之间的性能差异除以基线的性能，并以百分比表示。

5. **置信度**：显示的随时有效置信度是一种概率度量，可表明有多少证据能够表明给定变量与控制变量相同。 置信度越高，表明支持控制变量和非控制变量具有相同性能的假设的证据越少。置信度是一种概率（以百分比表示），您会发现给定变量和控制变量之间的转化率差异较小。 实际上，真实的潜在转化率没有区别。 就 *p* 值而言，显示的置信度为1-*p*-值。

>[!NOTE]
>
>对结果的完整描述应考虑所有可用证据（例如试验设计、样本量、转化率、置信度等），而不仅仅是宣布是否具有结论性。 即使结果尚未具有结论性，仍可以有令人信服的证据表明一个变量与另一个变量不同（例如，置信区间几乎不重叠）。 理想情况下，所有统计证据，在连续范围内解释，都应为决策提供依据。

## Adobe 的统计方法 {#statistics}

为了提供易于解释且安全的统计推断，Adobe 采用了基于[随时有效置信序列（Anytime Valid Confidence Sequences）](https://arxiv.org/abs/2103.06476)的统计方法。

置信序列是置信区间的&#x200B;*连续*&#x200B;模拟。 为了理解置信序列的含义，请设想您重复试验一百次。 计算每个进入试验的新用户&#x200B;*的平均业务量度（例如电子邮件的打开率）的估计值及其相关的95%置信序列。*

95%置信度序列包括您运行的100次实验中的95次实验中业务量度的“真”值。 （每个试验只能计算一次95%置信区间，以提供相同的95%覆盖率保证；而不是针对每个新用户）。 因此，通过使用置信序列，您可以连续监控试验，而不会增加误报错误率，即这些序列允许“窥视”结果。

## 解释非随机维度 {#non-randomized}

Customer Journey Analytics允许分析人员选择任何维度作为试验。 但是，当选择的实验维度不是随机人员的维度时，您如何解释该分析？

例如，以用户看到的广告为例。 如果您决定向人员显示&#x200B;*广告B*&#x200B;而不是&#x200B;*广告A*，则您可能有兴趣测量某些量度的变化（例如，平均收入）。 显示广告B（而不是广告A）的因果关系对于做出营销决策至关重要。 如果您使用显示广告B的替代策略替换了显示广告A的现状，则此因果效应可以测量为整个群体的平均收入。

A/B测试是行业内客观衡量此类干预效果的黄金标准。 A/B测试产生因果估计的关键原因是，接收可能变体之一的人员随机化。

现在，考虑一个不是通过随机化实现的维度，例如，人的美国状态。 主要来自纽约和加利福尼亚两个州。 由于地区天气差异，冬衣品牌在两个州的平均销售收入可能有所不同。 在这种情况下，天气可能是冬季服装销售背后的真正因果因素，而不是人的地理状态不同这一事实。

通过Customer Journey Analytics中的“试验”面板，可按人员的各个状态的平均收入差异分析数据。 在这种情况下，产出没有因果解释。 然而，这种分析可能仍然有意义。 它提供了按各州划分的平均收入差异的估计（以及不确定性的衡量标准）。  此值也称为&#x200B;*统计假设验证测试*。 此分析的输出可能很有趣，但不一定可操作。 仅仅因为您尚未随机化，有时也无法随机化人员以显示该维度的可能值之一。

下图比较了这两种情况：

![显示观察数据和随机试验的图表。](assets/randomize.png)

如果想衡量干预措施X对结果Y的影响，那么两者真正的原因可能是混淆因素C。如果数据不是通过X上的随机化实现的，影响更难测量，并且分析明确说明了C。随机化打破了X对C的依赖，让我们不必担心其他变量就可以测量X对Y的影响。

## 在实验中使用计算量度。 {#use-in-experimentation}

>[!NOTE]
>
>对于同时使用Customer Journey Analytics和Adobe Journey Optimizer的组织，此部分中的信息还适用于Journey Optimizer中的试验功能。

并非所有计算量度都与试验面板兼容。

包含以下任何量度或常量的计算量度与试验面板不兼容：

* 来自[摘要数据集](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/summary-data)的基本量度
* 基本量度彼此相除或相乘（例如，`Revenue`/`Orders`）
* 添加到基本量度或从基本量度减去的常量（例如，`Revenue+50`）
* 以下任一基本量度：
   * 人员

创建计算量度时，与“试验”面板不兼容的计算量度在&#x200B;[!UICONTROL **产品兼容性**]&#x200B;字段中的Customer Journey Analytics（不包括试验）处具有值&#x200B;[!UICONTROL **Everywhere**]。 有关创建计算量度的信息，请参阅[生成量度](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)。

## 在试验面板中使用计算量度

请参阅这篇博客帖子，了解有关在试验面板](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119)中使用计算量度的[的信息。
