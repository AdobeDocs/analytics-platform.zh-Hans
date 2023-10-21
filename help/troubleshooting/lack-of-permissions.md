---
title: 缺少权限
description: 了解如何对因缺少权限导致的问题进行故障排除
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
source-git-commit: 788d1d32548ef510cf12376b244fcc0e090e189d
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 3%

---

# 缺少权限

当某些Adobe Experience Platform权限未设置时，Customer Journey Analytics无法正常运行。

例如，创建 [连接](../connections/overview.md) 和 [数据视图](../data-views/data-views.md)中，您可能会在中看到以下错误消息 [组件](/help/data-views/create-dataview.md#components) 部分：


>[!BEGINSHADEBOX]

*[!UICONTROL 检索DULE策略时出错。请验证帐户权限、策略或标签。 消息：禁止访问。]*

>[!ENDSHADEBOX]


1. 确保您拥有正确的访问控制：

   * 对于具有Experience Platform产品的组织，您必须具有系统或产品管理员权限。 请参阅 [访问控制概述](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=en#platform-permissions) 以了解更多信息。

   * 您必须是AEP-Default-All-Users产品配置文件中的用户。 如果您没有将您自己添加到此配置文件的权限，请咨询管理员。 请参阅 [访问控制层级和工作流](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=en#access-control-hierarchy-and-workflow) 以了解更多信息。


1. 导航到AdobeExperience Platform UI。

1. 选择 **[!UICONTROL 权限]** 从左边栏开始。

1. 选择 **[!UICONTROL 角色]**.

1. 导航到相关角色。

1. 选择 ![编辑](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 编辑]** 以编辑角色。

1. 确保 **[!UICONTROL 管理数据使用策略]** 和 **[!UICONTROL 查看数据使用策略]** 都会添加到 **[!UICONTROL 数据管理]** 容器。

1. 选择 **[!UICONTROL 保存]** 以保存更改。
