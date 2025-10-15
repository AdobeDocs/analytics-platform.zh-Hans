---
title: 格式组件设置
description: 配置指标的格式。
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 6fdb6cbd6f12a0417f513565b02e3ad60c8df6cb
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 88%

---

# 格式组件设置 {#format-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format"
>title="格式"
>abstract="确定在报告中使用某个组件时如何显示该组件。"

<!-- markdownlint-enable MD034 -->


通过格式，可决定给定组件在报告中使用时的显示方式。

## 配置组件的格式设置

您可以通过调整给定组件的格式设置来确定其显示方式。

1. 在 Customer Journey Analytics 中，选择&#x200B;[!UICONTROL **数据视图**]&#x200B;选项卡。

1. 选择包含要配置格式设置的组件的数据视图。

1. 选择&#x200B;[!UICONTROL **“组件”**]&#x200B;选项卡。

1. 选择要配置的组件，然后展开页面右侧的&#x200B;[!UICONTROL **格式**]&#x200B;部分。

   ![格式设置](../assets/format-settings.png)

1. 指定以下信息：

   | 设置 | 描述 |
   | --- | --- |
   | **[!UICONTROL 格式]** | 使您可将组件的格式指定为“小数”、“时间”、“百分比”或“货币”。 |
   | **[!UICONTROL 小数]** | 在 Integer 架构数据类型上不可见。用于指定组件显示的小数位数。 |
   | **[!UICONTROL 日期]** | 用于确定在报告中将日期时间字段用作维度时的显示方式。[了解详情](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL 日期时间]** | 用于确定在报告中将日期时间字段用作维度时的显示方式。[了解详情](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL 货币]** | 用于确定希望组件以哪种货币显示。 <p>如果您要分析以不同货币进行交易的全球数据，请参阅[使用货币转换](#use-currency-conversion)。</p> |
   | **[!UICONTROL 将上升趋势显示为]** | 使您可指定此组件的上升趋势是好（绿色）还是坏（红色）。 |
   | **[!UICONTROL 真值]**&#x200B;和&#x200B;**[!UICONTROL 假值]** | 仅在 Boolean 架构数据类型上可见。使您可自定义 `true` 和 `false` 值的维度项标签。 |

   {style="table-layout:auto"}

## 使用货币转换 {#use-currency-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format_currencyconversion"
>title="货币转换"
>abstract="选择货币代码维度来配置和显示所选货币类型的货币。"

<!-- markdownlint-enable MD034 -->

Customer Journey Analytics 中的货币转换对于跨国经营的企业来说非常有价值。通过消除手动转换货币的复杂性，Customer Journey Analytics 中的货币转换可为财务数据带来统一性和清晰度。货币转换会跟踪每日程表史汇率，并将这些每日汇率保留 4 年。

例如，如果一家电子商务企业在美国、英国和欧盟开展业务，则销售数据可以自动转换为美元，以确保能够轻松比较并全面了解业绩。

>[!NOTE]
>
>在开始配置货币转换量度之前，请考虑以下事项：
>
>* 您为货币转换选择的量度必须具备数字类型 (Double、Long、Integer、Short、Byte)。
>* 将您的 Customer Journey Analytics 连接设置为包含至少一个事件数据集，该数据集为每个包含货币量度的事件提供货币代码维度。该货币代码维度使用符合 [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) 标准的字母货币代码来表示货币。这些值应采用全大写格式，例如 USD 代表 $、EUR 代表 €、GBP 代表 £。

要确定货币在给定量度中的显示和转换方式：

1. 如上所述，在[为量度配置格式设置](#configure-format-settings-for-a-metric)中，开始配置您希望使用货币作为格式的量度。

1. 选择好量度后，在页面右侧的&#x200B;[!UICONTROL **格式**]&#x200B;部分进行以下选择：

   * 在&#x200B;[!UICONTROL **格式**]&#x200B;字段，选择&#x200B;[!UICONTROL **货币**]。

   * 在&#x200B;[!UICONTROL **小数位**]&#x200B;字段中，选择量度显示的小数位数。

     仅当量度的数字类型为“Double”时，此选项才可用。

   * 选择&#x200B;[!UICONTROL **转换货币**]&#x200B;选项。

   * 在&#x200B;[!UICONTROL **选择货币代码维度**]&#x200B;字段中，选择代表您要转换的货币（即您的数据所基于的货币）的维度。例如，选择一个名为&#x200B;[!UICONTROL **货币代码**]&#x200B;的维度。

     如果您当前数据架构中没有包含货币代码字段的维度，则可以使用[数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hans)、[数据蒸馏器](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html?lang=zh-Hans)或者[派生字段](/help/data-views/derived-fields/derived-fields.md)创建新的货币代码字段。“数据准备”仅适用于新的实施，因为它仅适用于向前推进的情况。根据组织的设置，可以使用“数据蒸馏器”和“派生字段”来访问历史货币代码值。

   * 在&#x200B;[!UICONTROL **转换并显示货币**]&#x200B;字段中，选择您希望数据转换成的货币。

1. 如果您想将货币转换功能应用于其他量度，请重复这些步骤。



### 常见问题解答

+++ 货币转换如何进行？

在报告时，量度值和原始货币代码会先转换为美元 (USD)，然后再转换为配置的显示货币。在进行该转换时，将使用适用于事件发生时的每日汇率。

+++

