---
title: 评估和管理CJA使用情况
description: 显示两种估计使用情况的方法和一种管理使用情况的方法。
role: Admin
feature: CJA Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: a69cb8a419d95e0cab666fceea9cb7ebf6daef73
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 41%

---

# 查看并管理CJA使用情况

要查看CJA使用情况，可以使用以下几种方法：

* 为每个连接添加事件数据行。 请参阅 [预估连接大小](#estimate大小)。 这是查看特定时间戳中每个连接的事件行数据的简便方法。
* 可通过三种方式查看您的使用情况，每种方式的详细描述如下：
   * 使用Analysis Workspace报告上个月的事件。
   * 使用Report Builder报告上个月的事件。
   * 使用CJA API创建自动报表。

要管理CJA的使用情况，请执行以下操作：

* 定义滚动数据窗口。

## 预估连接大小 {#estimate-size}

您可能需要知道当前有多少行事件数据位于 [!UICONTROL Customer Journey Analytics]. 要准确了解贵组织的事件数据记录（数据行）使用情况，请执行以下操作 **对于贵组织创建的每个连接**.

>[!NOTE]
>
>由于Adobe在当天运行您的最新使用情况报表，因此请在每月的第一个星期五执行此操作。

1. 在 [!UICONTROL Customer Journey Analytics] 中，单击&#x200B;**[!UICONTROL 连接]**&#x200B;选项卡。

   您现在可以看到所有当前连接的列表。

1. 单击每个连接名称以转到连接管理器。

1. 将 **[!UICONTROL 可用事件数据的记录]** 对于贵组织创建的每个连接。 （根据连接的大小，数字可能需要一段时间才能显示。）

   ![](assets/event-data.png)

   >[!CAUTION]
   >
   >   此计数仅适用于事件数据，不适用于用户档案或查询数据。 如果您有用户档案和查询数据，则计数将稍高一些。 但是，目前无法在用户界面中报告用户档案和查找数据使用情况。 这项功能计划于2023年推出。

1. 获得所有事件数据行的总和后，在您的公司与 Adobe 签署的 Customer Journey Analytics 合同中查找“数据行”权利。

   这可让您获得销售订单中授权的最大数据行数。 如果步骤 3 产生的数据行数大于此数值，则表示您出现过量情况。

1. 要解决这种情况，您有以下几个选项：

   * 更改[数据保留设置](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=zh-Hans#set-rolling-window-for-connection-data-retention)。
   * [删除任何未使用的连接](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hans#implications-of-deleting-data-components)。
   * [在 AEP 中删除数据集](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hans#implications-of-deleting-data-components)。
   * 请联系您的 Adobe 客户经理以获得额外容量的许可。

## 使用所有事件数据创建工作区项目 {#workspace-event-data}

此方法允许您对使用数据以及使用历史记录进行更深入的分析。

1. 在工作区中创建项目之前， [创建数据视图](/help/data-views/create-dataview.md) ，且不应用任何过滤器。

>[!WARNING]
>
>    请勿创建仅用于测量使用情况的包含所有数据的新连接，因为这样实际上会使您的使用量增加一倍。

1. 在工作区中，根据每个数据视图创建新项目并提取所有事件(从 **[!UICONTROL 量度]** 下拉列表)，从当前CJA合同的第一天开始，到当月的第一个星期五。

   ![事件](assets/events-usage.png)

   这将使您能够很好地了解每月使用情况的趋势。

1. 根据您的需求，您可以按数据集等进行深入分析。

## 在Report Builder中创建数据块 {#arb}

在Report Builder中， [创建一个数据块](/help/report-builder/create-a-data-block.md) 对于每个数据视图，对其求和。

## 在CJA API中创建自动报表 {#api-report}

1. 使用 [CJA报表API](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) 运行所有事件数据的报告， **每个连接**. 设置此设置以便报表运行

   * 每月第一个星期五。
   * 回到您当前CJA合同的第一天。

   这将使您能够很好地了解每月使用情况的趋势。 它将为您提供所有CJA连接的总行数。

1. 使用Excel进一步自定义此报表。

## 通过定义滚动数据窗口来管理您的使用情况 {#rolling}

要管理您的使用情况，请 [连接UI](/help/connections/create-connection.md) 允许您在连接级别将CJA数据保留定义为以月（1个月、3个月、6个月等）为单位的滚动窗口。

主要好处是，您只需存储或报告适用且有用的数据，并且可删除不再有用的旧数据。它可以帮助您保持在合同限制范围内，并减少超出预期成本的风险。

如果您保留默认值（未选中），则保留期将被 Adobe Experience Platform 数据保留设置所取代。如果您在 Experience Platform 中有 25 个月的数据，那么 CJA 将通过回填获取 25 个月的数据。如果您在 Platform 中删除了其中的 10 个月，则 CJA 将保留剩余的 15 个月。

数据保留基于事件数据集时间戳并且仅适用于事件数据集。由于没有适用的时间戳，因此配置文件或查找数据集不存在滚动数据窗口设置。但是，如果您的连接包括任何配置文件或查找数据集（一个或多个事件数据集除外），则该数据将保留相同的时段。

