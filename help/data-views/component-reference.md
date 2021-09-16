---
title: 标准组件引用
description: 有关可添加到任何数据视图的所有标准组件的详细信息和信息。
source-git-commit: 86522f1ea5ae241351514d954672ec5fd7990944
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 57%

---


# 标准组件引用

CJA中的大多数维度和量度都基于Adobe Experience Platform数据集中的架构元素。 但是，无论您使用何种连接，都可以将多个组件添加到数据视图。

[!UICONTROL 标准组件]不是根据数据集架构字段生成的组件，而是系统生成的组件。需要某些系统组件才能在Analysis Workspace中实现报告功能，而其他系统组件则是可选的。

![标准组件](assets/standard-components.png)

## 必需的标准组件

默认情况下，这些所需的标准组件将添加到每个数据视图中。它们对于Customer Journey Analytics提供的报告功能至关重要。

| 组件名称 | 维度或量度 | 注释 |
| --- | --- | --- |
| [!UICONTROL 人员] | 量度 | 基于[!UICONTROL 连接]中指定的人员ID。 |
| [!UICONTROL 会话] | 量度 | 基于数据视图的会话设置。 |
| [!UICONTROL 事件] | 量度 | [!UICONTROL Connection]中所有事件数据集的行数。 |
| [!UICONTROL 分钟] | 维度 | 给定事件发生的分钟（向下舍入）。 第一个维度项是日期范围内的第一分钟，最后一个维度项是日期范围内的最后一分钟。 |
| [!UICONTROL 小时] | 维度 | 给定事件发生的小时（向下舍入）。 第一个维度项是日期范围内的第一个小时，最后一个维度项是日期范围内的最后一个小时。 |
| [!UICONTROL 日] | 维度 | 给定事件发生的日期。 第一个维度项是日期范围内的第一天，最后一个维度项是日期范围内的最后一天。 |
| [!UICONTROL 周] | 维度 | 特定事件发生的一周。 第一个维度项是日期范围内的第一周，最后一个维度项是日期范围内的最后一周。 |
| [!UICONTROL 月] | 维度 | 给定事件发生的月份。 第一个维度项是日期范围内的第一个月，最后一个维度项是日期范围内的最后一个月。 |
| [!UICONTROL 季度] | 维度 | 给定事件发生的季度。 第一个维度项是日期范围内的第一个季度，最后一个维度项是日期范围内的最后一个季度。 |
| [!UICONTROL 年] | 维度 | 特定事件发生的年份。 第一个维度项是日期范围内的第一个年份，最后一个维度项是日期范围内的最近年份。 |

## 可选标准组件

可选的标准组件位于&#x200B;**[!UICONTROL 数据视图]** > **[!UICONTROL 编辑数据视图]** > **[!UICONTROL 组件]**&#x200B;选项卡> **[!UICONTROL 标准组件]**&#x200B;选项卡下。

| 组件名称 | 维度或量度 | 注释 |
| --- | --- | --- |
| [!UICONTROL 会话开始] | 量度 | 作为会话第一个事件的事件数。 用在筛选器定义（例如“[!UICONTROL 会话开始]”）中时，它会逐渐筛选以仅显示每个会话的第一个事件。 |
| [!UICONTROL 会话结束] | 量度 | 作为会话最后一个事件的事件数。 与[!UICONTROL 会话开始]类似，它也用在筛选器定义中，用以逐渐筛选以仅显示每个会话的最后一个事件。 |
| [!UICONTROL 逗留时间（秒）] | 量度 | 对维度的两个不同值之间的时间求和。 |
| [!UICONTROL 每个事件逗留时间] | 维度 | 将[!UICONTROL 逗留时间]量度存储到[!UICONTROL 事件]存储段中。 |
| [!UICONTROL 每个会话逗留时间] | 维度 | 将[!UICONTROL 逗留时间]量度存储到[!UICONTROL 会话]存储段中。 |
| [!UICONTROL 每人逗留时间] | 维度 | 将[!UICONTROL 逗留时间]量度存储到[!UICONTROL 人员]存储段中。 |
| [!UICONTROL 批次 ID] | 维度 | 表示某个[!UICONTROL 事件]所属的 Experience Platform 批次。 |
| [!UICONTROL 数据集 ID] | 维度 | 表示某个[!UICONTROL 事件]所属的 Experience Platform 数据集。 |
