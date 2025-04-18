---
title: 报告Marketo Engage数据
description: 了解如何在Customer Journey Analytics中报告Marketo Engage数据
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
role: Admin
source-git-commit: 9f954709a3dde01b4e01581e34aece07fe0256b1
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 51%

---

# 报告Marketo Engage数据

您可以利用Adobe Experience Platform (Adobe Experience Platform)中新提供的Marketo Engage数据集，为B2B营销人员提供有价值的分析和报表解决方案。 然后在Adobe Customer Journey Analytics中报告这些数据集。

## 步骤 1：将 Marketo 源数据字段映射到其 XDM 目标

将 [人员](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html#persons) 和 [活动](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html#activities) 对象映射到各自的 XDM 架构目标字段。

## 步骤2：将Marketo数据摄取到Adobe Experience Platform

使用 [Marketo Engage 连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html)将 Marketo 的数据传送到 Experience Platform，并使用与平台连接的应用程序使这些数据保持最新。

## 步骤3：在Customer Journey Analytics中设置与此数据集的连接

为了报告Experience Platform数据集，您必须首先在Experience Platform和Customer Journey Analytics中的数据集之间建立连接。 有关详细信息[创建或编辑连接](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-hans)，请参阅。

## 步骤 4：创建一个或多个数据视图

[数据视图](/help/data-views/data-views.md) 是 Customer Journey Analytics 专属的容器，通过它，可决定如何解释来自连接的数据。 它指定所有可在 Analysis Workspace 中找到的维度和量度，在本例中，特指 Marketo 的量度和维度。 它还指定这些维度和量度从哪些列获取数据。 为准备 Analysis Workspace 中的报表而定义数据视图。

## 步骤 5：Analysis Workspace 中的报告

您可以探索的一个用例是：2020 年 4 月至 6 月，潜在客户访问了多少网页？

1. 打开 [Analytics Workspace](/help/analysis-workspace/home.md) 并创建新项目。拥有B2B/B2P CDP的客户可以在Customer Journey Analytics中进行B2C风格分析。 B2B 对象尚不可用。

1. 为网页视图创建一个[区段](/help/components/filters/create-filters.md)，如下所示：事件类型= web.webpagedetails.pageViews ：

   显示事件和事件类型的![定义窗口](../assets/marketo-filter.png)

1. 将您创建的区段拉入自由格式表 — 网页查看次数，然后拉入月份日期范围。 这样，您可以每月通过潜在客户访问网页：

   ![自由格式表，按月份显示事件。](../assets/marketo-freeform.png)

1. 或者拉入以下维度：人员密钥或工作电子邮件地址。 这将为您提供每个潜在客户的网页访问：

   ![自由格式表，显示事件和workEmail.Address及网页视图。](../assets/marketo-freeform2.png)
