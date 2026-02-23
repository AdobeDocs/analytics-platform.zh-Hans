---
description: 了解使用THEN运算符定义区段条件序列的顺序区段。
title: 顺序区段
feature: Filters, Segments
exl-id: 64cb10b5-36f0-42c8-b687-ae5de5ced8b5
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '2461'
ht-degree: 3%

---

# 顺序区段

在组件、容器和组件或容器之间使用[!UICONTROL Then]逻辑运算符创建顺序区段。 [!UICONTROL Then]逻辑运算符表示出现一个区段条件，然后是另一个区段条件。



>[!BEGINSHADEBOX]

观看演示视频的![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [顺序分段](https://experienceleague.adobe.com/zh-hans/docs/analytics-learn/tutorials/components/segmentation/sequential-segmentation){target="_blank"}。

{{videoaa}}

>[!ENDSHADEBOX]

顺序区段具有一些[基本功能](#basics)和其他选项，您可以配置这些选项来增加顺序区段的复杂性：

![顺序区段](assets/sequential-filter.gif)

* 序列区段定义中Then逻辑的[After和within](#after-and-within)约束：

* [包含哪些数据作为区段定义整体序列的一部分](#include)。 或者，对于定义为容器一部分的序列。 默认情况下，会考虑所有匹配数据。 该数据由![用户组](/help/assets/icons/UserGroup.svg) [!UICONTROL 包含每个人]标识。

   * 选择![SequenceBefore](/help/assets/icons/SequenceBefore.svg) **[!UICONTROL Only Before Sequence]**&#x200B;以仅考虑序列之前的数据。
   * 选择![SequenceAfter](/help/assets/icons/SequenceAfter.svg) **[!UICONTROL Only After After Sequence]**&#x200B;以仅考虑序列之后的数据。

* [排除](#exclude)的顺序区段定义数据。

* 如何在顺序区段定义中[逻辑分组](#logic-group)条件。

## 基础知识



生成顺序区段的基础知识与使用[区段生成器](seg-builder.md)生成常规区段的基础知识没有区别。 您可以使用[定义生成器](seg-builder.md#definition-builder)来构造区段定义。 在该构造中，使用组件、容器、运算符和逻辑。 只要在主定义或您在&#x200B;**[!UICONTROL 定义生成器]**&#x200B;中使用的任何容器中选择[Then](seg-builder.md#definition-builder)运算符，常规区段就会变成顺序区段。

### 示例

以下示例说明如何在各种用例中使用顺序区段。

#### 简单序列

识别查看了某个页面然后又查看了另一个页面的人员。 事件级别的数据将使用此序列进行分段。 不考虑以前、过去或临时人员会话，也不考虑会话之间发生的页面查看时间或次数。

![顺序区段包括所有人](assets/sequence-include-everyone.png)

#### 跨会话的序列

识别在一个会话中查看了某个页面，然后在另一个会话中查看了另一个页面的人员。 若要区分会话，请使用容器生成序列并为每个容器定义![访问](/help/assets/icons/Visit.svg) **[!UICONTROL 会话]**&#x200B;级别。

![跨会话对区段进行排序](assets/sequence-filter-session.png)

#### 混合级别序列

确定在次数不定的会话中查看两个页面，然后在单独的会话中查看第三个页面的人员。 同样，使用容器构建序列并在定义单独会话的容器上定义![访问](/help/assets/icons/Visit.svg) **[!UICONTROL 会话]**&#x200B;级别。

![具有单独最终会话的连续区段](assets/sequence-filter-final-session.png)

#### 聚合序列

确定在首次会话时访问特定页面，然后访问某些其他页面的人员。 若要区分事件的序列，请使用容器在![WebPage](/help/assets/icons/WebPage.svg) **[!UICONTROL 会话]**&#x200B;容器级别上分离逻辑。

![会话聚合容器](assets/session-aggregate-containers.png)


#### 嵌套序列

确定以下所有会话：用户先访问一个页面，然后再访问另一个页面，然后进行涉及其他两个页面的跟进会话。 例如，确定人员首先访问主页，然后访问类别1页面，然后又访问其他会话，其中每个会话访问类别2和类别3页面。

![嵌套序列](assets/sequence-nested.png)

## [!UICONTROL After]和[!UICONTROL Within]

您可以使用![Clock](/help/assets/icons/Clock.svg) **[!UICONTROL After]**&#x200B;和![Clock](/help/assets/icons/Clock.svg) **[!UICONTROL Within]** **[!UICONTROL Then]**&#x200B;运算符为事件、会话或维度[定义其他](#time-constraints)时间约束[或](#event-session-and-dimension-constraints)约束。

### 时间限制

要将时间约束应用于&#x200B;**[!UICONTROL Then]**&#x200B;运算符：

1. 选择![时钟](/help/assets/icons/Clock.svg)。
1. 从上下文菜单中选择&#x200B;**[!UICONTROL Within]**&#x200B;或&#x200B;**[!UICONTROL After]**。
1. 指定一个时间段（**[!UICONTROL 分钟]**，**[!UICONTROL 小时]**，最多&#x200B;**[!UICONTROL 年]**）。
1. 选择![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL *number *]**&#x200B;以打开一个弹出窗口，允许您使用&#x200B;**[!UICONTROL -]**&#x200B;或&#x200B;**[!UICONTROL +]**&#x200B;键入或指定数字。

若要移除时间限制，请使用![CrossSize75](/help/assets/icons/CrossSize75.svg)。

下表更详细地说明了时间限制运算符。

| 运算符 | 描述 |
|--- |--- |
| **[!UICONTROL After]** | [!UICONTROL After]运算符用于指定两个检查点之间的时间长度的最小限制。 设置After值时，时间限制从应用区段时开始。 例如，如果在容器上设置[!UICONTROL After]运算符以识别访问页面A，但直到一天后才返回访问页面B的人员，则访客离开页面A时将会开始该日期。 对于要包含在区段中的访客，离开页面A后必须至少经过1440分钟（一天）才能查看页面B。 |
| **[!UICONTROL Within]** | [!UICONTROL Within]运算符用于指定两个检查点之间的时间长度的最大限制。 例如，如果在容器上设置[!UICONTROL Within]运算符以识别访问页面A，然后在一天内返回访问页面B的人员，则该时间将从该人员离开页面A时开始。要包含在此区段中，人员最多需要在一天之后打开页面B。对于要包含在区段中的人员，在离开页面A以查看页面B后，最多必须在1440分钟（一天）内打开页面B。 |
| **[!UICONTROL 晚于]**&#x200B;之内 | 同时使用[!UICONTROL After]和[!UICONTROL Within]运算符时，这两个运算符是并行开始和结束的，而不是按顺序开始和结束。 <br/>例如，您生成了一个区段，其容器设置为： `After = 1 Week(s) and Within = 2 Week(s)`。<br/>此区段中用于识别访客的条件仅在一周至两周内满足要求。 这两个条件是从第一次查看页面时开始执行的。 |


#### 示例

有关使用时间约束的一些示例。

##### [!UICONTROL After]运算符

识别仅两周后访问了一个页面然后又访问另一个页面的人员。 例如，访问主页的人员，但 | 仅两周后才能翻页。

![序列在](assets/sequence-after.png)之后

如果主页的页面查看发生在2024年6月1日00:01，则页面查看针对页面女性 | 只要2024年6月15日00:01之后出现该页面查看，鞋就会匹配。

##### [!UICONTROL Within]运算符

识别在五分钟内访问了一个页面然后访问另一个页面的人员。 例如，访问主页的人，然后访问妇女 | 在5分钟内完成“鞋子”页面。

![在](assets/sequence-within.png)内排序

如果主页的页面查看发生在2024年6月1日12:01，则页面查看针对页面女性 | 只要该页面查看发生在2024年6月15日12:16之前，鞋就会匹配。

##### [!UICONTROL After]但[!UICONTROL Within]运算符

识别访问了一个页面然后在两周后但在一个月内访问另一个页面的人员。 例如，访问主页的人，两周后在一个月内访问的女性 | “鞋子”页面。

![序列晚于](assets/sequence-afterbutwithin.png)但在此范围内

2024年6月1日点击主页并返回妇女之家的任何人 | 2019年6月15日之后00:01但2019年7月1日之前的“鞋子”页面符合该区段的条件。


### [!UICONTROL 事件]、[!UICONTROL 会话]和[!UICONTROL Dimension]约束

![Clock](/help/assets/icons/Clock.svg) **[!UICONTROL After]**&#x200B;和![Clock](/help/assets/icons/Clock.svg) **[!UICONTROL Within]**&#x200B;约束不仅允许您指定时间约束，还可以指定事件、会话或维度约束。 选择&#x200B;**[!UICONTROL 事件]**、**[!UICONTROL 会话]**&#x200B;或&#x200B;**[!UICONTROL 其他维度]** ![V形右侧](/help/assets/icons/ChevronRight.svg) **[!UICONTROL *Dimension名称&#x200B;*]**。 您可以使用&#x200B;[!UICONTROL *搜索*]字段来搜索维度。

#### 示例

以下是一个序列区段示例，该区段会查找访问过一个产品类别页面的人员（女性） | 鞋子)，然后是结帐页面（结帐） | 谢谢)。

![在](assets/sequence-filter-within.png)内排序区段

以下示例序列匹配或不匹配：

| 序列 | ![ApproveReject](/help/assets/icons/ApproveReject.svg) |
|--- | :---: |
| 页面`Women \| Shoes`后跟页面`Checkout \| Thank You` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| 页面`Women \| Shoes`后跟页面`Women \| Tops`，后跟页面`Checkout \| Thank You` | ![移除圆圈](/help/assets/icons/RemoveCircle.svg) |

## [!UICONTROL 包含]

您可以指定要包含在顺序区段或作为顺序区段一部分的顺序容器中的数据。

### [!UICONTROL 每个人] {#include_everyone}

要创建包含每个人的顺序区段，请选择选项![用户组](/help/assets/icons/UserGroup.svg) **[!UICONTROL 包含每个人]**。

顺序区段识别整体匹配给定模式的数据。  下面是一个基本序列区段示例，该区段会查找访问过某个产品类别页面的人员（女性） | 鞋子)，然后是结帐页面（结帐） | 谢谢)。 该区段设置为![用户组](/help/assets/icons/UserGroup.svg) **[!UICONTROL 包含每个人]**。

![顺序区段包括所有人](assets/sequence-include-everyone.png)

以下示例序列匹配或不匹配：

| | 序列 | ![ApproveReject](/help/assets/icons/ApproveReject.svg) |
|---:|--- | --- |
| 1 | 在同一会话中`Women \| Shoes`然后`Checkout \| Thank You` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| 2 | `Women \| Shoes`然后`Men \| Shoes`然后`Checkout \| Thank You`（跨不同会话） | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| 3 | `Checkout \| Thank You`，然后`Women \| Shoes` | ![移除圆圈](/help/assets/icons/RemoveCircle.svg) |

### [!UICONTROL 仅在序列之前]，[!UICONTROL 仅在序列之后]

选项![SequenceBefore](/help/assets/icons/SequenceBefore.svg) **[!UICONTROL Only Before Sequence]**&#x200B;和![SequenceAfter](/help/assets/icons/SequenceAfter.svg) **[!UICONTROL Only Before Sequence]**&#x200B;将数据分段到指定序列之前或之后的子集。

* ![SequenceBefore](/help/assets/icons/SequenceBefore.svg) **Only Before Sequence**：包含序列之前的所有数据和序列本身的第一个数据。 如果序列作为数据的一部分出现多次，则[!UICONTROL 仅在序列之前]包括该序列最后一个实例的第一次点击和所有先前的点击。
* ![SequenceAfter](/help/assets/icons/SequenceAfter.svg) **Only After Sequence**：包含序列之后的所有点击以及该序列本身的最后一个数据。 如果序列作为数据的一部分出现多次，则[!UICONTROL 仅在序列之后]包括该序列第一个实例的最后一次点击以及所有后续点击。

考虑一个定义，该定义指定具有由B标识的标准、后跟(Then)具有由D标识的标准的组件序列的组件。三个选项将按以下方式标识数据：


| B然后D | A | B | C | D | E | F |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| 包含每个人 | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| 仅在序列之前 | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |  |  |  |  |
| 仅在序列之后 |  |  |  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |

{style="table-layout:fixed"}



| B然后D（出现多次） | A | B | C | D | B | C | D | E |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| 包含每个人 | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| 仅在序列之前 | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |  |  |  |
| 仅在序列之后 |  |  |  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |

{style="table-layout:fixed"}

#### 示例

您为网站区域定义了三个版本的顺序区段。 一个具有选项![UserGroup](/help/assets/icons/UserGroup.svg) **[!UICONTROL 包括所有人]**，一个具有选项![SequenceBefore](/help/assets/icons/SequenceBefore.svg) **[!UICONTROL 且仅在Sequence]**&#x200B;之前，另一个具有选项![SequenceAfter](/help/assets/icons/SequenceAfter.svg) **[!UICONTROL 且仅在Sequence]**&#x200B;之后。 您相应地命名了三个区段。

![序列区段](assets/site-section-filters.png)

在使用这三个区段报告网站区域时，自由格式表中的示例输出如下所示：

![连续区段报告](assets/sequential-filter-freeform-table.png)

## [!UICONTROL 排除]

区段定义包括所有数据，除非您使用![排除](/help/assets/icons/User.svg)专门排除[!UICONTROL User] ![Person](/help/assets/icons/Visit.svg)、[!UICONTROL Visit] ![Session](/help/assets/icons/WebPage.svg)或[!UICONTROL WebPage] **[!UICONTROL Event]**&#x200B;数据。

[!UICONTROL 排除]允许您关闭常见数据并创建更集中的区段。 “排除”还允许您创建排除特定人员组的区段。 例如，定义一个区段，该区段指定下订单的人员，然后排除该人员组以识别&#x200B;*非购买者*。 最佳做法是创建使用宽泛定义的规则，而不是尝试使用[!UICONTROL 排除]来定位与特定包含值匹配的特定角色。

排除定义的示例包括：

* **排除页面**。 使用区段定义从报告中排除特定页面（如&#x200B;*主页*），创建页面等于`Home Page`的事件规则，然后排除该规则。 此定义自动包括&#x200B;*主页*&#x200B;以外的所有页面。
* **排除反向链接域**。 请使用仅包含来自Google.com的反向链接域并排除所有其他域的定义。
* **识别非购买者**。 识别订单大于零的时间，然后排除[!UICONTROL 人员]。

[!UICONTROL Exclude]可用于识别人员不是特定会话一部分的序列或执行特定事件。 [!UICONTROL 排除]也可以包含在[!UICONTROL 逻辑组]中（请参阅下文）。

您可以排除容器而非组件。

### 示例

有关使用[!UICONTROL 排除]的示例，请参见下文。

#### [!UICONTROL 排除]，在

识别访问了一个页面、未访问另一个页面、然后又访问另一个页面的人员。 您使用![设置](/help/assets/icons/Setting.svg) [!UICONTROL 排除]排除容器。 排除的容器由左侧的红色细条标识。

![排除序列](assets/sequence-exclude.png)


#### 开始时[!UICONTROL 排除]

识别从未访问过某个页面就访问过另一个页面的人员。 例如，访客结帐后从未访问过主页。

![序列排除开始](assets/sequence-exclude-start.png)


#### 在末尾[!UICONTROL 排除]

识别访问过一个页面但从未访问过其他页面的人员。 例如，访问过您的主页但从未访问过任何结账页面的人员。

![序列排除结束](assets/sequence-exclude-end.png)


## [!UICONTROL 逻辑组]

>[!NOTE]
>
>[!UICONTROL 逻辑组]只能在顺序区段中定义，这意味着容器中使用[!UICONTROL Then]运算符。

使用逻辑组，您可以将条件分组到一个顺序区段检查点。作为序列的一部分，在标识为逻辑组的容器中定义的逻辑将在任何先前顺序检查点之后和任何后续顺序检查点之前进行评估。

可以按任意顺序满足逻辑组本身中的条件。 相反，非顺序容器（事件、会话、人员）不要求在整个序列中满足其条件，如果与Then运算符一起使用，则会产生可能不直观的结果。

[!UICONTROL 逻辑组]设计成将&#x200B;*多个条件视为一个组，在分组条件中没有任何排序*。 除此以外，逻辑组中条件的顺序无关。

使用逻辑组的一些最佳实践包括：

* 对顺序检查点进行分组。
* 简化顺序区段的构造。

### 示例

以下是如何使用逻辑组容器的示例。

#### 任何订单

识别访问了一个页面，然后以任意顺序从另一组页面中查看了每个页面的人员。 例如，访客访问了主页，然后又访问了“男性”页面、“女性”页面和“儿童”页面，而不管顺序如何。

您可以在不使用[!UICONTROL 逻辑组]的情况下生成此区段，但构建过程将会非常复杂和费力。 指定访客可以查看的每个页面序列。 为清楚起见，仅打开第一个容器![ChevronDown](/help/assets/icons/ChevronDown.svg)，关闭其他容器![ChevronRight](/help/assets/icons/ChevronRight.svg)。 您可以通过标题来派生其他容器的内容。

![示例不使用逻辑组](assets/logicgroup-example-notusing.png)

您可以使用[!UICONTROL 逻辑组]来简化生成此区段的过程，如下所示。 请确保为容器选择![组](/help/assets/icons/Group.svg) **[!UICONTROL 逻辑组]**。

![示例不使用逻辑组](assets/logicgroup-example-using.png)

#### 第一个匹配项

识别访问了一个页面或其他页面，然后又访问另一个页面的人员。 例如，访问了“女性”页面或“男性”页面，然后访问了“结帐”的人员 | 感谢页面。

![示例将第一个匹配与逻辑组一起使用](assets/logicgroup-example-firstmatch.png)

#### [!UICONTROL 排除] [!UICONTROL 和]

识别访问了一个页面，然后明确未访问一组其他页面，但又访问了另一页面的人员。 例如，访问过主页的人员，没有访问男性页面或女性页面，但访问了儿童页面。

![逻辑组排除和](assets/logicgroup-exclude-and.png)

#### [!UICONTROL 排除] [!UICONTROL 或]

识别访问了一个页面，然后明确不访问一组页面中的任何页面，但又访问另一个页面的人员。 例如，访问主页但未访问“男女”页面，但访问了“孩子”页面的人员。

![逻辑组排除和](assets/logicgroup-exclude-or.png)


<!--
An example of a complex sequential segment if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->


## 最后一个示例

最后一个示例，您希望识别学习了特定产品页面的人员，并且这些人员从未被您的“启用您的移动”营销活动所接触。 在第一次访问网上商店时，他们浏览了主页，但没有进一步查看“男性”类别的任何健身（装备）产品。 但是，在随后的下一个会话中，他们直接转到产品页面并下达在线订单，而没有先访问主页。


![复杂顺序区段示例](assets/sequential-complex.png)
