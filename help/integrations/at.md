---
title: Adobe Customer Journey Analytics中的Target报表
description: 将Adobe Target与Customer Journey Analytics集成
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
source-git-commit: b189776de8cadae3a93c717b6814f2130ab1be43
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 40%

---

# Adobe Customer Journey Analytics中的Target报表

使用Customer Journey Analytics中的Target报表功能，您可以直接在Customer Journey Analytics中测量和报告Adobe Target活动。 此功能与通过Analytics for Target (A4T)在Adobe Analytics (AA)中执行的功能类似，只是与Adobe Experience Platform (AEP)存在连接。

通过将Target分类查找数据集(默认情况下在Experience Platform中可用)添加到Customer Journey Analytics连接，用户现在可以充分了解Target报表工具、Target订单归因和其他功能。 只需在Customer Journey Analytics数据视图中进行一些小的准备和调整，任何希望将Target数据直接发送到CJA的用户都可以立即使用这些活动。

## 主要优势

* 营销人员可以随时将 Customer Journey Analytics 成功量度动态地应用到 Target 活动报表。在运行活动之前不需要指定各项内容。
* 营销人员可以利用 Customer Journey Analytics 功能（例如实验面板）进一步分析其网站个性化。
* 营销人员可以拥有 Adobe Journey Optimizer 和 Target 的单一报告来源。这两种个性化产品都可以连接到 Customer Journey Analytics，以便更全面地了解您的 Web 个性化情况。

## 注释和注意事项

将目标分类事件数据集添加到CJA连接后，在将这些组件添加为维度后，将在CJA数据视图中进行一些细微调整，包括：

* 设置持久性类似于在Target中跟踪持久性的方式（请与Target顾问或客户确认以确保设置正确）。

* 将持久性设置为ALL ，这允许同时跟踪多个Target活动，且不会被将来或以前的活动覆盖。

## 更多详细信息

有关更多信息，请参阅 Target 文档中的 [Adobe Customer Journey Analytics 中的 Target 报告](https://experienceleague.adobe.com/zh-hans/docs/target/using/integrate/cja/target-reporting-in-cja) 。

请参阅[实验面板](../analysis-workspace/c-panels/experimentation.md)，以获取有关分析师如何比较不同的用户体验、营销或消息传递变化以确定哪种方式最能推动特定结果的更多信息。您可以从任何试验平台评估任何 A/B 试验的提升度和置信度：在线、离线、来自 Target 或 Adobe Journey Optimizer 等 Adobe 解决方案、甚至是 BYO（自带）数据。
