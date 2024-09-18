---
description: 警报允许对通知进行粒度控制，并集成异常检测。
title: 警报概述
feature: Workspace Basics
role: User, Admin
source-git-commit: def8b074ea468e409e340415d5e96f75d6b69312
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 27%

---

# 警报概述

Customer Journey Analytics中的警报允许您根据更改的百分比或特定数据点接收通知。

根据您的Customer Journey Analytics包，您还可以使用要基于异常阈值触发的警报。 这些警报（也称为“智能警报”）提供了与[异常检测](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)集成的粒度控制，在您最需要它们时触发。

警报允许您：

* 预览警报触发的频率
* 通过含链接的电子邮件或短信将警报发送到自动生成的 Analysis Workspace 项目
* 创建可在一个警报中捕获了多个指标的“堆栈式”警报。
* 构建基于异常（90%、95%、99%、99.75%和99.9%阈值；百分比更改；以上/以下）的警报(仅适用于具有Select、Prime或Ultimate程序包的Customer Journey Analytics客户)

以下视频教程提供了警报的基本概述： [警报](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=zh-Hans) (5:34)

## 了解警报与Adobe AnalyticsCustomer Journey Analytics有何不同

在Customer Journey Analytics中使用警报的流程与在Adobe Analytics中使用警报的流程几乎相同。 然而，两者之间有着重要的区别。

有关详细信息，请参阅[警报功能比较：Customer Journey Analytics和Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)。

## 警报的异常回顾

>[!NOTE]
>
>使用具有异常检测（也称为&#x200B;_智能警报_）的警报仅适用于具有Select、Prime或UltimateCustomer Journey Analytics包的组织。

如果警报使用异常检测，则培训期会根据为警报选择的粒度而有所不同。

* 每月粒度：15 个月及去年的相应日期范围
* 每周粒度：15 周及去年的相应日期范围
* 每天粒度：35 天及去年的相应日期范围
* 每小时粒度：336 小时

有关详细信息，请参阅[异常检测中使用的统计技术](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)。

## 创建警报

有关如何在Customer Journey Analytics中创建警报的信息，请参阅[创建警报](/help/components/c-intelligent-alerts/alert-builder.md)。

>[!IMPORTANT]
>
>使用带时间戳的数据创建警报可能会导致警报无法正确触发。Adobe建议对警报使用不带时间戳的数据。

## 管理警报

您可以在警报管理器中管理现有警报。 您可以对警报执行各种管理任务，如标记、重命名、删除等。

有关如何管理Customer Journey Analytics中现有警报的详细信息，请参阅[管理警报](/help/components/c-intelligent-alerts/alert-manager.md)。

