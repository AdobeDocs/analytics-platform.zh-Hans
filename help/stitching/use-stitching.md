---
title: 请求拼接
description: 了解如何请求拼接。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: cbb18e9d0990d5df64995c2dabe8362c7c37bb45
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 26%

---

# 请求拼接


>[!IMPORTANT]
>
>不再需要通过Adobe进行请求拼接，此方法已弃用。 [在连接UI中启用拼接](use-stitching-ui.md)。
>

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
