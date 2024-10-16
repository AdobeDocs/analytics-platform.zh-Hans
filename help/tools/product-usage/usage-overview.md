---
title: 产品使用情况概述
description: 查看有关贵组织如何使用Customer Journey Analytics的见解和报表。
hide: true
hidefromtoc: true
source-git-commit: f337dfbd780aab4ae40534c5c1151dba35681b21
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 6%

---

# 产品使用情况概述

{{release-limited-testing}}

产品使用情况使贵组织能够查看有关贵组织如何使用Customer Journey Analytics的分析数据。 它适用于使用Customer Journey Analytics的所有组织。 启用后，将自动为您创建并关联以下Adobe Experience Platform组件：

* Adobe Experience Platform中的架构。 此架构为系统所有、只读，无法编辑。
* Adobe Experience Platform中的数据集。 此数据集是系统拥有的、只读的，无法编辑。
* Customer Journey Analytics中的连接。 此连接是系统拥有的、只读的，无法编辑。
* Customer Journey Analytics中的数据视图。 您可以使用上述连接编辑此数据视图或创建更多数据视图。 数据视图的所有者是允许您的组织使用产品的个人。

启用后，将自动为您配置所有数据收集和设置。 无论用户何时在Analysis Workspace中执行操作，都会跟踪该操作并可用于报表。

>[!IMPORTANT]
>
>此功能计入Adobe Experience Platform中的合同行限制。 在启用此功能之前，请确保您的组织可以容纳由此功能生成的数据。

## 可用维度

启用“产品使用”后，以下维度将可用：

| 维度 | 描述 |
| --- | --- |
| 操作名称 | 用户执行的操作的类型。 您可以通过在数据视图设置中创建副本，将此维度用作任何所需的量度。 |
| 使用的归因模型 | 组件使用的归因模型的类型。 |
| 组件 | 包括组件类型和组件名称的派生字段。 |
| 组件类型 | 添加、删除或修改的组件类型。 |
| 登录用户 | 执行操作的用户。 |
| 使用的面板 | 在其中添加、删除或修改组件的面板。 |
| 项目名称 | 项目的友好名称。 |
| 项目类型 | 项目类型。 |
| 用户 ID | 触发事件的用户ID。 |
| 使用的可视化 | 已添加、删除或修改的可视化图表。 |

仅打开或查看项目时，产品使用情况不会跟踪单个项目组件。 但是，会跟踪打开项目的用户操作。
