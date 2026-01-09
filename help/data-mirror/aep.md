---
title: 配置Experience Platform
description: 了解如何为Experience Platform Data Mirror for Customer Journey Analytics配置架构和数据集
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta 版"
exl-id: 87593d7d-9456-48f8-8d39-5c3d95fe51ec
source-git-commit: cd3baec708f1811a7cbc37dfe0a9c3af75eb97c3
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 2%

---

# 配置Experience Platform

{{release-limited-testing}}

适用于Customer Journey Analytics的Experience Platform Data Mirror需要正确配置多个Experience Platform组件：

* 架构
* 数据集
* 源连接器

查找在配置每个组件时应考虑的详细信息。

## 架构

您需要创建一个[关系架构](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/relational){target="_blank"}，该架构是要镜像的数据仓库本机表。 构造关系架构时，请确保满足以下要求：

* 在提示输入关系架构类型时，请确保选择手动选项。
* 为数据类型选择适当的架构。 请注意，Experience Platform Data Mirror主要用于时间序列数据（例如，事件数据），但也可用于基于记录的数据（查找和配置文件）。

* 定义架构中的字段及其属性
* 配置关系架构中字段的必需属性：

   * **主键**。
   * **版本描述符**，必须将其配置为序列号（整数字段类型）或日期时间字段类型。 当您使用DateTime字段类型时，版本描述符定义数据修改的时间戳，例如，包含上次修改的时间戳。
   * **时间戳描述符**（用于时间序列数据），它定义捕获事件时不可变的时间戳。 基于记录的关系架构不需要时间戳描述符。



## 数据集

您可以提前为架构设置数据集，或在设置源连接器时创建数据集。
当您提前创建数据集或选择数据集时，请确保数据使用您之前创建的关系[架构](#schema)。


## 源连接器

要设置到受支持Data Warehouse本机解决方案的源连接器，您可以使用源工作流引导您完成设置。 该工作流包含以下步骤：

### 身份验证

有关针对支持的Data Warehouse本机解决方案的身份验证，请参阅相关的Experience Platform文档：

* [Azure数据库](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/databricks)
* [Google BigQuery](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/bigquery)
* [Snowflake](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/databases/snowflake)


### 选择数据

成功连接到Data Warehouse本机解决方案后，从要用于数据镜像的Data Warehouse本机解决方案中选择表。 选择后，将显示数据内容的预览。


### 数据流详细信息

确保启用变更数据捕获。 您会看到一个信息面板，其中说明了变更数据捕获的要求。

指定基于之前创建的关系架构的新数据集或现有数据集。 在数据流详细信息界面中指定并选择其他选项。


### 映射

将Data Warehouse本机解决方案中表的字段映射到您为关系架构指定的字段。


### 日程计划

定义一个计划，将数据从Data Warehouse本机解决方案中的表镜像到Experience Platform中的数据集。


### 审核

查看支持数据镜像和变更数据捕获的数据仓库本机解决方案的源连接器的设置。


完成源连接器的设置后，将创建一个数据流。 从那时起，数据仓库本机解决方案中的数据更改（插入、更新、删除）就会镜像到指定的数据集。


>[!MORELIKETHIS]
>
>[Data Mirror快速入门指南：镜像并使用关系数据](relational.md)
>[Data Mirror (Experience Platform文档)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>[关系架构(Experience Platform文档)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/relational)
