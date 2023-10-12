---
description: 了解
title: 指标类型和归因
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 5bb7e04deb52e4805e7151afce0bad476df7f13d
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 37%

---

# 指标类型和归因

选择指标旁边的齿轮图标允许您指定指标类型和归因模型。

## 指标类型

要在构建计算量度时指定量度类型，请执行以下操作：

1. 选择要选择其类型的量度旁边的齿轮图标。

   ![](assets/cm_type_alloc.png)

1. 从以下选项中进行选择：

   | 指标类型 | 定义 |
   |---|---|
   | 标准 | 这些指标是在标准 [!DNL Analytics] 报表中使用的相同指标。如果公式包含一个标准指标，它会显示与其相对的非计算指标的相同数据。标准指标可用于创建特定于每个单独行项目的计算指标。例如， [订购] / [会话] 采用特定行项目的订单，然后除以该特定行项目的会话数。 |
   | 总计 | 在每个行项目中使用报告期间的总计。 如果公式包含一个总计指标，它会显示每个行项目上的相同总计。 总计量度可用于创建与总计数据相比较的计算量度。 例如， [订购] / [会话总数] 显示订单在一个渠道中相对于所有会话的比例，而不只是针对特定行项目的会话。 |

## 归因

有关Customer Journey Analytics中归因的信息，请参阅 [归因组件设置](/help/data-views/component-settings/attribution.md).
