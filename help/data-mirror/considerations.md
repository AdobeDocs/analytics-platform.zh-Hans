---
title: Data Mirror注意事项
description: 了解在Data Warehouse本机解决方案和Customer Journey Analytics之间同步数据时要考虑的其他事项。
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta 版"
hide: true
source-git-commit: 80083aad28e6efd0d9498264cb540d9f2898f2bc
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 1%

---

# Experience Platform Data Mirror注意事项

本文介绍了在设置Data Mirror数据集时应考虑的因素。

## 源表的新列

当在启用了CDC的数据镜像数据集的源表中添加新列时，该更改可能会触发所有现有行的更新。 这些更新将通过CDC作为更改进行处理，CDC将：

* 从进度的角度来看，其行为可以像完全表重写一样。
* 会显着增加摄取量，这可能会导致更新超过您的摄取授权。

源表中列的建议策略：

* 确保最初定义了所有相关列。
* 映射您最初可能认为需要的每个列。

如果要添加新列，根据是否需要追溯回填，可以选择以下两个选项：

* 追溯回填：

   * 删除当前数据集。
   * 使用更新的列再次配置连接器。

  这可以确保更加有效和及时地回填数据。

* 无追溯回填：

   * 在源表中添加该列。
   * 在目标数据集架构中添加列。
   * 更新映射以包含从源表到目标数据集的新字段（列）。

此策略：

* 避免以后代价高昂的架构演变（添加列时进行批量更新）。
* 与以后添加或修改列时相比，保持更改卷的可预测性更高。
* 有助于限制外部数据库端的潜在计算成本，因为数据仓库可能会将新列解释为所有行的更新。


## Privacy Service

与现在处理非关系架构的隐私请求一样，隐私请求也需要发生，因为隐私请求与数据的结构无关。

从外部关系架构镜像的数据将成为Adobe生态系统的一部分，并可在整个生态系统内共享，例如通过Customer Journey Analytics Audience Publishing共享。 提交隐私请求可确保在整个Adobe生态系统中正确处理身份和相关数据。

因此，隐私请求不应仅限于镜像的数据集，还应涉及对外部数据库中的源数据的更新。

## 卫生行为

保健服务在&#x200B;*主标识*&#x200B;上运行，但镜像的外部数据库中的表具有&#x200B;*主键*，而不是主标识。

主标识与主键之间差异的后果是，不能对这些关系表直接执行卫生删除。 因此，您必须：

* 在数据仓库解决方案中删除其各自源表中的数据，并确保删除操作通过CDC（或手动更改列）进行。
* 将任何基于下游XDM的数据集的卫生和隐私请求连同身份信息提交到Adobe（例如：Customer Journey Analytics视图、Real-Time Customer Data Platform数据集、Adobe Journey Optimizer专属数据集等）。

主标识和主键之间的区别引入了共享责任模型：

* Adobe会在存在身份的地方处理卫生问题。
* 作为客户，您有责任将源数据库中的卫生流程与提交到Adobe的卫生请求保持一致。

## 治理差异

在XDM [架构](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/schema/composition)和基础概念（如[字段组](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/schema/composition#field-group)）中，字段组中定义的[字段](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/schema/composition#field)将其标签传播到使用该字段组的所有数据集。 例如，字段组`identities`中的电子邮件字段`emailID`在所有使用字段组`identities`的数据集中标记为相同。

在关系模式中，列名是独立的。 表`customers`中名为`email`的列与表`prospects`中名为`email`的列独立且不同。 此行为意味着标签（如DULE使用标签、策略）必须单独应用于镜像数据集中的字段。 根据以上示例，您需要将标签同时应用于`customers`数据集中的`email`字段和`prospects`数据集中的`email`字段。

治理差异具有以下影响：

* 更多手动管理和配置工作适合您这样的客户。
* 您可能需要明确的指导，因此您不会认为通过字段组进行一次性标签设置足以进行适当治理。

## 拼接

关系架构在拼接方面具有以下注意事项：

* 部分支持基于图形的拼合。 无法为配置文件/为图表贡献内容启用关系架构。
* 完全支持基于字段的拼合。


## 系统键和字段

以下注意事项适用于系统键和字段：

* 主键、版本描述符和时间戳描述符必须是关系XDM架构中的根级别字段。 在引入期间使用[字段映射](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema)来支持此要求。
* 您可以在[映射阶段](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema)中忽略相应的源字段。
