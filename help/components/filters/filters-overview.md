---
title: 过滤器概述
description: 了解过滤器的用途以及如何创建简单的过滤器。
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
role: User
source-git-commit: 5fbb228fc02304be2246f0b49cb49de7f160b227
workflow-type: tm+mt
source-wordcount: '1423'
ht-degree: 8%

---


# 过滤器概述

Customer Journey Analytics 让您可以构建、管理、共享强大集中的受众过滤器，并将这些过滤器应用到您的报表。过滤器让您可以根据用户特征或交互情况来识别人员、会话或事件的子集。 过滤器是指正式设计编码的受众洞察，您可以根据自己的特定需求来构建，然后验证、编辑并与其他团队成员共享。

过滤器可以基于：

- 属性（浏览器类型、设备、访问次数、国家/地区、性别）、
- 交互（促销活动、关键词搜索、搜索引擎）、
- 退出和登录(来自Facebook、定义的登陆页、反向链接域、地理围栏事件的人员)，
- 自定义变量（表单字段、定义的类别、客户ID）、
- 和其他标准。

有关可用于创建筛选器的各种选项，请参阅[创建筛选器](/help/components/filters/create-filters.md)。 然后，在[筛选器生成器](filter-builder.md)中生成、修改和保存筛选器的定义。 或者，您可以使用[快速筛选器生成器](quick-filters.md)创建快速筛选器。 此外，您还可以从Workspace中的可视化图表生成过滤器，例如使用[流失](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu)可视化图表。

您使用[筛选器管理器](manage-filters.md)管理筛选器。

## 规划过滤器

尤其是作为管理员，正确规划过滤器可以提高使用过滤器的机会。 规划过滤器时，请考虑以下事项：

- **受众**：谁将使用您的筛选器？ 确保您提供准确的过滤器描述，以便受众了解：
   - 此过滤器有何用途？

   - 此过滤器应何时使用？

- **作用域**：哪个[筛选器容器](#filter-containers)最能代表您想要的数据？ 尽可能使用最小的容器。

- **组件**：决定筛选器定义中要包含哪些组件，以及条件应针对哪些值进行验证。

- **进程**：考虑您的筛选器的批准进程。 Customer Journey Analytics中没有审批工作流，但您仍然可以组织流程以确定是否审批过滤器。

- **模块性**：定义考虑到模块性的筛选器。 因此，您的筛选器的用户可以轻松[栈叠筛选器](filter-builder.md#stack-filters)以创建强大的新筛选器。


## 过滤器类型

您可以创建三种类型的过滤器：

### 快速筛选条件

快速筛选器允许您轻松地浏览给定Workspace项目中的数据，而无需在[筛选器生成器](/help/components/filters/create-filters.md)中创建筛选器。 可直接在Workspace界面中定义过滤器。 有关详细信息，请参阅[快速筛选器](quick-filters.md)。

### 常规过滤器

常规过滤器允许您根据一个或多个条件识别数据（人员、会话、事件）。 如果存在多个条件，则可以使用逻辑运算符（如And和Or）来进一步定义过滤器。 您可以使用容器对条件进行分组，并构建更复杂的过滤器。 有关详细信息，请参阅[筛选器生成器](filter-builder.md)。

### 顺序过滤器

>[!IMPORTANT]
>
>您必须具有&#x200B;**Select**&#x200B;包才能创建跨渠道顺序过滤器。 如果您不确定您拥有哪个Customer Journey Analytics包，请联系您的管理员。

通过顺序过滤器，您可以根据导航（网站中的页面查看次数、与移动应用程序中场景的交互或使用机顶盒上的菜单）来识别数据（人员、会话、事件）。 顺序过滤器可帮助您识别（例如）一个人喜欢什么，以及一个人避开什么。 可以使用Then逻辑运算符定义顺序过滤器。 有关详细信息，请参阅[顺序筛选器](seg-sequential-build.md)。


<!--
An example of a complex sequential filter if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## 过滤器容器 {#containers}

过滤器使用嵌套容器模型，并基于人员、会话和事件级别的层次结构。 利用嵌套的容器，可定义容器之间和容器内的条件。


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
>对于Adobe Analytics用户：
> 
> - 在Adobe Analytics中，**人员**&#x200B;容器称为&#x200B;**访客**&#x200B;容器。
> - **会话**&#x200B;容器在Adobe Analytics中称为&#x200B;**访问**&#x200B;容器。
> - **Event**&#x200B;容器在Adobe Analytics中称为&#x200B;**点击**&#x200B;容器。
>

过滤器设置条件以根据条件过滤人员、会话或事件。 例如，根据人员特性和导航特征筛选人员的条件。 要进一步划分数据，可以对特定会话、页面查看事件、屏幕点击、机顶盒上的菜单选项等内容进行过滤。 但也会根据您从CRM或忠诚度系统中摄取的属性进行过滤。 [筛选器生成器](/help/components/filters/filter-builder.md)提供了一个简单的界面来生成这些子集，并在嵌套的分层“人员”、“会话”或“事件”容器中应用条件。

[筛选器生成器](/help/components/filters/filter-builder.md)中使用的容器架构将“人员”定义为最外部的容器。 容器包含特定于人员的所有会话和事件（如页面查看、移动应用程序屏幕或机顶盒上的菜单屏幕）数据。 通过嵌套的“会话”容器，可设置规则以根据会话划分人员数据。 通过嵌套的事件容器，可根据各个交互划分人员信息。 通过每个容器，可跨人员的历史记录和按会话划分的交互进行报告，或者对各个事件进行划分。

### 人员容器

人员容器包括符合容器中指定条件的人员的每个会话和每个事件。 当您使用简单条件（如`Page Name equals Checkout`）定义过滤器时，“人员”容器解析为：

- 所有访问过名为`Checkout`的页面的人员。
- 所有这些人员的会议。
- 这些人员的所有事件数据。

作为定义范围最广的容器，在人员容器级别生成的报表将返回符合筛选条件的所有人员的事件和会话。 根据定义的日期范围，人员容器是最容易更改的。
人员容器可以包含基于人员整体历史记录的值：

- 距首次购买间隔的天数。
- 原始登入页面或移动设备应用程序主屏幕。
- 原始反向链接域名。

### 会话容器

通过会话容器可以识别页面交互或移动设备应用程序交互、促销活动或特定会话的转化。 会话容器是最常使用的容器，因为每当符合规则，会话容器就会捕获整个会话的行为。 通过会话容器，还可定义在生成和应用过滤器时要包含或排除的会话。  当您使用简单条件（如`Page Name equals Checkout`）定义过滤器时，会话容器解析为：

- 访问名为`Checkout`的页面的所有会话。
- 这些会话的所有事件数据。

会话容器可以帮助您回答以下问题：

- 有多少场会议同时涉及网络和呼叫中心数据源？
- 哪些页面有助于成功转化为销售？

会话容器包含的值以每个会话的事件为基础：

- 会话类型。
- 进入页面。
- 回访频度。
- 参与率量度。
- 线性分配的指标。

通过Customer Journey Analytics中的数据视图，可决定会话的持续时间，以及应何时创建新会话。 例如，您可以根据用户每次启动您的移动设备应用程序时定义一个新的移动设备应用程序会话。 有关详细信息，请参阅[会话设置](/help/data-views/session-settings.md)。

### 事件容器

事件容器定义要在过滤器中包含或排除的页面、移动应用程序或其他类型事件。 这是可用容器中最窄的一个，可用于识别条件为true的移动应用程序中的特定点击、页面查看、点按按钮的情况。 事件容器允许您查看单个跟踪代码，或隔离移动应用程序特定区域中的行为。 您可能还希望在发生操作时查明特定值，例如下订单时的营销渠道。 当您使用简单条件（如`Page Name equals Checkout`）定义过滤器时，事件容器解析为：

- 页面名称等于`Checkout`的所有页面查看事件。

事件容器包含基于值的单页面划分，用于：

- 产品
- 列表属性
- 列表维度
- 促销维度（在事件上下文中）


### 逻辑组容器

使用逻辑组，您可以将条件分组到单个顺序过滤器检查点中。 作为序列的一部分，在标识为[!UICONTROL 逻辑组]的容器中定义的逻辑将在任何先前顺序检查点之后和任何后续顺序检查点之前进行评估。 有关详细信息，请参阅[逻辑组](seg-sequential-build.md#logic-group)。

### 嵌套容器

在其他容器中创建容器时，您实际上是在过滤器中创建过滤器。 以下逻辑将应用于嵌套容器：

1. 确定使用最外部的容器包含哪些数据。在报表中，任何与此外部规则不匹配的数据都将被丢弃。
2. 将嵌套筛选器定义应用于剩余数据。 嵌套筛选器定义不适用于第一个定义放弃的任何数据。
3. 重复以上操作直到计算完所有嵌套的容器过滤器定义为止。 剩余的数据随后包含在结果中并用于报表。

>[!NOTE]
>
>在筛选器内嵌套筛选器时（例如，将筛选器从“组件”面板拖动到筛选器定义上），将创建一个包含拖动的筛选器定义的副本（而非引用）的容器。

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box filter template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Filter Name | Description |
| --- | --- |
| All Data | All Data is a required filter that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[创建筛选器](create-filters.md)
>[筛选器生成器](filter-builder.md)
>[快速筛选器](quick-filters.md)
>[顺序筛选器](seg-sequential-build.md)
>[管理筛选器](manage-filters.md)
>
