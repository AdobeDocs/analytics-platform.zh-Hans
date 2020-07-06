---
description: 您可以在 Analysis Workspace 中根据上下文查看和分析数据异常。
title: 异常检测概述
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 88%

---


# 异常检测概述

>[!NOTE]
>
>您正在查看Customer Journey Analytics中的Analysis Workspace文档。 其功能集与传统Adobe [Analytics的Analysis Workspace略有不同](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html)。 [了解更多...](/help/getting-started/cja-aa.md)

您可以在 Analysis Workspace 中根据上下文查看和分析数据异常。

[YouTube 上的异常检测](https://www.youtube.com/watch?v=krXyQCjXoeU&amp;index=63&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:53)

“异常检测”提供了一种统计方法来确定给定的量度相对于以前的数据发生了什么变化。

通过异常检测，您可以将“真实形势”与“假象”区分开来，然后确定对这些形势或异常造成影响的潜在因素。换言之，该功能可让您确认哪些统计波动会造成影响，而哪些不会。然后您便可以确认真正异常的根本原因。此外，您可以获得可靠的量度 (KPI) 预测。

您可能会调查的异常情况包括：

* 平均订单值的显著降低
* 低收入订单的剧增
* 试用注册量剧增或骤降
* 登录页面查看次数骤降
* 视频缓冲事件剧增
* 低视频比特率剧增

异常检测和[贡献分析](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html)是 Analysis Workspace 中的核心工作流程。您可以针对任何每日异常运行“贡献分析”，并将结果嵌入到您的 Analysis Workspace 项目中。

>[!IMPORTANT]
>
>贡献分析尚未在Customer Journey Analytics中提供。

Analysis Workspace 的异常检测算法包括

* 对每小时、每周和每月粒度以及现有的每天粒度的支持。
* 季节性（如“黑色星期五”）和假日的概念。

## 关闭异常检测

您可以转到列设置并取消选中&#x200B;**[!UICONTROL 异常]**&#x200B;来在列级别关闭异常检测。

![](assets/turnoff_anomalies.png)
