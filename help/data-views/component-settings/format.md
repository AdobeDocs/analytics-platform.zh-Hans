---
title: 格式组件设置
description: 配置指标的格式。
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 5c6e7c51369b451ac0efdcead86f71e38bd3a853
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 32%

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
| **[!UICONTROL 货币]** | 让您确定要以哪种货币显示指标。参见 [货币](#currency) 更多详细信息。 |
| **[!UICONTROL 将上升趋势显示为]** | 使您可指定此指标的上升趋势是好（绿色）还是坏（红色）。 |
| **[!UICONTROL 真值]**&#x200B;和&#x200B;**[!UICONTROL 假值]** | 仅在 Boolean 架构数据类型上可见。使您可自定义 `true` 和 `false` 值的维度项目标签。 |

{style="table-layout:auto"}


## 货币

当您选择时 **[!UICONTROL 货币]** 作为 [!UICONTROL 格式] 对于指标，您可以确定如何显示和转换货币。

### 显示货币

要显示指标的货币，请执行以下操作：

1. 输入数字 **[!UICONTROL 小数位]**.

2. 从中选择货币 **[!UICONTROL 显示货币]** 列表。


### 转换和显示货币

要为指标启用货币转换，请执行以下操作：

- 设置您的Customer Journey Analytics连接，使其至少包含一个事件数据集，该数据集为包含货币量度的每个事件保留一个货币代码维度。 该货币代码维度使用符合 [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) 表示货币的标准。 例如，USD表示$，EUR表示€，GBP表示£。

- 您已（可选）应用 [!UICONTROL 货币代码] 一个或多个维度的上下文标签，这些维度定义您的数据集中可用的货币代码。

  要应用 [!UICONTROL 货币代码] 上下文标签，在 [!UICONTROL 组件] 数据视图的选项卡：

  <!--![Currency Context Label](../assets/currency-context-label.png)-->

   1. 从包含货币代码的数据集之一中选择维度。 例如， [!UICONTROL 货币代码].

   2. 选择 **[!UICONTROL 货币代码]** 从 [!UICONTROL 上下文标签] 列表。

  如果您有更多维度包含要用于货币兑换的货币代码，请重复这些步骤。

>[!NOTE]
>
>为货币兑换选择的量度必须具有数字类型（双精度、长精度、整数、短精度、字节）。


要定义如何转换和显示量度的货币，请执行以下操作：

1. 输入数字 **[!UICONTROL 小数位]**.

2. 选择 **[!UICONTROL 转换并发]**.

3. 根据应用的上下文标签，来自的相应维度 **[!UICONTROL 货币代码维度]** 将自动选择列表。 您可以选择任何其他维度，包括您另外应用了货币代码上下文标签的维度。

4. 从中选择货币 **[!UICONTROL 转换和显示货币]** 列表。

### 常见问题解答

+++ 如何执行货币转换？

在报告时，量度和原始货币代码的值将转换为USD，然后转换为配置为显示的货币。 对于此转换，使用事件时适用的每日货币汇率。

+++

