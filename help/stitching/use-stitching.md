---
title: 使用拼合
description: 如何使用拼合
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
source-git-commit: 5e25cb4d974ab85cca3aa2bb777675e12f63038b
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 9%

---

# 使用拼合

如果贵组织满足所有[先决条件](#prerequisites)并了解常见的[限制](#limitations)和特定于拼接方法（[基于字段](#limitations-1)和[基于图形](#limitations-2)）的限制，则可以按照以下步骤在Customer Journey Analytics中开始使用拼接。

## 选择选项

您有权使用的Customer Journey Analytics包将决定可用的拼接方法、初始回填持续时间的选项、回顾时间范围、重放频率和允许拼接的最大数据集数。 有关更多详细信息，请参阅[Customer Journey Analytics的产品说明](https://helpx.adobe.com/cn/legal/product-descriptions/customer-journey-analytics.html)。 在请求支持之前决定可用的选项。

| | Customer Journey Analytics<br/>选择 | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| 可用的拼接方法 | <li>基于字段的拼合</li> | <li>基于字段的拼合</li><li>基于图形的拼接</li> | <li>基于字段的拼合</li><li>基于图形的拼接</li> |
| 一次性拼接回填持续时间 | 13 个月 | 13 个月 | 25 个月 |
| 回顾窗口和重放频率 | <li>1天，每天</li><li>长达7天，每周</li> | <li>1天，每天</li><li>长达14天，每周</li> | <li>1天，每天</li><li>长达30天，每周</li> |
| 允许拼合的最大数据集数 | 5 | 10 | 50 |

## 请求支持

1. 请联系 Adobe 客户支持并提供以下信息：

   - 启用拼合的请求。
   - 要重新生成键值的数据集的数据集ID。
   - 所需数据集（每行都显示的标识符）的永久ID的列名称（身份路径和命名空间）。
   - 对于基于字段的拼合，所需数据集的“临时ID”列名称（人员标识符，也用作连接上下文中数据集之间的链接）。 对于基于图的拼接，为用于查询身份图的身份命名空间。
   - 您的回顾窗口和重播频率首选项。 查看您的Customer Journey Analytics包，了解可用的[选项](#options)。
   - 沙盒名称。


2. Adobe客户支持与Adobe工程部门合作，以便在收到您的请求时启用拼合。 启用后，Adobe Experience Platform中会显示一个包含新拼接ID列的已重新生成键值的新数据集。 Adobe客户支持可以提供新数据集的ID。

3. 首次打开时，Adobe提供拼合数据的回填。 查看您的Customer Journey Analytics包，以了解有关[选项](#options)的可用信息。

4. 如果要在跨渠道分析中使用新拼接的数据集，则需要将新拼接的数据集添加到Customer Journey Analytics中的[连接](../connections/overview.md)。 然后，添加跨渠道分析所需的任何其他数据集，并为每个数据集选择正确的人员ID。

5. 根据连接[创建数据视图](/help/data-views/create-dataview.md)。

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

数据视图设置完成后，您可以跨渠道和设备运行Customer Journey Analytics报表分析。

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


