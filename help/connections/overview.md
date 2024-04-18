---
title: Customer Journey Analytics 连接概述
description: 了解 Customer Journey Analytics 中的连接。
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: dc3a109f162adfe48f621ba3ece95fedead3c6e1
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 55%

---

# 连接概述

连接允许Customer Journey Analytics产品管理员与其他用户建立连接 [!DNL Adobe Experience Platform] 数据源，例如事件、查找和配置文件数据集。 这些连接支持将连接中的数据集成到派生的数据视图中。连接是CJA的基础，创建自 [!DNL Experience Platform] 源数据集。 对连接的访问还允许您查看连接管理器，在其中可以查看组成连接的基础数据集，以及进行关键的编辑和配置选择。

我们建议仅允许核心管理组访问连接管理。连接级别的配置与用于Customer Journey Analytics数据的卷分配的合同有关。

以下是一段视频概述：

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## 所需权限

要创建 Customer Journey Analytics 连接，您需要 [Adobe Admin Console](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html) 中的以下权限：

Adobe Experience Platform：
* 数据建模：查看架构，管理架构
* 数据管理：查看数据集，管理数据集
* 数据摄取：管理源
* 查看标识命名空间

Customer Journey Analytics
* 产品管理员访问

>[!IMPORTANT]
>
>您可以将多个 [!DNL Experience Platform] 数据集合并到单个连接中。
