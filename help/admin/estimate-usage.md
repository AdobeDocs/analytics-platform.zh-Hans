---
title: 查看和管理您的 Customer Journey Analytics 使用情况
description: 展示了两种估算使用情况的方法和一种管理使用情况的方法。
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: ff71d21235bd37da73c0b6c628c395da6cda7659
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 72%

---

# 查看和管理您的 Customer Journey Analytics 使用情况

要查看您的Customer Journey Analytics使用情况，您可以使用多种方法：

* 为每个连接添加事件数据行。请参阅下面的 [估计连接大小]（#estimate size）。这是查看特定时间戳的每个连接的事件行数据的简单方法。
* 通过三种方式查看您的使用情况，下面对每种方式进行了更详细的描述：
   * 使用 Analysis Workspace 报告的上个月的事件。
   * 使用 Report Builder 报告的上个月的事件。
   * 使用Customer Journey AnalyticsAPI创建自动报表。

要管理Customer Journey Analytics使用情况，请执行以下操作：

* 定义滚动数据窗口。

## 估计连接大小 {#estimate-size}

您可能需要知道 [!UICONTROL Customer Journey Analytics] 中当前有多少行事件数据。要准确了解贵组织的事件数据记录（数据行）使用情况，**对于贵组织创建的每个连接**，请执行以下操作。

>[!NOTE]
>
>在每个月的第一个星期五执行此操作，因为 Adobe 会在那天运行您的最新使用报告。

1. 在 [!UICONTROL Customer Journey Analytics] 中，单击&#x200B;**[!UICONTROL 连接]**&#x200B;选项卡。

   您现在可以看到所有当前连接的列表。

1. 单击每个连接名称以转到连接管理器。

1. 添加组织创建的每个连接的&#x200B;**[!UICONTROL 可用事件数据记录]**。（根据连接的大小，数字可能需要一段时间才能显示。）

   ![](./assets/event-data.png)

   >[!CAUTION]
   >
   >   此计数仅适用于事件数据，不适用于配置文件或查找数据。如果您有配置文件和查找数据，则计数会略高。但是，目前无法在用户界面中报告配置文件和查找数据的使用情况。此功能定于 2023 年推出。

1. 获得所有事件数据行的总和后，在您的公司与 Adobe 签署的 Customer Journey Analytics 合同中查找“数据行”权利。

   这可让您获得销售订单中授权的最大数据行数。 如果步骤 3 产生的数据行数大于此数值，则表示您出现过量情况。

1. 要解决这种情况，您有以下几个选项：

   * 更改[数据保留设置](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=zh-Hans#set-rolling-window-for-connection-data-retention)。
   * [删除任何未使用的连接](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hans#implications-of-deleting-data-components)。
   * [删除Adobe Experience Platform中的数据集](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hans#implications-of-deleting-data-components).
   * 请联系您的Adobe客户团队以许可额外容量。

## 使用所有事件数据创建工作区项目 {#workspace-event-data}

此方法允许您对使用数据以及使用历史记录进行更深入的分析。

1. 在工作区中创建项目之前，[为每个连接创建一个数据视图](/help/data-views/create-dataview.md)，不应用任何过滤器。

>[!WARNING]
>
>    不要创建包含所有数据的新连接只是为了测量使用情况，因为这实际上会使您的使用量翻倍。

1. 在工作区中，根据每个数据视图创建新项目并拉入所有事件(从 **[!UICONTROL 量度]** 下拉列表)，从当前Customer Journey Analytics合同的第一天开始，开始每月第一个星期五。

   ![事件](./assets/events-usage.png)

   这将使您很好地了解每月的使用趋势。

1. 根据您的需要，您可以按数据集等深入分析。

## 在 Report Builder 中创建数据块 {#arb}

在 Report Builder 中，[为每个数据视图创建一个数据块](/help/report-builder/create-a-data-block.md)，然后将它们相加。

## 在Customer Journey AnalyticsAPI中创建自动报表 {#api-report}

1. 使用 [Customer Journey Analytics报表API](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) 要对您的所有事件数据运行报告， **每个连接**. 设置它以便报告运行

   * 每个月的第一个星期五。
   * 回到您当前Customer Journey Analytics合同的第一天。

   这将使您很好地了解每月的使用趋势。它会为您提供所有Customer Journey Analytics连接上的总行数。

1. 使用 Excel 进一步自定义此报告。

## 通过定义滚动数据窗口来管理您的使用情况 {#rolling}

要管理您的使用情况，请 [连接用户界面](/help/connections/create-connection.md) 允许您在连接级别将Customer Journey Analytics数据保留定义为以月计的滚动时段（1个月、3个月、6个月等）。

主要好处是，您只需存储或报告适用且有用的数据，并且可删除不再有用的旧数据。它可以帮助您保持在合同限制范围内，并减少超出预期成本的风险。

如果您保留默认值（未选中），则保留期将被 Adobe Experience Platform 数据保留设置所取代。如果您具有25个月的数据Experience Platform，则Customer Journey Analytics将通过回填获取25个月的数据。 如果您在Platform中删除了其中的10个月，则Customer Journey Analytics将保留剩余的15个月。

数据保留基于事件数据集时间戳并且仅适用于事件数据集。由于没有适用的时间戳，因此配置文件或查找数据集不存在滚动数据窗口设置。如果您的连接包括任何配置文件或查找数据集，则由于它们与事件数据集相连，因此会根据事件数据集时间戳上的数据保留设置将数据保留在Customer Journey Analytics中。

