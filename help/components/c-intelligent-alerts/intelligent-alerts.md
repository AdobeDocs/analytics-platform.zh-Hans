---
description: 了解如何使用警报功能，以实现对通知的精细化控制，并与异常检测集成。
title: 警报概述
feature: Workspace Basics
role: User, Admin
exl-id: 029be0c8-ec78-4bb7-a6cd-bb303b5ac82a
source-git-commit: 65e46a5d2a6759dd83b24bba2d1d4ee283b907c9
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 58%

---

# 警报概述

Customer Journey Analytics 中的警报允许您根据变化的百分比或特定数据点收到通知。

根据您的 Customer Journey Analytics 包，您还可以使用基于异常阈值触发的警报。这些警报（也称为&#x200B;*智能警报*）提供了与[异常检测](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)集成的粒度控制，在您最需要它们时触发。

* 预览警报触发的频率。
* 通过含链接的电子邮件或短信将警报发送到自动生成的 Analysis Workspace 项目。
* 创建可在一个警报中捕获了多个量度的&#x200B;*栈叠*&#x200B;警报。
* 根据以下条件生成警报：
   * 量度中的异常存在、高于或低于预期阈值。

     [异常检测](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)使用历史数据构建预期值以及上限和下限。 如果实际度量值高于定义为阈值的上限或低于下限，则该事件在阈值置信度级别被视为异常，并且会触发警报。 阈值越高（例如：99%或99.9%），则警报频度越大，由更极端的异常导致的警报就越少。 较低的阈值（例如：90%）意味着较窄的频带，这会导致由不太极端的异常引起的警报增加。
   * 按特定百分比列出的量度更改。
   * 大于、小于或等于特定值的量度。 (仅适用于具有Select、Prime或Ultimate包的Adobe Analytics客户)

此[视频教程](https://experienceleague.adobe.com/zh-hans/docs/analytics-learn/tutorials/data-science/intelligent-alerts)提供了警报的基本概述。



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
