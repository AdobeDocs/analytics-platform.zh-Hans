---
title: 格式组件设置
description: 配置指标的格式。
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 387c787dba4caa9db82d46071e23a2131043c8c6
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 30%

---

# 格式组件设置

通过“格式”，可决定如何显示给定的指标。

![格式设置](../assets/format-settings.png)

| 设置 | 描述 |
| --- | --- |
| **[!UICONTROL 格式]** | 使您可将指标的格式指定为“小数”、“时间”、“百分比”或“货币”。 |
| **[!UICONTROL 小数位数]** | 在 Integer 架构数据类型上不可见。使您可指定某个指标所显示的小数位数。 |
| **[!UICONTROL 日期]** | 用于确定在报告中将日期时间字段用作维度时的显示方式。 [了解详情](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL 日期时间]** | 用于确定在报告中将日期时间字段用作维度时的显示方式。 [了解详情](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL 货币]** | 让您确定要以哪种货币显示指标。请参阅 [货币](#currency) 以了解更多详细信息。 |
| **[!UICONTROL 将上升趋势显示为]** | 使您可指定此指标的上升趋势是好（绿色）还是坏（红色）。 |
| **[!UICONTROL 真值]**&#x200B;和&#x200B;**[!UICONTROL 假值]** | 仅在 Boolean 架构数据类型上可见。使您可自定义 `true` 和 `false` 值的维度项目标签。 |

{style="table-layout:auto"}

## 货币

当您选择时 **[!UICONTROL 货币]** 作为 [!UICONTROL 格式] 对于指标，您可以确定如何显示和转换货币。

### 显示货币

要显示指标的货币，请执行以下操作：

1. 输入数字 **[!UICONTROL 小数位]**.

1. 从中选择货币 **[!UICONTROL 显示货币]** 列表。


### 转换并显示货币

要为一个或多个量度启用货币转换，请执行以下操作：

- 设置您的Customer Journey Analytics连接，以至少包含一个事件数据集，该数据集为包含货币量度的每个事件保留一个货币代码维度。 该货币代码维度使用符合 [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) 表示货币的标准。 这些值应采用全大写格式，如$为USD，€为EUR，英镑为£。

   1. 从包含货币代码的其中一个数据集中选择维度。 例如， [!UICONTROL 货币代码].

   1. 选择 **[!UICONTROL 货币代码]** 从维度列表中。

- 如果有更多维包含要用于货币兑换的货币代码，请重复这些步骤。

>[!NOTE]
>
>为货币兑换选择的量度必须具有数字类型（双精度、长精度、整数、短整数、字节）。


要定义如何转换和显示量度的货币，请执行以下操作：

1. 输入数字 **[!UICONTROL 小数位]**.

1. 选择 **[!UICONTROL 转换并发]**.

1. 从包含货币代码字段的维度列表中选择相应的维度。

1. 从中选择货币 **[!UICONTROL 转换和显示货币]** 列表。

### 常见问题解答

+++ 如何执行货币转换？

在报告时，量度和原始货币代码的值将转换为USD，然后转换为配置为显示的货币。 对于此转换，使用事件时适用的每日货币汇率。

+++


+++ 每日转化率可维持多久以前的水平？

过去四年每日转换率保持不变。

+++


+++ 如果我当前数据架构中没有货币代码字段，该怎么办？

提供了多个用于创建新货币代码字段的选项，包括数据准备、数据Distiller和派生字段。 数据准备是新实施的理想选择，因为它仅在以后进行。 根据组织的设置，可以使用Data Distiller和派生字段来访问以往的货币代码值。

+++

