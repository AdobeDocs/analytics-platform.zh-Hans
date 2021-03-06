---
title: Customer Journey Analytics 中的数据视图的用例
description: 显示 Customer Journey Analytics 中数据视图的灵活性和强大功能的多个用例
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 11171eb6e079adbf41e0abc798a54a5749492eac
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 69%

---

# 数据视图用例

这些用例显示了 Customer Journey Analytics 中数据视图的灵活性和强大功能。

## 1. 根据字符串架构字段创建量度 {#string}

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

另一个例子是使用访客 ID（一个维度）作为量度来确定您的公司有多少访客 ID。

## 2. 使用整数作为维度 {#integers}

以前，整数会被自动视为 CJA 中的量度。现在，数字（包括 Adobe Analytics 中的自定义事件）可被视为维度。示例如下：

1. 将 [!UICONTROL call_length_min] 整数拖入[!UICONTROL 包含的组件]下的[!UICONTROL 维度]部分中：

   ![](assets/integers.png)

1. 您现在可以添加[!UICONTROL 值分段]以分段方式在报告中表示此维度。（若不添加分段，此维度的每个实例都会显示为 Workspace 报告中的一个行项目。）

   ![](assets/bucketing.png)

## 3. 在流量图中将数值维度作为“量度” {#numeric}

您可以使用数值维度将“量度”引入[!UICONTROL 流量]可视化图表中。

1. 在数据视图[组件](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html#configure-component-settings)选项卡上，将[!UICONTROL 营销渠道]架构字段拖动到[!UICONTROL [!UICONTROL 已包含组件]下的量度]区域。
2. 在工作区报表中，此流程显示[!UICONTROL 营销渠道]流入[!UICONTROL 订单]:

![](assets/flow.png)

## 4. 子事件筛选 {#sub-event}

具体来说，此功能适用于基于数组的字段。包含/排除功能允许您在子事件层进行筛选，而内置在过滤器构建器中的过滤器（区段）仅允许您在事件层上筛选。因此，您可以使用数据视图中的包含/排除进行子事件筛选，然后在事件层过滤器中引用这一新的量度/维度。

例如，使用数据视图中的包含/排除功能仅得到销售额超过 50 美元的产品。如果您有一个订单，包括 50 美元的产品购买和 25 美元的产品购买，那么就只删除 25 美元的产品购买，而不是整个订单。

1. 在数据视图[组件](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html#configure-component-settings)选项卡上，将[!UICONTROL 收入]架构字段拖动到[!UICONTROL 量度]区域中[!UICONTROL 已包含的组件]下。
1. 选择量度并在右侧配置以下内容：
a.在[!UICONTROL Format]下，选择[!UICONTROL Currency]。
b.在[!UICONTROL 货币]下，选择USD。
c.在[!UICONTROL Include/Exclude Values]下，选中[!UICONTROL Set include/exclude values]旁边的复选框。
d.在[!UICONTROL Match]下，选择[!UICONTROL 如果满足所有条件]。
e.在[!UICONTROL 标准]下，选择[!UICONTROL 大于或等于]。
f. 指定“50”为值。

这些新设置允许您仅查看高价值收入，筛选掉任何低于 50 美元的收入。

## 5. 利用[!UICONTROL “没有值”选项]设置 {#no-value}

您的公司可能已花时间培训了用户，所以报告中预计是“未指定”。数据视图中的默认值为“没有值”。现在，您可以在数据视图 UI 中[将“没有值”重命名为“未指定”](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html#configure-no-value-options-settings)。

另一个例子是关于会员资格计划注册的一个维度。在这种情况下，您可以将“没有值”重命名为“无会员资格计划注册”。

## 6. 使用不同[!UICONTROL 归因]设置创建多个量度。 {#attribution}

使用右上方的[!UICONTROL 复制]功能，创建多个具有不同归因设置的收入量度，如[!UICONTROL 首次联系]、[!UICONTROL 最近联系]和[!UICONTROL 算法]。

不要忘记重命名每个量度以反映差异，例如“算法收入”：

![](assets/algo-revenue.png)

有关数据视图设置的更多信息，请参阅[创建数据视图](/help/data-views/create-dataview.md)。
有关数据视图的概念性概述，请参阅[数据视图概述](/help/data-views/data-views.md)。

## 7.新增与重复会话报告 {#new-repeat}

>[!NOTE]
>
>此功能当前正在进行小范围测试。

您可以根据您为此数据视图定义的报告时间范围和13个月的回顾时间范围，确定某个会话是否确实是用户的第一个会话。 通过此报表，您可以确定以下内容：

* 新会话与重复会话的订单百分比是多少？

* 对于给定的营销渠道或特定的营销活动，您定位的是首次用户还是回访用户？ 这些选项对转化率有何影响？

有三个部分有助于进行此报告：

* 1个维度： [会话类型](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=en#optional)  — 此维度有两个值：1) [!UICONTROL 新建] 和2) [!UICONTROL 返回]. 的 [!UICONTROL 新建] 行项目包括确定为人员定义的第一个会话的会话中的所有行为（即针对此维度的量度）。 其他所有内容都包含在 [!UICONTROL 返回] 行项目（假定所有内容都属于会话）。 如果量度不是任何会话的一部分，则它们将归入此维度的“不适用”存储段。

* 2个量度： [新会话、回访会话](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=en#optional). 新会话定义为人员在报告窗口内定义的第一个会话。 回访会话是非人员首次会话的会话数。

要访问这些组件，请执行以下操作：

1. 转到数据视图编辑器。
1. 单击 **[!UICONTROL 组件]** > **[!UICONTROL 可选标准组件]** 选项卡。
1. 将它们拖动到数据视图中。

95%-99%的时间，将准确报告新会议。 唯一的例外是：

* 在13个月回顾窗口之前发生第一个会话时。 此会话将被忽略。

* 当会话同时跨回顾窗口和报告窗口时。 假设您在2022年6月1日至6月15日运行报表。 回顾窗口将包含2021年5月1日至2022年5月31日。 如果某个会话将于2022年5月30日开始，并于2022年6月1日结束，因为该会话包含在回顾窗口中，则报告窗口中的所有会话都将计为返回会话。

