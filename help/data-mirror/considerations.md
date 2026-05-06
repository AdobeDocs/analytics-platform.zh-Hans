---
title: Data Mirror注意事项
description: 了解在Data Warehouse本机解决方案和Customer Journey Analytics之间同步数据时要考虑的其他事项。
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta 版"
hide: true
source-git-commit: 93f38f57021bf66cacd700ce6fbc46338fd6a034
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 1%

---

# Experience Platform Data Mirror注意事项

本文介绍了在设置Data Mirror数据集时应考虑的因素。

## 源表的新列

当在启用了CDC的数据镜像数据集的源表中添加新列时，该更改可能会触发所有现有行的更新。 这些更新将通过CDC作为更改进行处理，CDC将：

* 从成本的角度来看，其行为可能类似于完全表重写。
* 可以显着增加摄取量，尤其是任何未来的&#x200B;*更改乘数*&#x200B;定价的情况下（例如，合并操作可能会以更高的速率收费）。

源表中列的建议策略：

* 确保最初定义了大部分（如果不是全部的话）相关列。
* 映射您最初可能认为需要的每个列。

此策略：

* 避免以后代价高昂的架构演变（添加列时进行批量更新）。
* 与以后添加或修改列时相比，保持更改卷的可预测性更高。
* 可能会导致外部数据库端产生一些额外的计算成本，因为数据仓库可能会将所有列解释为更新。

要在外部数据仓库表中处理新列，请执行以下步骤：

1. 使用添加的列创建新架构。
1. 配置将数据引入的新源连接器。
1. 正确加载回填。
1. 使用以后的CDC更改。

这种方法将对双方的影响降至最低。

## Privacy Service

与现在处理非关系架构的隐私请求一样，隐私请求也需要发生，因为隐私请求与数据的结构无关。

从基于关系模式的外部数据镜像到数据集的数据将成为Adobe生态系统的一部分，并且可以通过多种方式共享。 例如，通过受众发布。

因此，隐私请求不应仅限于镜像的数据集，还应涉及对外部数据库中的源数据的更新。

## 卫生行为

保健服务在&#x200B;*主标识*&#x200B;上运行，但镜像的外部数据库中的表具有&#x200B;*主键*，而不是主标识。

主标识与主键之间差异的后果是，不能对这些关系表直接执行卫生删除。 因此，您必须：

* 在数据仓库解决方案中删除其各自源表中的数据，并确保删除操作通过CDC（或手动更改列）进行。
* 将任何基于下游XDM的数据集的卫生和隐私请求连同身份信息提交到Adobe（例如：Customer Journey Analytics视图、Real-Time Customer Data Platform数据集、Adobe Journey Optimizer专属数据集等）。

主标识和主键之间的区别引入了共享责任模型：

* Adobe会在存在身份的地方处理卫生问题。
* 作为客户，您负责将源数据库中自己的卫生流程与提交给Adobe的卫生请求保持一致。

## 治理差异

在XDM [架构](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/schema/composition)和基础概念（如[字段组](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field-group)）中，字段组中定义的[字段](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field)将其标签传播到使用该字段组的所有数据集。 例如，字段组`identities`中的电子邮件字段`emailID`在所有使用字段组`identities`的数据集中标记为相同。

在关系模式中，列名是独立的。 表`customers`中名为`email`的列与表`prospects`中名为`email`的列独立且不同。 此行为意味着标签（如DULE使用标签、策略）必须单独应用于镜像数据集中的字段。 根据以上示例，您需要将标签同时应用于`customers`数据集中的`email`字段和`prospects`数据集中的`email`字段。

治理差异具有以下影响：

* 更多手动管理和配置工作适合您这样的客户。
* 您可能需要明确的指导，因此您不会认为通过字段组进行一次性标签设置足以进行适当治理。
