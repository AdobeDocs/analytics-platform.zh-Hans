---
title: 跨渠道分析常见问题解答
description: 跨渠道分析常见问题解答
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
source-git-commit: 2be442915587780ce41f33b13e27b8cf44e239a6
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 46%

---

# 常见问题解答

## 如何使用跨渠道分析 (CCA) 了解用户如何从一个渠道转移到另一个渠道？

您可以使用包含“数据集 ID”维度的流量可视化图表。

1. 登录到[analytics.adobe.com](https://analytics.adobe.com)并创建一个空白的工作区项目。
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

## 如果一个或多个事件中的“永久ID”字段为空，会发生什么情况？

如果`Persistent ID`字段在数据集中通过基于字段的拼合拼合的事件上为空，则CCA将以以下两种方式之一填充该事件的`Stitched ID`:
* 如果`Transient ID`字段不为空，CCA会使用`Transient ID`中的值作为`Stitched ID`。
* 如果`Transient ID`字段为空，则CCA也会将`Stitched ID`留空。 在这种情况下，事件上的`Persistent ID`、`Transient ID`和`Stitched ID`都将为空。 在任何CJA连接中，会使用拼合的数据集从CJA中删除此类事件，其中`Stitched ID`被选作`Person ID`。

## CJA拼合数据集中的量度与CJA未拼合数据集中的类似量度以及与传统Adobe Analytics的量度有何异同？

CJA中的某些量度与传统Analytics中的量度类似，但其他量度则有很大不同，具体取决于您比较的量度。 下表比较了几种常见量度：

| **CJA拼合数据** | **CJA未拼合数据** | **传统Adobe Analytics** | **带有CDA的Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **People**  =选择为的 `Person ID`不同 `Stitched ID` 的计数 `Person ID`。**** 根据拼合过程的结果， **人** 数可能会高于或低于传统Adobe Analytics中的独特访客。 | **人员** =根据选 `Person ID`择为的列计为不同 `Person ID`数。**** 如果与CJA中一样选择Adobe Analytics Connector(ADC)数据集，则 **该** 数据集与传统Adobe Analytics `endUserIDs. _experience. aaid.id` 中的独特 `Person ID` 访客类似。 | **独特访客** =独特访客ID的计数。请注意， **独特访客**&#x200B;可能与不同&#x200B;**ECID**&#x200B;的计数不同。 | 请参阅[People](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=en)。 |
| **会话**:基于CJA数据视图中指定的会话化设置进行定义。拼合过程可以将来自多个设备的单个会话合并到单个会话中。 | **会话**:基于CJA数据视图中指定的会话化设置进行定义。 | **访问**:请参阅 [访问](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=en)。 | **访问**:基于CDA虚拟报表包中指定的会话 [化设置](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=en)定义。 |
| **事件** = CJA中拼合数据的行数。通常，该值应靠近传统Adobe Analytics中的&#x200B;**发生次数**。 但是，请注意，上面有关带有空白`Persistent ID`的行的常见问题解答。 | **事件** = CJA中未拼合数据的行数。通常，该值应靠近传统Adobe Analytics中的&#x200B;**发生次数**。 但是，请注意，如果任何事件在AEP数据湖中的未拼合数据中具有空白`Person ID`，则这些事件将被丢弃（不包含）在CJA中。 | **发生次数**:请参阅 [发生次数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en)。 | **发生次数**:请参阅 [发生次数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en)。 |

其他量度在CJA和传统Adobe Analytics中可能类似。 例如，在传统的Adobe Analytics和CJA中，Adobe Analytics [自定义事件](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=en)（事件1-100）的总计数通常应非常接近（无论是拼合还是未拼合）。 但请注意，由于[功能(如CJA与传统Adobe Analytics之间的事件重复消除)存在差异，因此可能并非始终如此。](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-aa.html?lang=en)
