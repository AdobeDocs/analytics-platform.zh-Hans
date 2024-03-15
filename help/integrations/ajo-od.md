---
title: 将 Adobe Journey Optimizer 决策管理与 Adobe Customer Journey Analytics 集成
description: 引入 Adobe Journey Optimizer 决策管理生成的数据，并使用 Customer Journey Analytics 中的 Analysis Workspace 对其进行分析。
exl-id: fde45264-46cf-4c68-9872-7fb739748f21
feature: Experience Platform Integration
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: ht
source-wordcount: '710'
ht-degree: 100%

---

# 将决策管理与 Adobe Customer Journey Analytics 集成


Adobe Journey Optimizer [决策管理](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html)通过集中的营销优惠库和决策引擎（该引擎可将规则和约束应用于 Adobe Experience Platform 创建的丰富实时用户档案）帮助您在适当的时间向客户发送合适的优惠，从而轻松实现个性化。

决策管理是 Adobe Journey Optimizer 的一部分并与之集成。它还可以独立于 Adobe Journey Optimizer 中定义的历程和营销活动使用，利用其丰富的 [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html) 支持。

可通过执行以下步骤而导入决策管理生成的数据以在 Customer Journey Analytics 中执行高级分析：

## 将数据从决策管理发送到 Adobe Experience Platform

Adobe Experience Platform 作为中心数据源，联系着决策管理与 Customer Journey Analytics。决策管理的数据在体验平台中&#x200B;**自动**&#x200B;收集，或作为&#x200B;**明确发送的体验事件**（例如印象或点击）的一部分收集。有关详细信息，请参阅[数据收集快速入门](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html)。

## 创建连接

一旦决策管理数据进入 Adobe Experience Platform，即可根据决策管理数据集创建[连接](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hans)。或者，您可以将决策管理数据集添加到现有连接。

选择并配置以下数据集：

| 数据集 | 数据集类型 | 连接设置 | 描述 |
| --- | --- | --- | --- |
| ODE 决策事件 - _沙盒_&#x200B;决策 | 事件 | 人员 ID：`IdentityMap` | 包含决策管理决策事件的自动生成的数据。_沙盒_&#x200B;指的是具体的沙盒名称。 |
| Adobe Journey Optimizer 消息反馈事件数据集 | 事件 | 人员 ID：`IdentityMap` | 包含消息传递事件。 |
| Adobe Journey Optimizer 电子邮件跟踪体验事件数据集 | 事件 | 人员 ID：`IdentityMap` | 包含电子邮件跟踪事件。 |
| Adobe Journey Optimizer 推送跟踪体验事件数据集 | 事件 | 人员 ID：`IdentityMap` | 包含推送跟踪事件。 |
| Adobe Journey Optimizer 实体数据集 | 查询 | 键：`_id`<br>匹配键：`_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | 包含将历程和营销活动元数据与所有 Adobe Journey Optimizer 事件数据相关联的分类。 |

{style="table-layout:auto"}

## 创建数据视图

创建连接之后，可以创建一个或多个[数据视图](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html)，以配置可在 Customer Journey Analytics 中找到的所需的维度和量度。

>[!NOTE]
>
>Adobe Journey Optimizer 和 Customer Journey Analytics 之间的数据差异通常小于 1-2%。过去两小时内收集到的数据可能存在较大差异。请使用排除今天的日期范围以缓解涉及处理时间的差异。

### 配置维度

可在数据视图中创建以下维度，以实现与决策管理中类似的维度大致对等。有关维度自定义选项的详细信息，请参阅数据视图管理器中的[组件设置](/help/data-views/component-settings/overview.md)。

| 维度 | 模式元素 | 组件设置 |
| --- | --- | --- |
| 活动名称 | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | 组件类型：维度 |
| 容器标识符 | `_experience.decisioning.containerID` | 组件类型：维度 |
| 关联标识符 | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | 组件类型：维度 |
| 决策选项名称 | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | 组件类型：维度 |
| 回退决策选项名称 | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | 组件类型：维度 |
| 投放名称 | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | 组件类型：维度 |

{style="table-layout:auto"}


### 配置量度

可在数据视图中创建以下量度，以实现与决策管理中类似的量度大致对等。有关量度自定义选项的详细信息，请参阅数据视图管理器中的[组件设置](/help/data-views/component-settings/overview.md)。

| 量度 | 描述 | 模式元素 | 组件设置 |
| --- | --- | --- | --- |
| 事件类型（重命名以引用特定事件，例如适用于 `message.feedback` 的 `Feedback`）[1] | 特定类型事件的数量 | `eventType` | 组件类型：量度<br/>**[!UICONTROL 设置包含排除值&#x200B;]**：开启<br/>**[!UICONTROL 匹配]**：[!UICONTROL 如果满足所有条件]<br/>**[!UICONTROL 标准&#x200B;]**：**[!UICONTROL &#x200B;等于&#x200B;]**`message.feedback` |
| 决策选项得分 | 单个范围上下文中决策选项的计算值。 | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | 组件类型：量度 |
| 回退决策选项分数 | 单个范围上下文中回退决策选项的计算值。 | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | 组件类型：量度 |
| 优惠驳回 | 在没有任何其他直接互动的情况下被驳回或拒绝的优惠数量。 | `_experience.decisioning.`<br/>`propositionEventType.display` | 组件类型：量度 |
| 优惠显示 | 显示在配置文件中的优惠数量。 | `_experience.decisioning.`<br/>`propositionEventType.display` | 组件类型：量度 |
| 优惠互动 | 显示在配置文件中的优惠数量。 | `_experience.decisioning.`<br/>`propositionEventType.interact` | 组件类型：量度 |
| 优惠发送 | 发送到配置文件的优惠数量。 | `_experience.decisioning.`<br/>`propositionEventType.send` | 组件类型：量度 |
| 优惠触发 | 客户端 SDK 选择显示的优惠数量。 | `_experience.decisioning.`<br/>`propositionEventType.trigger` | 组件类型：量度 |
| 优惠取消订阅 | 配置文件请求的在将来不显示的优惠数量。 | `_experience.decisioning.`<br/>`propositionEventType.trigger` | 组件类型：量度 |

{style="table-layout:auto"}

[1] 您可以为各种可用事件类型定义多个量度。请参阅[包含排除值组件设置](/help/data-views/component-settings/include-exclude-values.md)，了解更多信息。
