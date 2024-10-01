---
title: 产品使用情况概述
description: 查看有关贵组织如何使用Customer Journey Analytics的见解和报表。
hide: true
hidefromtoc: true
source-git-commit: dcd3ee5f3db5af434b87bfded0e360c66643793e
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 7%

---

# 产品使用情况概述

{{release-limited-testing}}

产品使用情况使贵组织能够查看有关贵组织如何使用Customer Journey Analytics的分析数据。 它适用于使用Customer Journey Analytics的所有组织。 启用后，将自动为您创建并关联以下Adobe Experience Platform组件：

* Adobe Experience Platform中的架构。 此架构是只读的，无法编辑。
* Adobe Experience Platform中的数据集。 此数据集的设置是只读的，无法编辑。
* Customer Journey Analytics中的连接。 此连接的设置是只读的，无法编辑。
* Customer Journey Analytics中的数据视图。 您可以使用同一连接编辑此数据视图或创建更多数据视图。

启用后，将自动为您配置所有数据收集和设置。 无论用户何时在Analysis Workspace中执行操作，都会跟踪该操作并可用于报表。

>[!IMPORTANT]
>
>此功能计入Adobe Experience Platform中的合同行限制。 在启用此功能之前，请确保您的组织可以容纳由此功能生成的数据。

## 可用维度

启用“产品使用”后，以下维度将可用：

| 维度 | 描述 |
| --- | --- |
| 操作名称 | 用户执行的操作的类型。 您可以通过在数据视图设置中创建副本，将此维度用作任何所需的量度。 |
| 使用的归因模型 | 当前组件使用的归因模型类型。 |
| 组件 | 派生字段。 |
| 组件类型 | 添加、删除或修改的组件类型。 |
| 连接 | 项目使用的连接。 |
| 数据视图 | 项目使用的数据视图。 |
| 功能 | 项目使用的功能。 |
| 标识符 | 事件的唯一标识符。 |
| 登录用户 | 执行操作的用户。 |
| 使用的面板 | 在其中添加、删除或修改组件的面板。 |
| 项目 | 派生字段。 |
| 项目名称 | 项目的友好名称。 |
| 项目类型 | 项目类型。 |
| 用户 ID | 触发事件的用户ID。 |
| 使用的可视化 | 已添加、删除或修改的可视化图表。 |

仅打开或查看项目时，产品使用情况不会跟踪单个项目组件。 但是，会跟踪打开项目的用户操作。
