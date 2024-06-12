---
title: Customer Journey Analytics 连接概述
description: 了解 Customer Journey Analytics 中的连接。
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 7a5fa07e3bafa3da5b044ce37299196a006f1d64
workflow-type: ht
source-wordcount: '184'
ht-degree: 100%

---

# 连接概述

利用连接，Customer Journey Analytics 产品管理员可以与不同的[!DNL Adobe Experience Platform] 数据源（例如事件、查找和配置文件数据集）建立连接。这些连接支持将连接中的数据集成到派生的数据视图中。连接是 CJA 的基础，它是从[!DNL Experience Platform] 源数据集创建的。通过访问连接，还可以查看连接管理器，在其中可以查看构成连接的基础数据集，以及进行重要的编辑和配置选择。

我们建议仅允许核心管理组访问连接管理。连接级别的配置将对引入 Customer Journey Analytics 中的数据量分配产生合同性影响。

以下是一段视频概述：

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## 所需权限

要创建 Customer Journey Analytics 连接，您需要 [Adobe Admin Console](https://helpx.adobe.com/cn/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html) 中的以下权限：

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
