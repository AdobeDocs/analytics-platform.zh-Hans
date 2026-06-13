---
title: 从Google Analytics 4过渡到Customer Journey Analytics
description: 了解在Customer Journey Analytics中获取报表的关键概念，适用于熟悉Google Analytics 4的分析师。
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: 3d7c8b91-f2a4-4e6b-9c1d-5f8e3a720469
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 046df00868ca4a5b3bab3eb36cca7d91b141333a
workflow-type: tm+mt
source-wordcount: 590
ht-degree: 3%

---


# 从Google Analytics 4过渡到Customer Journey Analytics

本指南可帮助熟悉Google Analytics 4的分析人员了解Adobe Customer Journey Analytics中的等效概念和报表。 如果您负责技术实施而不是报告，请参阅[从第三方分析解决方案升级到Customer Journey Analytics](../cja-upgrade/cja-upgrade-third-party-solution.md)，以获取有关Web SDK设置和数据摄取的指导。 如果贵组织仍需要将现有Google Analytics数据迁移到Adobe Experience Platform，请参阅[从Google Analytics迁移数据](/help/use-cases/third-party/ga/overview.md)。

## GA4和Customer Journey Analytics之间的主要区别

GA4和Customer Journey Analytics具有相同的基本理念：每个用户交互都是一个事件，并且分析是在一个空白画布工具中执行的，在该工具中，您可以拖放维度和量度以构建自定义视图。 如果您熟悉GA4 Explore ，那么可以立即识别Analysis Workspace。

最显着的区别在于Customer Journey Analytics在GA4之外有何扩展：

* **跨渠道数据**： Customer Journey Analytics可以在同一分析中将Web分析与离线数据源（如呼叫中心记录、CRM活动、忠诚度计划或电子邮件参与）相结合。 GA4仅限于通过其SDK收集的数字交互。
* **报表时间处理**： Customer Journey Analytics在查询时而非收集时应用归因模型、会话定义和区段规则等逻辑。 对会话定义或归因模型所做的更改会逆向应用于所有历史数据，而无需重新处理。
* **灵活的会话定义**：会话超时持续时间、会话开始事件和会话结束事件均可按Customer Journey Analytics中的数据视图进行配置。 GA4的会话超时可调（默认为30分钟，最多7小时55分钟），但适用于属性范围，并且其会话开始和会话结束行为是固定的。
* **身份拼接**：Customer Journey Analytics的拼合功能可以将跨设备和跨渠道交互链接到同一个人，从而生成比GA4的混合身份模型更准确的人数。

## 帐户和数据结构

GA4和Customer Journey Analytics在平台级别采用不同的方式整理数据。

| GA4 | Customer Journey Analytics |
|---|---|
| Google帐户 | Adobe IMS组织 |
| 属性 | 连接+数据视图 |
| 数据流 | Platform中的[!UICONTROL 事件数据集] |
| 数据过滤器 | 数据视图组件筛选器 |
| 子属性 | 应用了筛选器的单独数据视图 |
| 汇总属性 | 组合多个数据集的连接 |

最重要的结构区别在于GA4属性将数据布线和报告处理为单个对象。 Customer Journey Analytics将这些概念分为两个不同的层：

* **连接**&#x200B;将一个或多个Adobe Experience Platform数据集链接到Customer Journey Analytics。 此步骤会以针对报表而优化的格式将数据摄取到Customer Journey Analytics。
* **数据视图**&#x200B;基于连接生成，并定义哪些维度、量度和设置可用于报告。 它是报表配置层。

在Customer Journey Analytics中分析数据之前，必须存在这两个变量。 Customer Journey Analytics中没有报表包。

## Analysis Workspace快速入门

GA4 Explore和Analysis Workspace都是空白画布和拖放分析工具。 交互模型相同，术语略有不同。

| GA4浏览 | Analysis Workspace |
|---|---|
| 探索画布 | 面板 |
| 图表或可视化图表类型 | 可视化图表 |
| 维度 | 维度 |
| 量度 | 量度 |
| 区段或过滤器 | 区段 |
| 事件计数 | [!UICONTROL 事件] |
| 用户 | [!UICONTROL 人员] |
| 会话 | [!UICONTROL 会话] |

>[!TIP]
>
>GA4区段容器的名称为“用户”、“会话”和“事件”。 在Customer Journey Analytics中，等效的容器为&#x200B;**[!UICONTROL 人员]**、**[!UICONTROL 会话]**&#x200B;和&#x200B;**[!UICONTROL 事件]**。 作用域逻辑相同。

>[!MORELIKETHIS]
>
>* [从Google Analytics迁移数据](/help/use-cases/third-party/ga/overview.md)
