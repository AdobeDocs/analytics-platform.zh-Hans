---
title: 缺乏权限
description: 了解如何解决因缺乏权限而导致的问题
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 100%

---

# 缺乏权限

当某些 Adobe Experience Platform 权限未到位时，Customer Journey Analytics 无法正常运行。

举例来说，创建 [连接](../connections/overview.md) 和 [数据视图](../data-views/data-views.md)后，您可能会在 [组件](/help/data-views/create-dataview.md#components) 部分看到以下错误消息：


>[!BEGINSHADEBOX]

*[!UICONTROL 检索 DULE 策略时出现问题。请验证帐户权限、策略或标签。消息：禁止。]*

>[!ENDSHADEBOX]


1. 确保您拥有正确的访问控制：

   * 您必须拥有拥有 Experience Platform 产品的组织的系统或产品管理员权限。请参阅 [Access 控制概述](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#platform-permissions) 了解更多信息。

   * 您必须是 AEP-Default-All-Users 产品配置文件中的用户。如果您没有权限将自己添加到该轮廓中，请询问您的管理员。请参阅 [Access 控制层次结构和工作流程](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#access-control-hierarchy-and-workflow) 了解更多信息。


1. 导航到 Adobe Experience Platfom UI。

1. 从左侧栏中选择 **[!UICONTROL 权限]** 。

1. 选择&#x200B;**[!UICONTROL 角色]**

1. 导航到相关角色。

1. 选择 ![编辑](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 编辑]** 以编辑角色。

1. 确保 **[!UICONTROL 管理数据使用策略]** 和 **[!UICONTROL 查看数据使用策略]** 被添加到 **[!UICONTROL 数据治理]** 容器中。

1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;来保存更改。
