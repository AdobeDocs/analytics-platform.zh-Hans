---
title: 格式组件设置
description: 配置指标的格式。
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 66e7adfbca3f20d21b4331033f70ac7d0933cd12
workflow-type: tm+mt
source-wordcount: '530'
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

- 设置您的Customer Journey Analytics连接，使其至少包含一个事件数据集，该数据集为包含货币量度的每个事件保留一个货币代码维度。 该货币代码维度使用符合 [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) 表示货币的标准。 这些值应采用全大写格式，例如$表示美元，欧元表示欧元，英镑表示英镑。

   1. 从包含货币代码的数据集之一中选择维度。 例如， [!UICONTROL 货币代码].

   2. 选择 **[!UICONTROL 货币代码]** 从维度列表中。

  如果您有更多维度包含要用于货币兑换的货币代码，请重复这些步骤。

>[!NOTE]
>
>为货币兑换选择的量度必须具有数字类型（双精度、长精度、整数、短精度、字节）。


要定义如何转换和显示量度的货币，请执行以下操作：

1. 输入数字 **[!UICONTROL 小数位]**.

2. 选择 **[!UICONTROL 转换并发]**.

3. 从包含货币代码字段的维度列表中选择相应的维度。

4. 从中选择货币 **[!UICONTROL 转换和显示货币]** 列表。

### 常见问题解答

+++ 如何执行货币转换？

在报告时，量度和原始货币代码的值将转换为USD，然后转换为配置为显示的货币。 对于此转换，使用事件时适用的每日货币汇率。

+++ 每日转化率可维持多久以前的水平？

过去四年中每天的兑换率保持不变？

+++ 如果我当前数据架构中没有货币代码字段，该怎么办？

有多个选项可用于创建新的货币代码字段，包括数据准备、数据Distiller和派生字段。 “数据准备”将是新实施的理想选择，因为它仅用于以后的实施。 根据组织的设置，可以使用Data Distiller和派生字段来访问历史货币代码值。

+++

