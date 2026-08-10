---
title: 管理同意报告和筛选配置
description: 了解如何查看、编辑和删除同意报告和筛选配置，以及同意策略查找数据集如何在Customer Journey Analytics中保持同步。
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 7bb16378fc8813ca126cb786c5d36bf9daa0fe7d
workflow-type: tm+mt
source-wordcount: 452
ht-degree: 5%

---

# 管理同意报告和筛选配置

在您[创建同意报告和筛选配置](/help/connections/consent-reporting-filtering/consent-configure.md)后，您可以查看、编辑或删除它。

只有系统管理员才能管理同意报告和筛选配置。

有关概述信息，请参阅[同意报告和筛选概述](/help/connections/consent-reporting-filtering/consent-overview.md)。

## 查看现有配置

要查看现有配置，请执行以下操作：

1. 在Customer Journey Analytics中，选择&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 同意报告和筛选]**。

   以下各列提供了有关每个配置的信息：

   * **[!UICONTROL 创建者]**：创建配置的用户。

   * **[!UICONTROL 沙盒]**：包含配置文件数据集的Experience Platform沙盒。

   * **[!UICONTROL 连接]**：配置应用到的连接。

   * **[!UICONTROL 正在筛选]**：已为其启用筛选的营销操作（如果有）。

   * **[!UICONTROL 创建日期]**：配置创建日期。

   * **[!UICONTROL 上次修改时间]**：上次修改配置的日期。

   * **[!UICONTROL 状态]**：配置的状态。

   通过选择“列”图标![列图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)，取消选择要隐藏的任何列，然后选择&#x200B;**[!UICONTROL 应用]**，可以隐藏任何列。

1. （可选）要筛选配置列表，请选择&#x200B;**筛选器** ![筛选器图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)，然后按以下任意条件进行筛选：

   * **[!UICONTROL 连接]**

   * **[!UICONTROL 创建者]**

   * **[!UICONTROL 沙盒]**

   * **[!UICONTROL 状态]**

## 编辑配置

>[!IMPORTANT]
>
>对筛选的更改只会影响在您保存对配置所做的更改之后摄取的数据。 启用筛选不会删除在更改之前摄取的非同意访客数据，并且禁用筛选不会恢复启用筛选时排除的数据。

编辑现有配置：

1. 在Customer Journey Analytics中，选择&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 同意报告和筛选]**。

1. 选择要编辑的配置名称。

   或

   选中要编辑的配置旁边的复选框，然后选择&#x200B;**[!UICONTROL 编辑]**。

1. 进行更改，然后选择&#x200B;**[!UICONTROL 保存]**。

## 删除配置

要删除现有配置，请执行以下操作：

1. 在Customer Journey Analytics中，选择&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 同意报告和筛选]**。

1. 选中要删除的配置旁边的复选框，然后选择&#x200B;**[!UICONTROL 删除]**。

## 同意策略查找数据集如何保持同步

Customer Journey Analytics会自动将同意策略查找数据集与Experience Platform保持同步。 在Experience Platform中创建、更新、重命名或删除同意策略时，查找数据集中对应的策略名称和描述将会更新。

请牢记以下事项：

* 每个沙盒最多存在一个同意策略查找数据集。 同一沙盒中的多个配置共享该查找数据集。
* 由于策略名称和描述来自Experience Platform，因此请在Experience Platform中更新策略元数据，而不是直接编辑查找数据集。
