---
title: 将AEP受众摄取到Customer Journey Analytics
description: 说明如何将AEP受众摄取到Customer Journey Analytics中以供进一步分析。
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
source-git-commit: 9c4869bb632f3d69d8704009744246b975cb5c4a
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 2%

---

# 将AEP受众摄取到Customer Journey Analytics(CJA)

此用例探讨了将Adobe Experience Platform(AEP)受众引入CJA的临时手动方式。 这些受众可能是在AEP区段生成器、Adobe Audience Manager或其他工具中创建的，并存储在实时客户配置文件(RTCP)中。 受众由一组用户档案ID以及任何适用的属性/事件等组成。 并且我们希望将它们引入CJA Workspace进行分析。

## 先决条件

* 访问 Adobe Experience Platform (AEP)，特别是实时客户资料。
* 访问创建/管理AEP架构和数据集。
* 访问AEP查询服务（以及编写SQL的功能）或执行一些轻量级转换的其他工具。
* 访问 Customer Journey Analytics. 您需要成为CJA产品管理员，才能创建/修改CJA连接和数据视图。
* 能够使用AdobeAPI（分段，可选择其他）

## 步骤1:在实时客户资料中选择受众 {#audience}

Adobe Experience Platform [实时客户资料](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) (RTCP)通过组合来自多个渠道（包括在线、离线、CRM和第三方）的数据，让您能够全面了解每个客户的视图。

RTCP中的受众可能来自各种来源。 选择一个或多个要摄取到CJA的受众。

## 步骤2:为导出创建配置文件并集数据集

要将受众导出到最终可添加到CJA中连接的数据集，您需要创建一个架构为“Profile”的数据集 [并集模式](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).

并集架构由多个架构组成，这些架构共享同一类并已为用户档案启用。 合并架构允许您查看共享同一类的架构内包含的所有字段的合并。 实时客户资料使用联合架构创建每个客户的整体视图。

## 步骤3:通过API调用将受众导出到配置文件合并数据集 {#export}

要将受众导入CJA，您需要先将其导出到AEP数据集。 这只能使用分段API来完成，特别是 [导出作业API端点](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en).

您可以使用所选的受众ID创建导出作业，并将结果放入您在步骤2中创建的配置文件并集AEP数据集中。 尽管您可以导出受众的各种属性/事件，但您只需导出与将利用的CJA连接中使用的人员ID字段相匹配的特定配置文件ID字段即可（请参阅下面步骤5中的）。

## 步骤4:编辑导出输出

需要将导出作业的结果转换为单独的用户档案数据集，才能将其摄取到CJA中。  此转换可通过 [AEP查询服务](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=en)，或您选择的其他转换工具。 在CJA中，我们只需要配置文件ID（与CJA中的人员ID匹配）和一个或多个受众ID即可进行报告。

但是，标准导出作业包含更多数据，因此我们需要编辑此输出以删除无关数据，并移动一些内容。  此外，您还需要先创建架构/数据集，然后再将转换后的数据添加到该架构/数据集。

以下是配置文件并集数据集中的导出输出示例， **之前** 任何编辑：

![未编辑的输出](assets/export-unedited.png)

请注意以下事项：

* 受众ID包含在 `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* 状态必须为“已实现”或“已输入”，但不得为“已退出”。

这是您可以发送到CJA的用户档案数据集的格式。

![编辑的输出](assets/export-edited.png)

以下是需要显示的数据元素：

* `_aresprodvalidation` 字符串字段：是指您的组织ID。 你的会不一样。
* `personID` 字符串字段：这是用户档案数据集上用于标识人员的标准XDM架构字段。 使用导出中的配置文件ID。
* `audienceMembershipId` 字符串字段：导出中的受众ID。  注意：此字段可以随意命名（从您自己的架构中）。
* 为受众添加易记名称(`audienceMembershipIdName`)，例如

   ![友好受众名称](assets/audience-name.png)

* 根据需要添加其他受众元数据。

## 步骤5:将此配置文件数据集添加到CJA中的现有连接

你可以 [创建新连接](/help/connections/create-connection.md)，但大多数客户将希望将配置文件数据集添加到现有连接。 受众ID可“丰富”CJA中的现有数据。

## 步骤6:修改现有（或新建）CJA数据视图

添加 `audienceMembershipId`, `audienceMembershipIdName` 和 `personID` 到数据视图。

## 步骤7:工作区中的报表

您现在可以报告 `audienceMembershipId`, `audienceMembershipIdName` 和 `personID` 中。

## 其他说明

* 您应当定期执行此过程，以便在CJA中不断刷新受众数据。
* 您可以在一个CJA连接中导入多个受众。 这增加了该过程的额外复杂性，但是这是可能的。 要使此功能正常工作，您需要对上述流程进行一些修改：
   1. 在RTCP中为受众集合中的每个所需受众执行此过程。
   1. 执行导出作业输出的转换时，需要创建 `audienceMembershipId(s)`，因为单个CJA人员ID可以属于多个受众。 在将来的某个时候，CJA将支持配置文件数据集中的数组/对象数组。 在支持这些对象后，将对象数组用于 `audienceMembershipId` 或 `audienceMembershipIdName` 是最佳选择。 在此期间，提取导出作业输出中每个配置文件ID的所有当前受众ID（状态为“已实现”或“已输入”），并将它们置于以逗号分隔的值字符串中(即 `<id1>,<id2>,...`)。  如果受众ID的状态为“已退出”，请确保该ID未在列表中。  如果要维护与ID的友好名称关联，可以将其附加到列表中每个ID的末尾（以及任何其他元数据）。
   1. 在数据视图中，使用 `audienceMembershipId` 字段将逗号分隔值字符串转换为数组。 注意：数组中当前限制为10个值。
   1. 您现在可以报告此新维度 `audienceMembershipIds` 在CJA工作区中。
