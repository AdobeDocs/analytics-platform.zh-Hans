---
title: Customer Journey Analytics 连接概述
description: 了解 Customer Journey Analytics 中的连接。
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: e4ddb98b800457e407bb414ed4929c5d5018cf30
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 10%

---

# 连接概述

连接允许Customer Journey Analytics产品管理员与其他[!DNL Adobe Experience Platform]数据源（如事件、查找、配置文件和摘要数据集）建立连接。 通过这些连接，可将来自连接的数据集成到派生数据视图。 连接是Customer Journey Analytics的基础，是从[!DNL Experience Platform]源数据集创建的。

>[!IMPORTANT]
>
>您可以将多个 [!DNL Experience Platform] 数据集合并到单个连接中。


## 连接工作流程

![连接工作流](assets/connection-workflow.png)

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

在概览中，连接工作流允许您：

| 界面 | 描述 |
|:---:|---|
| ➊AEM | 从连接管理器中[管理您的连接和总体使用情况](manage-connections.md) Customer Journey Analytics。 |
| ➋AEM | [检查连接](manage-connections.md#connection-details)的详细信息，如已摄取、已跳过或删除的数据集记录。 |
| ➌AEM | [创建或编辑连接的配置](create-connection.md#create-or-edit-a-connection)，如滚动数据窗口，以及哪些数据集是连接的一部分。 |
| ➍AEM | [将数据集添加到连接](create-connection.md#add-datasets)。 您的连接应至少具有一个事件或摘要数据集，但可以包含各种事件、个人资料、查找和摘要数据集。 |
| ➎AEM | [为您添加的数据集配置设置](create-connection.md#dataset-settings)。 因此，您可以决定如何根据基于通用人员的标识符或基于[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}帐户的标识符来链接不同的数据集。 |
| ➏AEM | [编辑现有数据集](create-connection.md#edit-a-dataset)的设置。 您始终可以在以后的阶段重新访问数据集设置。 |



## 访问控制

对连接管理的访问应限制到核心管理组。 连接配置涉及与引入Customer Journey Analytics的数据的卷分配有关的合同问题。

>[!MORELIKETHIS]
>
>[访问控制](/help/technotes/access-control.md)。

