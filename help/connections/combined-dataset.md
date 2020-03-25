---
title: 组合的数据集
description: 了解CJA如何通过组合数据集创建连接。
translation-type: tm+mt
source-git-commit: f9cdcb8a6efe688d553929c3081f3239e0691cd9

---


# 组合的数据集

创建连接时，CJA会将所有模式和数据集合到一个数据集中。 此“组合数据集”是CJA用于报告的。 在连接中包含多个模式或数据集时：

* 模式被合并。 重复模式字段将合并。
* 每个数据集的“人员ID”列将合并到一个列中，而不管其名称如何。 此列是识别CJA中唯一访客的基础。
* 根据时间戳处理行。

## 示例

请考虑以下示例。 您有两个数据集，每个数据集的字段都包含不同的数据。

> [!NOTE] Adobe Experience Platform通常以Unix毫秒为单位存储时间戳。 为了在此示例中实现可读性，使用日期和时间。

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |
| `user_310` | `1 Jan 7:04 AM` |  |  | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  | `3` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` |  |  | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  | `Triangle` | `3.1` |

使用这两个数据集创建连接时，将使用下表进行报告。

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |  |  |
| `user_310` | `1 Jan 7:04 AM` |  |  |  | `2` |  |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  |  | `3` |  |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` |  | `Circle` |  | `8.5` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` |  | `4` |  |
| `user_847` | `2 Jan 12:44 PM` |  |  |  | `2` |  |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` |  | `Square` |  | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  |  | `Triangle` |  | `3.1` |

此组合数据集是报告中使用的。 不管哪个数据集来自哪个行；CJA将所有数据视为位于同一数据集中。 如果两个数据集中都显示了匹配的人员ID，则它们被视为相同的唯一访客。 如果在30分钟内在两个数据集中都显示了匹配的人员ID，则这些人员ID将被视为同一会话的一部分。

此概念也适用于归因。 不管哪个数据集来自哪个行；归因的工作方式与所有事件来自单个数据集完全一样。 以上表为例：

如果连接仅包含第一个表而不包含第二个表，则使用最近联系归因的维度和 `string_color` 度量 `metric_a` 拉取报表将显示：

| string_color | metric_a |
| --- | --- |
| 蓝色 | 5 |
| 未指定 | 6 |
| 红色 | 2 |

但是，如果您在连接中包含两个表，则归因会发生更改，因为这 `user_847` 两个数据集中都有。 从第二个数据集属性到“黄色” `metric_a` 的一行，之前未指定这些属性：

| string_color | metric_a |
| --- | --- |
| 黄色 | 6 |
| 红色 | 2 |
| 蓝色 | 3 |
