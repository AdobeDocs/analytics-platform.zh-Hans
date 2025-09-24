---
title: 配置Experience Platform
description: 了解如何为Experience Platform Data Mirror for Customer Journey Analytics配置架构和数据集
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta 版"
exl-id: 87593d7d-9456-48f8-8d39-5c3d95fe51ec
source-git-commit: b585187f112c2081a8e51bd84d9f95e75ceebdc3
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 3%

---

# 配置Experience Platform

{{release-limited-testing}}

适用于Customer Journey Analytics的Experience Platform Data Mirror功能要求正确配置多个Experience Platform组件：

* 架构
* 数据集
* 源连接器

查找在配置每个组件时应考虑的详细信息。

## 架构

您需要创建基于模型的架构，以便为要镜像的数据仓库本机表建模。 构造基于模型的架构时，请确保满足以下要求：

* 在系统提示输入基于模型的架构类型时，请确保选择手动选项。
* 为数据类型选择适当的架构。 请注意，Data Mirror功能主要用于时间序列数据（例如事件数据）。

* 定义架构中的字段及其属性
* 在基于模型的架构中配置字段的必需属性：

   * 主键
   * 版本标识符
   * 时间戳标识符（用于时间序列数据）。

## 数据集

您可以提前为架构设置数据集，或在设置源连接器时创建数据集。
当您提前创建数据集或选择数据集时，请确保数据使用您之前创建的基于模型的[架构](#schema)。


## 源连接器

要设置到受支持Data Warehouse本机解决方案的源连接器，您可以使用源工作流引导您完成设置。 该工作流包含以下步骤：

### 身份验证

有关针对支持的Data Warehouse本机解决方案的身份验证，请参阅相关的Experience Platform文档：

* [Azure数据库](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/connectors/databases/databricks)
* [Google BigQuery](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/connectors/databases/bigquery)
* [Snowflake](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/connectors/databases/snowflake)


### 选择数据

成功连接到Data Warehouse本机解决方案后，从要用于数据镜像的Data Warehouse本机解决方案中选择表。 选择后，将显示数据内容的预览。


### 数据流详细信息

确保启用变更数据捕获。 您会看到一个信息面板，其中说明了变更数据捕获的要求。

指定新的或现有的数据集，该数据集基于您之前创建的基于模型的架构。 在数据流详细信息界面中指定并选择其他选项。


### 映射

将Data Warehouse本机解决方案中表的字段映射到您为基于模型的架构指定的字段。


### 日程计划

定义一个计划，将数据从Data Warehouse本机解决方案中的表镜像到Experience Platform中的数据集。


### 请查看

查看支持数据镜像和变更数据捕获的数据仓库本机解决方案的源连接器的设置。


完成源连接器的设置后，将创建一个数据流。 从那时起，数据仓库本机解决方案中的数据更改（插入、更新、删除）就会镜像到指定的数据集。


>[!MORELIKETHIS]
>
>[Data Mirror快速入门指南：镜像并使用基于模型的数据](model-based.md)
>
