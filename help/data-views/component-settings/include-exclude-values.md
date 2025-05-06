---
title: 包括排除值组件设置
description: 有条件地包括或排除某个维度项，具体取决于其值。
exl-id: 1a3f8ab5-bd82-415a-989a-f93e6714df4b
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 220ebd7dbc3fa75d221690cd6e5828bd94395434
workflow-type: ht
source-wordcount: '356'
ht-degree: 100%

---

# 包括排除值组件设置 {#include-exclude-values-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_includeexcludevalues"
>title="包括排除值"
>abstract="将量度只筛选到具有符合特定条件的数量值。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_includeexcludevalues"
>title="包括排除值"
>abstract="缩小维度以仅包含符合特定条件的值。在报告中，包含和排除发生在分配和分段之前。确定指定的区段逻辑是否区分大小写。"

<!-- markdownlint-enable MD034 -->

通过“包括排除值”，可创建依赖于维度项的值的规则。在 Analysis Workspace 中将不符合您设置的条件的值视为其从未存在，尽管基础数据集中仍存在这些数据。

![数据视图窗口，其中突出显示“包括排除值”](../assets/include-exclude.png)

| 设置 | 描述/用例 |
| --- | --- |
| [!UICONTROL 设置包括/排除值] | 一个复选框，通过它，可启用在数据视图中包括数据的条件。 |
| [!UICONTROL 区分大小写] | 在 String 架构数据类型上可见。默认开启。此设置仅适用于[!UICONTROL 包括/排除值]逻辑，而不适用于所得的值。通过它，可指定规则是否区分大小写。 |
| [!UICONTROL 匹配] | 用于指定您想要在归因和分段之前考虑用于报告的值（例如，仅使用包含短语“错误”的值）。您可以指定：**[!UICONTROL 如果满足所有条件]**&#x200B;或&#x200B;**[!UICONTROL 如果满足任意条件]**。使用空格分隔每个值。 |
| [!UICONTROL 条件] | 用于指定应该应用于特定区段规则的匹配逻辑。<ul><li>**字符串**：[!UICONTROL 包含短语]、[!UICONTROL 包含任何术语]、[!UICONTROL 包含所有术语]、[!UICONTROL 不包含任何术语]、[!UICONTROL 不包含短语]、[!UICONTROL 等于]、[!UICONTROL 不等于]、[!UICONTROL 开头为]、[!UICONTROL 结尾为]</li><li>**双精度/整数**：[!UICONTROL 等于]、[!UICONTROL 不等于]、[!UICONTROL 大于]、[!UICONTROL 小于]、[!UICONTROL 大于或等于]、[!UICONTROL 小于或等于]</li><li>**日期**：[!UICONTROL 等于]、[!UICONTROL 不等于]、[!UICONTROL 晚于]、[!UICONTROL 早于]、[!UICONTROL 期间]</li></ul> |
| [!UICONTROL 匹配运算数] | 用于指定应将匹配运算符应用到的匹配运算数。<ul><li>**字符串**：文本字段</li><li>**双精度/整数**：数值类型的文本字段（带上/下箭头）</li><li>**日期**：日期粒度选择器（日程表）</li><li>**日期时间**：日期和时间粒度选择器</li></ul> |
| [!UICONTROL 添加规则] | 用于指定附加匹配运算符和运算数。 |

{style="table-layout:auto"}
