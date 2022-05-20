---
title: 将 AEP 受众纳入 Customer Journey Analytics
description: 解释如何将 AEP 受众纳入 Customer Journey Analytics 以进行进一步分析。
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
source-git-commit: 9c4869bb632f3d69d8704009744246b975cb5c4a
workflow-type: ht
source-wordcount: '1049'
ht-degree: 100%

---

# 将 AEP 受众纳入 Customer Journey Analytics (CJA)

本用例探索了一种将 Adobe Experience Platform (AEP) 受众引入 CJA 的临时手动方式。 这些受众可能是在 AEP 区段生成器、Adobe Audience Manager 或其他工具中创建的，并存储在实时客户档案 (RTCP) 中。受众包括一组概要文件 ID，以及任何适用的属性/事件/等。 我们想把它们带到 CJA 的工作区进行分析。

## 先决条件

* 访问 Adobe Experience Platform (AEP)，特别是实时客户档案。
* 创建/管理 AEP 模式和数据集的权限。
* 访问 AEP 查询服务（以及编写 SQL 的能力）或其他工具来执行一些轻度转换。
* 访问 Customer Journey Analytics. 您需要是 CJA 产品管理员才能创建/修改 CJA 连接和数据视图。
* 能够使用 Adobe API（分段，可选其他）

## 步骤 1：在实时客户档案中选择受众 {#audience}

Adobe Experience Platform [实时客户档案](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=cn) (RTCP) 允许您通过组合来自多个渠道的数据（包括在线、离线、CRM 和第三方）来查看每个客户的整体视图。

RTCP 中可能已经有来自不同来源的受众。 选择一个或多个受众融入 CJA。

## 步骤 2：为导出创建用户档案合并数据集

为了将受众导出到最终可以添加到 CJA 连接的数据集，您需要创建一个数据集，其模式是一个用户档案 [合并模式](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=cn#understanding-union-schemas)。

合并模式由多个共享同一类并已启用用户档案的模式组成。 合并模式使您能够看到共享同一类的模式中包含的所有字段的合并。实时客户配置文件使用合并模式创建每个客户的整体视图。

## 步骤 3：通过 API 调用将受众导出到用户档案合并数据集 {#export}

在将受众引入 CJA 之前，需要将其导出到 AEP 数据集。 这只能使用分段 API，特别是 [导出作业 API 端点](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=cn)来完成。

您可以使用所选的受众 ID 创建导出作业，并将结果放入在步骤 2 中创建的概要文件联合 AEP 数据集中。 尽管您可以为受众导出各种属性/事件，但您只需要导出与您将要利用的 CJA 连接中使用的个人 ID 字段相匹配的特定用户档案 ID 字段（请参见下面的步骤 5）。

## 步骤 4：编辑导出输出

导出作业的结果需要转换为单独的用户档案数据集，以便纳入 CJA。  此转换可以使用 [AEP 查询服务](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=cn)或您选择的其他转换工具来完成。 我们只需要用户档案 ID（与 CJA 中的个人 ID 匹配）和一个或多个受众 ID 即可在 CJA 中进行报告。

然而，标准导出作业包含更多数据，因此我们需要编辑此输出以删除无关数据，并移动一些内容。  此外，在将转换后的数据添加到模式/数据集之前，需要先创建模式/数据集。

以下是用户档案合并数据集中的导出输出示例，在任何编辑&#x200B;**之前**：

![未编辑输出](assets/export-unedited.png)

请注意以下事项：

* 受众 ID 包含在 `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status` 下。
* 状态必须为“已实现”或“已输入”，但不能为“已退出”。

这是可以发送到 CJA 的用户档案数据集的格式。

![已编辑输出](assets/export-edited.png)

以下是需要呈现的数据元素：

* `_aresprodvalidation`字符串字段：指您的组织 ID。 您的会有所不同。
* `personID` 字符串字段：这是配置文件数据集上用于标识人员的标准 XDM 模式字段。 使用导出中的用户档案 ID。
* `audienceMembershipId`字符串字段：导出的受众 ID。  注意：此字段可以根据需要命名（从您自己的模式）。
* 为受众添加一个友好的名称 (`audienceMembershipIdName`)，例如

   ![友好的受众名称](assets/audience-name.png)

* 如果需要，可以添加其他受众元数据。

## 步骤 5：将此用户档案数据集添加到 CJA 中的现有连接

您可以 [创建新连接](/help/connections/create-connection.md)，但大多数客户都希望将用户档案数据集添加到现有连接。 受众 ID“丰富”CJA 中的现有数据。

## 步骤 6：修改现有（或创建新）CJA 数据视图

将 `audienceMembershipId`、`audienceMembershipIdName` 和 `personID` 添加到数据视图中。

## 步骤 7：工作区中的报告

现在，您可以在工作区中报告 `audienceMembershipId`、`audienceMembershipIdName` 和 `personID`。

## 其他说明

* 您应该定期执行此过程，以便在 CJA 中不断刷新受众数据。
* 您可以在单个 CJA 连接中导入多个访问群体。 这增加了流程的复杂性，但这是可能的。 为此，您需要对上述过程进行一些修改：
   1. 在 RTCP 中，为受众集合中的每个所需受众执行此过程。
   1. 在执行导出作业输出的转换时，您需要创建一个 `audienceMembershipId(s)` 列表，因为一个 CJA 人员 ID 可能属于多个受众。在将来的某个时候，CJA 将支持概要数据集中的阵列/对象阵列。 一旦这些都得到支持，为 `audienceMembershipId` 或 `audienceMembershipIdName` 使用对象数组将是最好的选择。在此期间，提取导出作业输出中每个用户档案 ID 的所有当前受众 ID（状态为“已实现”或“已输入”），并将其放入逗号分隔的值字符串中（即，`<id1>,<id2>,...`）。如果有状态为“退出”的受众 ID，请确保该 ID 不在列表中。  如果要维护与 ID 的友好名称关联，可以将其附加到列表中每个 ID 的末尾（以及任何其他元数据）。
   1. 在数据视图中，在 `audienceMembershipId` 字段上使用子字符串转换创建新维度，以将逗号分隔的值字符串转换为数组。 注意：数组中当前限制为 10 个值。
   1. 现在，您可以在 CJA 工作区中报告此新维度 `audienceMembershipIds`。
