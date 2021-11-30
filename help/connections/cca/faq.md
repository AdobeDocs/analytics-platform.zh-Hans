---
title: 跨渠道分析常见问题解答
description: 跨渠道分析常见问题解答
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 100%

---

# 常见问题解答

## 如何使用跨渠道分析 (CCA) 了解用户如何从一个渠道转移到另一个渠道？

您可以使用包含“数据集 ID”维度的流量可视化图表。

1. 登录 [analytics.adobe.com](https://analytics.adobe.com) 并创建一个空白的工作区项目。
2. 单击左侧的“可视化图表”选项卡，然后将流量可视化图表拖到右侧的画布上。
3. 单击左侧的“组件”选项卡，然后将“数据集 ID”维度拖到标记为“维度或项目”的中心位置。
4. 此流量报表是交互式的。单击任意值可将流量展开到后续或之前的页面。使用右键单击菜单可展开或折叠列。此外，还可以在同一流量报表中使用不同的维度。

如果要重命名“数据集 ID”维度项，可使用查找数据集。

## CCA 为访客重新生成键值的回顾时间范围是多久？

重新生成键值的回顾时间范围取决于您所需的数据[重播](replay.md)频率。例如，如果将 CCA 设置为每周重播一次数据，则重新生成键值的回顾时间范围为 7 天。如果将 CCA 设置为每天重播一次数据，则重新生成键值的回顾时间范围为 1 天。

## 如何处理共享设备？

在某些情况下，可能有多个用户从同一设备登录。例如，在家中使用共享设备，在图书馆中使用共享 PC，或在零售商店中使用自助终端。

临时 ID 会覆盖永久 ID，因此共享设备会被视为单独的人员（即使来自于同一设备也是如此）。

## CCA 如何处理一人拥有大量永久 ID 的情况？

在某些情况下，单个用户可能会与大量永久 ID 相关联。例如，经常清除浏览器 Cookie 的用户或使用浏览器私人/隐身模式的用户便会出现这种情况。

永久 ID 的数量与临时 ID 的使用无关。单个用户可以属于任意数量的设备，而不会影响 CCA 跨设备拼合的功能。

## 在与客户经理联系并提供所需信息后，已重新生成键值的数据集需要多长时间才可用？

在 Adobe 启用跨渠道分析后，大约需要 1 周才能进行实时拼合。回填可用性取决于现有数据的数量。小型数据集（每日的事件数量少于 100 万）通常需要几天时间，而大型数据集（每日的事件数量为 10 亿）可能需要一周或更长时间。

## 跨渠道分析如何处理 GDPR 和 CCPA 请求？

Adobe 将根据当地和国际法规处理 GDPR 和 CCPA 请求。Adobe 提供了 [Adobe Experience Platform 隐私服务](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hans)来提交数据访问和删除请求。这些请求同时适用于原始数据集和已重新生成键值的数据集。

## 如果一个或多个事件中的永久 ID 字段为空，会发生什么情况？

如果在使用基于字段的拼合功能进行拼合的数据集内，某个事件的 `Persistent ID` 字段为空，CCA 会通过以下两种方式之一填充该事件的 `Stitched ID`：
* 如果 `Transient ID` 字段不为空，CCA 将使用 `Transient ID` 中的值作为 `Stitched ID`。
* 如果 `Transient ID` 字段为空，CCA 还会将 `Stitched ID` 保留为空。在这种情况下，`Persistent ID`、`Transient ID` 和 `Stitched ID` 在此事件上将全部为空。如果在正拼合的数据集内，`Stitched ID` 被选定为 `Person ID`，则在使用该数据集的任何 CJA 连接中，会从 CJA 中删除此类事件。

## 与 CJA 未拼合数据集内的类似指标和传统 Adobe Analytics 相比，CJA 拼合数据集中的指标如何？

CJA 中的某些指标与传统 Analytics 中的指标相似，但其他指标则大不相同，具体取决于您要比较的内容。下表比较了几个常见的指标：

| **CJA 拼合数据** | **CJA 未拼合数据** | **传统 Adobe Analytics** | **带 CDA 的 Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **人员数** = 不同 `Person ID` 的数量，其中 `Stitched ID` 被选定为 `Person ID`。**人员数** 可能高于或低于传统 Adobe Analytics 中的&#x200B;**独特访客数**，具体取决于拼合过程的结果。 | **人员数** = 不同 `Person ID` 的数量（根据选定为 `Person ID` 的列）。如果在 CJA 中，`endUserIDs. _experience. aaid.id` 被选定为 `Person ID`，Adobe Analytics 连接器 (ADC) 数据集中的&#x200B;**人员**&#x200B;将等于传统 Adobe Analytics 中的&#x200B;**独特访客数**。 | **独特访客** = 不同访客 ID 的数量。请注意，**独特访客数**&#x200B;可能与不同 **ECID** 的数量不相同。 | 请参阅[人员数](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=en)。 |
| **会话**：根据 CJA 数据视图中指定的会话流程设置而定义。拼合过程可能将来自多个设备的各个会话组合成单个会话。 | **会话**：根据 CJA 数据视图中指定的会话流程设置而定义。 | **访问数**：请参阅[访问数](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=en)。 | **访问数**：根据 [CDA 虚拟报表包](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=en)中指定的会话流程设置而定义。 |
| **事件数** = CJA 中已拼合数据的行数。通常，在传统 Adobe Analytics 中，该值应该接近&#x200B;**发生次数**。但是，请注意上面关于带有空白 `Persistent ID` 的行的常见问题解答。 | **事件数** = CJA 中未拼合数据的行数。通常，在传统 Adobe Analytics 中，该值应该接近&#x200B;**发生次数**。但请注意，如果任何事件在 AEP 数据湖内的未拼合数据中有空白 `Person ID`，这些事件将被从 CJA 中删除（不包括在内）。 | **发生次数**：请参阅[发生次数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en)。 | **发生次数**：请参阅[发生次数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en)。 |

CJA 和传统 Adobe Analytics 中的其他指标可能类似。例如，Adobe Analytics [自定义事件](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=en)（事件 1-100）的总数在传统 Adobe Analytics 和 CJA（无论是已拼合还是未拼合）中通常应该非常接近。但请注意，由于[功能差异](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-aa.html?lang=en)（例如 CJA 与传统 Adobe Analytics 之间的事件重复数据删除），可能并不总是这样。
