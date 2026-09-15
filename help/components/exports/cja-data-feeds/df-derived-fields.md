---
title: 将数据转换应用于数据馈送
description: 了解使用组件设置、派生字段或SQL转换数据馈送数据的不同方法。
hide: true
feature: Components
source-git-commit: 082927c1d511ba0831beba08aaaac0e2d0d9fbf6
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 5%
---
# 将数据转换应用于数据馈送

{{release-limited-testing}}

您可以使用以下任一方法转换数据馈送数据：

* [数据视图组件设置](/help/data-views/component-settings/overview.md)，使用

* [派生字段](/help/data-views/derived-fields/derived-fields.md)

* SQL

您选择的方法有时取决于您的喜好。 下表比较了各种取舍。

## 比较数据转换方法

下表比较了每种方法的一般优缺点。

| 方法 | 优点 | 缺点 |
| --- | --- | --- |
| **组件设置** | <ul><li>在提交数据馈送之前在报告时应用。</li><li>在Analysis Workspace和数据馈送输出中，相同的逻辑始终适用。</li><li>不会用完您帐户中某个有限的派生字段。</li><li>某些转换（如持久性和量度重复数据删除）很难在SQL中复制，并且当前在派生字段中也不可能实现持久性。</li></ul> | <ul><li>仅适用于每个组件支持的特定设置集 — 没有使用派生字段构建自定义逻辑那么灵活。</li><li>对于一些设置，是否影响数据馈送输出仍待确认。 请参阅下表。</li></ul> |
| **派生字段** | <ul><li>在提交数据馈送之前在报告时应用。</li><li>在Analysis Workspace和数据馈送输出中，相同的逻辑始终适用。</li><li>与任何单个组件设置（如链接条件规则）相比，支持更灵活的自定义逻辑。</li><li>某些转换，特别是那些依赖范围设置或解析URL的转换很难在SQL中复制。</li></ul> | <ul><li>增加了处理开销，这可能会影响数据馈送提交性能。<!--Under a future usage-based pricing model, this could also add cost.--></li><li>使用您帐户中有限的派生字段之一。 如果组件设置可以执行相同的作业，则最好是使用该设置。</li></ul> |
| **SQL** | <ul><li>不受适用于派生字段的函数和运算符限制限制。</li><li>对数据馈送提交性能没有影响。</li></ul> | <ul><li>已在提交数据馈送后应用。</li><li>逻辑在Analysis Workspace中不适用，因此您需要单独在该处复制逻辑。</li><li>有些转换（特别是那些依赖范围设置、解析URL、删除重复值或跨范围保留值的转换）比较难以复制或不切实际。</li></ul> |

{style="table-layout:auto"}

## 数据转换

下表列出了特定的数据转换，显示了哪些方法（或方法）可以执行每一种转换，在SQL中复制的难度以及要使用的方法。<!--A few transformations are still being confirmed with the engineering team and are marked as open questions — don't treat those as confirmed to affect data feed output until that's resolved.-->

| 转换 | 组件设置 | 派生字段 | SQL中的困难 | 最佳拟合 | 注意事项 |
| --- | --- | --- | --- | --- | --- |
| **应用条件逻辑或按条件筛选值** | [包括排除值](/help/data-views/component-settings/include-exclude-values.md) | [案例时间](/help/data-views/derived-fields/derived-fields.md#casewhen) | 易于字符串；量度从中等到困难 | 对于字符串；量度的组件设置 | 对于字符串值，在所有三个值之间进行比较 — 这在很大程度上是出于优先考虑。 对于量度，SQL要求将`CASE`语句与`COUNT`结合使用，这是可行的，但更复杂，因此组件设置是更简单的路径。 |
| 成功事件的&#x200B;**属性点数** | [归因](/help/data-views/component-settings/attribution.md) | 不可用 | 不适用 | 不适用 | 不适用于数据馈送中的量度。 在SQL或其他情况下，没有要复制的数据馈送行为。 |
| **将数值装入范围** | [值分段](/help/data-views/component-settings/value-bucketing.md) | 案例时间（手动） | 困难 | 组件设置 | 从组件设置（最简单）到派生字段（一般，使用手动Case When），复杂性增加到了SQL（最复杂）。 |
| **使用查找样式映射对值进行分类** | 不可用 | [分类](/help/data-views/derived-fields/derived-fields.md#classify) | 易于审核 | 任一项 | 在SQL中可重现，但使用派生字段会保持相同的逻辑在Analysis Workspace和数据馈送输出中应用的一致性。 |
| **将字段值与分隔符组合** | 不可用 | [连接](/help/data-views/derived-fields/derived-fields.md#concatenate) | 易于审核 | 任一项 | 镜像将多个维度列添加到自由格式表的功能，该功能限制为完全表导出。 派生字段使类似输出可在数据馈送中使用。 |
| **转换字段的数据类型** | 不可用 | [类型](/help/data-views/derived-fields/derived-fields.md#typecast) | 易于审核 | 任一项 | 在SQL中可重现，但使用派生字段会保持相同的逻辑在Analysis Workspace和数据馈送输出中应用的一致性。 |
| **计数量度发生次数（值与实例数）** | [行为](/help/data-views/component-settings/behavior.md) | 自定义基于数学的解决方法 | 易于审核 | 任一项 | 这三种方法都能奏效；如果你能在Customer Journey Analytics中原生这样做，就没有理由不这样做。 |
| **在作用域内删除重复值** | [重复量度删除](/help/data-views/component-settings/metric-deduplication.md) | [删除重复项](/help/data-views/derived-fields/derived-fields.md#dedup) | 困难 | 组件设置或派生字段 | 取决于范围设置。 请参阅[作用域设置如何影响数据馈送](#scope-settings)。 组件设置和派生字段大致相同，但首选组件设置，因为它不会用完某个有限的派生字段。 |
| **确定会话中的字段深度** | 不可用 | [深度](/help/data-views/derived-fields/derived-fields.md#depth) | 困难 | 派生字段 | 使用会话作为作用域，且不可配置。<!-- Open question as of 2026-09-09: does the Depth counter carry over across an hourly/daily feed boundary using lookback-window context, or does it restart? Pending confirmation from engineering (Ron Fulkerson / Nate Purser). --> 仍在工程确认会话跨越馈送 — 投放边界时计数器的行为。 取决于范围设置。 请参阅[作用域设置如何影响数据馈送](#scope-settings)。 |
| **查找并替换文本值** | 不可用 | [查找和替换](/help/data-views/derived-fields/derived-fields.md#find-and-replace) | 易于审核 | 任一项 | 在SQL中可重现，但使用派生字段会保持相同的逻辑在Analysis Workspace和数据馈送输出中应用的一致性。 |
| **设置显示值的格式** | [格式](/help/data-views/component-settings/format.md) | 不可用 | 困难 | 组件设置 | 日期时间格式尚未反映在数据馈送输出中 — 馈送当前显示标准时间戳，无论此设置如何，尽管Adobe计划支持此设置以供正式发布。 量度的数值格式（小数、货币、百分比）是否影响数据馈送输出，仍在与团队确认。 |
| **从摘要数据集对维度进行分组** | [摘要数据组](/help/data-views/component-settings/summary-data-group.md) | 不可用 | 未完成的问题 | 未完成的问题 | 尚未与团队讨论。 在确认之前，请勿假定这会影响数据馈送输出。 |
| **处理空白（“无值”）字段** | [无值选项](/help/data-views/component-settings/no-value-options.md) | 不可用 | 未完成的问题 | 未完成的问题 | 这是否影响数据馈送输出（包括是否将空白值作为null发送，以及“视为值”是否更改基础数据），仍由团队进行审查。 |
| **从查找数据集中查找值** | 不可用 | [查找](/help/data-views/derived-fields/derived-fields.md#lookup) | 易于审核 | 任一项 | 如果查找表已存在，则SQL有效。 |
| **小写字符串** | [行为](/help/data-views/component-settings/behavior.md) | [小写](/help/data-views/derived-fields/derived-fields.md#lowercase) | 易于审核 | 组件设置或派生字段 | 两者是等效的，但首选组件设置，因为它不会占用一个有限的派生字段。 |
| **将多个字段合并为一个** | 不可用 | [合并字段](/help/data-views/derived-fields/derived-fields.md#merge) | 易于审核 | 任一项 | — |
| **将URL解析为其组件** | [子字符串](/help/data-views/component-settings/substring.md)（URL解析方法） | [URL分析](/help/data-views/derived-fields/derived-fields.md#urlparse) | 困难 | 组件设置或派生字段 | SQL需要自定义字符串分析来提取相同的组件。<!-- Possible discrepancy: in the component settings meeting, Matt and Derek described all Substring methods, including URL parse, as roughly interchangeable across component setting, derived field, and SQL ("either one would work... maybe a preference"), which is a looser SQL-difficulty read than "Difficult." Flagged for Luke to reconcile; not changed without confirmation. --> |
| **对数字字段执行基本数学运算** | 不可用 | [数学](/help/data-views/derived-fields/derived-fields.md#math) | 易于审核 | 任一项 | 在SQL中可重现，但使用派生字段会保持相同的逻辑在Analysis Workspace和数据馈送输出中应用的一致性。 |
| **跨事件保留维度值** | [持久性](/help/data-views/component-settings/persistence.md) | 当前不可用<!-- Derek: considering adding this to FDL and surfacing it in derived fields; not currently possible. --> | 困难 | 组件设置 | 使用组件设置比在SQL中复制此逻辑容易得多。 已确认与回顾日期范围交互的方式与范围相关的派生字段函数相同。 请参阅[了解回顾日期范围](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-lookback-date-range)。 |
| **使用正则表达式替换值** | [Substring](/help/data-views/component-settings/substring.md) （Regex方法） | [正则表达式替换](/help/data-views/derived-fields/derived-fields.md#regex-replace) | 易于审核 | 任一项 | 这三种方法产生的结果是一样的，这取决于人们的喜好。 |
| **解析会话中的下一个或上一个值** | 不可用 | [下一个或上一个](/help/data-views/derived-fields/derived-fields.md#next-previous) | 困难 | 派生字段 | 取决于范围设置。 请参阅[作用域设置如何影响数据馈送](#scope-settings)。 |
| **返回两个日期之间的差值** | 不可用 | [日期数学](/help/data-views/derived-fields/derived-fields.md#datemath) | 困难 | 派生字段 | 在SQL中复制非常复杂。 取决于范围设置。 请参阅[作用域设置如何影响数据馈送](#scope-settings)。 |
| **将量度的范围设为基于事件、配置文件或总数** | [范围](/help/data-views/component-settings/scope.md) | 不可用 | 未完成的问题 | 未完成的问题 | 尚未与团队讨论。 在确认之前，请勿假定这会影响数据馈送输出。 |
| **拆分分隔值** | [Substring](/help/data-views/component-settings/substring.md) （分隔符或来自左/右方法） | [拆分](/help/data-views/derived-fields/derived-fields.md#split) | 易于审核 | 任一项 | 这三种方法产生的结果是一样的，这取决于人们的喜好。 |
| **汇总或聚合作用域中的值** | 不可用 | [摘要](/help/data-views/derived-fields/derived-fields.md#summarize) | 困难 | 派生字段 | 取决于范围设置。 请参阅[作用域设置如何影响数据馈送](#scope-settings)。 |
| **从字符串修剪字符** | [Substring](/help/data-views/component-settings/substring.md) （Trim方法） | [修剪](/help/data-views/derived-fields/derived-fields.md#trim) | 易于审核 | 任一项 | 这三种方法产生的结果是一样的，这取决于人们的喜好。 |

{style="table-layout:auto"}

### 范围设置如何影响数据馈送 {#scope-settings}

“日期数学”、“去重”、“下一个”或“上一个”以及“摘要”都取决于“事件”、“会话”或“人员”的&#x200B;[!UICONTROL **范围**]&#x200B;设置（可用选项因函数而异）。 深度没有可配置的范围字段，但本质上与会话关联，类似于标准的事件深度维度。 具有范围的任何字段都会将相同的值写入该范围内的每行，该值取决于回顾日期范围内的数据。
<!-- Open question as of 2026-09-09: is the lookback date range boundary anchored to a fixed point (e.g., midnight), or does it float with the feed run time, and is this configurable? Pending confirmation from Ron Fulkerson. -->

由于[回顾日期范围](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-lookback-date-range)随每次数据馈送投放向前滑动，因此同一字段可能会在以后的投放中返回不同的值，即使对于已发生的事件。

风险随范围大小而增加：人员范围比会话范围风险更大，因为人员的历史在馈送运行中没有自然时间界限。

## 派生字段函数模板

[派生字段函数模板](/help/data-views/derived-fields/derived-fields.md#templates)允许您为特定用例快速创建派生字段，例如构建营销渠道、检测机器人或从URL提取UTM参数。 由于模板是从预建规则链构建的，因此在SQL中几乎总是最好使用模板来重制相同的逻辑。

如果模板包含依赖于“范围”设置的函数，则模板会继承该函数的范围警告。 请参阅[作用域设置如何影响数据馈送](#scope-settings)。
