---
title: 缺乏权限
description: 了解如何解决因缺乏权限而导致的问题
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
autotag-review: '2026-05-19T09:32:28.410Z'
TQID: 'https://experienceleague.adobe.com/qGrpX20MMcrjeEO75K2Ndoki4eiDmEvmaUCzED8jR1w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: a67cb189-a535-41f6-afa2-448f39c4759f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 94%

---

# 缺乏权限

当某些 Adobe Experience Platform 权限未到位时，Customer Journey Analytics 无法正常运行。

举例来说，创建 [连接](../connections/overview.md) 和 [数据视图](../data-views/data-views.md)后，您可能会在 [组件](/help/data-views/create-dataview.md#components) 部分看到以下错误消息：


>[!BEGINSHADEBOX]

*[!UICONTROL 检索DULE策略时出错。 请验证帐户权限、策略或标签。 消息：禁止。]*

>[!ENDSHADEBOX]


1. 确保您拥有正确的访问控制：

   * 您必须拥有拥有 Experience Platform 产品的组织的系统或产品管理员权限。 请参阅 [Access 控制概述](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=zh-Hans#platform-permissions) 了解更多信息。

   * 您必须是 AEP-Default-All-Users 产品配置文件中的用户。 如果您没有权限将自己添加到该轮廓中，请询问您的管理员。 请参阅 [Access 控制层次结构和工作流程](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=zh-Hans#access-control-hierarchy-and-workflow) 了解更多信息。


1. 导航到 Adobe Experience Platfom UI。

1. 从左侧栏中选择 **[!UICONTROL 权限]** 。

1. 选择&#x200B;**[!UICONTROL 角色]**

1. 导航到相关角色。

1. 选择 ![编辑](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 编辑]** 以编辑角色。

1. 确保 **[!UICONTROL 管理数据使用策略]** 和 **[!UICONTROL 查看数据使用策略]** 被添加到 **[!UICONTROL 数据治理]** 容器中。

1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;来保存更改。
