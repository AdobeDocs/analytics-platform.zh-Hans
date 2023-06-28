---
title: 拼合常见问题解答
description: 有关拼合的常见问题解答
solution: Customer Journey Analytics
feature: Stitching
source-git-commit: ec316d36c1e2ec6eb6e75e980ad3fed4ededfb94
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 36%

---

# 常见问题解答

请查看下面有关拼合的一些常见问题：

## 如何使用拼合功能查看用户如何从一个渠道转移到另一个渠道？

您可以使用包含“数据集 ID”维度的流量可视化图表。

1. 登录 [Customer Journey Analytics](https://analytics.adobe.com) 并创建一个空白的工作区项目。
2. 选择 **[!UICONTROL **&#x200B;可视化图表&#x200B;**]** 制表符，并拖动 **[!UICONTROL **&#x200B;流量&#x200B;**]** 可视化图表显示在右侧的画布上。
3. 选择 **[!UICONTROL **&#x200B;组件&#x200B;**]** 选项卡，并拖动维度 **[!UICONTROL **&#x200B;数据集Id **]** 到中心位置，标记为 **[!UICONTROL ** Dimension或项目&#x200B;**]**.
4. 此流量报表是交互式的。要将流量展开到后续或之前的页面，请选择任意值。 使用右键单击菜单可展开或折叠列。此外，还可以在同一流量报表中使用不同的维度。

如果要重命名“数据集 ID”维度项，可使用查找数据集。

## 拼合重播访客可追溯到多久之前？

重新生成键值的回顾时间范围取决于您所需的数据[重播](explained.md)频率。例如，如果将拼合设置为每周重播一次数据，则重新生成键值的回顾时间范围为7天。 如果将拼合设置为每天重播一次数据，则重新生成键值的回顾时间范围为一天。

## 如何处理共享设备？

在某些情况下，可能会有多人从同一设备登录。例如，在家中使用共享设备，在图书馆中使用共享 PC，或在零售商店中使用自助终端。

临时 ID 会覆盖永久 ID，因此共享设备会被视为单独的人员（即使来自于同一设备也是如此）。

## 拼合如何处理单个用户具有多个永久ID的情况？

在某些情况下，单个用户可以与许多永久性 ID 相关联。例如，个人经常清除浏览器的Cookie或使用浏览器的私人/无痕模式。

永久 ID 的数量与临时 ID 的使用无关。单个用户可以属于任意数量的设备，而不会影响Customer Journey Analytics跨设备拼合的功能。

## 在联系我的Adobe客户团队并提供所需信息后，重新生成键值的数据集需要多长时间才可用？

在Adobe启用拼接后大约一周，实时拼接功能可用。 回填可用性取决于现有数据的数量。小型数据集（每日的事件数量少于 100 万）通常需要几天时间，而大型数据集（每日的事件数量为 10 亿）可能需要一周或更长时间。

## 跨设备分析（传统Analytics中的一项功能）和跨渠道分析之间有何区别？

[跨设备分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html) 是传统Adobe Analytics特有的功能，它使您能够了解人们如何跨设备操作。 该功能提供了两种将设备数据链接在一起的工作流：基于字段的拼接和设备图。

跨渠道分析是特定于Customer Journey Analytics的用例，通过该分析，您可以同时了解人们如何跨设备和跨渠道操作。 它拼合数据集的人员ID，以便将该数据集与其他数据集无缝合并。 该功能在设计上类似于基于跨设备分析的字段拼合，但由于传统Analytics和Customer Journey Analytics之间的数据架构不同，因此实施方法有所不同。 参见 [拼接](overview.md) 和 [跨渠道分析](../use-cases/cross-channel/cross-channel.md) 用例以了解更多信息。

## 拼接如何处理GDPR和CCPA请求？

Adobe 将根据当地和国际法规处理 GDPR 和 CCPA 请求。Adobe 提供了 [Adobe Experience Platform 隐私服务](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hans)来提交数据访问和删除请求。这些请求同时适用于原始数据集和已重新生成键值的数据集。

## 如果一个或多个事件中的永久 ID 字段为空，会发生什么情况？

如果拼合的数据集中某个事件的持久ID字段为空，则该事件的拼合ID将通过以下两种方式之一确定：

* 如果“临时ID”字段不为空，则Customer Journey Analytics使用临时ID中的值作为拼合ID。
* 如果“临时ID”字段为空，则Customer Journey Analytics还会将“拼合ID”留空。 在这种情况下，事件中的永久ID、临时ID和拼合ID全部为空。 使用正在拼接的数据集从任何Customer Journey Analytics连接中删除这些类型的事件，其中，拼接的ID被选为人员ID。

## 与Customer Journey Analytics未拼接数据集中的类似指标和传统Adobe Analytics相比，Customer Journey Analytics拼接数据集中的指标如何？

Customer Journey Analytics中的某些指标与传统Analytics中的指标相似，但其他指标则有所不同，具体取决于您要比较的内容。 下表比较了几个常见的指标：

| **Customer Journey Analytics拼合数据** | **Customer Journey Analytics未拼合的数据** | **传统 Adobe Analytics** | **带 CDA 的 Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **人员** =已拼合ID被选为人员ID的不同人员ID的数量。 **人员数** 可能高于或低于传统 Adobe Analytics 中的&#x200B;**独特访客数**，具体取决于拼接过程的结果。 | **人员** =不同人员ID的数量（根据选定为人员ID的列）。 **人员** 在Adobe中，源连接器数据集类似于 **独特访客** 传统Adobe Analytics中的 `endUserIDs._experience.aaid.id` 用作Customer Journey Analytics中的人员ID。 | **独特访客** = 不同访客 ID 的数量。**独特访客**&#x200B;可能与不同 **ECID** 的数量不一致。 | 请参阅[人员数](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=zh-Hans)。 |
| **会话**：根据Customer Journey Analytics数据视图中的会话设置定义。 拼接过程可能会将来自多个设备的各个会话组合成单个会话。 | **会话**：根据Customer Journey Analytics数据视图中指定的会话设置定义。 | **访问数**：请参阅[访问数](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=zh-Hans)。 | **访问数**：根据 [CDA 虚拟报告包](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=zh-Hans)中特定的会话设置定义。 |
| **事件** =Customer Journey Analytics中已拼合数据的行数。 该量度通常接近于传统 Adobe Analytics 中的&#x200B;**发生次数**。但是，请注意上面关于具有空白永久ID的行的常见问题解答。 | **事件** =Customer Journey Analytics中未拼合数据的行数。 该量度通常接近于传统 Adobe Analytics 中的&#x200B;**发生次数**。但请注意，如果任何事件在Experience Platform数据湖的未拼接数据中具有空白的人员ID，则这些事件不包括在Customer Journey Analytics中。 | **发生次数**：请参阅[发生次数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=zh-Hans)。 | **发生次数**：请参阅[发生次数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=zh-Hans)。 |

Customer Journey Analytics和传统Adobe Analytics中的其他指标可能类似。 例如，Adobe Analytics的总数 [自定义事件](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=zh-Hans) 1-100在传统Adobe Analytics和Customer Journey Analytics（无论是已拼合还是未拼合）之间具有可比性。 [功能差异](/help/getting-started/aa-vs-cja/cja-aa.md))，例如，在Customer Journey Analytics与传统Adobe Analytics之间删除重复事件，可能会导致这两种产品之间存在差异。

## Customer Journey Analytics可以使用身份映射字段吗？

否，Customer Journey Analytics当前无法使用身份映射字段进行拼接。
