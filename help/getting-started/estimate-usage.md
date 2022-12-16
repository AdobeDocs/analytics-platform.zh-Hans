---
title: 评估和管理CJA使用情况
description: 显示两种估计使用情况的方法和一种管理使用情况的方法。
role: Admin
feature: CJA Basics
source-git-commit: 58d582b693708f883842fb6a18cc57d481f2b2ab
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 68%

---


# 评估和管理CJA使用情况

要了解CJA的用法，您可以使用2种方法：

* 为每个连接添加事件数据(请参阅 **预估连接大小** 下面)
* 使用Analysis Workspace...

要管理CJA的使用情况，请执行以下操作：

* 使用CJA API

## 预估连接大小 {#estimate-size}

您可能需要知道当前有多少行事件数据位于 [!UICONTROL Customer Journey Analytics]. 要准确了解贵组织的事件数据记录（数据行）使用情况，请执行以下操作 **对于贵组织创建的每个连接**.

>[!NOTE]
>
>由于Adobe在当天运行您的最新使用情况报表，因此请在每月的第一个星期五执行此操作。

1. 在 [!UICONTROL Customer Journey Analytics] 中，单击&#x200B;**[!UICONTROL 连接]**&#x200B;选项卡。

   您现在可以看到所有当前连接的列表。

1. 单击每个连接名称以转到连接管理器。

1. 将 **[!UICONTROL 可用事件数据的记录]** ，用于创建的所有连接。 （根据连接的大小，数字可能需要一段时间才能显示。）

   ![](assets/event-data.png)

1. 获得所有事件数据行的总和后，在您的公司与 Adobe 签署的 Customer Journey Analytics 合同中查找“数据行”权利。

   这可让您获得销售订单中授权的最大数据行数。 如果步骤 3 产生的数据行数大于此数值，则表示您出现过量情况。

1. 要解决这种情况，您有以下几个选项：

   * 更改[数据保留设置](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=zh-Hans#set-rolling-window-for-connection-data-retention)。
   * [删除任何未使用的连接](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hans#implications-of-deleting-data-components)。
   * [在 AEP 中删除数据集](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hans#implications-of-deleting-data-components)。
   * 请联系您的 Adobe 客户经理以获得额外容量的许可。
