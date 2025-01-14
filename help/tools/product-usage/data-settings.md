---
title: 产品使用情况数据设置
description: 启用、禁用或配置产品使用设置。
exl-id: 85e2b515-78e6-41e8-9947-369b1e65e4fd
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 23%

---

# 产品使用情况数据设置 {#product-usage-data-settings}

{{release-limited-testing}}

_数据设置_&#x200B;页面处理您的产品使用情况配置。 您可以使用此页面为您的组织启用或禁用产品使用。 您还可以配置在哪个Adobe Experience Platform沙盒下创建数据集，并根据需要覆盖数据保留窗口。 它仅对产品管理员可见。

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 工具]** > **[!UICONTROL 产品使用情况]** > **[!UICONTROL 数据设置]**

>[!IMPORTANT]
>启用此功能时，必须先接受条款和条件，然后才能使用它。 当您接受这些条款和条件时，您会代表整个组织进行接受。

此页面上提供以下设置：

* **[!UICONTROL 启用产品使用情况]**：切换产品使用情况数据收集的可用性。 如果启用产品使用，但以后又禁用它，则不会删除数据集、连接和数据视图。 当切换后，将全局禁用您组织的跟踪。
* **[!UICONTROL 沙盒]**：确定创建架构和数据集的Adobe Experience Platform沙盒。 您选择的沙盒不会影响产品使用情况数据收集。 如果更改此沙盒设置，则将删除所有现有数据。 在选定的沙盒中创建新数据集、连接和数据视图。
* **[!UICONTROL 覆盖数据保留窗口]**：每个数据集都有一个默认的数据保留窗口。 如果禁用此设置，则产品使用将遵循该默认时间段。 如果要缩短保留数据的时间，可以启用此设置。 缩短数据保留窗口，帮助降低成本，并允许您遵守任何特定于员工的隐私准则。 您无法将数据保留扩展到超出数据集的默认数据保留窗口之外。

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Adobe Experience Platform 沙盒"
>abstract="确定在其下创建架构和数据集的 Adobe Experience Platform 沙盒。"

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="覆盖数据保留窗口"
>abstract="缩短产品使用情况数据的可用性，以帮助降低成本或遵守隐私准则。"

>[!CONTEXTUALHELP]
>id="product_usage_sandbox"
>title="Adobe Experience Platform 沙盒"
>abstract="确定在其下创建架构和数据集的 Adobe Experience Platform 沙盒。"

>[!CONTEXTUALHELP]
>id="product_usage_data_retention"
>title="覆盖数据保留窗口"
>abstract="缩短产品使用情况数据的可用性，以帮助降低成本或遵守隐私准则。"
