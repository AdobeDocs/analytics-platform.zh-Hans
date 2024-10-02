---
title: 自由格式表中的动态维度项与静态维度项
description: 如何与表中的动态维度项和静态维度项交互
feature: Visualizations
exl-id: 7806f535-15c7-40f4-955a-724d9752969d
role: User
source-git-commit: 6a279ac39e6b94200ff93ac1a3796d202e6349c7
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 50%

---

# 自由格式表中的动态和静态维度项目

在自由格式表中，行和列包含各种组件值。这些值可以是动态的（随时间而改变）或静态的（不随时间而改变），具体取决于您要构建的分析。

## 动态维度项目

动态维度项目会随时间而改变，具体取决于自由格式表中按其排序的量度。 如果要分析给定时间段内排名靠前的项目，可首选使用动态维度项目。

将维度拖放到自由格式表后，将返回动态行。动态行表示与给定量度和时间段的维度对应的排名最前的项目。 此外，您还可以将某个维度拖放到自由格式表的列中，该维度会自动扩展为排名前 5 的维度项目。

例如，将“浏览器类型”维度拖入表中后，则排名靠前的“浏览器类型”维度项目（例如 Microsoft、Apple、Google 等）会动态返回到表行。如果拖放到列中，则会动态返回排名前 5 的“浏览器类型”维度项目。

动态维度项目具有行筛选器选项![筛选器](/help/assets/icons/Filter.svg)和![关闭](/help/assets/icons/Close.svg)，并且&#x200B;**不**&#x200B;存在锁![LockClosed](/help/assets/icons/LockClosed.svg)。 <!--do they have the lock icon? -->当您单击动态维度项旁边的![关闭](/help/assets/icons/Close.svg)时，将自动应用筛选器。 有关将筛选器应用到表的详细信息，请参阅[筛选和排序表](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)。


![突出显示过滤器图标的自由格式表。](assets/dynamic-items.png)

## 静态维度项目

静态维度项目不会随时间而改变；它们是自由格式表中始终返回的固定组件。如果您希望始终分析同一项目（无论是特定促销活动还是一周中的特定日期），可首选使用静态维度项目。

每当您手动选择特定组件值（维度、量度、过滤器、日期范围）并将其拖放到表中后，就会生成行或列的静态列表。

例如，当您将鼠标拖到特定的“浏览器类型”项目（例如 Microsoft 和 Apple）上时，这 2 个特定项目始终会提取到表中。

如果选择从所选行的上下文菜单中选择&#x200B;**[!UICONTROL 仅显示所选行]**，则也可以创建静态维度项。

静态维度项目&#x200B;**没有**&#x200B;行过滤器选项。相反，每个项目都有![LockClosed](/help/assets/icons/LockClosed.svg)和![Close](/help/assets/icons/Close.svg)。 选择![关闭](/help/assets/icons/Close.svg)以从表中删除该维度项。

![显示浏览器类型和带有锁图标的Microsoft行的自由格式表注意：此维度项是静态的，不会随时间而改变。](assets/static-items.png)

## 混合维度项目

来自不同维度的维度项目可以添加到同一个表中。在这些情况下，行标题显示&#x200B;**[!UICONTROL 混合Dimension]**。 这些维度项目是静态的。例如，从“浏览器组”维度添加特定维度项目，以及从“浏览器名称”维度添加其他维度项目。

![突出显示混合Dimension列的自由格式表。](assets/mixed-dimensions.png)

## 自由格式表总计行

动态行和静态行在自由格式表总计行中的行为方式有所不同。默认情况下：

* 动态行是服务器端总和，并且去除了重复量度，例如会话或人员。
* 静态行是客户端总和，并且&#x200B;**不会**&#x200B;去除重复量度。要计算服务器端总计行，请将“行”设置更改为&#x200B;**“显示总计”**。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html?lang=zh-Hans)
