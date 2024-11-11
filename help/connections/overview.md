---
title: Customer Journey Analytics 连接概述
description: 了解 Customer Journey Analytics 中的连接。
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 2f78905c2a1e94174a52269becc15474baf59f71
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 69%

---

# 连接概述

利用连接，Customer Journey Analytics 产品管理员可以与不同的[!DNL Adobe Experience Platform] 数据源（例如事件、查找和配置文件数据集）建立连接。这些连接支持将连接中的数据集成到派生的数据视图中。连接是 CJA 的基础，它是从[!DNL Experience Platform] 源数据集创建的。通过访问连接，还可以查看连接管理器，在其中可以查看构成连接的基础数据集，以及进行重要的编辑和配置选择。

我们建议仅允许核心管理组访问连接管理。连接级别的配置将对引入 Customer Journey Analytics 中的数据量分配产生合同性影响。

以下是一段视频概述：

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## 所需权限

要创建Customer Journey Analytics连接，您需要以下权限。 有关权限的其他详细信息，请参阅[Adobe Admin Console](https://helpx.adobe.com/cn/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html)和[Adobe Experience Platform权限](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home)的文档。

### 在Adobe Admin Console中：

* Customer Journey Analytics：产品管理员
* Adobe Experience Platform：已添加到名为&#x200B;*AEP-Default-All-Users*&#x200B;的产品配置文件

### 在Adobe Experience Platform权限内：

* 数据建模：查看架构，管理架构
* 数据管理：查看数据集，管理数据集
* 数据摄取：管理源
* Identity Management：查看身份命名空间
* 沙盒：相关Customer Journey Analytics连接中使用的沙盒

>[!IMPORTANT]
>
>您可以将多个 [!DNL Experience Platform] 数据集合并到单个连接中。
