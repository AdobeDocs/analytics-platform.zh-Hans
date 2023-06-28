---
title: 合并事件数据集
description: 了解Customer Journey Analytics如何通过组合数据集创建连接。
exl-id: 9f678225-a9f3-4134-be38-924b8de8d57f
solution: Customer Journey Analytics
feature: Connections
source-git-commit: cf6da1f126933f17e05fb458f52dff93c1601891
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 61%

---


# 合并事件数据集

创建连接时，Customer Journey Analytics会将所有架构和数据集合并到单个数据集中。 此“合并事件数据集”是Customer Journey Analytics用于报表的数据集。 如果您将多个架构或数据集纳入单个连接，则：

* 架构会被合并。重复架构字段会被合并。
* 每个数据集的“人员 ID”列将合并到单列中，无论其名称如何。此列是识别Customer Journey Analytics中独特人员的基础。
* 根据时间戳处理各行。
* 事件被解析到毫秒级别。

## 示例

请仔细研究下面的示例。您有两个事件数据集，每一个都有包含不同数据的不同字段。

>[!NOTE]
>
>Adobe Experience Platform 通常以 Unix 毫秒为单位存储时间戳。为了便于阅读和理解，本示例中使用了日期和时间。

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` | |
| `user_310` | `1 Jan 7:04 AM` | | | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` | | `3` |
| `user_847` | `2 Jan 12:31 PM` | | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` | | | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` | | |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` | | `Triangle` | `3.1` |

使用这两个事件数据集创建连接时，将使用下表进行报告。

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` | | | |
| `user_310` | `1 Jan 7:04 AM` | | | | `2` | |
| `user_310` | `1 Jan 7:08 AM` | `Blue` | | | `3` | |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | | `Circle` | | `8.5` |
| `user_847` | `2 Jan 12:31 PM` | | `Turtle` | | `4` | |
| `user_847` | `2 Jan 12:44 PM` | | | | `2` | |
| `user_847` | `2 Jan 1:01 PM` | `Red` | | | | |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | | `Square` | | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` | | | `Triangle` | | `3.1` |

此合并事件数据集就是报表中使用的数据集。不管某行来自哪个数据集，Customer Journey Analytics将所有数据视为位于同一数据集中。 如果两个数据集中都出现匹配的人员ID，则它们被视为同一个唯一人员。 如果两个包含时间戳（30 分钟内）都出现了匹配的人员 ID，则它们被视为属于同一个会话。

这种概念也适用于归因。不管某行数据源自哪个数据集，归因会像所有事件均源自单个数据集来进行处理。以上表为例：

如果您的连接仅包含第一个表而不包含第二个表，则在采用使用最后接触归因的 `string_color` 维度和 `metric_a` 量度来提取报表时将会显示：

| string_color | metric_a |
| --- | --- |
| 未指定 | 6 |
| 蓝色 | 3 |
| 红色 | 2 |

但是，如果连接中同时包含两个表，则归因会发生更改，因为两个数据集中都有 `user_847`。第二个数据集中的某行将 `metric_a` 归因为“黄色”，也就是之前的“未指定”：

| string_color | metric_a |
| --- | --- |
| 黄色 | 6 |
| 蓝色 | 3 |
| 红色 | 2 |

## 跨渠道分析

合并数据集的下一个级别是跨渠道分析，其中基于通用标识符（人员ID）合并来自不同渠道的数据集。 跨渠道分析可从拼接功能中获益，允许您重新生成数据集的人员ID键值，以便正确更新数据集，实现多个数据集的无缝拼合。 拼接查看来自经过身份验证和未经身份验证的会话的用户数据，以生成拼接ID。

跨渠道分析允许您回答以下问题：

* 有多少人在一个渠道开始体验，然后在另一个渠道结束体验？
* 有多少人与我的品牌互动？他们使用多少台设备？设备的类型如何？这些设备如何进行交叠？
* 出现下面这种情况的频率是多少：人们先是在移动设备上开启一项任务，随后为了完成该任务而移至桌面 PC？登陆一台设备后执行的营销活动点进次数是否会导致在其他设备上的转化？
* 如果考虑跨设备历程，我对营销活动效用的理解会有怎样的变化？ 我的漏斗分析会有怎样的变化？
* 用户从一台设备转到另一台设备时最常用的路径是什么？他们在哪里退出？他们在哪里继续？
* 使用多台设备的用户，其行为与使用单台设备的用户有何区别？


有关跨渠道分析的更多信息，请参阅特定用例：

* [跨渠道分析](../use-cases/cross-channel/cross-channel.md)

有关更深入的讨论拼合功能，请转到：

* [拼接概述](/help/stitching/overview.md)
* [拼合的工作原理](../stitching/explained.md)
* [常见问题解答](/help/stitching/faq.md)

