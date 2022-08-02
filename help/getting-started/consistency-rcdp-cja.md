---
description: 解释了哪些因素会影响 Real-time Customer Data Platform (Real-Time CDP) 和 CJA 之间量度和受众会员计数的一致性。
title: Real-Time CDP 和 CJA 之间量度和受众会员计数的一致性
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 769eef205df32865874753859ce79e573db40641
workflow-type: ht
source-wordcount: '577'
ht-degree: 100%

---


# Real-Time CDP 和 CJA 之间量度和受众会员计数的一致性

在现实情景中，无法保证跨 Real-time Customer Data Platform (Real-time CDP) 和 Customer Journey Analytics (CJA) 的量度和受众会员计数的一致性。本文档解释了原因。

在比较 Real-time CDP 和 CJA 之间的受众会员计数时，重要的是要记住这两种工具的不同用途。 Real-time CDP 使用客户档案数据将数字体验客户定位于个人消费者，而 CJA 旨在帮助用户了解关键业务量度和区段中的模式。 虽然受众从 CJA 发布到 Real-time CDP 允许这些工具的用户轻松地在本地“激活”洞察，利用在 CJA 中获得的知识，但这些工具的用途完全不同。

## 身份配置的差异

Real-time CDP 和 CJA 现在对个人的定义不同。 Real-time CDP 完全依赖于[身份图](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=zh-Hans)中的信息来构建合并的用户档案。

CJA 可以通过配置使用 [跨通道 Analytics](/help/connections/cca/overview.md)，从数据湖中的数据集提取标识符，并应用自定义逻辑将它们链接在一起。

未来，CJA 将能够使用身份图。

## 数据集配置的差异

您可以选择将一些数据放在 Real-time CDP 中，另一些放在 CJA 中；通常，客户选择在 CJA 中输入的历史数据比 Real-time CDP 中的数据更多。 相比 CJA，其他数据集可能与 Real-time CDP 更相关。

## 处理配置的差异

CJA 允许在查询时进行广泛的数据修改，例如组合字段、拆分字段以及其他操作，如包含/排除、子字符串、重复值消除、会话和行级过滤。

Real-time CDP 提供了一套不同的数据操作工具。 它应用[合并策略](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=zh-Hans)来确定哪些数据将被优先处理，哪些数据将合并以创建个人的统一视图。

## TTL（生存时间）和数据摄取的差异

即使 Real-time CDP 和 CJA 中的数据集相同， Real-time CDP 可能只保留非常有限的历史窗口。 相比之下，CJA 可能拥有多年的数据。 此外：

* CJA 和 Real-time CDP 客户可以相互独立地为数据设置自定义保留窗口。

* Real-time CDP 和 CJA 具有不同的数据社区逻辑。 CJA 忽略没有个人 ID 或时间戳的记录，并对单个用户档案/个人可能拥有的记录数量有严格限制。

* Real-time CDP 客户可以在 7 天内访问湖中的数据，主要是为了方便将数据载入用户档案和进行特别查询。

* 对于 CJA 客户，湖中的数据没有 TTL。 但是，CJA 用户可以在创建连接时自己在 CJA 中设置自定义保留窗口。

* Real-time CDP 中的用户档案存储允许客户配置 TTL。 客户可以将此 TTL 更改为他们所需的任何内容，以保持其许可权利。

## 数据摄取延迟的差异

CJA 尚不具备 Real-time CDP 的实时能力，因此，CJA 报告在数据可用于报告或受众创建之前存在一定的延迟。 Real-time CDP 通过具有不同延迟的不同系统处理数据。
