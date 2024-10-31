---
title: 格式组件设置
description: 配置指标的格式。
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: d65171873f68835de0628b95158f01713eaacb6b
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 23%

---

# 格式组件设置 {#format-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_metric_format"
>title="格式"
>abstract="确定在报表中使用某个组件时如何显示该组件。"

<!-- markdownlint-enable MD034 -->


通过格式，可决定给定的量度在报表中使用的显示方式。

## 配置量度的格式设置

您可以通过调整给定的量度的格式设置来确定其显示方式。

1. 在Customer Journey Analytics中，选择&#x200B;[!UICONTROL **数据视图**]&#x200B;选项卡。

1. 选择包含要配置其格式设置的组件的数据视图。

1. 选择&#x200B;[!UICONTROL **“组件”**]&#x200B;选项卡。

1. 选择要配置的组件，然后展开页面右侧的&#x200B;[!UICONTROL **格式**]&#x200B;部分。

   ![格式设置](../assets/format-settings.png)

1. 指定以下信息：

   | 设置 | 描述 |
   | --- | --- |
   | **[!UICONTROL 格式]** | 使您可将指标的格式指定为“小数”、“时间”、“百分比”或“货币”。 |
   | **[!UICONTROL 小数]** | 在 Integer 架构数据类型上不可见。使您可指定某个指标所显示的小数位数。 |
   | **[!UICONTROL 日期]** | 用于确定在报告中将日期时间字段用作维度时的显示方式。 [了解详情](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL 日期时间]** | 用于确定在报告中将日期时间字段用作维度时的显示方式。 [了解详情](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL 货币]** | 用于确定您希望量度以哪种货币显示。 <p>如果分析事务以不同货币发生的全局数据，请参阅[使用货币换算](#use-currency-conversion)。</p> |
   | **[!UICONTROL 将上升趋势显示为]** | 使您可指定此指标的上升趋势是好（绿色）还是坏（红色）。 |
   | **[!UICONTROL 真值]**&#x200B;和&#x200B;**[!UICONTROL 假值]** | 仅在 Boolean 架构数据类型上可见。使您可自定义 `true` 和 `false` 值的维度项目标签。 |

   {style="table-layout:auto"}

## 使用货币换算 {#use-currency-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_metric_format_currencyconversion"
>title="货币换算"
>abstract="选择货币代码维度来配置和显示所选货币类型的货币。"

<!-- markdownlint-enable MD034 -->

Customer Journey Analytics的货币兑换对于在国际上运营的企业可能极具价值。 通过消除手动货币转换的复杂性，Customer Journey Analytics中的货币转换实现了财务数据的统一性和明确性。 货币兑换可追踪每日历史汇率并维持该等每日汇率为期四年。

例如，如果电子商务业务在美国、英国和欧盟运营，则销售数据可以自动转换为美元，从而确保轻松比较和全面了解业绩。

>[!NOTE]
>
>在开始配置货币兑换指标之前，请考虑以下事项：
>
>* 为货币兑换选择的量度必须具有数字类型（双精度、长精度、整数、短整数、字节）。
>* 设置您的Customer Journey Analytics连接，以至少包含一个事件数据集，该数据集为包含货币量度的每个事件保留一个货币代码维度。 该货币代码维度使用符合[ISO 4217](https://www.iso.org/iso-4217-currency-codes.html)标准的字母货币代码来表示货币。 这些值应采用全大写格式，如$为USD，€为EUR，英镑为£。

要确定给定指标的货币显示和转换方式，请执行以下操作：

1. 如上所述，在[为量度配置格式设置](#configure-format-settings-for-a-metric)中开始配置要将货币用作格式的量度。

1. 选中该量度后，在页面右侧的&#x200B;[!UICONTROL **格式**]&#x200B;分区中进行以下选择：

   * 在&#x200B;[!UICONTROL **格式**]&#x200B;字段中，选择&#x200B;[!UICONTROL **货币**]。

   * 在&#x200B;[!UICONTROL **小数位**]&#x200B;字段中，选择指标显示的小数位数。

     仅当量度的数字类型为“双精度”时，此选项才可用。

   * 选择&#x200B;[!UICONTROL **转换货币**]&#x200B;选项。

   * 在&#x200B;[!UICONTROL **选择货币代码维度**]&#x200B;字段中，选择表示要转换的货币（数据所基于的货币）的维度。 例如，选择一个名为&#x200B;[!UICONTROL **货币代码**]&#x200B;的维度。

     如果当前数据架构中没有包含货币代码字段的维度，则可以使用[数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hans)、[数据Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html)或[派生字段](/help/data-views/derived-fields/derived-fields.md)创建新的货币代码字段。 数据准备仅适用于新的实施，因为它仅针对不断发展的问题。 根据组织的设置，可以使用Data Distiller和派生字段访问以往的货币代码值。

   * 在&#x200B;[!UICONTROL **转换和显示**]&#x200B;中的货币字段中，选择要转换数据的货币。

1. 如果要将货币兑换应用于其他指标，请重复这些步骤。



### 常见问题解答

+++ 如何执行货币转换？

在报告时，量度和原始货币代码的值将转换为USD，然后转换为配置为显示的货币。 对于此转换，使用事件时适用的每日货币汇率。

+++

