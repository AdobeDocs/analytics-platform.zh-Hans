---
title: 将Marketo Engage数据摄取到Adobe Experience Platform并在Customer Journey Analytics中报告
description: 了解如何将Marketo Engage数据引入Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 66%

---

# 将Marketo Engage数据摄取到Adobe Experience Platform并在Customer Journey Analytics中报告

您可以利用Adobe Experience Platform (Adobe Experience Platform)中新提供的Marketo Engage数据集，为B2B营销人员提供有价值的分析和报表解决方案。 然后在Adobe Customer Journey Analytics中报告这些数据集。

## 步骤 1：将 Marketo 源数据字段映射到其 XDM 目标

将 [人员](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=cn#persons) 和 [活动](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=cn#activities) 对象映射到各自的 XDM 模式目标字段。

## 步骤2：将Marketo数据摄取到Adobe Experience Platform

使用 [Marketo Engage 连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html?lang=cn)将 Marketo 的数据传送到 Experience Platform，并使用与平台连接的应用程序使这些数据保持最新。

## 步骤3：在Customer Journey Analytics中设置与此数据集的连接

要报告Experience Platform数据集，首先必须在Experience Platform和Customer Journey Analytics中的数据集之间建立连接。 在 [“创建连接”](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=cn) 下查找更多信息。

## 步骤 4：创建一个或多个数据视图

[数据视图](/help/data-views/data-views.md) 是 Customer Journey Analytics 专属的容器，通过它，可决定如何解释来自连接的数据。 它指定所有可在 Analysis Workspace 中找到的维度和量度，在本例中，特指 Marketo 的量度和维度。 它还指定这些维度和量度从哪些列获取数据。 为准备 Analysis Workspace 中的报表而定义数据视图。

## 步骤 5：Analysis Workspace 中的报告

您可以探索的一个用例是：2020 年 4 月至 6 月，潜在客户访问了多少网页？

1. 打开 [Analytics Workspace](/help/analysis-workspace/home.md) 并创建新项目。拥有B2B/B2P CDP的客户可以在Customer Journey Analytics中进行B2C风格的分析。 B2B 对象尚不可用。

1. 为网页视图创建一个[过滤器](/help/components/filters/create-filters.md)，如下所示：事件类型 = web.webpagedetails.pageViews :

   ![](../assets/marketo-filter.png)

1. 在自由格式表中，拉入您创建的过滤器“网页查看次数”，然后拉入月份日期范围。 这样，您可以每月通过潜在客户访问网页：

   ![](../assets/marketo-freeform.png)

1. 或者拉入以下维度：人员密钥或工作电子邮件地址。 这将为您提供每个潜在客户的网页访问：

   ![](../assets/marketo-freeform2.png)
