---
title: 产品使用情况数据设置
description: 启用、禁用或配置产品使用情况设置。
exl-id: 85e2b515-78e6-41e8-9947-369b1e65e4fd
source-git-commit: e7534a1943307f5bbc92a845ddffe0651794b854
workflow-type: ht
source-wordcount: '356'
ht-degree: 100%

---

# 产品使用情况数据设置 {#product-usage-data-settings}

_数据设置_&#x200B;页面会处理您的产品使用情况配置。您可以使用此页面为您的组织启用或禁用产品使用情况数据收集功能。您还可以配置在哪个 Adobe Experience Platform 沙盒下创建数据集，并根据需要覆盖数据保留窗口。它仅对产品管理员可见。

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 工具]** > **[!UICONTROL 产品使用情况]** > **[!UICONTROL 数据设置]**

>[!IMPORTANT]
>当您启用此功能时，您必须接受相关条款和条件才能使用。当您接受这些条款和条件时，您代表的是整个组织。

此页面提供以下设置：

* **[!UICONTROL 启用产品使用情况数据收集功能]**：切换产品使用情况数据收集功能的可用性。如果您先启用产品使用情况数据收集功能，之后又将其禁用，则数据集、连接和数据视图不会被删除。当该功能被关闭时，您所在组织的跟踪功能将被全局禁用。
* **[!UICONTROL 沙盒]**：确定在其下创建架构和数据集的 Adobe Experience Platform 沙盒。您选择的沙盒不会影响产品使用情况数据的收集。如果您更改此沙盒设置，则所有现有数据都会被删除。在选定的沙盒中创建新的数据集、连接和数据视图。
* **[!UICONTROL 覆盖数据保留窗口]**：每个数据集都有一个默认的数据保留窗口。如果禁用此设置，则产品使用情况将遵循默认的时段。如果您想缩短数据保存的时间，可以启用此设置。缩短数据保留窗口有助于降低成本，并允许您遵守任何特定于员工的隐私准则。您不能将数据保留期限延长至数据集的默认数据保留期限之后。

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
