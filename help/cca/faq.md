---
title: 跨渠道分析常见问题解答
description: 跨渠道分析常见问题解答
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 66%

---

# 常见问题解答

## 如何使用跨渠道分析 (CCA) 了解用户如何从一个渠道转移到另一个渠道？

您可以使用包含“数据集 ID”维度的流量可视化图表。

1. 登录 [analytics.adobe.com](https://analytics.adobe.com) 并创建一个空白的工作区项目。
2. 单击左侧的“可视化图表”选项卡，然后将流量可视化图表拖到右侧的画布上。
3. 在左侧单击“组件”选项卡，并将维度“数据集 ID”拖动到标记为“维度或项目”的中心位置。
4. 此流量报表是交互式的。单击任意值可将流量展开到后续或之前的页面。使用右键单击菜单可展开或折叠列。此外，还可以在同一流量报表中使用不同的维度。

如果要重命名“数据集 ID”维度项，可使用查找数据集。

## CCA为人员重新生成键值的回顾时间范围是多久？

重新生成键值的回顾时间范围取决于您所需的数据[重播](replay.md)频率。例如，如果将 CCA 设置为每周回放一次数据，则重新生成密钥的回看窗口为七天。例如，如果将 CCA 设置为每天回放一次数据，则重新生成密钥的回看窗口为一天。

## 如何处理共享设备？

在某些情况下，可能会有多人从同一设备登录。例如，在家中使用共享设备，在图书馆中使用共享 PC，或在零售商店中使用自助终端。

临时 ID 会覆盖永久 ID，因此共享设备会被视为单独的人员（即使来自于同一设备也是如此）。

## CCA 如何处理一个用户有多个永久性 ID 的情况？

在某些情况下，单个用户可以与许多永久性 ID 相关联。例如，经常清除浏览器 Cookie 的用户或使用浏览器私人/隐身模式的用户便会出现这种情况。

永久 ID 的数量与临时 ID 的使用无关。单个用户可以属于任意数量的设备，而不会影响 CCA 跨设备拼接的功能。

## 在联系我的Adobe客户团队并提供所需信息后，重新生成键值的数据集需要多长时间才可用？

在 Adobe 启用跨渠道分析后大约一周，实时拼接功能会变得可用。回填可用性取决于现有数据的数量。小型数据集（每天不到100万个事件）通常需要几天时间，而大型数据集（每天10亿个事件）可能需要一周或更长时间。

## 跨设备分析(Adobe Analytics中的一项功能)与跨渠道分析之间有何区别？

[跨设备分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html)是传统 Adobe Analytics 特有的功能，它使您能够了解人们如何跨设备操作。该功能提供了两种将设备数据链接在一起的工作流：基于字段的拼接和设备图。

[跨渠道分析](/help/cca/overview.md) 是Customer Journey Analytics特有的功能，它使您能够同时了解人们如何跨设备和跨渠道操作。 该功能会对数据集的个人 ID 重新生成密钥，使该数据集可与其他数据集无缝结合。此功能在设计上与CDA基于字段的拼合类似，但实施方式因Adobe Analytics和Customer Journey Analytics之间的数据架构不同而异。

## 跨渠道分析如何处理 GDPR 和 CCPA 请求？

Adobe 将根据当地和国际法规处理 GDPR 和 CCPA 请求。Adobe 提供了 [Adobe Experience Platform 隐私服务](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hans)来提交数据访问和删除请求。这些请求同时适用于原始数据集和已重新生成键值的数据集。

## 如果一个或多个事件中的永久 ID 字段为空，会发生什么情况？

如果在使用基于字段的拼接功能进行拼接的数据集内，某个事件的 `Persistent ID` 字段为空，CCA 会通过以下两种方式之一填充该事件的 `Stitched ID`：

* 如果 `Transient ID` 字段不为空，CCA 将使用 `Transient ID` 中的值作为 `Stitched ID`。
* 如果 `Transient ID` 字段为空，CCA 还会将 `Stitched ID` 保留为空。在这种情况下，`Persistent ID`、`Transient ID` 和 `Stitched ID` 在事件中均为空白。使用正在拼合的数据集的任何Customer Journey Analytics连接中，会删除这些类型的事件，其中 `Stitched ID` 被选为 `Person ID`.

## 与Customer Journey Analytics未拼接数据集中的类似指标和传统Adobe Analytics相比，Customer Journey Analytics拼接数据集中的指标如何？

Customer Journey Analytics中的某些指标与Adobe Analytics中的指标相似，但其他指标则大不相同，具体取决于您要比较的内容。 下表比较了几个常见的指标：

| **Customer Journey Analytics拼合数据** | **Customer Journey Analytics未拼合的数据** | **传统 Adobe Analytics** | **带 CDA 的 Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **人员数** = 不同 `Person ID` 的数量，其中 `Stitched ID` 被选定为 `Person ID`。**人员数** 可能高于或低于传统 Adobe Analytics 中的&#x200B;**独特访客数**，具体取决于拼接过程的结果。 | **人员数** = 不同 `Person ID` 的数量（根据选定为 `Person ID` 的列）。**人员** 在Adobe中，源连接器数据集类似于 **独特访客** 传统Adobe Analytics中的 `endUserIDs._experience.aaid.id` 被选为 `Person ID` 在Customer Journey Analytics中。 | **独特访客** =不同人员ID的数量。 **独特访客**&#x200B;可能与不同 **ECID** 的数量不一致。 | 请参阅[人员数](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=zh-Hans)。 |
| **会话**：根据Customer Journey Analytics数据视图中的会话设置定义。 拼接过程可能会将来自多个设备的各个会话组合成单个会话。 | **会话**：根据Customer Journey Analytics数据视图中指定的会话设置定义。 | **访问数**：请参阅[访问数](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=zh-Hans)。 | **访问数**：根据 [CDA 虚拟报告包](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=zh-Hans)中特定的会话设置定义。 |
| **事件** =Customer Journey Analytics中已拼合数据的行数。 该量度通常接近于传统 Adobe Analytics 中的&#x200B;**发生次数**。但是，请注意上面关于带有空白 `Persistent ID` 的行的常见问题解答。 | **事件** =Customer Journey Analytics中未拼合数据的行数。 该量度通常接近于传统 Adobe Analytics 中的&#x200B;**发生次数**。但请注意，如果任何事件包含空白 `Person ID` 在Experience Platform数据湖中的未拼合数据中，这些事件不包括在Customer Journey Analytics中。 | **发生次数**：请参阅[发生次数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=zh-Hans)。 | **发生次数**：请参阅[发生次数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=zh-Hans)。 |

Customer Journey Analytics和传统Adobe Analytics中的其他指标可能类似。 例如，Adobe Analytics的总数 [自定义事件](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=zh-Hans) 1-100通常在传统Adobe Analytics和Customer Journey Analytics（无论是已拼合还是未拼合）之间具有可比性。 [功能差异](/help/getting-started/aa-vs-cja/cja-aa.md))，例如，在Customer Journey Analytics与传统Adobe Analytics之间删除重复事件，可能会导致这两种产品之间存在差异。

## CCA 能否使用标识映射字段？

不能，CCA 目前不能使用标识映射字段。
