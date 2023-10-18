---
title: 使用派生字段报告目标
description: 了解如何使用派生字段报告工作区项目中的目标（目标）。
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: 69317871bae9ad2a0fecad6b1df1cc357094b05c
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 2%

---


# 使用派生字段报告目标

此用例介绍了如何使用派生字段的强大功能设置特定维度的目标，然后在工作区项目中使用这些目标。

如果您不熟悉派生字段，请参阅 [教程](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/data-views/derived-fields-in-cja.html?lang=en) 和 [文档](../data-views/derived-fields/derived-fields.md) 来做个介绍。


## 定义目标

要定义目标，请创建一个新的派生字段，您可以在其中使用派生字段定义中早期规则生成的值直接或间接显式设置自定义数值。


### 每月礼品证书订单目标

您希望为礼品证书订单明确设置四个月（从2023年7月到2023年10月）的目标。 请按以下步骤执行此操作：

1. 使用名称创建新的派生字段 `Monthly Gift Certificate Orders Goal (Incremental)`.

1. 使用CASE WHEN规则为每月设置静态值，方法是 **[!UICONTROL 自定义数值]**. 请参阅下面的每月产品目标规则。

   ![产品目标](assets/goals-derived-field-product-goals-1.png)


### 营销渠道收入目标

您需要为每个营销渠道设置每月收入目标。 请按以下步骤执行此操作：

1. 创建新的派生字段，使用 [营销渠道功能模板](/help/data-views/derived-fields/derived-fields.md#marketing-channels) 名称 `Monthly Marketing Channel Revenue Goal (Incremental)`.

1. 定义所有规则，以根据URL PARSE和CASE WHEN规则的组合正确标识每个营销渠道。 例如：

   ![营销渠道派生字段的规则定义](assets/goals-derived-field-marketing-channel-1.png)

1. 通过设置，在最终的CASE WHEN规则中为特定营销渠道明确设置静态值，该值表示每月收入目标 **[!UICONTROL 自定义数值]**. 请参阅 [!DNL Monthly Goal] 下规则。

   ![月度目标](assets/goals-derived-field-marketing-channel-2.png)



## 使用目标

要在工作区项目中使用目标，可使用计算量度功能将派生字段“标准化”回其原始静态值。 此标准化是必需的，因为您为定义目标的派生字段设置的静态值会随每个事件递增。

### 每月礼品证书订单目标

1. 创建名为的计算量度字段 `Monthly Gift Certificate Orders Goal`，定义为：

   ![订单目标](assets/calculated-metric-ordersgoals.png)

1. 您可以创建其他计算字段，例如 `% of Monthly Gift Certificate Orders Goal`，显示相对于目标的实际进度，例如：

   ![订单目标百分比](assets/calculated-metric-ordersgoalspercent.png)

您可以使用这些计算量度来报告自由格式表和可视化图表的进度。 例如：

![显示营销收入目标的自由格式表](assets/freeform-table-product-order-goals.png)


### 营销渠道收入目标

1. 创建名为的计算量度字段 `Marketing Channel Revenue Goal`，定义为：

   ![收入目标](assets/calculated-metric-revenuegoals.png)

1. 您可以创建其他计算字段，例如 `% of Marketing Channel Revenue Goal`，显示相对于目标的实际进度，例如：

   ![收入目标百分比](assets/calculated-metric-revenuegoalspercent.png)

您可以使用这些计算量度来报告自由格式表和可视化图表的进度。 例如：

![显示营销收入目标的自由格式表](assets/freeform-table-marketing-channel-revenue-goals.png)
