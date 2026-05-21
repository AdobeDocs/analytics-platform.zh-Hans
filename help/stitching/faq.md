---
title: 拼接常见问题解答
description: 了解有关拼接的常见问题解答。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
TQID: https://experienceleague.adobe.com/0y2eqwQxkHefcODFhxXCuioMnL-YCXm21335Z2upPB0
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 19cf20236196ab9c2518bf299a36d32f65210227
workflow-type: tm+mt
source-wordcount: 2373
ht-degree: 71%

---

# 常见问题解答

以下是有关拼接的一些常见问题：

## 跨渠道移动

**问题**：如何使用拼合功能查看用户如何从一个渠道转移到另一个渠道？

+++回答

您可以使用包含“数据集 ID”维度的流量可视化图表。

1. 登录 [Customer Journey Analytics](https://analytics.adobe.com)，然后创建一个空白的工作区项目。
2. 选择左侧的&#x200B;**[!UICONTROL **&#x200B;可视化图表&#x200B;**]**&#x200B;选项卡，然后将&#x200B;**[!UICONTROL **&#x200B;流量&#x200B;**]**&#x200B;可视化图表拖到右侧的画布上。
3. 选择左侧的&#x200B;**[!UICONTROL **&#x200B;组件&#x200B;**]**&#x200B;选项卡，然后将维度&#x200B;**[!UICONTROL **&#x200B;数据集 ID **]**&#x200B;拖到带有&#x200B;**[!UICONTROL **&#x200B;维度或项目&#x200B;**]**&#x200B;标签的中心位置。
4. 此流量报告是交互式的。 选择任何一个值，将流量扩展到之后或之前的页面。 使用右键单击菜单可展开或折叠列。 此外，还可以在同一流量报告中使用不同的维度。

如果要重命名“数据集 ID”维度项，可使用查找数据集。

+++

## 重播

**问题**：拼合重播配置文件可以追溯到多久之前？

+++回答

重新生成键值的回顾窗口取决于您所需的数据重播频率。 例如，如果将拼接设置为每周重播一次数据，重新生成键值的回顾窗口就是七天。 如果将拼接设置为每天重播一次数据，重新生成键值的回顾窗口就是一天。

+++

**问题**：重放进程何时确切运行？

+++回答

* **每周**&#x200B;重播在每个&#x200B;**星期六**&#x200B;夜间（客户时区）开始，并且到星期一上午会在Customer Journey Analytics报表中更新数据。
* **每日**&#x200B;重放在上午&#x200B;**3点**（客户时区）前后运行，并且数据在早上之前在Customer Journey Analytics报表中更新。

>[!IMPORTANT]
>
>无法通过自定义请求更改每周重放的日期和每日重放的小时。
>

+++

## 共享设备

**问题**：如何处理共享设备？

+++回答

在某些情况下，可能会有多人从同一设备登录。 例如，在家中使用共享设备，在图书馆中使用共享 PC，或在零售商店中使用自助终端。

人员 ID 会覆盖永久 ID，因此共享设备会被视为单独的人员（即使这些人员来自同一设备也是如此）。

更多信息请参阅[共享设备](/help/use-cases/stitching/shared-devices.md)用例。

+++

## 多个永久 ID

**问题**：拼合如何处理单个用户拥有多个永久ID的情况？

+++回答

在某些情况下，单个用户可以与多个永久 ID 相关联。 例如，经常清除浏览器的Cookie或使用浏览器私人/无痕模式的用户。

对于基于字段的拼接，永久 ID 的数量并不重要，重要的是人员 ID。 单个用户可以属于任意数量的设备，而不会影响 Customer Journey Analytics 的跨设备拼接功能。

对于基于图形的拼合，一个人在身份图中可以具有多个永久ID。 基于图形的拼接是使用基于指定命名空间的永久 ID。 如果同一命名空间有更多的永久ID，则使用词典编排的第一个永久ID。

+++

## 拼接过程

**问题**：在联系我的Adobe客户团队并提供所需信息后，已重新生成键值的数据集需要多长时间才可用？

+++回答

Adobe 启用拼接后大约一周，实时拼接功能就可供使用。 回填可用性取决于现有数据的数量。 小型数据集（每日的事件数量少于 100 万）通常需要几天时间，而大型数据集（每日的事件数量为 10 亿）可能需要一周或更长时间。

+++

## 跨设备分析与跨渠道分析

**问题**：跨设备分析（传统Analytics中的一项功能）和跨渠道分析之间有何区别？

+++回答

[跨设备分析](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/cda/overview)是传统 Adobe Analytics 的一项特有功能，它使您能够了解人们如何跨设备操作。 该功能提供了两种将设备数据链接在一起的工作流：基于字段的拼接和设备图。

跨渠道分析是 Customer Journey Analytics 的一个特有用例，允许您了解人们在各种设备和渠道上如何操作。 它会拼接数据集的人员 ID，使该数据集与其他数据集无缝组合。 此功能在设计上与基于跨设备分析字段的拼接功能类似，但由于传统 Analytics 和 Customer Journey Analytics 之间的数据架构不同，此功能的实施方法也不同。 更多信息请参阅[拼接](overview.md)和[跨渠道分析](../use-cases/cross-channel/cross-channel.md)用例。

+++

## 隐私

**问题**：拼合如何处理隐私请求？

+++回答

Adobe 会根据本地和国际法律处理隐私请求。 Adobe 提供了 [Adobe Experience Platform 隐私服务](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/privacy/home)来提交数据访问和删除请求。 这些请求同时适用于原始数据集和已重新生成键值的数据集。

>[!IMPORTANT]
>
>作为隐私请求的一部分，解除拼接过程在 2025 年初发生变化。 当前的解除拼接过程是使用最新版本的已知身份标识来重新拼接事件。 将事件重新分配给另一个身份标识可能会产生不良的法律后果。 为了消除这些疑虑，从 2025 年开始，新的解除拼接过程是通过永久 ID 更新隐私请求涉及的事件。
> 

举例来说，假设有以下关于身份标识、拼接前和拼接后事件的数据。

| 身份标识图 | Id | 时间戳 | 永久 ID | 永久命名空间 | 人员 ID | 人员命名空间 |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ecid | Bob | CustId |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| 事件数据集 | Id | 时间戳 | 永久 ID | 永久命名空间 | 人员 ID | 人员命名空间 |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| | 2 | ts1 | 123 | ecid | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| 拼接数据集 | Id | 时间戳 | 永久 ID | 永久命名空间 | 人员 ID | 人员命名空间 | 结果ID | 拼接命名空间 |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | Bob | CustId |
| | 2 | ts1 | 123 | ecid | Bob | CustId | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**隐私请求的当前进程**

收到 CustID Bob 的客户的隐私请求后，就会删除带有删除线条目的行。 其他事件使用身份标识图重新进行拼接。 例如，拼接数据集中的第一个拼接 ID 更新为 **Alex**。

| 身份标识图 | Id | 时间戳 | 永久 ID | 永久命名空间 | 人员 ID | 人员命名空间 |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| 事件数据集 | Id | 时间戳 | 永久 ID | 永久命名空间 | 人员 ID | 人员命名空间 |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| 拼接数据集 | Id | 时间戳 | 永久 ID | 永久命名空间 | 人员 ID | 人员命名空间 | 结果ID | 拼接命名空间 |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **Alex** | CustId |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**隐私请求的新过程**

收到 CustID Bob 的客户的隐私请求后，就会删除带有删除线条目的行。 其他事件使用永久 ID 重新进行拼接。 例如，拼接数据集中的第一个拼接 ID 更新为 **123**。

| 身份标识图 | Id | 时间戳 | 永久 ID | 永久命名空间 | 人员 ID | 人员命名空间 |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| 事件数据集 | Id | 时间戳 | 永久 ID | 永久命名空间 | 人员 ID | 人员命名空间 |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| 拼接数据集 | Id | 时间戳 | 永久 ID | 永久命名空间 | 人员 ID | 人员命名空间 | 结果ID | 拼接命名空间 |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **123** | ecid |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |

+++

## 空白的永久 ID 值

**问题**：如果一个或多个事件中的永久ID字段为空，会发生什么情况？

+++回答

如果在要拼合的数据集内，某个事件的持久ID字段为空，则会通过以下两种方式之一确定该事件的结果ID：

* 如果人员ID字段不为空，则Customer Journey Analytics使用人员ID中的值作为生成的ID。
* 如果人员ID字段为空，则Customer Journey Analytics还会将生成的ID留空。 在这种情况下，事件的永久ID、人员ID和结果ID全部为空。 使用拼合的数据集从任何Customer Journey Analytics连接中删除这些类型的事件，其中将选择生成的ID作为人员ID。

+++


## 未定义的人员 ID 值

**问题**：如果一个或多个事件中的人员ID字段具有占位符值（如`Undefined`），会发生什么情况？

+++回答

将拼接应用于为临时 ID 使用占位符值的数据时，会出现“人员折叠”，这种情况务必小心。 在下面的例表中，来自 CRM 系统的一个数据集中的未定义人员 ID 被填充为“Undefined”值，从而导致人员表示不正确。

| 事件 | 时间戳 | 永久 ID（Cookie ID） | 临时 ID | 生成的ID（重播后） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 123 | - | **Cory** |
| 2 | 2023-05-12 12:02 | 123 | Cory | **Cory** |
| 3 | 2023-05-12 12:03 | 456 | 未定义 | **未定义** |
| 4 | 2023-05-12 12:04 | 456 | - | **未定义** |
| 5 | 2023-05-12 12:05 | 789 | 未定义 | **未定义** |
| 6 | 2023-05-12 12:06 | 012 | 未定义 | **未定义** |
| 7 | 2023-05-12 12:07 | 012 | - | **未定义** |
| 8 | 2023-05-12 12:03 | 789 | 未定义 | **未定义** |
| 9 | 2023-05-12 12:09 | 456 | - | **未定义** |
| 10 | 2023-05-12 12:02 | 123 | - | **Cory** |
| | | **4 个设备** | **2 个人**：<br/>事件 1、4、7、9、10 已丢弃 | **2 个人**：<br/>Cory，未经身份验证（折叠为一个人） |

+++

## 量度比较

**问题**：与Customer Journey Analytics未拼接数据集中的类似量度相比，Customer Journey Analytics拼接数据集中的量度如何？与Adobe Analytics相比，如何？

+++回答

Customer Journey Analytics 中的某些量度与传统 Analytics 中的量度相似，但其他量度则大不相同，具体取决于您要比较什么。 下表比较了几个常见的量度：

| **Customer Journey Analytics 拼接数据** | **Customer Journey Analytics 未拼接数据** | **Adobe Analytics** | **带 CDA 的 Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **人员** =不同人员ID的数量，其中产生的ID被选作人员ID。 **人员数** 可能高于或低于传统 Adobe Analytics 中的&#x200B;**独特访客数**，具体取决于拼接过程的结果。 | **人员** = 根据被选为人员 ID 的列计算的不同人员 ID 的数量。 如果在 Customer Journey Analytics 中 `endUserIDs._experience.aaid.id` 用作人员 ID，Adobe 源连接器数据集中的&#x200B;**人员**&#x200B;就与传统 Adobe Analytics 中的&#x200B;**独特访客**&#x200B;类似。 | **独特访客** = 不同访客 ID 的数量。 **独特访客**&#x200B;可能与不同 **ECID** 的数量不一致。 | 请参阅[人员数](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/metrics/people)。 |
| **会话**：根据 Customer Journey Analytics 数据视图中的会话设置定义。 拼接过程可能会将来自多个设备的各个会话组合成单个会话。 | **会话**：根据 Customer Journey Analytics 数据视图中特定的会话设置定义。 | **访问数**：请参阅[访问数](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/metrics/visits)。 | **访问数**：根据 [CDA 虚拟报告包](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/cda/setup)中特定的会话设置定义。 |
| **活动**= Customer Journey Analytics 中拼接数据的行数。 该量度通常接近于传统 Adobe Analytics 中的&#x200B;**“发生次数”。** 但是，请注意上面关于包含空白永久 ID 的行的常见问题解答。 | **活动**= Customer Journey Analytics 中未拼接数据的行数。 该量度通常接近于传统 Adobe Analytics 中的&#x200B;**“发生次数”。** 但是请注意，如果任何事件在 Experience Platform 数据湖的未拼接数据中有空白的永久 ID，这些事件就不包括在 Customer Journey Analytics 中。 | **发生次数**：请参阅[发生次数](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/metrics/occurrences)。 | **发生次数**：请参阅[发生次数](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/metrics/occurrences)。 |

Customer Journey Analytics 和 Adobe Analytics 中的其他量度可能相似。 例如，Adobe Analytics [自定义事件](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/metrics/custom-events) 1 – 100 的总数在传统 Adobe Analytics 和 Customer Journey Analytics 之间具有可比性（无论是否拼接）。 Customer Journey Analytics 与 Adobe Analytics 之间的[功能差异](/help/getting-started/aa-vs-cja/cja-aa.md)（如消除重复事件）可能会导致这两种产品之间存在差异。

+++

## 身份标识图

**问题**： Customer Journey Analytics能否使用标识映射字段？

+++回答

可以，Customer Journey Analytics 可以为[基于字段的](/help/stitching/fbs.md#identitymap)和[基于图形的](/help/stitching/gbs.md#identitymap)拼接使用身份标识图字段。

+++

## 切换到基于图形的拼接

**问题**：是否需要重新摄取数据才能从基于字段的拼接切换到基于图形的拼接？

+++回答

数据不必重新摄取到Experience Platform。 但是，数据需要在Customer Journey Analytics中重新配置。 请执行以下步骤：

1. 使用基于图形的拼接来设置新的基于图形的拼接数据集。
1. 创建一个数据时间窗口非常短的新的临时连接。
1. 将新的基于图形的数据集配置为这个临时连接的一部分。
1. 通过这个新的临时连接验证基于图形的拼接是否正常工作。
1. 如果基于图形的拼接按预期工作，为基于图形的数据集请求进行任何额外回填，然后将原始连接中基于字段的数据集与新的基于图形的数据集交换。
1. 移除这个临时连接。

+++

## 报告中的干扰

**问题**：现有报表是否会发生任何中断？

+++回答

如果您按照上述步骤操作就不会。 如果不是这样，请联系 Adobe Consulting 获取更多支持。

+++

## 为身份标识服务启用数据集

**问题**：如何仅为Identity服务启用数据集？

+++回答

确保为Identity Service启用了数据集，以便将该数据集用于基于图形的拼合。

您要使用基于图形的拼接不必具有 Real-Time Customer Data Platform 许可。 基于图形的拼接是基于一个可用的身份标识图，而不是基于实时客户轮廓。

要检查现有数据集并仅为标识服务启用该数据集，请使用对仅使用`unifiedIdentity`标记的`/datasets`终结点的`PATCH`请求。 例如：

```shell
curl -X PATCH \
  https://platform.adobe.io/data/foundation/catalog/dataSets/{DATASET_ID} \
  -H 'Content-Type:application/json-patch+json' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '[
        { "op": "add", "path": "/tags/unifiedIdentity", "value": ["enabled:true"] }
      ]'
```

如果您未获得 Real-Time Customer Data Profile 的许可，在请求中 `unifiedProfile` 标记的任何使用都会返回错误。

更多信息请参阅[创建一个为轮廓和身份标识启用的数据集](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/catalog/datasets/enable-for-profile#enable-the-dataset)。

+++


## 拼接的命名空间值

**问题**：为什么拼接的命名空间值并不总是与可在CJA连接内的另一个数据集中使用的身份命名空间值相匹配？

+++回答

默认情况下，拼接的命名空间值为小写。 因此，`custEmail`将变为`custemail`。 如果您的另一个数据集的身份命名空间值为`custEmail`，则两个值不匹配。 若要解决报告中的这种行为，您可以使用[lowercase()](/help/data-views/derived-fields/derived-fields.md#lowercase)派生字段函数来匹配身份命名空间值。

+++
