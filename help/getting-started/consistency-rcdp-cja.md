---
description: 解释哪些因素会影响Real-time Customer Data Platform(Real-time CDP)与CJA之间量度和受众成员资格计数的一致性。
title: 实时CDP与CJA之间量度和受众成员资格计数的一致性
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 21d51ababeda7fe188fbd42b57ef3baf76d21774
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 2%

---


# 实时CDP与CJA之间量度和受众成员资格计数的一致性

在现实场景中，无法保证Real-time Customer Data Platform（实时CDP）和Customer Journey Analytics(CJA)中量度和受众成员资格计数的一致性。 本文档解释了原因。

## CJA尚未使用身份图

CDP和CJA当前对人员的定义不相同。 CJA尚未使用 [身份图](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hans) 以告知其对人的定义。 Real-time CDP完全依赖身份图中的信息来构建合并的配置文件。

CJA使用名为 [基于字段的拼合](/help/connections/cca/overview.md) 它会从数据湖中的数据集提取标识符，并应用自定义逻辑将它们链接在一起。 预计中期后，CJA将开始利用 [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en) 导出到数据湖，从而允许在实时CDP和CJA中共享身份概念。

>[!IMPORTANT]
>
>使Adobe Experience Platform Identity Service成为所有Adobe Experience Platform应用程序的真实身份源不会自动使各个应用程序的量度保持一致。 请阅读并了解原因。

## 应用程序数据灵活性

Experience Platform不会应用严格的强制措施来将实时客户资料和数据湖之间的数据保持相同。 在中处理数据的一些用例 [实时客户资料](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/profile/profile-overview.html?lang=en) （激活），而其他人则在工作 [数据湖](https://business.adobe.com/blog/basics/data-lake) （报告和查询服务）。

实时CDP客户通常不会将Adobe Experience Platform数据湖中100%的数据放入用户档案。 这是特意设计的 — 客户应专门在湖中为用户档案启用数据。 CJA允许数据分析人员自由选择要从数据湖引入哪些数据进行分析，而与实时CDP的功能无关。

## 特定于应用程序的修饰符

CJA允许在查询时对数据进行大量修改，如组合字段、拆分字段以及其他操作（如货币转换、重复值消除、会话化和行级过滤）。 这些功能对CDP不可用。

同样， Real-time CDP也适用 [合并策略](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) 确定哪些数据具有优先级，哪些数据将被合并以创建人员的统一视图。 这些配置牢牢地位于每个应用程序的逻辑内，不会共享。

## 读取时间行为与写入时间行为

Real-time CDP需要使用最新ID图形进行时间点配置文件拼合。

* Real-time CDP旨在实时组合用户档案信息以进行激活。

* 它可以实时容纳对给定用户的设置标识符的所有更改。

* 回顾窗口由区段定义控制。

CJA要求使用ID图表导出在写入时拼合数据。

* CJA在数据准备好进行分析之前，会应用复杂的预处理步骤，如索引、共享和分组。

* 给定用户的人员标识符是预处理阶段的关键输入；之后更改人员标识符会产生重大的重新处理成本。

* 回顾窗口在应用程序级别进行控制。

## TTL（存留期）和数据获取方面的差异

即使Real-time CDP和CJA中的数据集相同， Real-time CDP也只能保留非常有限的历史记录窗口。 相比之下，CJA公司可能拥有多年的数据。 此外:

* CJA和Real-time CDP客户可以为数据设置自定义保留窗口，这两个窗口彼此独立。

* 实时CDP和CJA在摄取数据时具有不同的逻辑。 CJA会忽略没有人员ID或时间戳的记录，并对单个用户档案/人员可能拥有的记录数量有严格限制。

* 实时CDP客户可以在湖中访问7天的数据，这主要是为了方便数据载入到用户档案中以及进行临时查询。

* 对于CJA客户，湖中的数据没有TTL。 但是，CJA用户在创建连接时，自己可以在CJA中设置自定义保留窗口。

* Real-time CDP中的配置文件存储允许客户可配置的TTL。 客户可以将此TTL更改为需要保留在其许可证授权内的任何TTL。

## GDPR（《通用数据保护条例》）处理方法的差异

跨实时CDP和数据湖的GDPR和数据卫生的数据处理逻辑存在很大差异。 我们正在努力采取一种单一的方法。

## 数据获取滞后的差异

CJA报表在数据可用于报表或创建受众之前会存在一些延迟。 Real-time CDP通过具有不同滞后的不同系统处理数据。
