---
title: 时间线视图
description: 浏览会话活动中的模式。
feature: Guided Analysis
keywords: 产品分析
role: User
source-git-commit: ecdbe1b68aa0824bd9db4acefd3ef9059d9ac927
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---

# [!UICONTROL 时间线] 视图

此 **[!UICONTROL 时间线]** 视图允许您分析各个会话以确定行为模式。 右边栏允许您选择要分析的人员ID。 中心区域显示人员的时间、选定的属性值和每个事件的持续时间。

此分析要求您添加 **[!UICONTROL 人员ID]** 标准组件到 [数据视图](/help/data-views/component-reference.md#optional). 如果您没有 [!UICONTROL 人员ID] 组件添加到数据视图，将显示以下消息：

> 此分析需要PersonID属性。请将PersonID添加到数据视图。

## 用例

此视图类型的用例包括：

* **摩擦探究**：如果您发现 [摩擦](friction.md) 视图，您可以使用此视图调查该下降的潜在原因。
* **错误行为**：如果用户在您的产品中遇到错误，您可以探索用户在看到该错误之前或之后做什么。
* **数据收集验证**：数据管理员可以筛选此视图以隔离自己。 此视图提供了一种可靠的方法，可确保贵组织的实施按预期工作。

## 查询边栏

利用查询边栏，可配置以下组件：

* **[!UICONTROL 属性]**：要查看其值的属性。 中心的会话分析显示此处所选属性的值。 您还可以按选定的属性过滤数据。 筛选器的有效运算符包括 [!UICONTROL 等于]， [!UICONTROL 不等于]， [!UICONTROL 开头为]， [!UICONTROL 结束于]， [!UICONTROL 包含]， [!UICONTROL 不包含]， [!UICONTROL 存在]、和 [!UICONTROL 不存在].
* **[!UICONTROL 区段]**：要测量的区段。 所选区段会过滤您的数据，以仅关注符合您的区段标准的个人。 此视图支持一个区段。

## 图表设置

此 [!UICONTROL 时间线] 视图提供了以下图表设置，可在图表上方的菜单中调整这些设置：

* **[!UICONTROL 显示为]**：显示所需的属性值。
   * [!UICONTROL 显示所有]
   * [!UICONTROL 突出显示]
   * [!UICONTROL 仅查看]

## 日期范围

分析所需的日期范围。 此设置包含两个组件：

* **[!UICONTROL 间隔]**：要查看趋势数据所依据的日期粒度。 此设置不会影响非趋势视图，例如时间线。
* **[!UICONTROL 日期]**：开始日期和结束日期。 您可以为方便起见，使用滚动日期范围预设和以前保存的自定义范围，也可以使用日历选择器来选择固定日期范围。
