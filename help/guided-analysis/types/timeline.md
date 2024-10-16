---
title: 时间线视图
description: 观察一段时间内用户级别的会话事件，以查找体验模式。
feature: Adobe Product Analytics, Guided Analysis
keywords: 产品分析
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
source-git-commit: ce04e69d2c933f893eeeff04abb0f56fb4000e6f
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 1%

---

# [!UICONTROL 时间线]视图

![时间线](/help/assets/icons/Timeline.svg) **[!UICONTROL 时间线]**&#x200B;视图允许您观察一段时间内用户级别的会话事件，以查找体验模式并讲述更好的用户故事。 左边栏允许您按属性值和区段过滤流。 右边栏允许您从符合筛选条件的随机用户列表中进行选择。 中心区域按会话显示选定用户的流，包括时间戳、属性值和持续时间。 持续时间不可用于给定会话中的最后一个事件。

>[!VIDEO](https://video.tv.adobe.com/v/3427810/?learn=on)

>[!NOTE]
>
>时间轴视图要求[数据视图](/help/data-views/component-reference.md#optional)中具有&#x200B;**[!UICONTROL 人员ID]**&#x200B;标准组件。 在数据视图中包括人员ID由您的Customer Journey Analytics管理员进行管理，这使您的组织能够完全控制谁可以访问此数据。

如果数据视图未添加[!UICONTROL 人员ID]组件，则会显示以下消息：

* **管理员**： *此分析需要PersonID属性。 请向数据视图添加人员ID。*
* **非管理员**： *此分析需要PersonID属性。 请与您的Customer Journey Analytics管理员合作，将人员ID添加到数据视图。*

## 用例

此视图类型的用例包括：

* **摩擦探索**：如果在[摩擦](funnel.md)视图中发现急剧下降，则可以创建这些用户的区段，并在此视图中应用该区段来调查可能的原因。
* **错误行为**：如果用户遇到产品错误，您可以探索用户在看到该错误之前或之后正在做什么。
* **数据收集验证**：数据管理员可将此视图筛选为其自己的人员ID，以验证其组织的实施是否按预期工作。

## 查询边栏

利用查询边栏，可配置以下组件：

* **[!UICONTROL 属性]**：要查看其流式处理值的属性。 中心流显示选定属性的值。 您还可以应用过滤器来将流缩小到更相关的数据。 筛选器的有效运算符包括[!UICONTROL 等于]、[!UICONTROL 不等于]、[!UICONTROL 开头为]、[!UICONTROL 结尾为]、[!UICONTROL 包含]、[!UICONTROL 不包含]、[!UICONTROL 存在]和[!UICONTROL 不存在]。
* **[!UICONTROL 区段]**：要分析的区段。 所选区段会过滤您的数据，以仅关注符合您的区段标准的个人。 如果要将视图缩小到特定人员ID，则可以在此处筛选到该人员ID。 此视图支持一个区段。

## 图表设置

[!UICONTROL 时间轴]视图提供了以下图表设置，可以在图表上方的菜单中调整这些设置：

* **[!UICONTROL 显示为]**：显示所需的属性值。
   * [!UICONTROL 显示全部]：显示会话中的所有属性值。
   * [!UICONTROL 突出显示]：以可视方式突出显示会话中与查询筛选器匹配的属性值。
   * [!UICONTROL 仅查看]：仅在匹配查询筛选器的会话中显示属性值。

## 日期范围

分析所需的日期范围。 此设置包含两个组件：

* **[!UICONTROL 时间间隔]**：要查看趋势数据的日期粒度。 此设置不会影响非趋势视图，例如时间线。
* **[!UICONTROL 日期]**：开始和结束日期。 您可以为方便起见，使用滚动日期范围预设和以前保存的自定义范围，也可以使用日历选择器来选择固定日期范围。
