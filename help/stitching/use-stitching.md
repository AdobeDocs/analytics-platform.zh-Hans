---
title: 请求拼接
description: 了解如何请求拼接。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: a94f3fe6821d96c76b759efa3e7eedc212252c5f
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 20%

---

# 请求拼接


>[!IMPORTANT]
>
>不再需要通过Adobe进行请求拼接，此方法已弃用。 [在连接UI中启用拼接](use-stitching-ui.md)。
>

如果贵组织满足常规[先决条件](overview.md#prerequisites)，了解常见[限制](overview.md#limitations)，并且了解特定于拼接方法（[基于字段](fbs.md)和[基于图形](gbs.md)）的先决条件和限制，则可以按照以下步骤在Customer Journey Analytics中请求并开始使用拼接。

## 选择选项

您有权使用的Customer Journey Analytics包将确定可用的拼接方法、初始回填持续时间的选项、回顾窗口、重放频率和允许拼接的最大数据集数。 有关更多详细信息，请参阅[Customer Journey Analytics产品描述](https://helpx.adobe.com/cn/legal/product-descriptions/customer-journey-analytics.html)。 在请求支持之前决定可用的选项。

| | Customer Journey Analytics<br/>选择 | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| 可用的拼接方法 | 基于字段的拼接 | 基于字段的拼接<br/>基于图形的拼接 | 基于字段的拼接<br>基于图形的拼接</li> |
| 一次性拼接回填持续时间 | 13 个月 | 13 个月 | 25 个月 |
| 回顾窗口和重放频率 | 1天，每天<br/>最多7天，每周 | 1天，每天<br/>最多14天，每周 | 1天，每天<br/>最多30天，每周 |
| 允许拼合的最大数据集数 | 5 | 15 | 50 |

## 请求支持

1. 请联系 Adobe 客户支持并提供以下信息：

   - 启用拼合的请求。
   - 要重新生成键值的数据集的数据集ID。
   - 所需数据集（每行都显示的标识符）的永久ID的列名称（身份路径和命名空间）。
   - 如果数据集支持`identityMap`：
      - 对于基于字段的拼接，请为永久ID和人员ID指定命名空间。
      - 对于基于图的拼接，请指定持久ID的命名空间以及用于查询身份图的身份命名空间。
   - 如果数据集不支持`identityMap`：
      - 对于基于字段的拼合，是指所需数据集的人员ID的列名称（人员标识符，还充当连接上下文中数据集之间的链接）。
      - 对于基于图的拼接，为要用于查询身份图的身份命名空间。
   - 您的回顾窗口和重播频率首选项。 查看您的Customer Journey Analytics程序包以了解[选项](#options)。
   - 沙盒名称。


2. Adobe客户支持可与Adobe工程部门合作，以便在收到您的请求时启用拼合。 启用后，Adobe Experience Platform中会显示一个包含拼接ID列的已重新生成键值的数据集。 Adobe客户支持可以提供新数据集的ID。
3. 首次打开时，Adobe会提供拼合数据的回填。 查看您的Customer Journey Analytics程序包，了解有关[选项](#options)的信息，该程序包已推出。

4. 如果要在跨渠道分析中使用拼接的数据集，则需要将拼接的数据集添加到Customer Journey Analytics中的[连接](../connections/overview.md)。 然后，添加跨渠道分析所需的任何其他数据集，并为每个数据集选择正确的人员ID。

5. 根据连接[创建数据视图](/help/data-views/create-dataview.md)。

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

设置数据视图后，您可以跨渠道和设备运行Customer Journey Analytics报表分析。

## 限制

- 对源事件数据集架构所做的任何更改，也应同步应用到新的拼接数据集架构中。

- 如果移除源数据集，拼接的数据集将停止处理，并被系统移除。

- 数据使用情况标签不会自动传播到拼接的数据集架构。如果您将数据使用情况标签应用于源数据集架构，就需要将这些数据使用情况标签手动应用于拼接的数据集架构。请参阅[管理 Experience Platform 中的数据使用情况标签](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/data-governance/labels/overview)，了解更多信息。
