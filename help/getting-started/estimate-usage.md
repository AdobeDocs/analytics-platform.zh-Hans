---
title: 评估和管理CJA使用情况
description: 显示两种估计使用情况的方法和一种管理使用情况的方法。
role: Admin
feature: CJA Basics
source-git-commit: 2bcf1f805a54581f13f7d08b9ef034535d7959b1
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 42%

---


# 评估和管理CJA使用情况

要了解CJA的用法，您可以使用2种方法：

* 为每个连接添加事件数据行。 (请参阅 **预估连接大小** 下面)
* 使用Analysis Workspace报告上个月的事件。 (请参阅 **使用所有事件数据创建工作区项目** )。

要管理CJA的使用情况，请执行以下操作：

* 使用CJA API。 (请参阅 **在CJA API中创建报表** )。

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

1. 在工作区中创建项目之前， [创建数据视图](/help/data-views/create-dataview.md) 从您的所有连接中提取数据且未应用任何过滤器的数据。 换句话说，它包含您的所有数据。

1. 在工作区中，创建新项目并提取所有事件(从 **[!UICONTROL 量度]** 下拉列表)。

   ![事件](assets/events-usage.png)

1. 执行此操作

## 在CJA API中创建报表 {#api-report}

使用 [CJA报表API](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) 运行所有事件数据的报告。