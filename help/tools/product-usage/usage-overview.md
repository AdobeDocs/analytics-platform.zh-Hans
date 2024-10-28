---
title: 产品使用概述
description: 查看关于您的组织如何使用Customer Journey Analytics的见解和报告。
source-git-commit: 7d22c512e8e96963b288567704d2245e64411b10
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 6%

---

# 产品使用概述

{{release-limited-testing}}

产品使用情况使您的组织能够查看有关您的组织如何使用Customer Journey Analytics的分析数据。 适用于所有使用Customer Journey Analytics的企业。 启用后，将自动创建以下Adobe Experience Platform组件并与之关联。 这些组件均由系统拥有，是只读的，无法编辑。

* Adobe Experience Platform中的架构
* Adobe Experience Platform中的数据集
* Customer Journey Analytics中的连接
* Customer Journey Analytics中的数据视图

启用后，系统会自动为您配置所有数据收集和设置。 每当用户在Analysis Workspace中进行操作时，都将跟踪该操作并可用于报告。

>[!IMPORTANT]
>
>此功能会计入Adobe Experience Platform中的合同行限制。 在启用此功能之前，请确保您的组织能够容纳由此功能生成的数据。

## 可用维度

启用“产品使用”后，下列维可用。 如果要更改任何维设置，请创建系统拥有的数据视图的副本，并在Analysis Workspace中使用复制的数据视图。

| 维度 | 描述 |
| --- | --- |
| 操作名称 | 用户执行的操作的类型。 通过在数据视图设置中创建副本，可以将该维用作任何所需的度量。 |
| 使用的归因模型 | 组件使用的归因模型的类型。 |
| 组件 | 包括组件类型和组件名称的派生字段。 |
| 组件类型 | 添加、删除或修改的组件的类型。 |
| 登录用户 | 执行操作的用户。 |
| 使用的面板 | 在其中添加、删除或修改组件的面板。 |
| 项目名称 | 项目的友好名称。 |
| 项目类型 | 项目类型。 |
| 用户 ID | 触发事件的用户ID。 |
| 使用的可视化 | 已添加、删除或修改的可视化。 |

仅打开或查看项目时，产品使用情况不会跟踪单个项目组件。 但是，系统会跟踪打开项目的用户操作。
