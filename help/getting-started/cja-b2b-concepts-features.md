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
source-git-commit: 3812b10e558c1b8a3ee4fe474405543c68433d8e
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 0%

---

# B2B edition概念和功能

{{draft-b2b}}

本文介绍了数据集和容器的一般概念和功能，以及Customer Journey Analytics的标准和B2B edition之间的差异。

数据集是连接的源。 在设置连接时，您需要将数据集定义为连接的一部分。

容器是Customer Journey Analytics中使用的一种，用于支持和促进过滤器、计算量度和高级分析功能等功能。




## 标准容器

Customer Journey Analytics的&#x200B;*standard*&#x200B;版本是围绕三个容器的概念生成的：人员、会话和事件。 在标准Customer Journey Analytics设置中，这些相关的容器是根据您的设置隐式生成的。

在配置数据视图时，您可以重新定义这些容器的命名方式，但从概念上讲，标准版本使用基于人员的容器层次结构。

![B2C](assets/b2c-containers.svg){zoomable="yes"}

在连接中，您添加事件、配置文件和查找数据集，并选择要用于定义这些数据集之间的连接的身份。 作为连接的一部分，会自动生成基于人员的容器层次结构。 在该层次结构中，会话容器由数据视图中的[会话设置](/help/data-views/session-settings.md)定义。


## B2B容器

在Customer Journey Analytics B2B edition中，帐户容器将添加到生成的容器列表中。  您还可以选择配置生成其他容器，如Global Account 、 Purching Group和Opportunity。

![B2B](assets/b2b-containers.svg){zoomable="yes"}

在此连接中，您可以添加Event 、 Account 、 Global Account 、 Opportunity 、 Purching Group和其他查找数据集。 您可以选择帐户作为连接的主ID，以便使用基于帐户的标识来定义数据集之间的连接。 作为连接的一部分，会自动生成基于帐户的容器层次结构。 在该层次结构中，人员容器和事件容器之间的会话容器由数据视图中的[会话设置](/help/data-views/session-settings.md)定义。 此外，当前不支持会话容器，例如介于帐户和事件之间的容器。

商机、采购组和人员都是帐户容器的同级容器。 有关说明和基本用法，请参阅下表。

| B2B容器 | 描述<br/>基本用例 |
|---|---|
| 帐户 | 作为您业务的客户或潜在客户的公司。 这可以是大型组织的子公司或分部。 帐户表示您要销售的目标组织以及要在该组织层跟踪的组织。 |
| 全局帐户（可选） | 一组关联公司的顶级母公司。 全局帐户没有母公司，但可能有属于该全局帐户的子公司或部门。 如果在设置连接时同时启用了帐户字段和全局帐户字段中的功能，则没有父或子帐户的帐户应同时在“帐户”字段和全局帐户字段中列出。 |
| 机会（可选） | 一起销售的产品和服务集合。 销售机会通常涉及销售周期的各个阶段，以销售结束。<br>您将使用销售机会数据来衡量销售漏斗中的机会进展。 例如，提供从业务机会阶段3移至阶段4的排名最前的业务机会的详细信息的报表。 |
| 购买组（可选） | 组织内参与购买产品或服务的决策过程的人员集合。 <br/>您将使用购买群组数据通过促销活动管理来跟踪购买群组。 例如，构建关键购买群体的受众区段。<br/>您最可能希望从购买组查找个人资料数据，以便可以报告购买组中的人员。 |
| 人员 | 个人，通常通过与公司进行交互的唯一电子邮件地址进行标识。 <br/>您将使用个人资料数据来识别为帐户工作的人员。 例如：定向某个帐户中已注册会议的所有人员。 |


## 按容器或字段匹配

在Customer Journey Analytics中定义连接时，可以为每个记录（用户档案或查找）数据集定义，无论该数据集是由容器匹配还是由字段匹配。

### 按容器匹配

如果记录数据集与容器匹配（例如购买组），则在用户界面中，该记录数据集将被视为用户档案数据集类型和用户档案数据集。

### 按字段匹配

如果记录数据集与字段匹配（例如，营销列表成员），则记录数据集将被视为查询数据集类型，并在用户界面中被视为查询数据集。



## 报告基于人员和帐户的数据

如果要报告基于人员的容器（和人员身份）和基于帐户的容器（和帐户身份），则应在Customer Journey Analytics中设置两个单独的连接。 一个连接是选择人员作为主ID，另一个连接是选择帐户作为主ID。 Customer Journey Analytics不支持来自同一容器的基于人员和基于帐户的报表。
