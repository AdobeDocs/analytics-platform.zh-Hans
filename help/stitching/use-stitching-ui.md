---
title: 使用拼合
description: 如何使用拼合
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
hide: true
hidefromtoc: true
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: 4bca14492374939cd1ea6508c774720db61a6283
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 3%

---

# 使用拼合

您可以对作为连接的一部分配置的一个或多个事件数据集启用拼合。 您可以为拼合启用的事件数据集的数量由您许可的Customer Journey Analytics包决定。

当您[创建连接](/help/connections/create-connection.md#dataset-settings)或[编辑连接](/help/connections/create-connection.md)时，可以将拼合作为事件数据集的[数据集设置](/help/connections/manage-connections.md#edit-a-connection)的一部分启用。

要启用拼接，请在&#x200B;**[!UICONTROL 添加数据集]**&#x200B;或&#x200B;**[!UICONTROL 编辑数据集]**&#x200B;对话框的事件数据集部分中：

启用身份拼接时![身份拼接选项](assets/identity-stitching-ui.png)

1. 选择&#x200B;**[!UICONTROL 启用身份拼接]**。

   如果为现有事件数据集启用拼合，**[!UICONTROL 更改人员ID]**&#x200B;对话框会显示由于使用拼合而更改人员ID所隐含的影响。 选择&#x200B;**[!UICONTROL 继续]**&#x200B;以继续。

   **[!UICONTROL 启用身份拼接]**&#x200B;对话框汇总了拼接身份的结果。 选择&#x200B;**[!UICONTROL 继续]**&#x200B;以继续。

1. 从&#x200B;**[!UICONTROL 永久ID]**&#x200B;下拉菜单中选择一个永久ID。

   如果您为永久ID选择&#x200B;**[!UICONTROL 身份映射]**，则必须选择命名空间。 您有两个选项：

   * 启用&#x200B;**[!UICONTROL 使用主身份命名空间]**&#x200B;以使用主身份命名空间。
   * 从&#x200B;**[!UICONTROL 命名空间]**&#x200B;下拉菜单中选择一个命名空间。

1. 从&#x200B;**[!UICONTROL 人员ID]**&#x200B;下拉菜单中选择人员ID。

   如果您为人员ID选择&#x200B;**[!UICONTROL 身份映射]**，则必须选择命名空间。 您有两个选项：

   * 启用&#x200B;**[!UICONTROL 使用主身份命名空间]**&#x200B;以使用主身份命名空间。
   * 从&#x200B;**[!UICONTROL 命名空间]**&#x200B;下拉菜单中选择一个命名空间。

   如果您为人员ID选择&#x200B;**[!UICONTROL 身份图]**，则必须选择命名空间。 在此之前，将显示&#x200B;**[!UICONTROL 更改为身份图]**&#x200B;对话框，以确保在使用身份图进行拼接之前已完成身份图的设置。 选择&#x200B;**[!UICONTROL 继续]**&#x200B;以继续。

   * 从&#x200B;**[!UICONTROL 命名空间]**&#x200B;下拉菜单中选择一个命名空间。


1. 从&#x200B;**[!UICONTROL 回顾窗口]**&#x200B;下拉菜单中选择一个回顾窗口。 选项为&#x200B;**[!UICONTROL 1天]**、**[!UICONTROL 7天]**、**[!UICONTROL 14天]**&#x200B;或&#x200B;**[!UICONTROL 30天]**。
