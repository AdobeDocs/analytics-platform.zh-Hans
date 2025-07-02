---
title: 数据视图用例
description: 了解多个用例，这些用例显示Customer Journey Analytics中数据视图的灵活性和强大功能
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0e9dc47b80db142801a94dcbf31470d99a610949
workflow-type: tm+mt
source-wordcount: '1358'
ht-degree: 30%

---

# 数据视图用例

这些用例说明了Customer Journey Analytics中数据视图的灵活性和强大功能。

## 使用绑定维度量度

有关更多详细信息，请参阅[使用绑定维度量度](binding-dimensions-metrics.md)用例。

## 使用摘要数据

有关详细信息，请参阅[使用摘要数据](summary-data.md)用例。

## BI 扩展用例

请参阅[BI扩展用例](bi-extension-usecases.md)，了解如何使用Customer Journey Analytics BI扩展完成多个用例。

## 根据字符串架构字段创建量度 {#string}

例如，在创建数据视图时，您可以根据字符串形式的[!UICONTROL 页面标题]架构字段创建一个[!UICONTROL 订单]量度。



1. 在&#x200B;**[!UICONTROL 组件]**&#x200B;选项卡上，将&#x200B;**[!UICONTROL 页面标题]**&#x200B;拖到&#x200B;**[!UICONTROL 包含的组件]**&#x200B;下的[!UICONTROL 量度]部分。
1. 突出显示您刚才拖入的量度，并在上的`Orders`组件设置&#x200B;**[!UICONTROL 中将其重命名为]**
1. 打开&#x200B;**[!UICONTROL 包括/排除值]**&#x200B;部分，并指定以下内容：
   1. 启用&#x200B;**[!UICONTROL 设置包括排除值]**。
   1. 从&#x200B;**[!UICONTROL 匹配]**&#x200B;中选择&#x200B;**[!UICONTROL 如果满足所有条件]**。
   1. 指定`confirmation`。 **[!UICONTROL page_title]**&#x200B;的文本指示此页面与下订单相关。 在查看满足这些条件的所有页面标题后，将为每个实例计算`1`。 结果是一个新量度（而非计算量度）。具有已添加/排除值的量度可用于可使用任何其他量度的任何位置。 这些量度可与归因、区段配合使用，以及用在可使用标准量度的任何其他位置。

   ![Dimension到指标](../assets/string-to-metric.gif){width=100%}
1. 您可以进一步为此量度指定归因模型，例如[!UICONTROL 回顾时间范围]为[!UICONTROL 会话]的[!UICONTROL 最近联系]。
您还可以根据同一字段创建另一个[!UICONTROL 订单]量度，并指定不同的归因模型。 如[!UICONTROL 首次联系]和其他[!UICONTROL 回顾时间范围]，如[!UICONTROL 30天]。

另一个示例是使用人员ID作为维度来确定您的公司有多少人员ID。

## 使用整数作为维度 {#integers}

以前，整数会被自动视为Customer Journey Analytics中的量度。 现在，数字（包括 Adobe Analytics 中的自定义事件）可被视为维度。示例如下：



1. 将&#x200B;**[!UICONTROL 持续时间]**&#x200B;整数拖入&#x200B;**[!UICONTROL 包含的组件]**&#x200B;下的[!UICONTROL 维度]节：
1. 您现在可以添加&#x200B;**[!UICONTROL 值分段]**&#x200B;以分段方式在报告中表示此维度。如果不进行分段，此维度的每个实例都会显示为Workspace报表中的行项目。
   ![整数到维度](../assets/integer-to-dimension.gif){width=100%}


## 在流量图中将数值维度用作量度 {#numeric}

您可以使用数值维度将量度纳入[!UICONTROL 流量]可视化图表。

1. 在数据视图[组件](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview)选项卡上，将[!UICONTROL 营销渠道]架构字段拖动到[!UICONTROL [!UICONTROL 已包含组件]下的量度]区域。
2. 在工作区报表中，此流程显示[!UICONTROL 营销渠道]流入[!UICONTROL 订单]:

![营销渠道从电子邮件流向退出/订单。](../assets/flow.png)

## 执行子事件筛选 {#sub-event}

具体来说，此功能适用于基于数组的字段。包含/排除功能允许您在子事件级别进行筛选，而内置在区段生成器中的区段仅允许您在事件级别进行分段。 您可以使用数据视图中的包含/排除进行子事件筛选，然后在事件级别的区段中引用这一新的量度/维度。

例如，使用数据视图中的包含/排除功能，仅重点关注产生的销售额超过$50的产品。 因此，如果您的订单包括$50的产品购买和$25的产品购买，则包含/排除功能会删除$25的产品购买，而不是整个订单。

1. 在数据视图[组件](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview)选项卡上，将&#x200B;**[!UICONTROL 收入]**&#x200B;架构字段拖动到&#x200B;**[!UICONTROL 量度]**&#x200B;区域中[!UICONTROL 已包含的组件]下。
1. 选择量度并在右侧配置以下内容：
a.在&#x200B;**[!UICONTROL Format]**&#x200B;下，选择&#x200B;**[!UICONTROL Currency]**。
b.在&#x200B;**[!UICONTROL 货币]**&#x200B;下，选择&#x200B;**[!UICONTROL USD]**。
c.在&#x200B;**[!UICONTROL Include/Exclude Values]**&#x200B;下，选中&#x200B;**[!UICONTROL Set include/exclude values]**&#x200B;旁边的复选框。
d.在&#x200B;**[!UICONTROL Match]**&#x200B;下，选择&#x200B;**[!UICONTROL 如果满足所有条件]**。
e.在&#x200B;**[!UICONTROL 标准]**&#x200B;下，选择&#x200B;**[!UICONTROL 大于或等于]**。
f.指定`50`作为值。

这些新设置允许您仅查看高价值收入，筛选掉任何低于 50 美元的收入。

## 使用[!UICONTROL 无值选项]设置 {#no-value}

您的公司可能已花时间培训了用户，因此报告中维度预计为“未指定”。 数据视图中维度的默认值为&#x200B;*无值*。 但是，您可以为每个维度指定如何报告无值。 查看维度组件的&#x200B;**[!UICONTROL 无值]**&#x200B;选项。

![无值选项](../assets/no-value-options.gif){width=100%}


## 使用不同的归因设置创建多个量度 {#attribution}

使用右上角的&#x200B;**[!UICONTROL 复制]**&#x200B;功能创建多个具有不同归因设置的总收入量度，如&#x200B;**[!UICONTROL 首次联系]**、**[!UICONTROL 最近联系]**&#x200B;和&#x200B;**[!UICONTROL 算法]**。

不要忘记重命名每个量度以反映差异，例如`Total Revenue (Algorithmic)`

![重复不同归因设置的量度](../assets/duplicate-metric-for-attribution.gif){width=100%}

有关数据视图设置的更多信息，请参阅[创建数据视图](/help/data-views/create-dataview.md)。
有关数据视图的概念性概述，请参阅[数据视图概述](/help/data-views/data-views.md)。

## 新会话和回归会话报告 {#new-repeat}

您可以确定某个会话到底是某个用户的首次会话，还是回归会话。 基于为此数据视图定义的报表时段和13个月的回溯时段。 通过此报表可确定，例如：

* 您的订单中有多大百分比来自新会话或回归会话？

* 对于给定的营销渠道或特定的营销活动，您是面向首次访问的用户还是回归用户？此选择如何影响转化率？

有一个维度和两个指标可简化此报表：

* [会话类型](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference) — 此维度有两个值：[!UICONTROL New]和[!UICONTROL Returning]。 [!UICONTROL New]行项目包括已确定为个人的首次会话的所有行为（即针对该维度的量度）。 其他所有内容都包含在[!UICONTROL 返回]的行项目中（假设所有内容都属于一个会话）。如果量度不是任何会话的一部分，则它们属于该维度的“不适用”范围。 

* [首次会话](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference)。 首次会话量度被定义为个人在报告窗口内定义的首次会话。

* [返回会话](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference)返回会话量度是非个人首次会话的会话数。—>

要访问组件，请执行以下操作：

1. 进入数据视图编辑器。
1. 选择&#x200B;**[!UICONTROL 组件]**&#x200B;选项卡，然后从左边栏中选择&#x200B;**[!UICONTROL 标准组件]**。
1. 将&#x200B;**[!UICONTROL 会话类型]**、**[!UICONTROL 首次会话]**&#x200B;和&#x200B;**[!UICONTROL 返回会话]**&#x200B;组件拖动到数据视图中。

新会话几乎总是准确报告。 唯一的例外是：

* 当首次会话发生在 13 个月的回看窗口之前时。 <br/>此会话被忽略。
* 当会话同时跨越回看窗口和报告窗口时。<br/>例如，您从2022年6月1日到2022年6月15日运行报告。 回看窗口期将为2021年5月1日至2022年5月31日。 如果会话从2022年5月30日开始，到2022年6月1日结束，则该会话将包含在回看窗口中。 并且报告窗口中的所有会话都计为返回会话。

## 使用日期和日期时间功能 {#date}

Adobe Experience Platform 中的架构包含[!UICONTROL 日期]和[!UICONTROL 日期时间]字段。 Customer Journey Analytics数据视图现在支持这些字段。 将这些字段作为维度拖动到数据视图中时，可以指定其[格式](/help/data-views/component-settings/format.md)。 此格式设置确定字段在报告中的显示方式。 例如：

* 对于日期格式，如果您选择&#x200B;**[!UICONTROL 天]**&#x200B;格式为&#x200B;**[!UICONTROL 月、日、年]**，则报告中的示例输出可能如下所示：2022 年 8 月 23 日。

* 对于日期时间格式，如果选择&#x200B;**[!UICONTROL 一天中的分钟]**&#x200B;格式为&#x200B;**[!UICONTROL 小时:分钟]**，则输出可能为：20:20。

支持1900年1月1日之后的日期（1970年1月1日除外）和2000年1月1日之后的日期时间值00:00:00。

### 日期和日期时间用例

* 日期：旅行公司收集旅行的出发日期作为其数据中的字段。 公司希望有一份报告，其中对收集的所有出发日期的[!UICONTROL 每周时间]进行比较，以了解哪一天最受欢迎。 公司希望对[!UICONTROL 月份]执行相同的操作。

* 日期时间：零售公司收集其每一次店内销售点(POS)购买的时间。 在给定的一个月内，公司希望了解一天[!UICONTROL 小时]中最繁忙的购物时段。

>[!MORELIKETHIS]
>
>格式组件设置中的[日期和日期时间](/help/data-views/component-settings/format.md)
>

