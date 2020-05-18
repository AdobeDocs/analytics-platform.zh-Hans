---
title: 组合的数据集
description: 了解 CJA 如何通过组合数据集创建连接。
translation-type: ht
source-git-commit: 2dab33dca173fcc0eab657b810e85e4740e5d7e0

---


# 组合的数据集

创建连接后，CJA 会将所有架构和数据集合到单个数据集中。CJA 将此“组合的数据集”用于报表。如果您将多个架构或数据集纳入单个连接，则：

* 架构会被合并。重复架构字段会被合并。
* 每个数据集的“人员 ID”列将合并到单列中，无论其名称如何。此列是识别 CJA 中唯一访客的基础。
* 根据时间戳处理各行。

## 示例

请仔细研究下面的示例。您有两个数据集，每个数据集具有包含不同数据的不同字段。

>[!NOTE] Adobe Experience Platform 通常以 Unix 毫秒为单位存储时间戳。为了便于阅读和理解，本示例中使用了日期和时间。

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

此合并的数据集就是报表中使用的数据。不管某行数据源自哪个数据集，CJA 会像所有数据均位于同一数据集中一样来处理它们。如果两个数据集中都出现了匹配的人员 ID，则它们被视为相同的唯一访客。如果两个包含时间戳（30 分钟内）都出现了匹配的人员 ID，则它们被视为属于同一个会话。

这种概念也适用于归因。不管某行数据源自哪个数据集，归因会像所有事件均源自单个数据集来进行处理。以上表为例：

如果您的连接仅包含第一个表而不包含第二个表，则在采用使用最后接触归因的 `string_color` 维度和 `metric_a` 量度来提取报表时将会显示：

| string_color | metric_a |
| --- | --- |
| 蓝色 | 5 |
| 未指定 | 6 |
| 红色 | 2 |

但是，如果连接中同时包含两个表，则归因会发生更改，因为两个数据集中都有 `user_847`。第二个数据集中的某行将 `metric_a` 归因为“黄色”，也就是之前的“未指定”：

| string_color | metric_a |
| --- | --- |
| 黄色 | 6 |
| 红色 | 2 |
| 蓝色 | 3 |
