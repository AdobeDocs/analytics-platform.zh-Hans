---
description: 了解如何计算工作区总计。
title: 工作区总计
feature: Visualizations
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 18%

---

# 工作区总计 {#workspace-totals}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_grandtotal"
>title="总计"
>abstract="带有统计行的表或细分不支持全部总计"

<!-- markdownlint-enable MD034 -->


在自由格式表中，每个划分级别都显示一个总计行，可以显示两个总计行：

![自由格式表突出显示总计和表总计。](assets/total-row.png)

* **[!UICONTROL 表总计]**➊ — 此总计通常等于[!UICONTROL 总计]或为其一部分。 总计反映了自由格式表内应用的任何表筛选器，包括[!UICONTROL 不包含任何内容]选项。
* **[!UICONTROL 总计]** （**[!UICONTROL 个，共]**&#x200B;个&#x200B;*数字*） ➋ — 此总计表示已收集的所有事件。 当在面板级别或自由格式表中应用过滤器时，此总计会进行相应的调整以反映符合筛选条件的所有事件。




## 显示总计

在![设置](/help/assets/icons/Setting.svg) **[!UICONTROL 列设置]**&#x200B;下，有&#x200B;**[!UICONTROL 显示总计]**&#x200B;和&#x200B;**[!UICONTROL 显示总计]**&#x200B;的选项。 如果未选中这些设置，则将从表中删除总计，在总计不适用的情况下，可能需要此操作。


[静态行](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)总计的行为方式不同，并使用![设置](/help/assets/icons/Setting.svg) **[!UICONTROL 行设置]**&#x200B;进行控制。

| 选项 | 描述 |
|---|---|
| **[!UICONTROL 将当前行的总和显示为总计]** | 显示表中行的客户端总和。 此总计&#x200B;**未**&#x200B;删除重复的量度，如会话或人员。 |
| **[!UICONTROL 显示总计]** | 显示服务器端总和。 此总计可消除重复量度，如会话或人员。 |

查看自由格式表中的[动态与静态维度项目](column-row-settings/manual-vs-dynamic-rows.md)。


## 常见问题解答

| 问题 | 回答 |
|---|---|
| 灰色列百分比基于哪个&#x200B;*总计*？ | 此&#x200B;*总计*&#x200B;取决于&#x200B;**[!UICONTROL 行设置]**&#x200B;下的&#x200B;**[!UICONTROL 百分比]**&#x200B;设置选择：<ul><li>按列计算百分比 — 此设置是默认设置。 百分比基于表总计。</li><li>按行计算百分比 — 百分比基于总计。</li></ul> |
| **[!UICONTROL 包括“没有值”]**&#x200B;设置对总计有何影响？ | 如果未选中&#x200B;**[!UICONTROL 包括“无值”]**&#x200B;设置，则将从表、表总计中删除&#x200B;**[!UICONTROL 无值]**&#x200B;行，并将执行使用&#x200B;[*总计*&#x200B;度量类型](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md)的任何计算量度。 |
| 将自定义表筛选器应用于自由格式表后，我的所有计算量度和条件格式是否都将筛选器考虑在内？ | 当前不是。**[!UICONTROL 包括“没有值”]**&#x200B;已考虑在内，但自定义表筛选器不会影响以下内容：<ul><li>条件格式使用的列最大/最小范围将检查所有数据。</li><li>利用&#x200B;**[!UICONTROL 总计]**&#x200B;个量度类型的计算量度。</li><li>使用函数计算自由格式表中各行的计算量度：列总和、列最大值、列最小值、计数、平均值、中间值、百分位数、四分位数、行计数、标准偏差、方差、累积、累积平均值、回归变量、T分数、T检验、Z分数和Z检验。</li></ul> |
| 在计算量度中，**[!UICONTROL 总计]**&#x200B;量度类型反映什么？ | **[!UICONTROL 总计]**&#x200B;继续引用&#x200B;**[!UICONTROL 总计]**，并未反映应用于表或&#x200B;**[!UICONTROL 表总计]**&#x200B;的筛选器。 |
| 从自由格式表复制和粘贴数据或通过 CSV 下载数据时，显示的总计是多少？ | 总行仅反映&#x200B;**[!UICONTROL 表总计]**，并遵循列&#x200B;**[!UICONTROL 显示总计]**&#x200B;设置。 |
