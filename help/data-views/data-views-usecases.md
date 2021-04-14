---
title: Customer Journey Analytics中数据视图的用例
description: 在Customer Journey Analytics中展示数据视图的灵活性和强大功能的多种用例
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
translation-type: tm+mt
source-git-commit: f9fae62af3d57b2b700c26a402c7232c0255806b
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---

# 数据视图使用案例

>[!IMPORTANT]
>
>此功能将于2021年4月22日正式推出。

这些用例显示了Customer Journey Analytics视图的灵活性和强大功能。

## 从pageTitle（字符串）模式字段创建订单量度

例如，在创建视图时，您可以从作为字符串的[!UICONTROL pageTitle]模式字段创建[!UICONTROL Orders]量度。 以下是步骤：

1. 在“组件”选项卡上，将[!UICONTROL pageTitle]拖到[!UICONTROL 包含的组件]下的[!UICONTROL Metrics]部分。
   ![](assets/use-case1a.png)
1. 现在，突出显示您刚拖入的量度，并将其重命名在右侧[!UICONTROL 组件设置]下：
   ![](assets/orders.png)
1. 打开右侧的[!UICONTROL 包含/排除值]对话框，并指定以下内容：
   ![](assets/orders2.png)

   “确认”短语表示这是订单。 在查看所有符合这些条件的页面标题后，将对每个实例计为“1”。 结果是新量度（而非计算量度）。 包含/排除值的量度可在任何其他可以使用的量度中使用。 它可与Attribution IQ、过滤器及其他您可以使用标准量度的地方配合使用。
1. 您可以进一步指定此量度的归因模型，如[!UICONTROL 上次触摸]，并且[!UICONTROL 会话]的[!UICONTROL 回顾窗口]。
您还可以从同一字段创建另一个[!UICONTROL Orders]量度，并为它指定不同的归因模型，如[!UICONTROL First Touch]和不同的[!UICONTROL 回顾窗口]，如[!UICONTROL 30天]。

## 使用整数作为维

以前，整数在CJA中会自动被视为量度。 现在，数字(包括来自Adobe Analytics的自定义事件)可以视为尺寸。 示例如下：

1. 将[!UICONTROL call_length_min]整数拖动到[!UICONTROL 包含的组件]下的[!UICONTROL Dimension]部分：

   ![](assets/integers.png)

1. 您现在可以添加[!UICONTROL 值分段]以按报告以分段方式显示此维。 (如果没有分段，此维度的每个实例将在Workspace报告中显示为行项。)

   ![](assets/bucketing.png)

有关其他视图设置的详细信息，请参阅[创建视图](/help/data-views/create-dataview.md)。
有关数据视图的概念概述，请参阅[视图概述](/help/data-views/data-views.md)。
