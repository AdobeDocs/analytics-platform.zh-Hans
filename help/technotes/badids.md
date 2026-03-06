---
title: Customer Journey Analytics错误ID
description: 了解Customer Journey Analytics中的错误ID (BAVID)。 了解如何识别数据中的错误ID、它们影响报表的原因，以及如何调查和解决连接中的错误ID泄露。
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: b7b2a1f3eb1c149caf65ab3e4321e4f4347695cc
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 0%

---


# 错误 ID

本文提供了有关错误ID的上下文，以及如何使用查询服务检测数据中是否存在错误ID或错误发生风险。


>[!INFO]
>
>错误ID在Customer Journey Analytics界面中也称为BAVID（源自[Analytics BAVID](https://experienceleague.adobe.com/zh-hans/docs/experience-cloud-kcs/kbarticles/ka-16444)）。
>

## 定义

在Customer Journey Analytics中，作为连接中定义的所有数据的一部分，错误ID是一个标识符：

* ，并使用源自的特定ID值
   * 来自人员ID字段（非拼接数据集），**或**
   * 永久性ID或人员ID字段（支持拼合的数据集）中的任意值，

  **和**
* 在一个月内对连接数据中的超过100万(1,000,000)个事件（对连接内的所有数据集都计数）进行计数。

当某个ID值被标记为错误ID时，任何包含该ID值的未来事件都将从连接数据中舍弃，并且不会在报表中显示。

### 示例

错误ID场景的一个示例是，在人员ID字段中具有自定义或占位符值（例如，匿名流量为`undefined`）。 对于启用拼合的数据集，这种情况可能对报表数据产生更大的影响，因为拼合质量最有可能受到影响。 要解决此问题，您可能需要清除并重新启用拼合设置，包括删除连接中数据集的历史数据。


## 量度

Customer Journey Analytics连接界面在界面的多个位置提供&#x200B;**[!UICONTROL 错误的ID]**&#x200B;指标信息。

* 您可以在&#x200B;**[!UICONTROL 检查跳过的详细信息]**&#x200B;对话框中看到&#x200B;**[!UICONTROL 错误的ID]**（或&#x200B;**[!UICONTROL BAVID]**）作为跳过记录的可能原因。 在连接的&#x200B;**[!UICONTROL 详细信息屏幕]**&#x200B;中，使用&#x200B;**[!UICONTROL 跳过的记录]**&#x200B;下方的[检查详细信息](/help/connections/create-connection.md)（如果可用）。
* 对于已启用拼接的数据集，[**[!UICONTROL 数据集预览]**](/help/stitching/use-stitching-ui.md#bad-ids)在&#x200B;**[!UICONTROL 拼接量度]**&#x200B;中显示&#x200B;**[!UICONTROL 错误的ID]**。 此量度可帮助您识别可能的ID错误案例。 但是，请注意，此量度是根据有限的数据集计算的。

请参阅[错误的ID泄露](#bad-ids-exposure)，以帮助您识别计划在连接中使用的数据集的错误ID存在（无论是否启用了拼接）。


## 曝光

要调查某个数据集字段的错误ID泄露，请考虑在Experience Platform查询服务中执行以下查询。 检查返回的最大ID值，以查看是否有适用的ID无效。 请注意，[错误的ID定义](#definition)考虑到了连接中的所有数据集。


### 识别字段中的错误ID（风险）

您可以使用Experience Platform Query为识别字段内错误ID的潜在风险提供服务。

以下查询返回字段中的前20个ID值。 按事件总数降序排列。 并且在特定时间间隔（例如，最近30天内）内检测到每个值。

为要分析的特定人员ID字段运行此查询。 对于需要拼合的数据集，您还可以运行对持久ID字段的查询。

```sql
SELECT
    /* INSERT FIELD HERE */,
    COUNT(*) AS occurrences
FROM /* INSERT DATASET TABLE NAME HERE */
WHERE timestamp >= NOW() - INTERVAL '30 days' 
GROUP BY /* INSERT FIELD HERE */
ORDER BY occurrences DESC
LIMIT 20; 
```

在查询中，根据您调查错误ID的字段类型替换`INSERT FIELD HERE`：

* `full.field.path.from.XDM.schema` （用于XDM架构中定义的字符串字段）
* `identityMap['namespace_value'][0].id` （对于`namespace_value`中用`identityMap`定义的字段）

检查结果以查看是否存在问题的ID值。 如自定义值或占位符值，或者频繁出现的值，在连接数据级别的一个月内将达到或可能接近100万。
即使您的实施仍然处于开发阶段，只要设置稳定并准备好生产，您就应该评估存在错误ID的风险。
