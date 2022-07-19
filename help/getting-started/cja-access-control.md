---
title: CJA访问控制
description: 了解创建连接、添加数据集、创建数据视图等的访问控制要求。
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 13513561ec288c1f4ab69128769cd0e7c059e44b
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 91%

---


# CJA访问控制

要创建连接、添加数据集等，您需要在 [Admin Console](https://adminconsole.adobe.com/enterprise/) 中具有以下权限：

* 要访问 Customer Journey Analytics 或建立连接，您必须作为管理员，添加到 **Admin Console** 的 [Customer Journey Analytics 产品](https://adminconsole.adobe.com/enterprise/)中。产品管理员享有以下权限：
   * 创建/更新/删除连接或数据视图
   * 更新/删除项目、过滤器、计算量度或其他用户创建的过滤器
   * 将工作区项目共享给所有用户
* 仅在 Customer Journey Analytics 中担任产品管理员不足以创建、更新或删除连接。要创建与 Experience Platform 数据集的连接，您还需要取得 Experience Platform 权限。具体而言，您必须属于授予您以下权限的 **Experience Platform 产品用户档案**：
   * 查看架构
   * 管理架构
   * 查看身份命名空间
   * 查看数据集

有关 Experience Platform 权限的更多信息，请参阅 [Adobe Experience Platform 中的访问控制](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html)。

>[!NOTE]
>
>您不能像在传统的 Adobe Analytics 中那样，在 Customer Journey Analytics 中授予或拒绝对单个量度或维度的权限。 量度和维度可以在[数据视图](/help/data-views/data-views.md)中修改，因此可能会在 CJA 中出现更改，这也会追溯性地更改报告。

## 用户访问

Customer Journey Analytics 中的非产品管理员（用户）无法查看数据视图或连接，但可以创建过滤器、项目和计算量度。