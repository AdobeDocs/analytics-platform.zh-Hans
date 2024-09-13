---
description: 新的智能警报系统允许对警报进行更多粒度控制，而且还将异常检测与警报系统集成在一起。
title: 智能警报概述
feature: Workspace Basics
role: User, Admin
source-git-commit: 1613b3fc7e9cce1fb74b86bb7435612b2d469eb1
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 56%

---

# 智能警报概述

Customer Journey Analytics中的“智能警报”（或“警报”）允许您在数据中发生异常事件时收到通知。

您可以设置根据异常阈值、变化的百分比或特定数据点触发的警报。警报提供与[异常检测](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)集成的粒度控件，在您最需要它们时触发。

智能警报允许您：

* 构建基于异常的警报（90%、95%、99%、99.75% 和 99.9% 阈值；% 更改；以上/以下）。
* 预览警报触发的频率
* 通过含链接的电子邮件或短信将警报发送到自动生成的 Analysis Workspace 项目
* 创建可在一个警报中捕获了多个指标的“堆栈式”警报。

以下视频教程提供了警报的基本概述： [智能警报](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=zh-Hans) (5:34)

## 了解警报与Adobe AnalyticsCustomer Journey Analytics有何不同

在 Customer Journey Analytics 中使用智能警报的过程与在 Adobe Analytics 中使用智能警报的过程几乎相同。然而，两者之间有着重要的区别。

有关详细信息，请参阅[智能警报功能比较：Customer Journey Analytics和Adobe Analytics](/help/analysis-workspace/c-intelligent-alerts/alerts-feature-comparison.md)。

## 警报的异常回顾

如果警报使用异常检测，则培训期会根据为警报选择的粒度而有所不同。

* 每月粒度：15 个月及去年的相应日期范围
* 每周粒度：15 周及去年的相应日期范围
* 每天粒度：35 天及去年的相应日期范围
* 每小时粒度：336 小时

有关详细信息，请参阅[异常检测中使用的统计技术](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)。

## 创建警报

有关如何在Customer Journey Analytics中创建警报的信息，请参阅[创建警报](/help/analysis-workspace/c-intelligent-alerts/alert-builder.md)。

>[!IMPORTANT]
>
>使用带时间戳的数据创建警报可能会导致警报无法正确触发。Adobe 建议对智能警报使用不带时间戳的数据。

## 管理警报

您可以在警报管理器中管理现有警报。 您可以对警报执行各种管理任务，如标记、重命名、删除等。

有关如何管理Customer Journey Analytics中现有警报的详细信息，请参阅[管理警报](/help/analysis-workspace/c-intelligent-alerts/alert-manager.md)。

