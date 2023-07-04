---
title: 拼接概述
description: 拼接概述。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
source-git-commit: 3fd4038c44b50490618f838d281684742920d152
workflow-type: tm+mt
source-wordcount: '1246'
ht-degree: 24%

---

# 拼接概述

身份拼合（或简单地说就是拼合）是一项强大的功能，它增强了事件数据集对跨渠道分析的适用性。 跨渠道分析是Customer Journey Analytics可以处理的主要用例，允许您根据通用标识符（人员ID）无缝地组合和运行来自不同渠道的多个数据集的报表。

当您合并具有相似人员 ID 的数据集时，将跨设备和渠道进行归因。例如，用户首先通过台式计算机上的广告访问了您的网站。该用户在下单时遇到了问题，随后致电客服团队以请求其帮助解决此问题。通过跨渠道分析，您可以将呼叫中心事件归因于最初点击的广告。

遗憾的是，并非所有作为Customer Journey Analytics中连接一部分的基于事件的数据集都已充分填充了数据，以支持开箱即用的归因。 特别是，基于Web或基于移动设备的体验数据集通常没有可用于所有事件的实际人员ID信息。

拼接允许为一个数据集行中的身份重新生成键值，确保人员ID（拼接ID）在每个事件上可用。 拼接查看来自经过身份验证和未经身份验证的会话的用户数据，以确定可用作拼接ID的通用临时ID值。 这允许将不同的记录解析为单个拼合ID，以供在人员级别（而不是设备或Cookie级别）进行分析。

如果在定义Customer Journey Analytics连接时合并一个或多个拼接数据集与其他数据集（例如呼叫中心数据），则您将受益于跨渠道分析。 这假设其他那些数据集在每行上都已包含一个人员ID，类似于拼合的ID。


## 先决条件

>[!IMPORTANT]
>
>如果不满足所有先决条件，则可能会导致无法正确进行跨渠道分析。

在使用拼合之前，请确保贵组织已做好以下准备：

* 将所需数据导入Adobe Experience Platform：

   * 有关Adobe Analytics数据，请参阅 [在Customer Journey Analytics中使用Adobe Analytics报表包数据](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   * 有关其他类型的数据，请参阅 Adobe Experience Platform 文档中的[创建模式](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hans)和[摄取数据](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=zh-Hans)。

* Adobe Experience Platform中要应用拼接的事件数据集必须具有两个帮助识别访客的列：

   * **持久 ID**，即每行都存在的标识符。例如，由Adobe AnalyticsAppMeasurement库生成的访客ID或由Adobe Experience Cloud Identity服务生成的ECID。
   * **临时 ID**，即仅在部分行存在的标识符。例如，经过身份验证的访客的经过哈希处理的用户名或电子邮件地址。您实际上可以使用任何喜欢的标识符。 拼接将考虑使用此字段来保存实际的人员ID信息。 为获得最佳的拼接结果，应在数据集的事件中为每个永久ID至少发送一次临时ID。
如果计划在Customer Journey Analytics连接中包含此数据集，最好其他数据集也具有类似的通用标识符。

* 拼接包括合并经过身份验证的用户数据和未经身份验证的用户数据。 在激活事件数据集的拼合之前，请确保遵守适用的法律和法规，包括获取必要的最终用户权限。


## 使用拼合

贵组织在满足所有先决条件并了解 [限制](#limitations)中，您可以按照以下步骤开始在Customer Journey Analytics中使用拼合：

### 请求支持

1. 请联系 Adobe 客户支持并提供以下信息：

   * 启用拼合的请求。
   * 要重新生成键值的数据集的数据集 ID.
   * 所需数据集的永久ID的列名称（每行显示的标识符）。
   * 所需数据集的临时ID列名称（人员标识符，还用作连接上下文中的数据集之间的链接）。
   * 您的[重播](explained.md)频率和回顾时间范围首选项。选项包括每周重播一次（回顾时间范围为 7 天）或每天重播一次（回顾时间范围为 1 天）。
   * 沙盒名称。


2. Adobe客户支持与Adobe工程部门合作，以便在收到您的请求时启用拼合。 启用后，Adobe Experience Platform中会显示一个包含新拼接ID列的已重新生成键值的新数据集。 Adobe客户支持可以提供新数据集的ID。

3. 首次打开时，Adobe提供回填30天以前的拼合数据。

4. 如果要在跨渠道分析中使用新拼合的数据集，则需要将其添加到 [连接](../connections/overview.md) 与其他所需数据集一起Customer Journey Analytics。 为每个数据集选择正确的人员 ID。

5. 根据连接[创建数据视图](/help/data-views/create-dataview.md)。

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

设置数据视图后，您可以跨渠道和设备运行Customer Journey Analytics报表分析。

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->


## 限制

>[!IMPORTANT]
>
>将您对全局事件数据集架构所做的任何更改也应用于新拼接的数据集架构，否则这会断开拼接的数据集。
>
>此外，如果移除源数据集，缝合的数据集将停止处理并被系统移除。

拼接是一项具有突破性的强大功能，但其使用方式存在限制。

* 当前，重新生成键值功能只能执行一步（即将永久 ID 转换为临时 ID）。而不支持多步重新生成键值功能（例如，将永久 ID 转换为临时 ID，然后再转换为另一个临时 ID）。
* 仅支持事件数据集。不支持其他数据集，例如查找数据集。
* 不支持在组织中使用的自定义 ID 映射。
* 拼接不会以任何方式转换用于拼接的字段。 拼接使用指定字段中的值，因为该值存在于数据湖中未拼接的数据集中。 拼接过程区分大小写。例如，如果字段中有时出现“Bob”一词，有时出现“BOB”一词，则这些id将被视为两个不同的人。
* 拼接区分大小写。 对于通过Analytics Source Connector生成的数据集，Adobe建议审查任何适用于临时ID字段的VISTA规则或处理规则。 此审查可确保这些规则都不会引入同一ID的新形式。 例如，对于部分事件，您应确保没有任何 VISTA 或处理规则将小写字母引入到临时 ID 字段。
* 拼接不会组合或连接字段。
* 临时ID字段应包含单一类型的ID（来自单个命名空间的ID）。 例如，临时 ID 字段不应包含登录 ID 和电子邮件 ID 的组合。
* 如果对于同一持久ID发生了多个具有同一时间戳的事件，但临时ID字段中的值不同，则拼接操作会根据字母顺序选择该ID。 因此，如果持久ID A具有时间戳相同的两个事件，其中一个事件指定Bob，而另一个事件指定Ann，则拼接操作将选择Ann。
* 如果一台设备由多人共享，并且用户之间的转换总数超过50,000，则Customer Journey Analytics将停止为该设备拼合数据。

不要将拼接与以下内容混淆：

* 两个或多个数据集的合并。 拼接仅适用于一个数据集。 数据集合并是设置Customer Journey Analytics连接并在连接中的选定数据集中选择相同的人员ID的结果。

* 两个数据集的连接。 在Customer Journey Analytics中，连接通常用于Analysis Workspace中的查找或分类。 尽管拼接使用连接功能，但过程本身涉及的内容远不止连接。

