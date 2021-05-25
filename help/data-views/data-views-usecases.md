---
title: Customer Journey Analytics 中的数据视图的用例
description: 显示 Customer Journey Analytics 中数据视图的灵活性和强大功能的多个用例
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
source-git-commit: 3553a6a684bc2cd015d1b2ad6a3b02987d6d6bb2
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 90%

---

# 数据视图用例

这些用例显示了 Customer Journey Analytics 中数据视图的灵活性和强大功能。

## 根据 pageTitle（字符串）架构字段创建一个“订单”量度

例如，在创建数据视图时，您可以根据字符串形式的 [!UICONTROL pageTitle] 架构字段创建一个[!UICONTROL 订单]量度。步骤如下：

1. 在“组件”选项卡上，将 [!UICONTROL pageTitle] 拖入[!UICONTROL 包含的组件]下的[!UICONTROL 量度]部分中。
   ![](assets/use-case1a.png)
1. 现在，突出显示您刚才拖入的量度，并在右侧的[!UICONTROL 组件设置]下重命名它：
   ![](assets/orders.png)
1. 打开右侧的[!UICONTROL 添加/排除值]对话框，并指定以下内容：
   ![](assets/orders2.png)

   “确认”短语指示这是个订单。查看满足这些条件的所有页面标题后，系统会为每个实例统计“1”。结果是一个新量度（而非计算量度）。具有已添加/排除值的量度可用在可使用任何其他量度的任意位置。它可与 Attribution IQ、过滤器配合使用，以及用在可使用标准量度的任何其他位置。
1. 您可以进一步为此量度指定归因模型，例如[!UICONTROL 回顾时间范围]为[!UICONTROL 会话]的[!UICONTROL 最近联系]。
您还可以根据同一字段创建另一个[!UICONTROL 订单]量度，并为其指定不同的归因模型（例如[!UICONTROL 首次联系]）和不同的[!UICONTROL 回顾时间范围]（例如 [!UICONTROL 30 天]）。

## 使用整数作为维度

以前，整数会被自动视为 CJA 中的量度。现在，数字（包括 Adobe Analytics 中的自定义事件）可被视为维度。示例如下：

1. 将 [!UICONTROL call_length_min] 整数拖入[!UICONTROL 包含的组件]下的[!UICONTROL 维度]部分中：

   ![](assets/integers.png)

1. 您现在可以添加[!UICONTROL 值分段]以分段方式在报告中表示此维度。（若不添加分段，此维度的每个实例都会显示为 Workspace 报告中的一个行项目。）

   ![](assets/bucketing.png)

## 在流程图中将数值维度用作“量度”

您可以使用数值维度将“量度”导入[!UICONTROL 流量]可视化。 以下示例显示了[!UICONTROL 营销渠道]流入[!UICONTROL 订单]的内容：

![](assets/flow.png)

## 包含或排除量度值

有关数据视图设置的更多信息，请参阅[创建数据视图](/help/data-views/create-dataview.md)。
有关数据视图的概念性概述，请参阅[数据视图概述](/help/data-views/data-views.md)。