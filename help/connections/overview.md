---
title: Customer Journey Analytics连接概述
description: 了解 Customer Journey Analytics 中的连接。
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 93%

---

# 连接概述

通过连接，Customer Journey Analytics 产品管理员可以定义摄取哪些 [!DNL &#x200B; Experience Platform] 数据源，例如事件、查找、轮廓和摘要数据集。连接是 Customer Journey Analytics 的基础，它决定了您可以在[数据视图](/help/data-views/data-views.md)中将其定义为维度或量度的数据（字段）的可用性。

>[!IMPORTANT]
>
>您可以将多个 [!DNL Experience Platform] 数据集合并到单个连接中。


## 连接工作流程

![连接工作流程](assets/connection-workflow.png)

>[!BEGINSHADEBOX]

观看演示视频的![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [连接到数据源](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/connections/connecting-customer-journey-analytics-to-data-sources-in-platform){target="_blank"}。

>[!ENDSHADEBOX]

从较高层面看，连接工作流程允许您：

| 界面 | 描述 |
|:---:|---|
| ➊ | 从连接管理器管理 Customer Journey Analytics 的[连接和总体使用情况](manage-connections.md)。 |
| ➋ | [检查连接的详细信息](manage-connections.md#connection-details)，例如摄取、跳过或删除的数据集记录。 |
| ➌ | [创建或编辑连接的配置](create-connection.md#create-or-edit-a-connection)，例如滚动数据窗口、要使用的沙盒、哪些数据集是连接的一部分，等等。 |
| ➍ | [在连接中添加新数据集](create-connection.md#add-datasets)。您的连接至少应该有一个事件或摘要数据集，但可以包含各种事件、配置文件、查找和多个摘要数据集。 |
| ➎ | 为您添加的数据集[配置设置](create-connection.md#dataset-settings)。您可以确定如何根据一个基于共同人员或基于 [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} 帐户的标识符来链接不同的数据集。 |
| ➏ | [编辑现有数据集的设置](create-connection.md#edit-a-dataset)。您可以在某个后期阶段随时重新访问数据集设置。 |



## 访问控制

对连接管理的访问权限应限制在一个核心管理组中。连接配置对 Customer Journey Analytics 中被引入数据的数量分配具有合同性影响。

>[!MORELIKETHIS]
>
>[访问控制](/help/technotes/access-control.md)。

