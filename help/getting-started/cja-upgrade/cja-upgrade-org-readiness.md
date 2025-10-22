---
title: 从 Adobe Analytics 升级到 Customer Journey Analytics
description: 了解从 Adobe Analytics 升级到 Customer Journey Analytics 时的推荐步骤
role: Admin
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 7c0342a68f75774fd7b29979d3ce610f22d047ae
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 8%

---

# 准备您的组织以升级到Customer Journey Analytics

成功升级(如[从Adobe Analytics升级到Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)中所述)的部分步骤是，通过关注某些操作注意事项来准备您的组织。 要准备您的组织，建议您：

* 获得关键利益相关者的认同和协调

* 定义并记录您的目标

* 设定现实且深思熟虑的时间线

* 为参与者定义明确的责任

## 利益相关者参与并保持一致

贵组织中的关键利益相关者和决策者需要根据您升级到Customer Journey Analytics的情况进行调整。

以下各节介绍让利益相关者达成一致的方式。

### 关注价值

关注Customer Journey Analytics将为您的组织带来的价值，以及它将如何加快实现您的业务目标。

下表介绍了您可能要重点介绍的一些主要功能。

| 功能 | 好处 | 示例 |
|---------|----------|---------|
| **[所有类型数据的容纳](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/home)** | Customer Journey Analytics与Experience Platform保存各种数据架构和类型的能力相结合。 | 零售组织可以将以下类型的数据集成到单个视图中，从而提供对完整客户历程的可见性： <ul><li>Web点击流交易</li><li>移动应用程序交易</li><li>店内交易</li><li>CRM和忠诚度数据</li></ul> |
| **[跨渠道分析](/help/use-cases/cross-channel/cross-channel.md)** | 通过将各种Web、移动和离线资产中的数据统一起来，支持跨各种渠道的客户行为的单个整合视图。 | 从多个渠道收集数据的零售组织可以执行以下类型的分析：<p>购物者点击付费搜索广告，在线浏览牛仔裤，收到推送通知，然后两天后在店内购买。 此统一的观点支持准确的跨渠道归因，显示数字接触点对店内销售的贡献情况。 它还支持更精确的分段，例如通过量身定制的优惠来定位“在线浏览、店内购买”的客户。 此外，它在一个仪表板中提供清晰、全渠道的收入报告，用对客户行为的全面了解代替分散的、孤立的洞察。 |
| **[报告时间处理](/help/getting-started/aa-to-cja.md#get-comfortable-with-report-time-processing)** | 应用可追溯的设置并创建变量持久性的多个版本，而无需更改基础数据的收集方式。 | 由于Customer Journey Analytics允许您在不重新摄取或重新处理数据的情况下动态创建和调整量度、维度和归因模型，因此零售组织无需请求工程部门重建数据集，即可了解最近的社交活动如何影响在线和店内销售。 他们可以立即将归因模型从最近联系更改为首次联系或基于规则的自定义归因。 |
| **[Content Analytics](/help/content-analytics/content-analytics.md)** | 帮助营销人员了解内容如何影响企业定义的关键绩效指标。 除了行为数据之外，Content Analytics 还收集关于内容如何被消费以及内容如何产生影响的数据。 | 通过集成Web、应用程序、电子邮件甚至店内数据，零售组织可以准确地了解他们创建的每段数字内容对客户历程和转化的贡献。 <p>零售组织可以发现，在流行社交媒体平台上推出“夏季牛仔装风格指南”，有助于提高忠诚会员的参与度，而且一周内这些会员在店内购买牛仔布的可能性会提高40%。</p> |

### 指定执行发起人

在您的组织内查找并指定执行发起人。 此执行发起人需要了解Customer Journey Analytics将如何加快实现您的业务目标。

执行发起人至关重要，因为他们：

* 该组织中的Customer Journey Analytics冠军

* 移除障碍

* 批准资源

### 确保整个组织的主要领导提供安全支持

在执行发起人的帮助下，确保获得整个组织内其他关键领导者的支持。 来自贵公司以下领域的领导者必须了解Customer Journey Analytics的好处，并且愿意为成功的实施作出贡献，这一点至关重要：

* Analytics

* 营销

* IT

* 法律和法规遵从性

* 单个业务单位

## 制定升级和通信计划

### 制定升级计划并将其分发给利益相关者

升级计划可能包含以下信息：

* 清晰描述升级原因。 例如，描述用户以及整个组织或业务的好处。 有关权益的详细信息，请参阅[关注值](#focus-on-value)。

* 一般时间表，例如计划何时开始升级、关键里程碑概述以及计划何时完成升级的预估。

* 指示用户何时可以开始参加正式培训以学习如何使用Customer Journey Analytics。 有关详细信息，请参阅[培训整个组织的最终用户](#train-end-users-throughout-your-organization)。

* 此信息介绍了谁将负责升级，以及人们如何或何时可以提出问题。

### 创建通信计划

通信计划可能包括以下注意事项：

* 将通信发送到利益相关者和用户的定义频率

* 将发送的信息类型大纲

* 关于谁将发送通信的计划

* 定义了反馈循环，以允许利益相关者和用户提问或提供反馈

## 评估和审核您的Adobe Analytics实施

对您的Adobe Analytics实施情况进行彻底评估和审核，重点关注以下关键方面：

* 当前用户

* 用户访问

* 项目

* 业务流程

* 自定义组件

请参阅以下资源来帮助收集此信息：

* [分析库存](https://experienceleague.adobe.com/zh-hans/docs/analytics/admin/admin-tools/analytics-inventory)

  提供有关您组织内的项目、区段、计算指标、报表包和用户数的信息。

* [准备将组件和项目从Adobe Analytics迁移到Customer Journey Analytics](https://experienceleague.adobe.com/zh-hans/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)

  提供有关如何准备迁移组件、项目和用户的信息。

## 识别支持者和率先采用者

识别整个组织中的拥护者。 这些冠军企业应该是：

* Adobe Analytics高级用户

* 能够快速熟练掌握Customer Journey Analytics

* 随着Customer Journey Analytics更广泛地推出，可以为他人提供帮助和指导

## 培训整个组织的最终用户

* 提供实践培训，重点介绍Customer Journey Analytics中的数据模型、报表范例和新功能中的差异。

* 提供实时讲座（研讨会或办公时间）和按需资源（视频教程、动态Wiki页面和内部文档）。

* 将用户引导至Experience League的相关培训、教程和文档。

  以下资源可帮助您入门：

   * [Customer Journey Analytics教程](https://experienceleague.adobe.com/zh-hans/docs/customer-journey-analytics-learn/tutorials/overview)

   * [Customer Journey Analytics 是什么？](https://experienceleague.adobe.com/zh-hans/docs/customer-journey-analytics-learn/tutorials/cja-basics/what-is-customer-journey-analytics)

   * [Customer Journey Analytics简介](https://experienceleague.adobe.com/zh-hans/docs/customer-journey-analytics-learn/tutorials/cja-basics/understanding-customer-journey-analytics)

   * [Customer Journey Analytics 功能支持](/help/getting-started/aa-vs-cja/cja-aa.md)

## 按照建议的升级步骤操作

准备好开始升级过程后，请按照[建议的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或《Customer Journey Analytics升级指南》中动态生成的升级步骤操作。 要从 Customer Journey Analytics 访问升级指南，请选择&#x200B;**[!UICONTROL 工作区]**&#x200B;选项卡，然后在左侧面板中选择&#x200B;**[!UICONTROL 升级到 Customer Journey Analytics]**。按照屏幕上的说明操作。

