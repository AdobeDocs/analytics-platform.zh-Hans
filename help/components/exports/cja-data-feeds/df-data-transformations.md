---
title: 将数据转换应用于数据馈送
description: 了解使用组件设置、派生字段或SQL转换数据馈送数据的不同方法。
hide: true
feature: Components
source-git-commit: 3203774ba463c070783125e0b02ef8c391f46308
workflow-type: tm+mt
source-wordcount: '1693'
ht-degree: 5%
---
# 将数据转换应用于数据馈送

{{release-limited-testing}}

您可以使用以下任一方法转换数据馈送数据：

* [数据视图组件设置](/help/data-views/component-settings/overview.md)

* [派生字段](/help/data-views/derived-fields/derived-fields.md)

* SQL

每种方法都有各自的优缺点。 以下各节比较了常规转换和特定转换之间的权衡。

## 一般比较数据转换方法

下表比较了每种方法的一般优缺点。

| 方法 | 优点 | 缺点 |
| --- | --- | --- |
| **组件设置** | <ul><li>在提交数据馈送之前在报告时应用。</li><li>在Analysis Workspace和数据馈送输出中，相同的逻辑始终适用。</li><li>不使用您帐户中有限的某个派生字段。</li><li>您可以使用的组件设置数量没有限制。</li><li>增加了处理开销，这可能会影响数据馈送提交性能</li></ul> | <ul><li>仅适用于每个组件支持的特定设置集。 没有使用派生字段构建自定义逻辑那么灵活。</li></ul> |
| **派生字段** | <ul><li>在提交数据馈送之前在报告时应用。</li><li>在Analysis Workspace和数据馈送输出中，相同的逻辑始终适用。</li><li>与任何单个组件设置（如链接条件规则）相比，支持更灵活的自定义逻辑。</li><li>某些转换，特别是那些依赖范围设置或解析URL的转换很难在SQL中复制。</li><li>增加了处理开销，这可能会影响数据馈送提交性能</li></ul> | <ul><li>增加了处理开销，这可能会影响数据馈送提交性能。<!--Under a future usage-based pricing model, this could also add cost.--></li><li>使用您帐户中有限的派生字段之一。 如果组件设置可以执行相同的转换，请改用它。</li></ul> |
| **SQL** | <ul><li>不受适用于派生字段的函数和运算符限制限制。</li><li>对数据馈送提交性能没有影响。</li></ul> | <ul><li>已在提交数据馈送后应用。</li><li>逻辑在Analysis Workspace中并不适用，因此您需要在该处单独复制逻辑。</li><li>某些转换很难复制或不切实际，特别是那些依赖范围设置、解析URL或跨范围消除重复或保留值的转换。</li></ul> |

{style="table-layout:auto"}

## 按转换类型比较数据转换方法

下表列出了特定的数据转换，显示了哪些方法（或方法）可以执行每一种转换，在SQL中复制的困难程度，以及建议使用的方法。<!--A few transformations are still being confirmed with the engineering team and are marked as open questions — don't treat those as confirmed to affect data feed output until that's resolved.-->

| 转换 | 组件设置（在CJA中） | 派生字段（在CJA中） | 推荐的方法（在CJA中） | SQL中的困难 | 注意事项 |
| --- | --- | --- | --- | --- | --- |
| **应用条件逻辑或按条件筛选值** | [包括排除值](/help/data-views/component-settings/include-exclude-values.md) | [案例时间](/help/data-views/derived-fields/derived-fields.md#casewhen) | 组件设置<p>建议这样做，因为它不占用您有限的派生字段之一。</p> | 轻松处理字符串<p>量度的难度适中（需要`CASE`语句与`COUNT`组合）</p> | |
| 成功事件的&#x200B;**属性点数** | [归因](/help/data-views/component-settings/attribution.md) | 不可用 | 组件设置 | 不适用 | 仅适用于数据馈送中的维度。 对于量度，没有要复制的数据馈送行为。 |
| **将数值装入范围** | [值分段](/help/data-views/component-settings/value-bucketing.md) | 手动[案例条件](/help/data-views/derived-fields/derived-fields.md#casewhen) | 组件设置<p>推荐使用，因为它不会占用您有限的派生字段之一。</p> | 困难 | 从组件设置（最简单）到派生字段（一般，使用手动Case When），复杂性增加到了SQL（最复杂）。 |
| **使用查找样式映射对值进行分类** | 不可用 | [分类](/help/data-views/derived-fields/derived-fields.md#classify) | 派生字段 <p>之所以推荐，是因为相同的逻辑始终适用于Analysis Workspace和数据馈送输出。</p> | 简单/适中 | |
| **将字段值与分隔符组合** | 不可用 | [连接](/help/data-views/derived-fields/derived-fields.md#concatenate) | 派生字段<p>之所以推荐，是因为相同的逻辑始终适用于Analysis Workspace和数据馈送输出。</p> | 简单/适中 | 镜像将多个维度列添加到自由格式表的功能，该功能限制为完全表导出。 派生字段使类似输出可在数据馈送中使用。 |
| **转换字段的数据类型** | 不可用 | [类型](/help/data-views/derived-fields/derived-fields.md#typecast) | 派生字段<p>之所以推荐，是因为相同的逻辑始终适用于Analysis Workspace和数据馈送输出。</p> | 简单/适中 | |
| **计数量度发生次数（值与实例数）** | [行为](/help/data-views/component-settings/behavior.md) | 自定义基于数学的解决方法 | 组件设置<p>推荐原因：</p><ul><li>相同的逻辑在Analysis Workspace和数据馈送输出中始终如一地适用（对于SQL则不可能）</li><li>它不会占用您有限的派生字段之一。</li></ul> | 简单/适中 | |
| **在作用域内删除重复值** | [重复量度删除](/help/data-views/component-settings/metric-deduplication.md) | [删除重复项](/help/data-views/derived-fields/derived-fields.md#dedup) | 组件设置<p>建议这样做，因为它不占用您有限的派生字段之一。</p> | 困难 | 取决于范围设置。 请参阅[作用域设置如何影响数据馈送](#scope-settings)。 |
| **确定会话中的字段深度** | 不可用 | [深度](/help/data-views/derived-fields/derived-fields.md#depth) | 派生字段<p>为便于使用，建议这样做，因为相同的逻辑在Analysis Workspace和数据馈送输出中始终适用。</p> | 困难 | <!-- Open question as of 2026-09-09: does the Depth counter carry over across an hourly/daily feed boundary using lookback-window context, or does it restart? Pending confirmation from engineering (Ron Fulkerson / Nate Purser). How the counter behaves when a session spans a feed-delivery boundary is still being confirmed with engineering. --> <p>取决于范围设置（使用会话作为范围，且不可配置）。 请参阅[作用域设置如何影响数据馈送](#scope-settings)。</p> |
| **查找并替换文本值** | 不可用 | [查找和替换](/help/data-views/derived-fields/derived-fields.md#find-and-replace) | 派生字段<p>为便于使用，建议这样做，因为相同的逻辑在Analysis Workspace和数据馈送输出中始终适用。</p> | 简单/适中 | |
| **设置显示值的格式** | [格式](/help/data-views/component-settings/format.md) | 不可用 | 组件设置<p>为便于使用，建议这样做，因为相同的逻辑在Analysis Workspace和数据馈送输出中始终适用。</p> | 困难 | <!-- Date-time formatting isn't yet reflected in data feed output — feeds currently show the standard timestamp regardless of this setting, though Adobe plans to support this for general availability. Whether numeric formats (decimal, currency, percent) on metrics affect data feed output is still being confirmed with the team.--> |
| **从摘要数据集对维度进行分组** | 不适用 | 不适用 | 不适用 | 不适用 | 摘要数据组仅适用于摘要数据集，这些数据集不用于数据馈送。 此转换不适用于数据馈送输出。 |
| **处理空白（“无值”）字段** | [无值选项](/help/data-views/component-settings/no-value-options.md)<br/>将“无值”视为值&#x200B;**]选项适用于数据馈送，而默认情况下[!UICONTROL **&#x200B;不显示“无值”**]和[!UICONTROL **&#x200B;默认情况下显示“无值”**]选项不适用于数据馈送。[!UICONTROL ** | 不可用 | 组件设置 | 不可能 | 所有“没有值”在最终数据馈送输出中都将作为空值返回，而不是作为“没有值”字符串返回。 |
| **从查找数据集中查找值** | 不可用 | [查找](/help/data-views/derived-fields/derived-fields.md#lookup) | 派生字段<p>为便于使用，建议这样做，因为相同的逻辑在Analysis Workspace和数据馈送输出中始终适用。</p> | 简单/适中<p>查询表必须已存在。</p> | |
| **小写字符串** | [行为](/help/data-views/component-settings/behavior.md) | [小写](/help/data-views/derived-fields/derived-fields.md#lowercase) | 组件设置<p>推荐原因：</p><ul><li>相同的逻辑在Analysis Workspace和数据馈送输出中始终如一地适用（对于SQL则不可能）</li><li>它不会占用您有限的派生字段之一。</li></ul> | 简单/适中 | |
| **将多个字段合并为一个** | 不可用 | [合并字段](/help/data-views/derived-fields/derived-fields.md#merge) | 派生字段<p>为便于使用，建议这样做，因为相同的逻辑在Analysis Workspace和数据馈送输出中始终适用。</p> | 简单/适中 | |
| **将URL解析为其组件** | [子字符串](/help/data-views/component-settings/substring.md)（URL解析方法） | [URL分析](/help/data-views/derived-fields/derived-fields.md#urlparse) | 组件设置<p>建议这样做，因为它不占用您有限的派生字段之一。</p> | 困难<p>需要自定义字符串解析以提取相同的组件。</p> | <!-- Possible discrepancy: in the component settings meeting, Matt and Derek described all Substring methods, including URL parse, as roughly interchangeable across component setting, derived field, and SQL ("either one would work... maybe a preference"), which is a looser SQL-difficulty read than "Difficult." Flagged for Luke to reconcile; not changed without confirmation. --> |
| **对数字字段执行基本数学运算** | 不可用 | [数学](/help/data-views/derived-fields/derived-fields.md#math) | 派生字段<p>为便于使用，建议这样做，因为相同的逻辑在Analysis Workspace和数据馈送输出中始终适用。</p> | 简单/适中 | |
| **跨事件保留维度值** | [持久性](/help/data-views/component-settings/persistence.md) | 当前不可用<!-- Derek: considering adding this to FDL and surfacing it in derived fields; not currently possible. --> | 组件设置<p>推荐使用，因为它不会占用您有限的派生字段之一。</p> | 困难 | 与回顾日期范围交互的方式与范围相关的派生字段函数相同。 请参阅[了解回顾日期范围](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-lookback-date-range)。 |
| **使用正则表达式替换值** | [Substring](/help/data-views/component-settings/substring.md) （Regex方法） | [正则表达式替换](/help/data-views/derived-fields/derived-fields.md#regex-replace) | 组件设置<p>所有三种方法都会产生相同的结果，但首选组件设置，因为：</p><ul><li>相同的逻辑在Analysis Workspace和数据馈送输出中始终如一地适用（对于SQL则不可能）</li><li>它不会占用您有限的派生字段之一。</li></ul> | 简单/适中 | |
| **解析会话中的下一个或上一个值** | 不可用 | [下一个或上一个](/help/data-views/derived-fields/derived-fields.md#next-previous) | 派生字段<p>为便于使用，建议这样做，因为相同的逻辑在Analysis Workspace和数据馈送输出中始终适用。</p> | 困难 | 取决于范围设置。 请参阅[作用域设置如何影响数据馈送](#scope-settings)。 |
| **返回两个日期之间的差值** | 不可用 | [日期数学](/help/data-views/derived-fields/derived-fields.md#datemath) | 派生字段<p>为便于使用，建议这样做，因为相同的逻辑在Analysis Workspace和数据馈送输出中始终适用。</p> | 困难 | 取决于范围设置。 请参阅[作用域设置如何影响数据馈送](#scope-settings)。 |
| **将量度的范围设为基于事件、配置文件或总数** | [范围](/help/data-views/component-settings/scope.md) | 不可用 | | | <!--Not yet discussed with the team. Don't assume this affects data feed output until confirmed.--> |
| **拆分分隔值** | [Substring](/help/data-views/component-settings/substring.md) （分隔符或来自左/右方法） | [拆分](/help/data-views/derived-fields/derived-fields.md#split) | 组件设置<p>推荐原因：</p><ul><li>相同的逻辑在Analysis Workspace和数据馈送输出中始终如一地适用（对于SQL则不可能）</li><li>它不会占用您有限的派生字段之一。</li></ul> | 简单/适中 | |
| **汇总或聚合作用域中的值** | 不可用 | [摘要](/help/data-views/derived-fields/derived-fields.md#summarize) | 派生字段<p>为便于使用，建议这样做，因为相同的逻辑在Analysis Workspace和数据馈送输出中始终适用。</p> | 困难 | 取决于范围设置。 请参阅[作用域设置如何影响数据馈送](#scope-settings)。 |
| **从字符串修剪字符** | [Substring](/help/data-views/component-settings/substring.md) （Trim方法） | [修剪](/help/data-views/derived-fields/derived-fields.md#trim) | 组件设置<p>推荐原因：</p><ul><li>相同的逻辑在Analysis Workspace和数据馈送输出中始终如一地适用（对于SQL则不可能）</li><li>它不会占用您有限的派生字段之一。</li></ul> | 简单/适中 | |

{style="table-layout:auto"}

### 范围设置如何影响数据馈送 {#scope-settings}

“日期数学”、“去重”、“下一个”或“上一个”以及“摘要”都取决于“事件”、“会话”或“人员”的&#x200B;[!UICONTROL **范围**]&#x200B;设置（可用选项因函数而异）。 深度没有可配置的范围字段，但本质上与会话关联，类似于标准的事件深度维度。 具有范围的任何字段都会将相同的值写入该范围内的每行，该值取决于回顾日期范围内的数据。
<!-- Open question as of 2026-09-09: is the lookback date range boundary anchored to a fixed point (e.g., midnight), or does it float with the feed run time, and is this configurable? Pending confirmation from Ron Fulkerson. -->

由于[回顾日期范围](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-lookback-date-range)随每次数据馈送投放向前滑动，因此同一字段可能会在以后的投放中返回不同的值，即使对于已发生的事件。

风险随范围大小而增加：人员范围比会话范围风险更大，因为人员的历史在馈送运行中没有自然时间界限。

## 派生字段函数模板

[派生字段函数模板](/help/data-views/derived-fields/derived-fields.md#templates)允许您为特定用例快速创建派生字段，例如构建营销渠道、检测机器人或从URL提取UTM参数。 由于模板是从预建规则链构建的，因此使用模板几乎总是比在SQL中从头开始重现相同的逻辑要好，就像使用`Marketing Channel Template`一样。

如果模板包含依赖于“范围”设置的函数，则模板会继承该函数的范围警告。 请参阅[作用域设置如何影响数据馈送](#scope-settings)。
