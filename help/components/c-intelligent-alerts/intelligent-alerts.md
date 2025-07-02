---
description: 了解如何使用警报以实现通知的粒度控制，并集成异常检测。
title: 警报概述
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 94%

---

# 警报概述

Customer Journey Analytics 中的警报允许您根据变化的百分比或特定数据点收到通知。

根据您的 Customer Journey Analytics 包，您还可以使用基于异常阈值触发的警报。这些警报（也称为“智能警报”）提供与[异常检测](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)集成的粒度控制，在您最需要时触发。

警报允许您：

* 预览警报触发的频率
* 通过含链接的电子邮件或短信将警报发送到自动生成的 Analysis Workspace 项目
* 创建可在一个警报中捕获了多个量度的“堆栈式”警报。
* 根据异常情况生成警报（90%、95%、99%、99.75% 和 99.9% 阈值；% 变化；高于/低于）（仅适用于拥有 Select、Prime 或 Ultimate 包的 Customer Journey Analytics 客户）

以下视频教程提供了警报的基本概述：[警报](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=zh-Hans)（5:34）

## 了解警报有何不同

在 Customer Journey Analytics 中使用警报的过程与在 Adobe Analytics 中使用警报的过程几乎相同。但是，有一些重要的不同之处。

有关更多信息，请参阅[警报功能比较：Customer Journey Analytics 和 Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)。

## 警报的异常回顾

>[!NOTE]
>
>只有拥有 Customer Journey Analytics Select、Prime 或 Ultimate 包的组织才能使用带有异常检测的警报（也称为&#x200B;_智能警报_）。

如果警报使用异常检测，则培训期会根据为警报选择的粒度而有所不同。

* 每月粒度：15 个月及去年的相应日期范围
* 每周粒度：15 周及去年的相应日期范围
* 每天粒度：35 天及去年的相应日期范围
* 每小时粒度：336 小时

有关更多信息，请参阅[异常检测中使用的统计技术](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)。

## 创建警报

有关如何在 Customer Journey Analytics 中创建警报的信息，请参阅[创建警报](/help/components/c-intelligent-alerts/alert-builder.md)。

>[!IMPORTANT]
>
>使用带时间戳的数据创建警报可能会导致警报无法正确触发。Adobe 建议对警报使用不带时间戳的数据。

## 管理警报

您可以在警报管理器中管理现有警报。您可以对警报执行各种管理任务，例如标记、重命名、删除等。

有关如何管理 Customer Journey Analytics 中现有警报的更多信息，请参阅[管理警报](/help/components/c-intelligent-alerts/alert-manager.md)。
