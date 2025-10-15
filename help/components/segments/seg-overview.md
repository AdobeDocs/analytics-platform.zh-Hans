---
title: 分段概述
description: 了解区段的用途以及如何创建简单的区段。
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters, Segments
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '1474'
ht-degree: 99%

---


# 分段概述

使用 Customer Journey Analytics，您可以构建、管理、共享强大集中的受众区段，并将这些区段应用到您的报告。使用区段，您可以根据特征或交互识别人员、会话或事件的子集。区段的设计基于对受众洞察的分析整理，您可以根据自己的特定需求来构建，然后验证、编辑并与其他团队成员共享。

区段可以基于：

- 属性（浏览器类型、设备、访问次数、国家/地区、性别），
- 交互（营销活动、关键词搜索、搜索引擎），
- 退出和进入（来自 Facebook 的人员、定义的登陆页面、反向链接域、地理围栏事件），
- 自定义变量（表单字段、定义的类别、客户 ID），
- 以及其他标准。

请参阅[创建区段](/help/components/segments/seg-create.md)，了解可用于创建区段的各种选项。然后，您可以在[区段生成器](seg-builder.md)中构建、更改和保存某个区段的定义。或者，您也可以使用[快速区段生成器](seg-quick.md)创建快速区段。您还可以从工作区中的可视化图表生成区段，例如使用[流失](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu)可视化图表。

您可以使用[区段管理器](seg-manage.md)来管理区段。

## 计划区段

特别是作为管理员，适当的区段规划可以提高区段被使用的机会。规划区段时应考虑以下事项：

- **受众**：谁将使用您的区段？确保提供良好的区段描述，以便受众理解：
   - 此区段在哪些方面有用？

   - 我应何时使用此区段？

- **范围**：哪个[区段容器](#segment-containers)最能代表您所追求的数据？尽可能使用最小的容器。

- **组件**：决定在区段定义中包含哪些组件，以及应该根据哪些值来验证条件。

- **流程**：考虑为您的区段制定一个审批流程。Customer Journey Analytics 中没有审批工作流程，但您仍然可以组织一个流程来决定是否批准某个区段。

- **模块化**：定义区段时应考虑模块化。区段的用户应该能够轻松[堆叠区段](seg-builder.md#stack-filters)，以创建强大的新区段。


## 区段类型

您可以创建三种类型的区段：

### 快速区段

快速区段允许您轻松浏览某个给定工作区项目中的数据，而无需在[区段生成器](/help/components/segments/seg-create.md)中创建区段。您可以直接在工作区界面中定义区段。请参阅[快速区段](seg-quick.md)了解更多信息。

### 常规区段

使用常规区段，您可以根据一个或多个条件识别数据（人员、会话、事件）。如果有多个条件，可以使用 And 和 Or 等逻辑运算符进一步定义区段。您可以使用容器将条件分组，构建更复杂的区段。请参阅[区段生成器](seg-builder.md)了解更多信息。

### 顺序区段

>[!IMPORTANT]
>
>您必须拥有 **Select** 包才能创建跨渠道顺序区段。如果您不确定您拥有的是哪个 Customer Journey Analytics 包，请联系您的管理员。

使用顺序区段，您可以根据导航（网站上的各页面浏览次数、与移动应用中各场景的交互，或使用机顶盒上的菜单）识别数据（人员、会话、事件）。例如，顺序区段可帮助您识别某个人喜欢什么以及会避免什么。您可以使用 Then 逻辑运算符来定义顺序区段。请参阅[顺序区段](seg-sequential-build.md)了解更多信息。


<!--
An example of a complex sequential segment if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## 区段容器 {#containers}

区段基于一个采用嵌套容器模型的人员级、会话级和事件级的层级。嵌套容器允许您定义容器之间和容器内部的条件。


<table style="table-layout: fixed; border: none;" width="100%">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> 人员</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> 会话</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> 事件</td>
</tr>
</table>

>[!NOTE]
>
>对于 Adobe Analytics 用户：
> 
> - **人员**&#x200B;容器在 Adobe Analytics 中称为&#x200B;**访客**&#x200B;容器。
> - **会话**&#x200B;容器在 Adobe Analytics 中称为&#x200B;**访问**&#x200B;容器。
> - **事件**&#x200B;容器在 Adobe Analytics 中称为&#x200B;**点击**&#x200B;容器。
>

区段设置了条件，以根据这些条件将人员、会话或事件分段。例如，将人员分段的条件是基于人员特征和导航特性。为了进一步细分数据，您可以根据特定会话、页面浏览事件、屏幕点击、机顶盒上的菜单选项等进行分段。您还可以根据从某个 CRM 或忠诚度系统中摄取的属性进行分段。[区段生成器](/help/components/segments/seg-builder.md)提供了一个简单的界面来生成这些子集，并应用嵌套的层级结构的“人员”、“会话”或“事件”容器中的条件。

[区段生成器](/help/components/segments/seg-builder.md)中部署的容器架构将“人员”定义为最外层容器。该容器包含对于各种会话及事件（例如页面浏览次数、移动应用程序屏幕或者机顶盒上的菜单屏幕）中人员特定的总体数据。嵌套的会话容器允许您设置用于根据会话细分人员数据的规则。通过嵌套的事件容器，您可以根据个人交互细分人员信息。通过每个容器，您都可以报告跨人员的历史记录和按会话细分的交互，或者细分个人事件。

### 人员容器

人员容器包含符合该容器中指定条件的人员的每个会话和每个事件。如果您使用 `Page Name equals Checkout` 这样的简单条件定义一个区段，人员容器就会解析为：

- 所有访问过名为 `Checkout` 的页面的人员。
- 这些人的所有会话。
- 这些人的所有事件数据。

作为定义最广泛的容器，在人员容器级别上生成的报告将返回符合该区段的所有人员的事件和会话。人员容器是最容易受到所定义的日期范围影响的容器。人员容器可以包含基于某个人总体历史记录的值：

- 首次购买前的天数。
- 原始登入页面或者移动应用程序主屏幕。
- 原始反向链接域。

### 会话容器

通过会话容器可以识别页面交互或移动应用程序交互、营销活动或者特定会话的转化。会话容器是最常使用的容器，因为只要符合规则，该容器便会立即捕获整个会话的行为。使用会话容器可以定义在构建和应用某个区段时想要包含或排除哪些会话。如果您使用 `Page Name equals Checkout` 这样的简单条件定义一个区段，会话容器就会解析为：

- 访问了名为 `Checkout` 的页面的所有会话。
- 这些会话的所有事件数据。

会话容器可以帮助您回答以下问题：

- 有多少会话同时需要 Web 和呼叫中心数据源？
- 哪些页面有助于成功转化为销售？

会话容器中包含基于每次会话的事件的值：

- 会话类型。
- 登入页面。
- 回访频率。
- 参与率量度。
- 线性分配的量度。

通过 Customer Journey Analytics 中的数据视图，您可以确定会话持续的时间，以及应何时创建新会话。例如，您可以根据某个用户每次启动您的移动应用程序来定义一个新的移动应用程序会话。请参阅[会话设置](/help/data-views/session-settings.md)了解更多信息。

### 事件容器

事件容器定义了您想要在一个区段中包含或排除的页面、移动应用程序或其他类型的事件。它是可用的容器中最窄的一种。您可以识别移动应用中条件为真的特定点击、页面浏览和按钮点击。使用事件容器，您可用查看单个跟踪代码，或者分离出移动应用程序某个特定区域中的行为。您也可能想要准确确定在出现某个行为时的某个特定值，比如下订单时的营销渠道。如果您使用 `Page Name equals Checkout` 这样的简单条件定义一个区段，事件容器就会解析为：

- 页面名称为 `Checkout` 的所有页面浏览事件。

事件容器包括对以下内容的基于值的单页面细分：

- 产品
- 列表属性
- 列表维度
- 促销维度（在事件上下文中）



### B2B 容器

[!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}

如果您有权访问 [Customer Journey Analytics B2B Edition](/help/getting-started/cja-b2b-edition.md)，还有其他容器可供区段使用。您可以在 [B2B 概念和特点](/help/getting-started/cja-b2b-concepts-features.md)中找到有关使用这些附加容器的更多详细信息。


### 逻辑组容器

使用逻辑组，您可以将条件分组到一个顺序区段检查点。作为序列的一部分，该容器中定义的逻辑被标识为[!UICONTROL 逻辑组]，在任何先前的顺序检查点之后以及在任何后续的顺序检查点之前被评估。请参阅[逻辑组](seg-sequential-build.md#logic-group)了解更多信息。

### 嵌套容器

在其他容器内创建容器实际上就是在一个区段内创建区段。以下逻辑应用于嵌套的容器：

1. 确定使用最外部的容器包含哪些数据。不符合此外部规则的所有数据都将在报告中被丢弃。
2. 将嵌套的区段定义应用到其余数据。嵌套的区段定义不适用于因第一个定义而丢弃的任何数据。
3. 重复此过程，直到所有嵌套的容器区段定义都计算完毕。然后，其余数据会包含到结果中并用于报告。

>[!NOTE]
>
>如果您将一个区段嵌套在另一个区段中（例如，将一个区段从组件面板拖放到区段定义上），就会创建一个容器及所拖放区段定义的副本（而不是引用）。

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box segment template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Segment Name | Description |
| --- | --- |
| All Data | All Data is a required segment that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[创建区段](seg-create.md)
>&#x200B;>[区段生成器](seg-builder.md)
>&#x200B;>[快速区段](seg-quick.md)
>&#x200B;>[顺序区段](seg-sequential-build.md)
>&#x200B;>[管理区段](seg-manage.md)
