---
title: 产品使用情况数据设置
description: 启用、禁用或配置产品使用设置。
source-git-commit: 7d22c512e8e96963b288567704d2245e64411b10
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 14%

---

# 产品使用情况数据设置 {#product-usage-data-settings}

{{release-limited-testing}}

_数据设置_&#x200B;页面处理您的产品使用情况配置。 您可以使用此页面为您的组织启用或禁用产品使用。 您还可以配置在哪个Adobe Experience Platform沙箱下创建数据集，并根据需要覆盖数据保留窗口。 只有产品管理员才能看到它。

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 工具]** > **[!UICONTROL 产品使用情况]** > **[!UICONTROL 数据设置]**

>[!IMPORTANT]
>启用此功能后，您必须先接受条款和条件，然后才能使用它。 接受这些条款和条件后，您将代表整个组织执行操作。

此页面上提供以下设置：

* **[!UICONTROL 启用产品使用情况]**：切换产品使用情况数据收集的可用性。 如果启用产品使用，则以后禁用它，则不会删除数据集、连接和数据视图。 关闭后，将对您的组织全局禁用跟踪。
* **[!UICONTROL 沙箱]**：确定创建架构和数据集时使用的Adobe Experience Platform沙箱。 您选择的沙箱不会影响产品使用情况数据收集。 如果更改此沙箱设置，则所有现有数据都将被删除。 将在选定的沙箱中创建一个新数据集、连接和数据视图。
* **[!UICONTROL 覆盖数据保留窗口]**：每个数据集都有一个默认的数据保留窗口。 如果禁用此设置，则产品使用将遵循该默认时间段。 如果要缩短保留数据的时间，可以启用此设置。 缩短数据保留窗口并帮助降低成本，同时让您能够遵守任何特定于员工的隐私准则。 您无法将数据保留扩展到数据集默认的数据保留窗口之外。

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Adobe Experience Platform 沙盒"
>abstract="确定在其下创建架构和数据集的 Adobe Experience Platform 沙盒。"

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="覆盖数据保留窗口"
>abstract="缩短产品使用情况数据的可用性，以帮助降低成本或遵守隐私准则。"
