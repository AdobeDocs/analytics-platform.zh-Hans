---
description: 了解时间划分维度如何采用所收集事件的时间戳，并将这些事件划分为更有意义的维度，例如每天时间或每周时间。
title: 时间划分维度
feature: Dimensions
exl-id: 5c3c2867-58de-4765-a4e1-91eac1891b38
role: User
TQID: https://experienceleague.adobe.com/pWuE5mm3euhky9BVYY9CqSsdOUgESs8S8LiizcWp6t4
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 203
ht-degree: 34%

---

# 时间划分维度

时间划分会采用所收集事件的时间戳，并将其划分为更有意义的维度，例如&#x200B;**小时**&#x200B;或&#x200B;**星期**。

时间划分维度基于数据视图的时区。 Analysis Workspace中提供了这些维度，它们有助于回答以下问题：

* 在较大的日期范围内，一天中哪个时间最常被访问我的网站或应用程序？
* 在我的网站或应用程序中，是存在每天转化率较高的时间，还是存在每天的小时数？
* 我的周末销售额与工作日销售额相比如何？
* 特定营销活动是在上午还是在下午产生更高的转化？

| 维度 | 示例值 |
|--- |--- |
| **[!UICONTROL 这天的其中一个小时]** | 0 时至 23 时 |
| **[!UICONTROL 上午/下午]** | 上午，下午 |
| **[!UICONTROL 这周的其中一天]** | 星期一、星期二、星期三、星期四、星期五、星期六、星期日 |
| **[!UICONTROL 工作日/周末]** | 工作日、周末 |
| **[!UICONTROL 这月的其中一天]** | 1 日至 31 日 |
| **[!UICONTROL 这年的其中一个月]** | 1-12月份 |
| **[!UICONTROL 每年的某一天]** | 第 1 天至第 366 天 |
| **[!UICONTROL 这年的其中一个季度]** | 第一季度、第二季度、第三季度和第四季度 |
