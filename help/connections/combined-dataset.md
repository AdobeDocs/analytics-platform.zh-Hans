---
title: 合并事件数据集
description: 了解Customer Journey Analytics如何通过组合数据集来创建连接。
exl-id: 9f678225-a9f3-4134-be38-924b8de8d57f
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 3389c141105ff71ed26abe4384fe3bb930448d43
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 35%

---


# 合并事件数据集

创建连接时，Customer Journey Analytics会将所有事件数据集合并为一个数据集。 此组合的事件数据集是Customer Journey Analytics用于报告的（与配置文件和查找数据集一起）。 在连接中包含多个事件数据集时：

* 基于以下项的数据集中字段的数据 **相同的架构路径** 合并到合并数据集中的一列。
* 为每个数据集指定的“人员ID”列合并为合并数据集中的一列， **不管他们的名字**. 此栏是确定Customer Journey Analytics中独特人物的基础。
* 根据时间戳处理各行。
* 事件被解析到毫秒级别。

## 示例

请仔细研究下面的示例。您有两个事件数据集，每一个都有包含不同数据的不同字段。

>[!NOTE]
>
>Adobe Experience Platform通常以UNIX®毫秒为单位存储时间戳。 为了便于阅读，本示例使用了日期和时间。

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

当您使用这两个事件数据集创建连接时，已确定

* `example_id` 作为第一个数据集的个人ID，以及
* `different_id` 作为第二个数据集的个人ID，

以下组合数据集用于报告。

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

要说明架构路径的重要性，请考虑此方案。 在第一个数据集中， `string_color` 基于架构路径 `_experience.whatever.string_color` 在架构路径上的第二个数据集中  `_experience.somethingelse.string_color`. 在此方案中，数据是 **not** 合并到生成的合并数据集中的一列。 结果却是 `string_color` 组合数据集中的列。

此合并事件数据集就是报表中使用的数据集。行来自哪个数据集并不重要。 Customer Journey Analytics处理所有数据的方式就好像它位于同一数据集中。 如果两个数据集中都出现匹配的人员ID，则认为这两个数据集是同一个唯一的人员。 如果匹配的人员ID出现在两个数据集中，且时间戳在30分钟内，则它们被视为同一会话的一部分。 合并具有相同架构路径的字段。

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

>[!NOTE]
>
>如果合并字段是连接中一个事件数据集的查找关键字，则关联的查找数据集将丰富 *全部* 字段的值。 行来自哪个事件数据集并不重要，因为查找关系与共享架构路径相关联。

## 跨渠道分析

下一级合并数据集是跨渠道分析，其中基于公共标识符（人物ID）合并来自不同渠道的数据集。 跨渠道分析可从拼接功能中获益，允许您重新设置数据集个人ID的密钥，以便正确更新数据集，实现多个数据集的无缝组合。 正在拼接查看已验证和未验证会话中的用户数据，以生成已拼接的ID。

跨渠道分析允许您回答以下问题：

* 有多少人在一个渠道开始体验，然后在另一个渠道结束体验？
* 有多少人与我的品牌互动？他们使用多少台设备？设备的类型如何？这些设备如何进行交叠？
* 出现下面这种情况的频率是多少：人们先是在移动设备上开启一项任务，随后为了完成该任务而移至桌面 PC？营销活动在某一台设备上进行的点进是否会导致转换到其他地方？
* 如果我考虑跨设备旅程，我对营销活动效果的理解会发生什么变化？ 我的漏斗分析会有怎样的变化？
* 用户从一台设备转到另一台设备时最常用的路径是什么？他们在哪里退出？他们在哪里继续？
* 使用多台设备的用户，其行为与使用单台设备的用户有何区别？


有关跨渠道分析的更多信息，请参阅特定的用例：

* [跨渠道分析](../use-cases/cross-channel/cross-channel.md)

有关拼接功能的更深入讨论，请访问：

* [拼接概述](/help/stitching/overview.md)
* [常见问题解答](/help/stitching/faq.md)

