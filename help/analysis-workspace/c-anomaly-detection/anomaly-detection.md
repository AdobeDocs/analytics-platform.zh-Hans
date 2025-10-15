---
description: 了解 Analysis Workspace 中的数据异常检测。
title: 异常检测概述
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
role: User
source-git-commit: e07b901f66a59aba1a7a517443eec73387d23c57
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 25%

---

# 异常检测概述

您可以在 Analysis Workspace 中基于上下文查看并分析数据异常。

[异常检测视频教程](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html?lang=zh-Hans) (4:53)

“异常检测”提供了一种统计方法来确定给定的量度相对于以前的数据发生了什么变化。

异常检测允许您将“真实信号”与“噪声”分离，然后识别导致这些信号或异常的潜在因素。 换言之，它可以让您识别哪些统计波动重要，哪些不重要。然后，您可以确定真正异常的根本原因。 此外，您还可以获得可靠的指标(KPI)预测。

您可能会调查的异常示例包括：

* 平均订单价值急剧下降
* 收入较低的订单激增
* 试用注册数量激增或下降
* 登陆页面查看次数下降
* 视频缓冲事件激增
* 低视频比特率激增

Analysis Workspace的异常检测算法包括

* 支持每小时、每周和每月粒度，以及现有的每日粒度。
* 注意季节性（如“黑色星期五”）和假日。
