---
title: 缺少权限
description: 了解如何对因缺少权限导致的问题进行故障排除
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
feature: Troubleshooting
source-git-commit: 1905e37b76843a7622af4e874a2d74aceff55384
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 4%

---


# 缺少权限

当某些Adobe Experience Platform权限未设置时，Customer Journey Analytics无法正常运行。

例如，创建 [连接](../connections/overview.md) 和 [数据视图](../data-views/data-views.md)中，您可能会在中看到以下错误消息 [组件](/help/data-views/create-dataview.md#components) 部分：


>[!BEGINSHADEBOX]

*[!UICONTROL 出现问题，无法加载架构字段。请重试。]*

>[!ENDSHADEBOX]


要更正此错误，您必须对拥有Experience Platform产品的组织具有系统或产品管理员权限。 请参阅 [访问控制概述](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=en#platform-permissions) 以了解更多信息。

1. 导航到Adobe Experience Platform UI。

1. 选择 **[!UICONTROL 权限]** 从左边栏开始。

1. 选择 **[!UICONTROL 角色]**.

1. 导航到相关角色。

1. 选择 ![编辑](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 编辑]** 以编辑角色。

1. 确保 **[!UICONTROL 管理数据使用策略]** 和 **[!UICONTROL 查看数据使用策略]** 都会添加到 **[!UICONTROL 数据管理]** 容器。

1. 选择 **[!UICONTROL 保存]** 以保存更改。


