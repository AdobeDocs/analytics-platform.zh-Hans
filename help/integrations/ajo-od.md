---
title: 将Adobe Journey Optimizer决策管理与Adobe Customer Journey Analytics集成
description: 引入Adobe Journey Optimizer决策管理生成的数据，并在Customer Journey Analytics中使用Analysis Workspace分析这些数据。
exl-id: fde45264-46cf-4c68-9872-7fb739748f21
feature: Platform Integration
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 20%

---

# 将Decision Management与Adobe Customer Journey Analytics集成


Adobe Journey Optimizer [决策管理](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=en) 借助集中的营销优惠库和决策引擎(该引擎可将规则和约束应用于Adobe Experience Platform创建的丰富实时用户档案)，帮助您在适当的时间向客户发送合适的优惠，从而轻松实现个性化。

决策管理是Adobe Journey Optimizer的一部分并与之集成。 它还可以使用其丰富的资源，独立于Adobe Journey Optimizer中定义的历程和营销活动 [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=en) 支持。

您可以导入决策管理生成的数据，以便通过执行以下步骤在Customer Journey Analytics中执行高级分析：

## 将数据从决策管理发送到Adobe Experience Platform

Adobe Experience Platform作为中央数据源，并作为决策管理和Customer Journey Analytics之间的链接。 从Decision Management中收集数据的Experience Platform **自动** 或作为的一部分 **明确发送的体验事件** （例如展示次数或点击次数）。 参见 [数据收集快速入门](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=en) 了解更多详细信息。

## 创建连接

一旦决策管理数据进入Adobe Experience Platform，您就可以创建 [连接](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hans) 基于您的决策管理数据集。 或者，您也可以将决策管理数据集添加到现有连接。

选择并配置以下数据集：

| 数据集 | 数据集类型 | 连接设置 | 描述 |
| --- | --- | --- | --- |
| ODE DecisionEvents - _沙盒_ 决策 | 事件 | 人员 ID: `IdentityMap` | 包含为决策管理决策事件自动生成的数据。 _沙盒_ 是指特定的沙盒名称。 |
| Adobe Journey Optimizer消息反馈事件数据集 | 事件 | 人员 ID: `IdentityMap` | 包含消息投放事件。 |
| Adobe Journey Optimizer电子邮件跟踪体验事件数据集 | 事件 | 人员 ID: `IdentityMap` | 包含电子邮件跟踪事件。 |
| Adobe Journey Optimizer推送跟踪体验事件数据集 | 事件 | 人员 ID: `IdentityMap` | 包含推送跟踪事件。 |
| Adobe Journey Optimizer实体数据集 | 查询 | 密钥： `_id`<br>匹配键： `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | 包含将历程和促销活动元数据与所有Adobe Journey Optimizer事件数据关联的分类。 |

{style="table-layout:auto"}

## 创建数据视图

创建连接之后，可创建一个或多个[数据视图](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=zh-Hans)配置可在 Customer Journey Analytics 中找到的所需的维度和度量。

>[!NOTE]
>
>Adobe Journey Optimizer和Customer Journey Analytics之间的数据差异通常小于1-2%。 过去两小时内收集到的数据可能存在较大差异。请使用排除今天的日期范围以缓解涉及处理时间的差异。

### 配置维度

可在数据视图中创建以下维度，以实现与决策管理中类似维度的近似等同性。 有关维度自定义选项的详细信息，请参阅数据视图管理器中的[组件设置](/help/data-views/component-settings/overview.md)。

| 维度 | 模式元素 | 组件设置 |
| --- | --- | --- |
| 活动名称 | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | 组件类型：维度 |
| 容器标识符 | `_experience.decisioning.containerID` | 组件类型：维度 |
| 关联标识符 | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | 组件类型：维度 |
| 决策选项名称 | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | 组件类型：维度 |
| 备用决策选项名称 | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | 组件类型：维度 |
| 版面名称 | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | 组件类型：维度 |

{style="table-layout:auto"}


### 配置量度

可在数据视图中创建以下量度以实现与决策管理中类似量度的大致对等。 有关度量自定义选项的详细信息，请参阅数据视图管理器中的[组件设置](/help/data-views/component-settings/overview.md)。

| 度量 | 描述 | 模式元素 | 组件设置 |
| --- | --- | --- | --- |
| 事件类型(重命名是指特定事件，例如 `Feedback` 对象 `message.feedback`) [1] | 特定类型事件的金额 | `eventType` | 组件类型：量度<br/>**[!UICONTROL 设置包括排除值&#x200B;]**： On<br/>**[!UICONTROL 匹配]**： [!UICONTROL 如果满足所有条件]<br/>**[!UICONTROL 标准&#x200B;]**：**[!UICONTROL &#x200B;等于&#x200B;]**`message.feedback` |
| 决策选项分数 | 单个范围上下文中决策选项的计算值。 | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | 组件类型：量度 |
| 备用决策选项分数 | 在单个范围的上下文中计算出的后备决策选项值。 | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | 组件类型：量度 |
| 优惠关闭 | 在没有任何其他直接交互的情况下已驳回或拒绝的优惠数量。 | `_experience.decisioning.`<br/>`propositionEventType.display` | 组件类型：量度 |
| 优惠显示 | 向配置文件显示的优惠数量。 | `_experience.decisioning.`<br/>`propositionEventType.display` | 组件类型：量度 |
| 选件交互 | 向配置文件显示的优惠数量。 | `_experience.decisioning.`<br/>`propositionEventType.interact` | 组件类型：量度 |
| 优惠发送 | 发送到配置文件的优惠数量。 | `_experience.decisioning.`<br/>`propositionEventType.send` | 组件类型：量度 |
| 选件触发器 | 选择由客户端SDK显示的选件数。 | `_experience.decisioning.`<br/>`propositionEventType.trigger` | 组件类型：量度 |
| 优惠取消订阅 | 配置文件请求的、未来不显示的选件数。 | `_experience.decisioning.`<br/>`propositionEventType.trigger` | 组件类型：量度 |

{style="table-layout:auto"}

[1] 您可以为可用的各种事件类型定义多个量度。 参见 [包括/排除值组件设置](/help/data-views/component-settings/include-exclude-values.md) 了解更多信息。
