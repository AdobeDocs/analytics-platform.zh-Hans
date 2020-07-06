---
description: 同类群组分析的用例示例。
keywords: Analysis Workspace
title: 同类群组分析用例
topic: Reports and analytics
uuid: 5ec46f84-5702-4bc1-a796-874a3abe87c9
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 73%

---


# [!UICONTROL 群组分析] 使用案例

>[!NOTE]
>
>您正在查看Customer Journey Analytics中的Analysis Workspace文档。 其功能集与传统Adobe [Analytics的Analysis Workspace略有不同](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html)。 [了解更多...](/help/getting-started/cja-aa.md)

Use case examples for [!UICONTROL Cohort Analysis].

## 应用程序参与度用例

假设您想分析在安装了您的应用程序的用户中，该应用程序在一段时间内的具体使用情况。他们是否安装后就再也没使用过？使用了一段时间后就放弃不用了？还是说，仍然在继续使用？

You can create a six-month [!UICONTROL Cohort Analysis]:

**粒度**：按月，从 2015 年 1 月至 2015 年 6 月。

**包含量度**：应用程序安装。

**返回量度**：会话次数或启动次数

在随后的数月中，访客并不会被算作“已参与”(*`engaged`*)，除非他们会进行会话，或者至少启动该应用程序。[!UICONTROL 同期群分析] ，随后将向您显示使用模式，该模 *`App Install`* 式始终出现在第0个月。 您或许会注意到，无论用户是在何时安装该应用程序，第三个月的使用量都会下降（对于那些在 2015 年 1 月安装了该应用程序的用户而言，第三个月指的是 2015 年 3 月。如果用户在 2015 年 2 月安装了该应用程序，那么第三个月指的是 2015 年 4 月，依此类推）。该项分析允许您在用户安装了应用程序的第二个月内，向他们发送电子邮件或推送消息，提醒他们使用这个应用程序。

## 订阅用例

您就职于 Adobe.com，并且向用户提供了一份免费的 Creative Cloud 订阅。其目的在于让用户从免费版本升级至 30 天的试用版本，或者，最终升级到付费版本。

**粒度**：按月

**包含量度**：下载链接

**返回量度**：购买付费的 Creative Cloud

Using this [!UICONTROL Cohort Analysis], you could see, for example, that anywhere between 8% and 10% of free Creative Cloud users upgrade in the first month after installation, regardless of when they installed. 12-15% 的用户会在使用后的第二个月内进行升级。随后，升级的用户数量会大幅缩减：第三个月为 4%-5%，第四个月为 3%-4%，到了第五个月就缩减为 1%-2%。

在意识到不能失去第三个月的潜在客户后，您可以全力以赴，在第三个月的中期为部分用户安排一次电子邮件促销活动，向尚未升级的用户提供 50 美元的优惠券。

请您在几个月后再关注同类群组分析报表。对于在启动促销活动后形成的同类群组而言，第三个月内转化为付费的 Creative Cloud 订阅的用户概率由 4%-5% 上升为 13%-14%，使得每个按月统计的同类群组从此都能产生数十万美元的收入。

## 复杂同类群组区段用例

一家大型连锁酒店针对多个客户群组进行了促销，并跟踪促销活动的效果。为了确定要定位的最佳用户同类群组，他们想要创建非常具体的同类群组。Using the augmented [!UICONTROL Inclusion] and [!UICONTROL Return] Criteria within [!UICONTROL Cohort] Tables, they are able to define just the right cohort groupings with multiple metrics and segments to identify underperforming customers groups in order to target them with promotions and deals to increase bookings.

## 采用的应用程序版本用例

一家大型保险公司通过使用其移动设备应用程序大大提高了客户的参与度。但是，由于他们的应用程序中添加了新功能，因此，需要将他们的客户升级到最新的应用程序版本。They can analyze and compare all of their app versions side-by-side using [!UICONTROL Custom Dimension] Cohort to see which customers on which app version to target. 此外，他们还可以跟踪维系率和流失率，以查看在一段时间内，特定应用程序版本是否会促使客户停止使用该应用程序。通过移动设备消息传递功能，他们可以重新联系这些用户，让用户升级到最新版本，进而利用他们的最新功能。

## 促销活动吸引力用例

一家跨国媒体公司为提高客户的参与度，使用有针对性的促销活动来吸引用户访问其各种平台。该公司根据客户的参与度和维系率分配每个平台的广告支出；因此，成功的促销活动对于他们的业务取得成功至关重要。They use our new [!UICONTROL Custom Dimension] Cohort feature in [!UICONTROL Cohort] Tables to compare various campaigns side-by-side to identify which campaigns are most effective at acquiring and retaining users to increase engagement. 然后，他们可以确定哪些方面使活动成功，并将其应用于其他活动，以提高跨不同平台的参与度。

## 产品上市用例

一家大型服装零售商拥有许多特定的客户区段，这些区段为他们的业务带来了很大一部分收入。每个区段都有专门为该区段设计和制造的特定产品。每次有产品上市时，他们都想知道新产品如何在一段时间内增加各个同类群组的销售额。Using the new [!UICONTROL Latency Table] setting in [!UICONTROL Cohort Analysis], they are able to analyze a given customer segment&#39;s pre-launch and post-launch behavior and revenue. 利用这些信息，他们可以确定哪些产品正在增加收入，哪些产品对客户没有吸引力。

## 个人吸引力 - 最忠诚的用户使用案例

一家大型航空公司的成功和大部分收入均来自于其忠诚的旧客户。在许多情况下，他们的忠实旅客为其带来了大部分收入；要想取得长期成功，留住这些客户至关重要。识别最忠诚的固定客户通常十分困难。However, using the new [!UICONTROL Rolling Calculation] setting in [!UICONTROL Cohort Analysis], they were able to analyze loyal customer segments and find out which travelers were repeat purchasers month-over-month. 然后，他们能够为这些旅客提供奖励和优厚待遇，以答谢旅客的忠诚。此外，通过将同类群组类型从维系更改为流失，他们还能够确定哪些客户不是每月的重复购买者，然后通过促销活动来定位这些区段，以便让客户重新参与并确保这些客户以后仍是忠诚客户。
