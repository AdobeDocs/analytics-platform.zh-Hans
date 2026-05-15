---
description: 解释了哪些因素会影响 Real-time Customer Data Platform (Real-Time CDP) 和 Customer Journey Analytics 之间量度和受众会员计数的一致性。
title: 指标和受众会员资格的一致性
role: Admin
feature: Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
TQID: https://experienceleague.adobe.com/IYlFUArrqejRjs5uDJ0MNGixQG4IP6ly4qLQBMALCjA
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 671
ht-degree: 100%

---

# 指标和受众会员资格的一致性

在现实情景中，无法保证跨 Real-time Customer Data Platform（Real-time CDP）和 Customer Journey Analytics 的量度和受众会员计数的一致性。 本文档解释了原因。

在比较 Real-time CDP 和 Customer Journey Analytics 之间的受众会员计数时，重要的是要记住这两种工具的不同用途。 Real-time CDP 使用客户轮廓数据将数字体验客户锁定于个人消费者，而 Customer Journey Analytics 旨在帮助用户了解关键业务量度和区段中的模式。 虽然受众从 Customer Journey Analytics 发布到 Real-time CDP 允许这些工具的用户轻松地在本地“激活”洞察，利用在 Customer Journey Analytics 中获得的知识，但这些工具的用途完全不同。

## 身份标识配置的差异

Real-time CDP 和 Customer Journey Analytics 现在对个人的定义不同。 Real-time CDP 完全依赖于[身份标识图](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html)中的信息来构建合并的轮廓。

可以将 Customer Journey Analytics 配置为使用 [拼接](../stitching/overview.md)。 如果您使用[基于字段的拼接](/help/stitching/fbs.md)作为拼接机制，可从数据湖中的某个数据集中指定一个标识符，以拼接并提升该数据集的合并轮廓质量。 如果您使用[基于图形的拼接](/help/stitching/gbs.md)作为拼接机制，则会基于指定的身份标识命名空间，利用身份标识图执行类似的处理流程。


## 数据集配置的差异

您可以选择将一些数据放在 Real-time CDP 中，另一些放在 Customer Journey Analytics 中；通常，客户选择在 Customer Journey Analytics 中输入的历史数据比 Real-time CDP 中的数据更多。 相比 Customer Journey Analytics，其他数据集可能与 Real-time CDP 更相关。

## 处理配置的差异

Customer Journey Analytics 允许在查询时进行广泛的数据修改，例如组合字段、拆分字段以及其他操作，如包含/排除、子字符串、重复值消除、会话和行级过滤。

Real-time CDP 提供了一套不同的数据操作工具。 它应用[合并策略](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html)来确定哪些数据将被优先处理，哪些数据将合并以创建个人的统一视图。

## TTL（生存时间）和数据摄取的差异

即使 Real-time CDP 和 Customer Journey Analytics 中的数据集相同，Real-time CDP 可能只保留非常有限的历史窗口。 相比之下，Customer Journey Analytics 可能拥有多年的数据。 此外：

* Customer Journey Analytics 和 Real-time CDP 客户可以相互独立地为数据设置自定义保留窗口。

* Real-time CDP 和 Customer Journey Analytics 具有不同的数据提取逻辑。 Customer Journey Analytics 忽略没有人员 ID 或时间戳的记录，并对单个轮廓/个人可能拥有的记录数量有严格限制。

* Real-time CDP 客户可以在 7 天内访问湖中的数据，主要是为了方便将数据载入轮廓和进行特别查询。

* 对于 Customer Journey Analytics 客户，湖中的数据没有 TTL。 但是，Customer Journey Analytics 用户可以在创建连接时在 Customer Journey Analytics 中设置自定义保留窗口。

* Real-time CDP 中的用户轮廓存储允许客户配置 TTL。 客户可以将此 TTL 更改为他们所需的任何内容，以保持其许可权利。

## 数据摄取延迟的差异

Customer Journey Analytics 尚不具备 Real-time CDP 的实时能力，因此，Customer Journey Analytics 报告在数据可用于报告或受众创建之前存在一定的延迟。 Real-time CDP 通过各种具有不同延迟的系统来处理数据。
