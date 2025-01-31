---
title: Customer Journey Analytics 连接概述
description: 了解 Customer Journey Analytics 中的连接。
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: a2262e446a15ee58be2f3f674c77223368fc8f76
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 100%

---

# 连接概述

利用连接，Customer Journey Analytics 产品管理员可以与不同的[!DNL Adobe Experience Platform] 数据源（例如事件、查找和轮廓数据集）建立连接。这些连接支持将连接中的数据集成到派生的数据视图中。连接是 CJA 的基础，它是从[!DNL Experience Platform] 源数据集创建的。通过访问连接，还可以查看连接管理器，在其中可以查看构成连接的基础数据集，以及进行重要的编辑和配置选择。

我们建议仅允许核心管理组访问连接管理。连接级别的配置将对引入 Customer Journey Analytics 中的数据量分配产生合同性影响。

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target=&#34;_blank&#34;} for a demo video.

>[!ENDSHADEBOX]

-->

## 所需权限

要创建 Customer Journey Analytics 连接，您需要以下权限。有关权限的更多详细信息，请参阅 [Adobe Admin Console](https://helpx.adobe.com/cn/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html) 和 [Adobe Experience Platform 权限](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/access-control/home)文档。

### 在 Adobe Admin Console 中：

* Customer Journey Analytics：产品管理员
* Adobe Experience Platform：已添加到名为 *AEP-Default-All-Users* 的产品轮廓中

### 在 Adobe Experience Platform 权限内：

* 数据建模：查看架构，管理架构
* 数据管理：查看数据集，管理数据集
* 数据摄取：管理源
* Identity Management：查看标识命名空间
* 沙盒：相关 Customer Journey Analytics 连接中使用的沙盒

>[!IMPORTANT]
>
>您可以将多个 [!DNL Experience Platform] 数据集合并到单个连接中。
