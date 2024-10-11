---
description: 使用汇总数字和汇总变更可视化图表来显示项目中的重要数据点。
title: 摘要数字和摘要变化
feature: Visualizations
exl-id: 8872fc58-0957-415d-9958-ce564612ce87
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 50%

---

# 概要数字和概要变化

## 摘要数字 {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_summarynumber_button"
>title="摘要数字"
>abstract="创建显示总计和小计的可视化效果。"

<!-- markdownlint-enable MD034 -->

使用![摘要](/help/assets/icons/123.svg) **[!UICONTROL 摘要数字]**&#x200B;可视化图表突出显示项目中的大型重要数字。 此可视化图表的行为方式如下，使用关联的数据源：

* 如果未选中单元格，此可视化则会选择总列数。
* 如果选中了单个单元格，此可视化则会显示该单元格的概要。
* 如果选中了多个单元格，此可视化则会显示所选单元格的第一个单元格。
* 如果选中了列，此可视化则会选择列中的第一个单元格值。

![概要数字可视化](asses/../assets/summary-number.png)

作为可视化图表设置的一部分，可以使用特定的概要数字选项。

| 选项 | 定义 |
|--- |--- |
| **[!UICONTROL 缩写值]** | 选择&#x200B;**[!UICONTROL 缩写值]**&#x200B;智能缩写数值。 选中后，输入数字以定义缩写金额。 例如：<br/><table><tr><td>**原始值**</td><td>**缩写值**</td><td>**结果**</td></tr><tr><td>12,011,141.25美元</td><td>未选择</td><td  align="right">12,011,141.25美元</td></tr><tr><td>12,011,141.25美元</td><td>已选定，设置为`0`</td><td align="right">1200万美元</td></tr><tr><td>12,011,141.25美元</td><td> 已选定，设置为`1`</td><td  align="right">1200万美元</td></tr><tr><td>12,011,141.25美元</td><td>已选定，设置为`2`</td><td align="right">1201万美元</td></tr><tr><td>12,011,141.25美元</td><td>已选定，设置为`3`</td><td align="right">1201.1万美元</td></tr></table> |
| **[!UICONTROL 值汇总方式]** | 选择显示所选数据的最大值、最小值、平均值、中间值或总和。 |

## 概要变化 {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_summarychange_button"
>title="概要变化"
>abstract="创建一个显示两个数字之间增量（变化）的可视化图表"

<!-- markdownlint-enable MD034 -->


使用![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL 摘要变化]**&#x200B;可视化图表显示两个数字之间的增量（变化）。<!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.
-->

此可视化图表的行为方式如下：

* 如果未选中单元格，此可视化会比较列中的前两个单元格值。
* 如果选中了一个单元格，此可视化会显示 0，因为它将单元格值与其自身进行比较。
* 如果选中了两个单元格，则第一个选定的单元格将作为分子，第二个单元格将作为分母。
* 如果选中了两个以上的单元格，则会仅考虑比较前两个单元格。
* 如果选中了单元格范围，则会将范围内选定的第一个单元格与最后一个单元格进行比较。
* 如果选中了列，会将第一个值与其自身进行比较，结果会显示变化为 0。


![显示两个数字之间差异的摘要更改可视化图表。s](assets/summary-change.png)


作为可视化设置的一部分，可以使用特定的&#x200B;**[!UICONTROL 摘要更改选项]**。

| 选项 | 定义 |
|--- |--- |
| **[!UICONTROL 显示百分比变化]** | 显示2个数字之间的百分比变化。 |
| **[!UICONTROL 显示原始差异]** | 显示2个数字之间的原始差异。 您还可以对此选项使用缩写值，并最多显示 3 个小数位。 |
| **[!UICONTROL 缩写值]** | 选择&#x200B;**[!UICONTROL 缩写值]**&#x200B;以智能地缩写更改的值。 选中后，输入数字以定义缩写金额。 例如：<br/><table><tr><td>**原始值**</td><td>**缩写值**</td><td>**结果**</td></tr><tr><td>12,011,141.25美元</td><td>未选择</td><td  align="right">12,011,141.25美元</td></tr><tr><td>12,011,141.25美元</td><td>已选定，设置为`0`</td><td align="right">1200万美元</td></tr><tr><td>12,011,141.25美元</td><td> 已选定，设置为`1`</td><td  align="right">1200万美元</td></tr><tr><td>12,011,141.25美元</td><td>已选定，设置为`2`</td><td align="right">1201万美元</td></tr><tr><td>12,011,141.25美元</td><td>已选定，设置为`3`</td><td align="right">1201.1万美元</td></tr></table> |

>[!MORELIKETHIS]
>
>[将可视化图表添加到面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[可视化设置](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[可视化上下文菜单](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
