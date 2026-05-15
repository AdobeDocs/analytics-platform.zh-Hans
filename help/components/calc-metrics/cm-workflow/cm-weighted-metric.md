---
description: 显示计算指标的示例。
title: 计算量度示例
feature: Calculated Metrics
exl-id: 5e73ab52-627a-4064-bfb7-354c0ba1e4ee
TQID: https://experienceleague.adobe.com/awAk0boIVigYBssgLcSz3t-5eExHhasCVDtwoa3v19k
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 252
ht-degree: 4%

---

# 计算量度示例

本文举例说明如何定义更高级的计算指标。

## 跳出率

您希望计算跳出率。

+++ 详细信息

跳出的定义将在另一篇讨论中讨论，但在本例中，您定义了一个“跳出”事件区段，其中会话开始等于1，会话结束等于1。 使用此区段可以定义会话的退回率。


### 区段

![退回事件](assets/example-bounce-bouncedevents.png)

### 计算量度

![跳出率](assets/example-bounce-rate.png)


### 派生字段

或者，您可以使用派生字段[&#128279;](/help/data-views/derived-fields/derived-fields.md#bounces)定义跳出率。

派生字段是数据视图的一部分，其优点是并非每个用户都可以覆盖或修改跳出率量度的定义。 这一优势也带来了局限性。 无权访问数据视图的用户无法使用派生字段，并且必须依靠区段和计算量度来定义跳出率。

有关如何在Customer Journey Analytics中计算跳出率和跳出率的更多背景信息，请参阅此[博客帖子](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446)。

+++


## 条件页面查看次数

您要定义一个计算度量，该度量只计算100多个会话中已访问页面的页面查看次数。

+++ 详细信息 

![条件页面查看次数](assets/conditional-page-views.png)

+++

## 前30%会话的页面查看次数

您要定义一个计算度量，该度量只计算前30%会话的页面查看次数。

+++ 详细信息

![前30%页面查看次数](assets/top30-page-views.png)

+++
