---
title: 将AEP受众摄取到Customer Journey Analytics
description: 说明如何将AEP受众摄取到Customer Journey Analytics中以供进一步分析。
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: cd1d639ad698c188c506881b2b17103b0a3559f2
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 2%

---


# 将AEP受众摄取到Customer Journey Analytics(CJA)

(AEP文档经理称，“Brandon， fyi， &#39;Unified Profile&#39;”是“实时客户资料”的过时术语。 在AEP文档集中，您找不到任何UP文档。)

此用例探讨了将Adobe Experience Platform(AEP)受众引入CJA的临时手动方式。 这些受众可能是在AEP区段生成器、Adobe Audience Manager或其他工具中创建的，并存储在实时客户配置文件(RTCP)中。 受众由人员ID、用户档案ID等列表组成。 并且我们希望将它们引入CJA Workspace进行分析。

## 先决条件

* 访问 Adobe Experience Platform (AEP)，特别是实时客户资料。
* 访问 Customer Journey Analytics
* 是否能编写自定义代码？
* 还有什么。

## 步骤1:在实时客户资料中选择受众 {#audience}

Adobe Experience Platform [实时客户资料](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) (RTCP)通过组合来自多个渠道（包括在线、离线、CRM和第三方）的数据，让您能够全面了解每个客户的视图。 RTCP中的受众可能来自各种来源。 选择一个或多个受众。

## 步骤2:为导出创建配置文件并集数据集

要将受众导出到随后可以与CJA建立连接的数据集，您需要创建一个架构为“配置文件”的数据集 [并集模式](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).
并集架构由多个架构组成，这些架构共享同一类并已为用户档案启用。 合并架构允许您查看共享同一类的架构内包含的所有字段的合并。 实时客户资料使用联合架构创建每个客户的整体视图。

## 步骤3:通过API调用将受众导出到数据集 {#export}

在将受众导入CJA之前，您需要将其导出到AEP中的数据集。 这只能使用分段API来完成，特别是 [导出作业API端点](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en). 您可以创建导出作业，并将结果放入在步骤2中创建的配置文件并集AEP数据集中。

## 步骤4:编辑导出输出

在为受众创建导出作业时，我们只需人员ID和受众ID即可在CJA中执行报表。 但是，标准导出作业包含更多数据，因此我们需要编辑此输出以删除无关数据。

以下是配置文件并集数据集中的导出输出示例， **之前** 任何编辑：

![未编辑的输出](assets/export-unedited.png)

请注意以下事项：

* 受众ID包含在 `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* 状态必须为“已实现”或“已输入”，但不得为“已退出”。 将“已退出”替换为“空白”。

这是您可以发送到CJA的用户档案数据集的格式。

![编辑的输出](assets/export-edited.png)

以下是需要显示的数据元素：

* `_aresprodvalidation`:是指您的组织ID。 你的会不一样。
* `personID`:在这种情况下，为易记名称
* `audienceMembershipIdList` 字符串字段：受众ID
* 为受众添加易记名称(`audienceMembershipIdName`)，例如

   ![友好受众名称](assets/audience-name)

## 步骤5:在CJA中创建与此配置文件数据集的连接

[创建连接](/help/connections/create-connection.md)

## 步骤6:创建数据视图

添加 `audienceMembershipIdName` 和 `personID` 到dataview。

## 步骤7:工作区中的报表

您现在可以报告 `audienceMembershipIdName` 和 `personID` 中。
屏幕截图会很棒。

要执行以下操作：

在处理属于多个受众的成员的人员时，请编写更多步骤。




