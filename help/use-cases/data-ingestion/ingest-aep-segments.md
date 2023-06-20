---
title: 将Adobe Experience Platform受众引入Customer Journey Analytics
description: 说明如何将Adobe Experience Platform受众纳入Customer Journey Analytics以供进一步分析。
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 52%

---

# 将Adobe Experience Platform受众引入Adobe Customer Journey Analytics

本用例探索了一种将Adobe Experience Platform (Adobe Experience Platform)受众引入Customer Journey Analytics的临时手动方式。 这些受众可能创建于Adobe Experience Platform区段生成器、Adobe Audience Manager或其他工具中，并存储在实时客户档案(RTCP)中。 受众包括一组概要文件 ID，以及任何适用的属性/事件/等。 我们希望将它们带入Customer Journey Analytics工作区进行分析。

## 先决条件

* 访问 Adobe Experience Platform (Adobe Experience Platform)，特别是实时客户档案。
* 创建/管理Adobe Experience Platform架构和数据集的权限。
* 访问Adobe Experience Platform查询服务（以及编写SQL的能力）或其他工具来执行一些轻量级转换。
* 访问 Customer Journey Analytics. 您需要是Customer Journey Analytics产品管理员才能创建/修改Customer Journey Analytics连接和数据视图。
* 能够使用 Adobe API（分段，可选其他）

## 步骤 1：在实时客户档案中选择受众 {#audience}

Adobe Experience Platform [实时客户档案](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans?lang=cn) (RTCP) 允许您通过组合来自多个渠道的数据（包括在线、离线、CRM 和第三方）来查看每个客户的整体视图。

RTCP 中可能已经有来自不同来源的受众。 选择一个或多个受众以摄取到Customer Journey Analytics。

## 步骤 2：为导出创建用户档案合并数据集

为了将受众导出到最终可以添加到Customer Journey Analytics连接的数据集，您需要创建其架构是配置文件的数据集 [合并模式](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=zh-Hans?lang=cn#understanding-union-schemas).

合并模式由多个共享同一类并已启用用户档案的模式组成。 合并模式使您能够看到共享同一类的模式中包含的所有字段的合并。实时客户配置文件使用合并模式创建每个客户的整体视图。

## 步骤 3：通过 API 调用将受众导出到用户档案合并数据集 {#export}

在将受众引入Customer Journey Analytics之前，您需要将其导出到Adobe Experience Platform数据集。 这只能使用分段 API，特别是 [导出作业 API 端点](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=zh-Hans?lang=cn)来完成。

您可以使用所选受众ID创建导出作业，并将结果放入在步骤2中创建的配置文件合并Adobe Experience Platform数据集中。 尽管您可以为受众导出各种属性/事件，但您只需要导出与您将要利用的Customer Journey Analytics连接中使用的人员ID字段匹配的特定用户档案ID字段（请参阅下面的步骤5）。

## 步骤 4：编辑导出输出

导出作业的结果需要转换为单独的用户档案数据集，才能被摄取到Customer Journey Analytics中。  此转换可以通过以下方式完成 [Adobe Experience Platform查询服务](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=zh-Hans?lang=cn)或您选择的其他转换工具进行转换。 我们只需要用户档案ID(与Customer Journey Analytics中的人员ID匹配)和一个或多个受众ID即可在Customer Journey Analytics中生成报表。

然而，标准导出作业包含更多数据，因此我们需要编辑此输出以删除无关数据，并移动一些内容。  此外，在将转换后的数据添加到模式/数据集之前，需要先创建模式/数据集。

以下是用户档案合并数据集中的导出输出示例，在任何编辑&#x200B;**之前**：

![未编辑输出](../assets/export-unedited.png)

请注意以下事项：

* 受众 ID 包含在 `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status` 下。
* 状态必须为“已实现”或“已输入”，但不能为“已退出”。

这是您可以发送到Customer Journey Analytics中的用户档案数据集的格式。

![已编辑输出](../assets/export-edited.png)

以下是需要呈现的数据元素：

* `_aresprodvalidation`字符串字段：指您的组织 ID。 您的会有所不同。
* `personID` 字符串字段：这是配置文件数据集上用于标识人员的标准 XDM 模式字段。 使用导出中的用户档案 ID。
* `audienceMembershipId`字符串字段：导出的受众 ID。  注意：此字段可以根据需要命名（从您自己的模式）。
* 为受众添加一个友好的名称 (`audienceMembershipIdName`)，例如

  ![友好的受众名称](../assets/audience-name.png)

* 如果需要，可以添加其他受众元数据。

## 步骤5：将此配置文件数据集添加到Customer Journey Analytics中的现有连接

您可以 [创建新连接](/help/connections/create-connection.md)，但大多数客户都希望将用户档案数据集添加到现有连接。 受众ID“扩充”了Customer Journey Analytics中的现有数据。

## 步骤6：修改现有（或新建）Customer Journey Analytics数据视图

将 `audienceMembershipId`、`audienceMembershipIdName` 和 `personID` 添加到数据视图中。

## 步骤 7：工作区中的报告

现在，您可以在工作区中报告 `audienceMembershipId`、`audienceMembershipIdName` 和 `personID`。

## 其他说明

* 您应该定期执行此过程，以便在Customer Journey Analytics中不断刷新受众数据。
* 您可以在单个Customer Journey Analytics连接中导入多个受众。 这增加了流程的复杂性，但这是可能的。 为此，您需要对上述过程进行一些修改：
   1. 在 RTCP 中，为受众集合中的每个所需受众执行此过程。
   1. Customer Journey Analytics支持配置文件数据集中的阵列/对象阵列。 为 audienceMembershipId 或 audienceMembershipIdName 使用[对象数组](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/complex-data/object-arrays.html?lang=zh-Hans)是最佳选项。
   1. 在数据视图中，在 `audienceMembershipId` 字段上使用子字符串转换创建新维度，以将逗号分隔的值字符串转换为数组。 注意：数组中当前限制为 10 个值。
   1. 您现在可以报告此新维度 `audienceMembershipIds` 在Customer Journey Analytics工作区中。
