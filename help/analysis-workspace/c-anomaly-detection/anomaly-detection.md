---
description: 了解 Analysis Workspace 中的数据异常检测。
title: 异常检测概述
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
role: User
TQID: https://experienceleague.adobe.com/beFLMQfzXJUoCbg6fSLpFqcbaB7GSuo6SHroSS6V5wI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: aff2ef09-fc60-4018-9197-e2befd623064
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 83%

---

# 异常检测概述

您可以在 Analysis Workspace 中基于上下文查看并分析数据异常。

[异常检测视频教程](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html?lang=zh-Hans) (4:53)

“异常检测”提供了一种统计方法来确定给定的量度相对于以前的数据发生了什么变化。

通过异常检测，您可以将“真实形势”与“假象”区分开来，然后确定对这些形势或异常造成影响的潜在因素。 换言之，它可以让您识别哪些统计波动重要，哪些不重要。 然后，您可以确定真正异常的根本原因。 此外，您可以获得可靠的量度 (KPI) 预测。

您可能会调查的异常情况包括：

* 平均订单价值显著降低
* 低收入订单的剧增
* 试用版注册量剧增或骤降
* 登陆页面浏览量骤降
* 视频缓冲事件剧增
* 视频低码率剧增

Analysis Workspace 的异常检测算法包括

* 对每小时、每周和每月粒度以及现有的每天粒度的支持。
* 季节性（如“黑色星期五”）和假日的意识。
