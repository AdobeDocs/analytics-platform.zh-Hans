---
description: 解释哪些因素会影响Real-time Customer Data Platform(Real-time CDP)与CJA之间量度和受众成员资格计数的一致性。
title: 实时CDP与CJA之间量度和受众成员资格计数的一致性
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: cf4e2136f5ab4e0ed702820e52e9a62ea8251860
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 0%

---


# 实时CDP与CJA之间量度和受众成员资格计数的一致性

在现实场景中，无法保证Real-time Customer Data Platform（实时CDP）和Customer Journey Analytics(CJA)中量度和受众成员资格计数的一致性。 本文档解释了原因。

## 身份配置的差异

Real-time CDP和CJA当前对人员的定义不相同。 Real-time CDP完全依赖 [身份图](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=en) 来构建合并的配置文件。

CJA可配置为使用 [跨渠道分析](/help/connections/cca/overview.md) 它会从数据湖中的数据集提取标识符，并应用自定义逻辑将它们链接在一起。
将来，CJA将能够使用身份图。

## 数据集配置的差异

您可以选择在Real-time CDP中放置一些数据，在CJA中放置一些数据；通常，客户会选择在CJA中放置比与实时CDP相关的更多历史数据。 与CJA相比，其他数据集可能与Real-time CDP更相关。

## 处理配置的差异

CJA允许在查询时对数据进行大量修改，如组合字段、拆分字段以及其他操作（如包含/排除、子字符串、重复值消除、会话化和行级过滤）。

Real-time CDP提供了一组不同的数据操作工具。 它适用 [合并策略](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) 确定哪些数据具有优先级，哪些数据将被合并以创建人员的统一视图。

## TTL（存留期）和数据获取方面的差异

即使Real-time CDP和CJA中的数据集相同， Real-time CDP也只能保留非常有限的历史记录窗口。 相比之下，CJA公司可能拥有多年的数据。 此外:

* CJA和Real-time CDP客户可以为数据设置自定义保留窗口，这两个窗口彼此独立。

* 实时CDP和CJA在摄取数据时具有不同的逻辑。 CJA会忽略没有人员ID或时间戳的记录，并对单个用户档案/人员可能拥有的记录数量有严格限制。

* 实时CDP客户可以在湖中访问7天的数据，这主要是为了方便数据载入到用户档案中以及进行临时查询。

* 对于CJA客户，湖中的数据没有TTL。 但是，CJA用户在创建连接时，自己可以在CJA中设置自定义保留窗口。

* Real-time CDP中的配置文件存储允许客户可配置的TTL。 客户可以将此TTL更改为需要保留在其许可证授权内的任何TTL。

## 数据获取滞后的差异

CJa尚未具备实时CDP的实时功能，因此，CJA报表会在数据可用于报表或创建受众之前存在一些延迟。 Real-time CDP通过具有不同滞后的不同系统处理数据。
