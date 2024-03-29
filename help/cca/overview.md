---
title: 跨渠道分析概述
description: 在多个数据集中重新生成人员 ID 的键值，以对人员进行拼接。
exl-id: 69763313-de27-4487-8e32-8277f1f693d8
solution: Customer Journey Analytics
hide: true
hidefromtoc: true
source-git-commit: bfaf76fa5f225e9aa3153fc4ee10c5be8f3164e7
workflow-type: ht
source-wordcount: '1159'
ht-degree: 100%

---


# 跨渠道分析概述

**历程 IQ：跨渠道分析**&#x200B;功能允许重新生成数据集的人员 ID 键值，从而实现多个数据集的无缝拼接。CCA 将同时考虑来自经过身份验证和未经身份验证的会话的用户数据，以生成拼接 ID。通过使用跨渠道分析，您可以回答类似下面的问题：

* 有多少人在一个渠道开始体验，然后在另一个渠道结束体验？
* 有多少人与我的品牌互动？他们使用多少台设备？设备的类型如何？这些设备如何进行交叠？
* 出现下面这种情况的频率是多少：人们先是在移动设备上开启一项任务，随后为了完成该任务而移至桌面 PC？登陆一台设备后执行的营销活动点进次数是否会导致转换到其他设备上？
* 如果考虑跨设备历程，我对营销活动效用的理解会有怎样的变化？我的漏斗分析会有怎样的变化？
* 用户从一台设备转到另一台设备时最常用的路径是什么？他们在哪里退出？他们在哪里继续？
* 使用多台设备的用户，其行为与使用单台设备的用户有何区别？

当您合并具有相似人员 ID 的数据集时，将跨设备和渠道进行归因。例如，用户首先通过台式计算机上的广告访问了您的网站。该用户在下单时遇到了问题，随后致电客服团队以请求其帮助解决此问题。通过跨渠道分析，您可以将呼叫中心事件归因于最初点击的广告。

## 前提条件

>[!IMPORTANT]
>
>如果未能满足所有前提条件，可能会导致无法创建 CCA 连接，或导致合并数据集的效果不佳。

在使用跨渠道分析之前，请确保贵组织已做好以下准备：

* Adobe Experience Platform 中必须有一个数据集具有以下两个用于标识人员的列：
   * **持久 ID**，即每行都存在的标识符。例如，由 Adobe Analytics AppMeasurement 库生成的个人 ID。
   * **临时 ID**，即仅在部分行存在的标识符。例如，通过身份验证的人员的经过哈希处理的用户名或电子邮件地址。实际上，您可以使用任何想要使用的标识符，但前提是该标识符与给定的永久 ID 至少有一次存在于同一事件。
* 还要具有每行都包含临时 ID 的另外一个数据集，如呼叫中心数据。此人员 ID 必须与另一个数据集中的临时 ID 采用相似的格式。
* 此功能允许您同时拼接包含经过身份验证的用户数据和未经身份验证的用户数据的数据集。在合并数据集之前，请确保遵守任何适用的法律和法规，包括获取必要的最终用户权限。

## 限制

>[!IMPORTANT]
>
>对全局事件数据集架构的任何更改还必须应用到新拼接的数据集架构中，否则这会断开拼接的数据集。
>
>此外，如果移除源数据集，缝合的数据集将停止处理并被系统移除。

跨渠道分析是一项具有突破性的强大功能，但其使用方式存在限制。

* 当前，重新生成键值功能只能执行一步（即将永久 ID 转换为临时 ID）。而不支持多步重新生成键值功能（例如，将永久 ID 转换为临时 ID，然后再转换为另一个临时 ID）。
* 仅支持事件数据集。不支持其他数据集，例如查找数据集。
* 不支持在组织中使用的自定义 ID 映射。
* 不支持跨设备专用图。
* 跨渠道 Analytics 不以任何方式转换用于拼接的字段。基于字段的拼接使用存在于数据湖内非拼接数据集中的指定字段中的值。拼接过程区分大小写。例如，如果字段中有时出现“Bob”一词，有时出现“BOB”一词，则将这两个词视为单独的两人。
* 由于基于字段的拼接区分大小写，对于通过 Analytics Source Connector 生成的分析数据集来说，Adobe 建议审查适用于临时 ID 字段的任何 VISTA 规则或处理规则，以确保这些规则都不会引入相同 ID 的新形式。例如，对于部分事件，您应确保没有任何 VISTA 或处理规则将小写字母引入到临时 ID 字段。
* 基于字段的拼接不组合或连接字段。
* 临时 ID 字段应仅包含一种类型的 ID（即 ID 仅来自一个命名空间）。例如，临时 ID 字段不应包含登录 ID 和电子邮件 ID 的组合。
* 如果对于同一持久 ID 发生了多个具有同一时间戳的事件，但临时 ID 字段中有多个不同的值，则基于字段的拼接将根据字母顺序进行选择。因此，如果持久 ID A 具有时间戳相同的两个事件，其中一个事件指定 Bob，而另一个指定 Ann，则基于字段的拼接将选择 Ann。
* 如果一台设备由多人共享，且用户之间的转换总数超过 50.000，CCA 将停止为该设备缝合数据。

## 启用跨渠道分析

如果贵组织满足所有前提条件并已了解跨渠道分析存在的限制，便可按照以下步骤在 Customer Journey Analytics 中开始使用该功能。

1. 将所需数据导入 Adobe Experience Platform。有关 Adobe Analytics 数据，请查阅[在 Customer Journey Analytics 中使用 Adobe Analytics 报告包](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)。有关其他类型的数据，请参阅 Adobe Experience Platform 文档中的[创建模式](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hans)和[摄取数据](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=zh-Hans)。
1. 请联系 Adobe 客户支持并提供以下信息：
   * 启用跨渠道分析的请求
   * 要重新生成键值的数据集的数据集 ID
   * 所需数据集的“永久 ID”列名称（每行都显示的标识符）
   * 所需数据集的“临时 ID”列名称（数据集之间的人员标识符关联）
   * 您的[重播](replay.md)频率和回顾时间范围首选项。选项包括每周重放一次且回看时段为 7 天或每天重放一次且回看时段为 1 天
   * 沙盒名称。
1. Adobe 客户支持将与 Adobe 工程部门合作，在收到您的请求时启用跨渠道分析。一旦启用，Adobe Experience Platform 中就会出现一个更新了密钥的新数据集，其中包含新的人员 ID 列。Adobe 客户支持可以提供新的数据集 ID 和人员 ID 列名。
1. 首次开启后，Adobe 将提供拼接数据的回填，最远可追溯到上月初（最多 60 天）。为进行此回填，当时的非拼接数据中必须存在临时 ID。
1. 在 Customer Journey Analytics 中使用新生成的数据集以及任何其他要包含的数据集[创建或编辑连接](/help/connections/create-connection.md)。为每个数据集选择正确的人员 ID。
1. 根据连接[创建数据视图](/help/data-views/create-dataview.md)。

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

数据视图设置完成后，将在 Customer Journey Analytics 中进行分析，此分析与 Customer Journey Analytics 中的其他分析基本一样，只是现在的数据操作是跨渠道和跨设备进行的。
