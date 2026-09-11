---
title: 在数据馈送中使用派生字段
description: 了解如何在数据馈送中使用派生字段。
hide: true
feature: Components
source-git-commit: a9f53472d57a3a26004bd5ca583a43134bbdba7e
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 2%

---

# 在数据馈送中使用派生字段

{{release-limited-testing}}

您可以使用[派生字段](/help/data-views/derived-fields/derived-fields.md)对数据馈送数据执行数据转换。

许多派生字段函数执行也可使用SQL应用的转换，如替换值、组合字段或转换字段的数据类型，因此选择的方法有时是首选方法。

## 派生字段与SQL

下表比较了使用派生字段或SQL的优缺点。

| 方法 | 优点 | 缺点 |
| --- | --- | --- |
| **派生字段** | <ul><li>同样的逻辑在Analysis Workspace和数据馈送输出中始终适用，因为派生字段与标准维度和量度一起作为组件包含在数据馈送架构中。</li><li>某些转换，特别是那些依赖范围设置或解析URL的转换很难在SQL中复制。</li></ul> | 增加了处理开销，这可能会影响数据馈送提交性能。<!--Under a future usage-based pricing model, this could also add cost.--> |
| **SQL** | <ul><li>不受适用于派生字段的函数和运算符限制限制。</li><li>对数据馈送提交性能没有影响。</li></ul> | <ul><li>逻辑在Analysis Workspace中不适用，因此您需要单独在该处复制逻辑。</li><li>有些转换（特别是那些依赖范围设置或解析URL的转换）很难复制或不实际。</li></ul> |

{style="table-layout:auto"}

## 派生字段函数

下表描述了每个派生字段函数，无论它最适合派生字段还是SQL，以及在使用它之前要牢记的任何注意事项。

| 派生字段函数 | 使用SQL进行复制存在困难 | 最佳拟合（派生字段或SQL） | 注意事项 |
| --- | --- | --- | --- |
| [**Case When**](/help/data-views/derived-fields/derived-fields.md#casewhen)<br/>&#x200B;根据一个或多个字段的条件应用条件，然后根据匹配的条件设置输出值。 | 易于审核 | 任一项 | 在SQL中可重现，但使用派生字段会保持相同的逻辑在Analysis Workspace和数据馈送输出中应用的一致性。 当涉及大量规则（如营销渠道分类）时，这尤其有用。 |
| [**分类**](/help/data-views/derived-fields/derived-fields.md#classify)<br/>&#x200B;定义由新派生字段中的相应值替换的一组值。 | 易于审核 | 任一项 | 在SQL中可重现，但使用派生字段会保持相同的逻辑在Analysis Workspace和数据馈送输出中应用的一致性。 |
| [**连接**](/help/data-views/derived-fields/derived-fields.md#concatenate)<br/>&#x200B;使用定义的分隔符（例如，页面名称和营销渠道）将字段值合并为一个新的派生字段。 | 易于审核 | 任一项 | 镜像将多个维度列添加到自由格式表的功能，该功能限制为完全表导出。 派生字段使类似输出可在数据馈送中使用。 |
| [**日期数学**](/help/data-views/derived-fields/derived-fields.md#datemath)<br/>&#x200B;返回两个日期或日期时间字段（例如，预订日期和登记日期之间的天数）之间的差值，范围为事件、会话或人员。 | 困难 | 派生字段 | 在SQL中复制非常复杂。 此函数依赖于“范围”设置。 有关详细信息，请参阅[函数中的作用域设置如何影响数据馈送](#scope-settings)。 |
| [**删除重复项**](/help/data-views/derived-fields/derived-fields.md#dedup)<br/>&#x200B;避免在人员范围或会话范围内多次计算值（例如，删除重复的预订确认ID）。 | 困难 | 派生字段 | 此函数依赖于“范围”设置。 有关详细信息，请参阅[函数中的作用域设置如何影响数据馈送](#scope-settings)。 |
| [**深度**](/help/data-views/derived-fields/derived-fields.md#depth)<br/>&#x200B;返回字段的深度，类似于标准的事件深度维度（例如，内部搜索深度）。 | 困难 | 派生字段 | 使用会话作为作用域，且不可配置。<!-- Open question as of 2026-09-09: does the Depth counter carry over across an hourly/daily feed boundary using lookback-window context, or does it restart? Pending confirmation from engineering (Ron Fulkerson / Nate Purser). --> 仍在工程确认会话跨越馈送 — 投放边界时计数器的行为。 此函数依赖于“范围”设置。 有关详细信息，请参阅[函数中的作用域设置如何影响数据馈送](#scope-settings)。 |
| [**查找并替换**](/help/data-views/derived-fields/derived-fields.md#find-and-replace)<br/>&#x200B;查找选定字段中的所有值，并用其他值替换它们。 | 易于审核 | 任一项 | 在SQL中可重现，但使用派生字段会保持相同的逻辑在Analysis Workspace和数据馈送输出中应用的一致性。 |
| [**查找**](/help/data-views/derived-fields/derived-fields.md#lookup)<br/>&#x200B;使用匹配键从查找数据集中查找一个值，并在新的派生字段中返回该值。 | 易于审核 | 任一项 | 如果查找表已存在，则SQL有效。 |
| [**小写**](/help/data-views/derived-fields/derived-fields.md#lowercase)<br/>&#x200B;将字段中的值转换为小写。 | 易于审核 | 任一项 | 在SQL中可重现，但使用派生字段会保持相同的逻辑在Analysis Workspace和数据馈送输出中应用的一致性。 |
| [**Math**](/help/data-views/derived-fields/derived-fields.md#math)<br/>&#x200B;将基本的数学运算符（加、减、乘、除或加幂）应用于数值字段，并逐次计算点击。 | 易于审核 | 任一项 | 在SQL中可重现，但使用派生字段会保持相同的逻辑在Analysis Workspace和数据馈送输出中应用的一致性。 |
| [**合并字段**](/help/data-views/derived-fields/derived-fields.md#merge)<br/>&#x200B;检查两个或更多字段中的第一个字段是否具有值；如果没有，则使用下一个字段，依此类推。 | 易于审核 | 任一项 | 无 |
| [**下一个或上一个**](/help/data-views/derived-fields/derived-fields.md#next-previous)<br/>&#x200B;解析访问或事件表字段的下一个或上一个值，范围为人员或会话。 | 困难 | 派生字段 | 此函数依赖于“范围”设置。 有关详细信息，请参阅[函数中的作用域设置如何影响数据馈送](#scope-settings)。 |
| [**正则表达式替换**](/help/data-views/derived-fields/derived-fields.md#regex-replace)<br/>&#x200B;使用正则表达式替换字段中的值。 | 易于审核 | 任一项 | 在SQL中可重现，但使用派生字段会保持相同的逻辑在Analysis Workspace和数据馈送输出中应用的一致性。 |
| [**拆分**](/help/data-views/derived-fields/derived-fields.md#split)<br/>&#x200B;将字段中的值拆分为新的派生字段（例如，将分隔列表转换为数组）。 | 易于审核 | 任一项 | 在SQL中可重现，但使用派生字段会保持相同的逻辑在Analysis Workspace和数据馈送输出中应用的一致性。 |
| [**汇总**](/help/data-views/derived-fields/derived-fields.md#summarize)<br/>&#x200B;将聚合函数（如sum、count或最常用函数）应用于范围“事件”、“会话”或“人员”的字段。 | 困难 | 派生字段 | 此函数依赖于“范围”设置。 有关详细信息，请参阅[函数中的作用域设置如何影响数据馈送](#scope-settings)。 |
| [**修剪**](/help/data-views/derived-fields/derived-fields.md#trim)<br/>&#x200B;从字段值的开头或结尾修剪空格、特殊字符或设置的字符数。 | 易于审核 | 任一项 | 在SQL中可重现，但使用派生字段会保持相同的逻辑在Analysis Workspace和数据馈送输出中应用的一致性。 |
| [**Typecast**](/help/data-views/derived-fields/derived-fields.md#typecast)<br/>&#x200B;更改字段的数据类型，使其可用于其他转换。 | 易于审核 | 任一项 | 在SQL中可重现，但使用派生字段会保持相同的逻辑在Analysis Workspace和数据馈送输出中应用的一致性。 |
| [**URL解析**](/help/data-views/derived-fields/derived-fields.md#urlparse)<br/>&#x200B;解析URL的各个部分，包括协议、主机、路径、查询字符串参数或哈希值。 | 困难 | 派生字段 | SQL需要自定义字符串分析来提取相同的组件。 |

{style="table-layout:auto"}

### 函数中的范围设置如何影响数据馈送 {#scope-settings}

[!UICONTROL **Date Math**]、[!UICONTROL **Deduplicate**]、[!UICONTROL **Next或Previous**]&#x200B;以及&#x200B;[!UICONTROL **Summary**]&#x200B;每个都依赖于“事件”、“会话”或“人员”的&#x200B;[!UICONTROL **作用域**]&#x200B;设置（可用选项因函数而异）。 [!UICONTROL **Depth**]&#x200B;没有可配置的范围字段，但它与会话存在固有联系，类似于标准的Event Depth维度。 具有范围的任何字段都会将相同的值写入该范围内的每行，该值取决于回顾日期范围内的数据。
<!-- Open question as of 2026-09-09: is the lookback date range boundary anchored to a fixed point (e.g., midnight), or does it float with the feed run time, and is this configurable? Pending confirmation from Ron Fulkerson. -->

由于回顾日期范围随每次数据馈送提交向前滑动，因此同一字段可能会在以后的提交中返回不同的值，即使对于已发生的事件。

风险随范围大小而增加：人员范围比会话范围风险更大，因为人员的历史在馈送运行中没有自然时间界限。

## 派生字段函数模板

[派生字段函数模板](/help/data-views/derived-fields/derived-fields.md#templates)允许您为特定用例快速创建派生字段，例如构建营销渠道、检测机器人或从URL提取UTM参数。 由于模板是从预建规则链构建的，因此在SQL中几乎总是最好使用模板来重制相同的逻辑。

如果模板包含依赖于“范围”设置的函数，则模板会继承该函数的范围警告。 请参阅[函数中的作用域设置如何影响数据馈送](#scope-settings)。

