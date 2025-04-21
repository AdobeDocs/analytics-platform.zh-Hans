---
title: 分段概述
description: 了解区段的用途以及如何创建简单区段。
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
role: User
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '1428'
ht-degree: 5%

---


# 分段概述

Customer Journey Analytics允许您生成、管理、共享强大而集中的受众区段，并将其应用于您的报表。 区段允许您根据特性或交互情况识别人员、会话或事件的子集。 区段设计为编码的受众洞察，您可以根据特定需求构建这些区段，然后验证、编辑并与其他团队成员共享。

区段可以基于：

- 属性（浏览器类型、设备、访问次数、国家/地区、性别）、
- 交互（促销活动、关键词搜索、搜索引擎）、
- 退出和登录（来自Facebook、定义的登陆页面、反向链接域、地理围栏事件的人员），
- 自定义变量（表单字段、定义的类别、客户ID）、
- 和其他标准。

有关创建区段的各种可用选项，请参阅[创建区段](/help/components/filters/create-filters.md)。 然后，在[区段生成器](filter-builder.md)中生成、修改和保存区段的定义。 或者，您可以使用[快速区段生成器](quick-filters.md)创建快速区段。 此外，您还可以从Workspace中的可视化图表生成区段，例如使用[流失](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu)可视化图表。

您使用[区段管理器](manage-filters.md)管理区段。

## 计划区段

尤其是作为管理员，正确规划区段可以提高区段被使用的可能性。 规划区段时，请考虑以下事项：

- **受众**：谁将使用您的区段？ 确保提供准确的区段描述，以便受众了解：
   - 此区段有何用途？

   - 此区段应何时使用？

- **范围**：哪个[区段容器](#filter-containers)最能代表您正在访问的数据？ 尽可能使用最小的容器。

- **组件**：决定区段定义中要包含哪些组件，以及条件应针对哪些值进行验证。

- **流程**：考虑为区段设置审批流程。 Customer Journey Analytics中没有审批工作流，但您仍然可以组织流程以确定是否审批区段。

- **模块性**：定义考虑模块性的区段。 区段的用户应该能够轻松[栈叠区段](filter-builder.md#stack-filters)以创建强大的新区段。


## 区段类型

您可以创建三种类型的区段：

### 快速区段

快速区段允许您在给定的Workspace项目中轻松浏览数据，而无需在[区段生成器](/help/components/filters/create-filters.md)中创建区段。 可直接在Workspace界面中定义区段。 有关详细信息，请参阅[快速区段](quick-filters.md)。

### 常规区段

常规区段允许您根据一个或多个条件识别数据（人员、会话、事件）。 如果您有多个条件，则可以使用逻辑运算符（如And和Or）来进一步定义区段。 您可以使用容器对条件进行分组并构建更复杂的区段。 有关详细信息，请参阅[区段生成器](filter-builder.md)。

### 顺序区段

>[!IMPORTANT]
>
>您必须具有&#x200B;**Select**&#x200B;包才能创建跨渠道顺序区段。 如果您不确定您拥有的是哪个 Customer Journey Analytics 包，请联系您的管理员。

通过顺序区段，您可以根据导航（网站中的页面查看次数、与移动应用程序中场景的交互或使用机顶盒上的菜单）识别数据（人员、会话、事件）。 顺序区段可帮助您识别某个人喜欢和避开的内容。 可以使用Then逻辑运算符定义顺序区段。 有关详细信息，请参阅[顺序区段](seg-sequential-build.md)。


<!--
An example of a complex sequential segment if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## 区段容器 {#containers}

区段基于人员、会话和事件级别的层次结构，并采用嵌套容器模型。 利用嵌套的容器，可定义容器之间和容器内的条件。


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

区段设置条件以根据条件划分人员、会话或事件。 例如，将人员划分的条件基于人员特征和导航特征。 要进一步划分数据，您可以按特定会话、页面查看事件、屏幕点击、机顶盒上的菜单选项等划分数据。 您还可以根据从CRM或忠诚度系统中摄取的属性进行分段。 [区段生成器](/help/components/filters/filter-builder.md)提供了一个简单的界面来生成这些子集，并在嵌套的分层“人员”、“会话”或“事件”容器中应用条件。

[区段生成器](/help/components/filters/filter-builder.md)中使用的容器架构将“人员”定义为最外部的容器。 此容器包含特定于人员的总体数据，该数据在机顶盒上的会话和事件（如页面查看、移动应用程序屏幕或菜单屏幕）之间有效。 通过嵌套的“会话”容器，可设置规则以根据会话划分人员数据。 通过嵌套的事件容器，可根据各个交互划分人员信息。 通过每个容器，可跨人员的历史记录和按会话划分的交互进行报告，或者对各个事件进行划分。

### 人员容器

人员容器包括符合容器中指定条件的人员的每个会话和每个事件。 当您使用简单条件（如`Page Name equals Checkout`）定义区段时，人员容器解析为：

- 所有访问过名为`Checkout`的页面的人员。
- 所有这些人员的会议。
- 这些人员的所有事件数据。

作为定义最广泛的容器，在人员容器级别生成的报表将返回适用于所有符合区段条件的人员的事件和会话。 根据定义的日期范围，人员容器是最容易更改的。
人员容器可以包含基于人员整体历史记录的值：

- 距首次购买间隔的天数。
- 原始登入页面或移动设备应用程序主屏幕。
- 原始反向链接域名。

### 会话容器

通过会话容器可以识别页面交互或移动设备应用程序交互、促销活动或特定会话的转化。 会话容器是最常使用的容器，因为每当符合规则，会话容器就会捕获整个会话的行为。 通过会话容器，还可定义在生成和应用区段时要包含或排除的会话。  当您使用简单条件（如`Page Name equals Checkout`）定义区段时，会话容器解析为：

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

事件容器定义要在区段中包含或排除的页面、移动应用程序或其他类型的事件。 这是可用容器中最窄的。 在条件为true的移动应用程序中，通过此选项可识别特定的点击、页面查看和点击按钮。 事件容器允许您查看单个跟踪代码，或隔离移动应用程序特定区域中的行为。 您可能还希望在发生操作时查明特定值，例如下订单时的营销渠道。 当您使用简单条件（如`Page Name equals Checkout`）定义区段时，事件容器解析为：

- 页面名称等于`Checkout`的所有页面查看事件。

事件容器包含基于值的单页面划分，用于：

- 产品
- 列表属性
- 列表维度
- 促销维度（在事件上下文中）


### 逻辑组容器

通过逻辑组，您可以将条件分组到单个顺序区段检查点中。 作为序列的一部分，在标识为[!UICONTROL 逻辑组]的容器中定义的逻辑将在任何先前顺序检查点之后和任何后续顺序检查点之前进行评估。 有关详细信息，请参阅[逻辑组](seg-sequential-build.md#logic-group)。

### 嵌套容器

在其他容器中创建容器时，您实际上是在区段中创建区段。 以下逻辑将应用于嵌套容器：

1. 确定使用最外部的容器包含哪些数据。在报表中，任何与此外部规则不匹配的数据都将被丢弃。
2. 将嵌套区段定义应用于其余数据。 嵌套区段定义不适用于第一个定义放弃的任何数据。
3. 重复执行上述操作，直到所有嵌套容器区段定义均已计算完毕。 剩余的数据随后包含在结果中并用于报表。

>[!NOTE]
>
>在区段内嵌套区段时（例如，将区段从“组件”面板拖动到区段定义上），将创建一个包含拖动区段定义的副本（而非引用）的容器。

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
>[创建区段](create-filters.md)
>[区段生成器](filter-builder.md)
>[快速区段](quick-filters.md)
>[顺序区段](seg-sequential-build.md)
>[管理区段](manage-filters.md)
>
