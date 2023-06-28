---
description: 解释哪些因素会影响Real-time Customer Data Platform (Real-time CDP)与Customer Journey Analytics之间量度和受众会员计数的一致性。
title: Real-time CDP与Customer Journey Analytics之间量度和受众会员计数的一致性
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: cf6da1f126933f17e05fb458f52dff93c1601891
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 25%

---


# Real-time CDP与Adobe Customer Journey Analytics之间的量度和受众会员计数的一致性

在真实情景中，无法保证跨Real-time Customer Data Platform (Real-time CDP)和Customer Journey Analytics的量度和受众会员计数的一致性。 本文档解释了原因。

在比较Real-time CDP和Customer Journey Analytics之间的受众会员计数时，必须牢记这两种工具的不同用途。 Real-time CDP使用客户档案数据将数字体验定位到个人消费者，而Customer Journey Analytics旨在帮助用户了解关键业务量度和区段中的模式。 虽然从Customer Journey Analytics到Real-time CDP的受众发布功能允许这些工具的用户利用在Customer Journey Analytics中获得的知识，轻松且原生“激活”洞察，但这些工具的用途完全不同。

## 身份配置的差异

Real-time CDP和Customer Journey Analytics目前对个人的定义不同。 Real-time CDP 完全依赖于[身份图](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=zh-Hans)中的信息来构建合并的用户档案。

可以将Customer Journey Analytics配置为使用 [拼接](../stitching/overview.md) 它会从数据湖中的数据集提取标识符，并应用自定义逻辑将它们链接在一起。

将来，Customer Journey Analytics将能够使用身份图。

## 数据集配置的差异

您可以选择将一些数据放在Real-time CDP中，另一些放在Customer Journey Analytics中；通常，客户选择放在Customer Journey Analytics中的历史数据比Real-time CDP中的要多。 与Customer Journey Analytics相比，其他数据集可能与Real-time CDP更相关。

## 处理配置的差异

Customer Journey Analytics允许在查询时进行广泛的数据修改，例如组合字段、拆分字段以及其他操作，如包含/排除、子字符串、重复值消除、会话和行级过滤。

Real-time CDP 提供了一套不同的数据操作工具。 它应用[合并策略](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=zh-Hans)来确定哪些数据将被优先处理，哪些数据将合并以创建个人的统一视图。

## TTL（生存时间）和数据摄取的差异

即使Real-time CDP和Customer Journey Analytics中的数据集相同，Real-time CDP可能只保留非常有限的历史窗口。 相比之下，Customer Journey Analytics可能拥有多年的数据。 此外：

* Customer Journey Analytics和Real-time CDP客户可以相互独立地为数据设置自定义保留窗口。

* Real-time CDP和Customer Journey Analytics具有不同的数据摄取逻辑。 Customer Journey Analytics会忽略没有个人ID或时间戳的记录，并对单个用户档案/个人可能拥有的记录数量有严格限制。

* Real-time CDP 客户可以在 7 天内访问湖中的数据，主要是为了方便将数据载入用户档案和进行特别查询。

* 对于Customer Journey Analytics客户，湖中的数据没有TTL。 但是，Customer Journey Analytics用户可以在创建连接时自己在Customer Journey Analytics中设置自定义保留窗口。

* Real-time CDP 中的用户档案存储允许客户配置 TTL。 客户可以将此 TTL 更改为他们所需的任何内容，以保持其许可权利。

## 数据摄取延迟的差异

Customer Journey Analytics尚不具备Real-time CDP的实时功能，因此，Customer Journey Analytics报表在数据可用于报表或创建受众之前存在一定的延迟。 Real-time CDP 通过各种具有不同延迟的系统来处理数据。
