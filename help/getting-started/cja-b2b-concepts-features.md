---
title: Customer Journey Analytics B2B edition概念和功能
description: Customer Journey Analytics的B2B edition的概念和功能。
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
hide: true
hidefromtoc: true
badgePremium: label="B2B edition"
exl-id: df2cc922-d214-49b9-8fdb-443cc1dac05b
source-git-commit: e16bfa01dd3bedc96a147b2510ba33f4b88b01b9
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 0%

---

# B2B edition概念和功能

{{draft-b2b}}

本文介绍了在Customer Journey Analytics中常用的连接、标识符、容器和数据集等概念。 以及Customer Journey Analytics B2B edition如何在这些概念中添加其他功能。


## 连接和标识符

在Customer Journey Analytics中，您可以选择一个通用标识符（称为人员ID），以将事件数据与其他数据集（如配置文件数据集和查找数据集）相关联。 这种类型的连接称为基于人员的连接，它便于进行基于人员的报告和分析。

在Customer Journey Analytics B2B edition中，您可以在基于人员的连接或基于帐户的连接之间进行选择。 基于帐户的连接便于基于帐户的报告和分析。

* 对于基于人员的连接，请选择“人员”作为主要标识符。 然后，您可以为基于人员的报表配置并设置连接、数据视图和工作区项目。
* 对于基于帐户的连接，请选择“帐户”作为主标识符。 然后，您可以选择为Global Account、Puring Group和Opportunity添加附加容器。 根据您是否添加全局帐户，您的主要标识符是帐户标识符还是全局帐户标识符。


## 容器

在Customer Journey Analytics中，容器是作为连接和数据视图配置的一部分生成的。 容器仅存储标识符，以促进快速高性能地执行分段、划分等功能。

### 标准容器

Customer Journey Analytics基于三个容器的概念而构建：人员、会话和事件。 在配置期间，将隐式生成这些容器。

在配置数据视图时，您可以重新定义这些容器的命名方式，但层次结构和容器之间的关系是预先确定的。 会话容器是根据您在数据视图的[会话设置](/help/data-views/session-settings.md)中定义会话的方式生成的。

![B2C](assets/b2c-containers.svg){zoomable="yes"}


### B2B容器

在Customer Journey Analytics B2B edition中，帐户容器将添加到生成的容器列表中。 您还可以选择配置生成其他容器，如Global Account 、 Purching Group和Opportunity。

容器之间的层次和关系是预定的。 商机、采购组和人员都是帐户容器的同级容器。 在该层次结构中，人员容器和事件容器之间的会话容器是根据您在数据视图的[会话设置](/help/data-views/session-settings.md)中定义会话的方式生成的。 当前不生成并支持其他会话容器，例如帐户容器和事件容器之间的会话容器。 有关B2B容器的说明和基本用法，请参阅下表。

![B2B](assets/b2b-containers.svg){zoomable="yes"}

| B2B容器 | 描述<br/>基本用例 |
|---|---|
| 帐户 | 作为您业务的客户或潜在客户的公司。 该公司可以是大型组织的子公司或部门。 帐户表示您要销售的目标组织以及要在该组织层跟踪的组织。 |
| 全局帐户（可选） | 一组关联公司的顶级母公司。 全局帐户没有母公司，但可能有属于该全局帐户的子公司或部门。 当您在连接中配置了全局帐户容器时，没有父或子公司的帐户应同时列在“帐户”字段和“全局帐户”字段中。 |
| 机会（可选） | 一起销售的产品和服务集合。 在销售周期中，销售机会往往涉及各个阶段，直到销售结束。<br>您将使用数据来测量销售漏斗中的商机进展。 例如，提供从阶段3移至阶段4的热门机会详细信息的报表。 |
| 购买组（可选） | 组织内参与购买产品或服务的决策过程的人员集合。 <br/>您将使用购买群组数据通过促销活动管理来跟踪购买群组。 例如，构建关键购买群体的受众区段。<br/>您最可能希望从购买组查找个人资料数据，以便可以报告购买组中的人员。 |
| 人员 | 个人，通常通过与公司进行交互的唯一电子邮件地址进行标识。 <br/>您将使用个人资料数据来识别为帐户工作的人员。 例如：定向某个帐户中已注册会议的所有人员。 |

>[!IMPORTANT]
>
>* 如果您在基于帐户的连接中&#x200B;**启用了**&#x200B;全局帐户容器，则事件数据集的每条记录都应包含帐户ID和全局帐户ID。 如果没有，则跳过记录。
>* 如果您&#x200B;**未在基于帐户的连接中启用**&#x200B;全局帐户容器，则事件数据集的每条记录都应包含帐户ID。 如果没有，则跳过记录。

## 数据集

当您在Customer Journey Analytics B2B edition中为基于帐户的连接配置[数据集设置](/help/connections/create-connection.md#dataset-settings)时，某些设置的可用选项取决于[数据集类型](/help/connections/create-connection.md#dataset-types)。 例如，您必须：

* 为已为事件数据集配置的每个容器指定标识符。
* 为您的用户档案数据集定义帐户字段或全局帐户字段。
* 为查找数据集定义键以及如何匹配这些键（按字段容器）。

## 按容器或字段匹配

您可以为每个查找数据集定义，无论您是按字段还是按容器匹配数据集。

### 按容器匹配

如果记录数据集按容器使用匹配，则该记录数据集将被视为用户档案数据集类型，并在用户界面中被视为用户档案数据集。 在支持已配置容器的数据集上使用按容器匹配。 例如，购买组数据集。

### 按字段匹配

如果记录数据集使用匹配依据字段，则该记录数据集将被视为查询数据集类型，并在用户界面中被视为查询数据集。 在支持通过查找获得其他详细信息的数据集上使用按字段匹配，例如，营销列表成员数据集或产品详细信息数据集。


## 报告基于人员和帐户的数据

如果要报告基于人员的容器（和人员身份）和基于帐户的容器（和帐户身份），则应在Customer Journey Analytics中设置两个单独的连接。 一个连接是选择人员作为主ID，另一个连接是选择帐户作为主ID。 Customer Journey Analytics不支持从单个容器层次结构中生成基于人员和基于帐户的报表。

