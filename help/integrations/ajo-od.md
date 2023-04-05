---
title: 将Adobe Journey Optimizer决策管理与Customer Journey Analytics(CJA)集成
description: 导入Adobe Journey Optimizer决策管理生成的数据，并在Customer Journey Analytics中使用Analysis Workspace对其进行分析。
source-git-commit: 00a87f5f370310672ca37ab9df08350d14fc6a91
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 18%

---

# 将决策管理与Customer Journey Analytics集成


Adobe Journey Optimizer [决策管理](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=en) 通过集中的营销选件库和决策引擎，将规则和约束应用于Adobe Experience Platform创建的丰富实时用户档案，以帮助您在适当的时间向客户发送正确的选件，从而轻松实现个性化。

决策管理是Adobe Journey Optimizer(AJO)的一部分，并与之集成。 它还可以使用其丰富的 [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=en) 支持。

您可以通过执行以下步骤，导入决策管理生成的数据，以在Customer Journey Analytics(CJA)中执行高级分析：

## 将数据从决策管理发送到Adobe Experience Platform

Adobe Experience Platform用作决策管理和Customer Journey Analytics之间的中央数据源和链接。 在Experience Platform中收集来自决策管理的数据 **自动** 或作为 **明确发送的体验事件** （例如，展示次数或点击次数）。 请参阅 [数据收集入门](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=en) 以了解更多详细信息。

## 创建连接

将决策管理数据放入Adobe Experience Platform后，您可以创建 [连接](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hans) 基于决策管理数据集。 或者，您也可以将决策管理数据集添加到现有连接。

选择并配置以下数据集：

| 数据集 | 数据集类型 | 连接设置 | 描述 |
| --- | --- | --- | --- |
| 代码决策事件 —  _沙盒_ 决策 | 事件 | 人员 ID: `IdentityMap` | 包含为决策管理决策事件自动生成的数据。 _沙盒_ 是指特定的沙盒名称。 |
| AJO消息反馈事件数据集 | 事件 | 人员 ID: `IdentityMap` | 包含消息投放事件。 |
| AJO电子邮件跟踪体验事件数据集 | 事件 | 人员 ID: `IdentityMap` | 包含电子邮件跟踪事件。 |
| AJO推送跟踪体验事件数据集 | 事件 | 人员 ID: `IdentityMap` | 包含推送跟踪事件。 |
| AJO实体数据集 | 查询 | 键： `_id`<br>匹配键： `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | 包含将历程和促销活动元数据与所有AJO事件数据关联的分类。 |

{style="table-layout:auto"}

## 创建数据视图

创建连接后，可以创建一个或多个 [数据视图](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=zh-Hans) 以配置CJA中可用的所需维度和量度。

>[!NOTE]
>
>AJO 和 CJA 之间的数据差异通常小于 1-2%。过去两小时内收集到的数据可能存在较大差异。请使用排除今天的日期范围以缓解涉及处理时间的差异。

### 配置维度

您可以在数据视图中创建以下维度，以便与决策管理中的类似维度实现近似对等。 有关维度自定义选项的详细信息，请参阅数据视图管理器中的[组件设置](/help/data-views/component-settings/overview.md)。

| 维度 | 模式元素 | 组件设置 |
| --- | --- | --- |
| 活动名称 | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | 组件类型：维度 |
| 容器标识符 | `_experience.decisioning.containerID` | 组件类型：维度 |
| 关联标识符 | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | 组件类型：维度 |
| 决策选项名称 | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | 组件类型：维度 |
| 回退决策选项名称 | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | 组件类型：维度 |
| 版面名称 | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | 组件类型：维度 |

{style="table-layout:auto"}


### 配置量度

您可以在数据视图中创建以下量度，以便与决策管理中的类似量度实现近似对等。 有关度量自定义选项的详细信息，请参阅数据视图管理器中的[组件设置](/help/data-views/component-settings/overview.md)。

| 度量 | 描述 | 模式元素 | 组件设置 |
| --- | --- | --- | --- |
| 事件类型(重命名为引用特定事件，例如 `Feedback` 表示 `message.feedback`) [1] | 特定事件类型的数量 | `eventType` | 组件类型：量度<br/>**[!UICONTROL 设置“包含排除值”]**:开<br/>**[!UICONTROL 匹配]**: [!UICONTROL 如果满足所有标准]<br/>**[!UICONTROL 标准&#x200B;]**:**[!UICONTROL &#x200B;等于&#x200B;]**`message.feedback` |
| 决策选项得分 | 单个范围上下文中决策选项的计算值。 | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | 组件类型：量度 |
| 回退决策选项得分 | 单个范围上下文中回退决策选项的计算值。 | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | 组件类型：量度 |
| 优惠取消 | 未进行任何其他直接交互即可拒绝或拒绝的选件数量。 | `_experience.decisioning.`<br/>`propositionEventType.display` | 组件类型：量度 |
| 选件显示 | 显示给用户档案的选件数量。 | `_experience.decisioning.`<br/>`propositionEventType.display` | 组件类型：量度 |
| 选件交互 | 显示给用户档案的选件数量。 | `_experience.decisioning.`<br/>`propositionEventType.interact` | 组件类型：量度 |
| 选件发送 | 发送到用户档案的选件数量。 | `_experience.decisioning.`<br/>`propositionEventType.send` | 组件类型：量度 |
| 选件触发器 | 客户端SDK要显示的选件数。 | `_experience.decisioning.`<br/>`propositionEventType.trigger` | 组件类型：量度 |
| 选件取消订阅 | 用户档案请求的将来不显示的选件数量。 | `_experience.decisioning.`<br/>`propositionEventType.trigger` | 组件类型：量度 |

{style="table-layout:auto"}

[1] 您可以为各种可用事件类型定义多个量度。 请参阅 [“包含排除值”组件设置](/help/data-views/component-settings/include-exclude-values.md) 以了解更多信息。
