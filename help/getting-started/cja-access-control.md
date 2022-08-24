---
title: CJA 访问控制
description: 了解CJA中三个访问级别的访问控制要求。
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: ed1885b4dd560bdbce66a1fa2bad1bcd822a3ea3
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 46%

---

# CJA 访问控制

Customer Journey Analytics(CJA)受三个访问级别或三个角色的约束：产品管理员角色、产品配置文件管理员角色和用户级别访问权限。 本主题将更详细地介绍这些角色。

## 产品管理员角色

产品管理员有权在CJA中完成任何必需的任务。 您必须作为产品管理员添加到 **Customer Journey Analytics产品配置文件** 在 [Admin Console](https://adminconsole.adobe.com/enterprise/) 在Customer Journey Analytics>管理员选项卡>添加管理员下。 产品管理员享有以下权限：

* 创建/更新/删除连接或数据视图
* 更新/删除项目、过滤器、计算量度或其他用户创建的过滤器
* 将工作区项目共享给所有用户

仅在 Customer Journey Analytics 中担任产品管理员不足以创建、更新或删除连接。 要创建与 Experience Platform 数据集的连接，您还需要取得 Experience Platform 权限。具体而言，您必须属于授予您以下权限的 **Experience Platform 产品用户档案**：

* 数据建模：查看架构，管理架构
* 数据管理：查看数据集，管理数据集
* 数据摄取：管理源
* 查看标识命名空间

有关 Experience Platform 权限的更多信息，请参阅 [Adobe Experience Platform 中的访问控制](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html)。

## 产品配置文件管理员角色

此角色与产品管理员类似，但其作用范围更为有限。 产品配置文件是一组权限。 例如，产品配置文件管理员可以为产品配置文件的成员授予对所有或特定数据视图的访问权限。 对于报表工具，这些管理员可以添加以下权限：

![管理控制台权限](assets/permissions.png)

## 用户级别访问

Customer Journey Analytics中的非产品管理员（用户）无法创建、编辑或查看数据视图或连接。 用户可以在Admin Console中创建具有特殊权限的过滤器、项目、受众和计算量度。

## 工作区项目策划

有关如何在工作区项目级别限制组件（维度、量度、区段、日期范围）以及管理与数据视图关联的更多信息，请参阅 [组织项目](/help/analysis-workspace/curate-share/curate.md).

## 授予对单个量度或维度的访问权限

您不能像在传统的 Adobe Analytics 中那样，在 Customer Journey Analytics 中授予或拒绝对单个量度或维度的权限。 量度和维度可以在[数据视图](/help/data-views/data-views.md)中修改，因此可能会在 CJA 中出现更改，这也会追溯性地更改报告。

