---
title: 拼合常见问题解答
description: 拼接常见问题解答
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: ae0e7a906700522d7babc1d573a0b4cdbf1be6fc
workflow-type: tm+mt
source-wordcount: '1910'
ht-degree: 28%

---

# 常见问题解答

以下是有关拼接的一些常见问题：

## 跨渠道移动

+++ 如何使用拼合功能查看用户如何从一个渠道转移到另一个渠道？

您可以使用包含“数据集 ID”维度的流量可视化图表。

1. 登录到[Customer Journey Analytics](https://analytics.adobe.com)并创建一个空白的Workspace项目。
2. 选择左侧的&#x200B;**[!UICONTROL **&#x200B;可视化图表&#x200B;**]**&#x200B;选项卡，然后将&#x200B;**[!UICONTROL **&#x200B;流量&#x200B;**]**&#x200B;可视化图表拖到右侧的画布上。
3. 选择左侧的&#x200B;**[!UICONTROL **&#x200B;组件&#x200B;**]**&#x200B;选项卡，并将维度&#x200B;**[!UICONTROL **&#x200B;数据集ID **]**&#x200B;拖到标记为&#x200B;**[!UICONTROL ** Dimension或项&#x200B;**]**&#x200B;的中心位置。
4. 此流量报告是交互式的。要将流量展开到后续或之前的页面，请选择任意值。 使用右键单击菜单可展开或折叠列。此外，还可以在同一流量报告中使用不同的维度。

如果要重命名“数据集 ID”维度项，可使用查找数据集。

+++

### 重播

+++ 拼合重播访客可追溯到多久之前？

重新生成键值的回顾时间范围取决于您所需的数据重播频率。 例如，如果将拼合设置为每周重播一次数据，则重新生成键值的回顾时间范围为7天。 如果将拼合设置为每天重播一次数据，则重新生成键值的回顾时间范围为一天。

+++

## 共享设备

+++ 如何处理共享设备？

在某些情况下，可能会有多人从同一设备登录。例如，在家中使用共享设备，在图书馆中使用共享 PC，或在零售商店中使用自助终端。

临时 ID 会覆盖永久 ID，因此共享设备会被视为单独的人员（即使来自于同一设备也是如此）。

+++

## 许多永久ID

+++ 拼合如何处理单个用户拥有多个永久ID的情况？

在某些情况下，单个用户可以与许多永久性 ID 相关联。例如，经常清除浏览器的Cookie或使用浏览器私人/隐身模式的用户。

对于基于字段的拼合，永久ID的数量与临时ID的数量无关。 单个用户可以属于任意数量的设备，而不会影响Customer Journey Analytics跨设备拼合的功能。

对于基于图的拼合，一个人在身份图中可以具有多个永久ID。 基于图形的拼接使用基于指定命名空间的永久ID。 如果同一命名空间存在更多永久ID，则使用词典编排的第一个永久ID。

+++

## 拼接过程

+++ 在与 Adobe 帐户团队联系并提供所需信息后，已重新生成键值的数据集需要多长时间才可用？

在Adobe启用拼接后大约一周，实时拼接功能会可用。 回填可用性取决于现有数据的数量。小型数据集（每日的事件数量少于 100 万）通常需要几天时间，而大型数据集（每日的事件数量为 10 亿）可能需要一周或更长时间。

+++

## 跨设备分析与跨渠道分析

+++ 跨设备分析（传统Analytics中的一项功能）和跨渠道分析之间有何区别？

[跨设备分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html)是传统Adobe Analytics特有的功能，它使您能够了解人们如何跨设备操作。 该功能提供了两种将设备数据链接在一起的工作流：基于字段的拼接和设备图。

跨渠道分析是特定于Customer Journey Analytics的用例，通过它，您可以同时了解人们如何跨设备和跨渠道操作。 它拼合数据集的人员ID，允许将该数据集与其他数据集无缝组合。 该功能在设计上类似于基于跨设备分析的字段拼接，但由于传统Analytics和Customer Journey Analytics之间的数据架构不同，因此实施方法也不同。 有关详细信息，请参阅[拼接](overview.md)和[跨渠道分析](../use-cases/cross-channel/cross-channel.md)用例。

+++

## 隐私

+++ 拼接如何处理隐私请求？

Adobe将根据当地和国际法律处理隐私请求。 Adobe 提供了 [Adobe Experience Platform 隐私服务](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hans)来提交数据访问和删除请求。这些请求同时适用于原始数据集和已重新生成键值的数据集。

>[!IMPORTANT]
>
>作为隐私请求的一部分，取消拼合过程在2025年初发生变化。 当前的取消拼接过程使用最新版本的已知身份重置事件。 将事件重新分配给另一个身份可能会产生不良的法律后果。 为了消除这些疑虑，从2025年开始，新的解拼接流程将使用永久ID更新隐私请求中的事件。
> 

举例来说，可以想象以下用于标识的数据，即拼接之前和拼接之后的事件。

| 标识映射 | Id | timestamp | 永久ID | 永久命名空间 | 临时id | 瞬态命名空间 |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ecid | Bob | CustId |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| 事件数据集 | Id | timestamp | 永久ID | 永久命名空间 | 临时id | 瞬态命名空间 |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| | 2 | ts1 | 123 | ecid | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| 拼接数据集 | Id | timestamp | 永久ID | 永久命名空间 | 临时id | 瞬态命名空间 | 拼接 ID | 拼接的命名空间 |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | Bob | CustId |
| | 2 | ts1 | 123 | ecid | Bob | CustId | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**隐私请求的当前进程**

当收到具有CustID Bob的客户的隐私请求时，将删除具有删除线条目的行。 使用标识映射重新获取其他事件。 例如，拼接数据集中的第一个拼接ID已更新为&#x200B;**Alex**。

| 标识映射 | Id | timestamp | 永久ID | 永久命名空间 | 临时id | 瞬态命名空间 |
|:---:|---|---|---|---|---|---|
| ![删除大纲](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| 事件数据集 | Id | timestamp | 永久ID | 永久命名空间 | 临时id | 瞬态命名空间 |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![删除大纲](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| 拼接数据集 | Id | timestamp | 永久ID | 永久命名空间 | 临时id | 瞬态命名空间 | 拼接 ID | 拼接的命名空间 |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **Alex** | CustId |
| ![删除大纲](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**隐私请求的新流程**

当收到具有CustID Bob的客户的隐私请求时，将删除具有删除线条目的行。 使用永久id重新获取其他事件。 例如，拼接数据集中的第一个拼接ID已更新为&#x200B;**123**。

| 标识映射 | Id | timestamp | 永久ID | 永久命名空间 | 临时id | 瞬态命名空间 |
|:---:|---|---|---|---|---|---|
| ![删除大纲](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| 事件数据集 | Id | timestamp | 永久ID | 永久命名空间 | 临时id | 瞬态命名空间 |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![删除大纲](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| 拼接数据集 | Id | timestamp | 永久ID | 永久命名空间 | 临时id | 瞬态命名空间 | 拼接 ID | 拼接的命名空间 |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **123** | ecid |
| ![删除大纲](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |

+++

## 持久ID值为空

+++ 如果一个或多个事件中的永久 ID 字段为空，会发生什么情况？

如果在要拼合的数据集内，某个事件的持久ID字段为空，则会通过以下两种方式之一确定该事件的拼合ID：

* 如果“临时ID”字段不为空，则Customer Journey Analytics会使用临时ID中的值作为拼合ID。
* 如果“临时ID”字段为空，则Customer Journey Analytics还会将“拼合ID”留空。 在这种情况下，事件中的永久ID、临时ID和拼合ID全部为空。 使用正在拼接的数据集从任何Customer Journey Analytics连接中删除这些类型的事件，其中，拼接ID被选为人员ID。

+++


## 未定义的临时ID值

+++ 如果一个或多个事件中的临时ID字段具有占位符值（如`Undefined`），会发生什么情况？

务必要谨慎，当将拼合应用于将占位符值用于临时ID的数据时，会出现“人员折叠”。 在下面的示例表中，源自于CRM系统数据集的未定义人员ID被填充为“Undefined”值，从而导致人员的表示不正确。

| 事件 | 时间戳 | 永久性ID(Cookie ID) | 临时ID（登录ID） | 拼合ID（重播后） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 123 | - | **科里** |
| 2 | 2023-05-12 12:02 | 123 | 科里 | **科里** |
| 3 | 2023-05-12 12:03 | 456 | 未定义 | **未定义** |
| 4 | 2023-05-12 12:04 | 456 | - | **未定义** |
| 5 | 2023-05-12 12:05 | 789 | 未定义 | **未定义** |
| 6 | 2023-05-12 12:06 | 012 | 未定义 | **未定义** |
| 7 | 2023-05-12 12:07 | 012 | - | **未定义** |
| 8 | 2023-05-12 12:03 | 789 | 未定义 | **未定义** |
| 9 | 2023-05-12 12:09 | 456 | - | **未定义** |
| 10 | 2023-05-12 12:02 | 123 | - | **科里** |
| | | **4个设备** | **2人**：<br/>已丢弃事件1、4、7、9、10 | **2个人**：<br/>科里，未验证（折叠为一个人） |

+++

## 量度比较

+++ 与Customer Journey Analytics未拼接数据集中的类似指标相比，Customer Journey Analytics拼接数据集中的指标如何？与Adobe Analytics相比如何？

Customer Journey Analytics中的某些指标与传统Analytics中的指标相似，但其他指标则有所不同，具体取决于您要比较的内容。 下表比较了几个常见的量度：

| **Customer Journey Analytics 拼接数据** | **Customer Journey Analytics 未拼接数据** | **Adobe Analytics** | **带 CDA 的 Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **人员** =将拼合ID选为人员ID的不同人员ID数。 **人员数** 可能高于或低于传统 Adobe Analytics 中的&#x200B;**独特访客数**，具体取决于拼接过程的结果。 | **人员** =不同人员ID的数量（根据选定为人员ID的列）。 如果Customer Journey Analytics中将`endUserIDs._experience.aaid.id`用作人员ID，则Analytics源连接器数据集中的&#x200B;**人员**&#x200B;类似于传统Adobe Analytics中的&#x200B;**独特访客**。 | **独特访客** = 不同访客 ID 的数量。**独特访客**&#x200B;可能与不同 **ECID** 的数量不一致。 | 请参阅[人员数](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=zh-Hans)。 |
| **会话**：根据 Customer Journey Analytics 数据视图中的会话设置定义。拼接过程可能会将来自多个设备的各个会话组合成单个会话。 | **会话**：根据 Customer Journey Analytics 数据视图中特定的会话设置定义。 | **访问数**：请参阅[访问数](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=zh-Hans)。 | **访问数**：根据 [CDA 虚拟报告包](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=zh-Hans)中特定的会话设置定义。 |
| **活动**= Customer Journey Analytics 中拼接数据的行数。该量度通常接近于传统 Adobe Analytics 中的&#x200B;**“发生次数”。**&#x200B;但是，请注意上面关于具有空白永久ID的行的常见问题解答。 | **活动**= Customer Journey Analytics 中未拼接数据的行数。该量度通常接近于传统 Adobe Analytics 中的&#x200B;**“发生次数”。**&#x200B;但是，请注意，如果任何事件在Experience Platform数据湖的未拼接数据中有空白的人员ID，则Customer Journey Analytics中不包括这些事件。 | **发生次数**：请参阅[发生次数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=zh-Hans)。 | **发生次数**：请参阅[发生次数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=zh-Hans)。 |

Customer Journey Analytics和Adobe Analytics中的其他指标可能类似。 例如，Adobe Analytics [自定义事件](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=zh-Hans) 1-100的总数在传统Adobe Analytics和Customer Journey Analytics之间是可比较的（无论是已拼合还是未拼合）。 Customer Journey Analytics与Adobe Analytics之间的[功能差异（如消除重复事件）可能会导致这两种产品之间存在差异。](/help/getting-started/aa-vs-cja/cja-aa.md)

+++

## 标识映射

+++ Customer Journey Analytics可以使用身份映射字段吗？

否，Customer Journey Analytics当前无法使用身份映射字段进行拼接。

+++

## 切换到基于图形的拼合

+++ 是否需要摄取数据才能从基于字段的拼合切换到基于图形的拼合？

数据不必重新摄取到Experience Platform中，但需要在Customer Journey Analytics中重新配置。 请按照以下步骤操作：

1. 设置新的基于图形的拼合数据集。
1. 在Customer Journey Analytics中将新数据集配置为新连接的一部分。
1. 切换现有数据视图以使用新连接（以及基于图形的新拼接数据集）
1. 删除使用基于字段的拼合数据集的旧连接。

+++

## 报告中断

+++ 现有报告是否会受到干扰？

如果您按照上述步骤操作，则不然。 否则，请联系Adobe Consulting以获取其他支持。

+++


