---
title: 过滤器概述
description: 了解过滤器的用途以及如何创建简单的过滤器。
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 23%

---


# 过滤器概述 {#overview}

Customer Journey Analytics 让您可以构建、管理、共享强大集中的受众过滤器，并将这些过滤器应用到您的报表。过滤器让您可以根据用户特征或交互情况来识别用户子集。 过滤器是指正式设计编码的受众洞察，您可以根据自己的特定需求来构建，然后验证、编辑并与其他团队成员共享。

筛选器可以基于

- 属性（浏览器类型、设备、访问次数、国家/地区、性别）、
- 交互（促销活动、关键词搜索、搜索引擎）、
- 退出和登录(来自Facebook、定义的登陆页、反向链接域、地理围栏事件的人员)，
- 自定义变量（表单字段、定义的类别、客户ID）、
- 和其他标准。

您可以在过滤器生成器中构建和保存过滤器，或从“流失”可视化图表（在工作区中）生成过滤器。此外，过滤器可以一起用作堆叠过滤器。

筛选器包括[筛选器生成器](/help/components/filters/filter-builder.md)和[筛选器管理器](/help/components/filters/manage-filters.md)，前者用于构造筛选器并运行预测试，后者用于在您的组织内收集、标记、批准、设置安全和共享筛选器。

每个 IMS 组织可创建的最大过滤器数为 50000。

## 过滤器类型 {#types}

有关可用筛选器类型以及如何创建这些类型的信息，请参阅[创建筛选器](/help/components/filters/create-filters.md)。

## 顺序过滤器 {#sequential}

通过顺序过滤器，您可以根据导航（网站中的页面查看次数、与移动应用程序中场景的交互或使用机顶盒上的菜单）来识别人员。 顺序过滤器提供已定义操作和交互的过滤器，帮助您识别人员喜欢和避开的内容。 生成顺序过滤器时，使用THEN运算符来定义和排序人员导航。

>[!IMPORTANT]
>
>您必须具有&#x200B;**Select**&#x200B;包才能创建跨渠道顺序过滤器。 如果您不确定您拥有哪个Customer Journey Analytics包，请联系您的管理员。

示例如下：

| 会话一 | 第二场会议 | 第三场会议 |
| --- | --- | --- |
| 该人员转到主登陆页面A，排除促销活动页面B，然后查看产品页面C。 | 该人员再次转到主登陆页面A，排除促销活动页面B，再次转到产品页面C，然后转到新页面D。 | 人员进入并按照第一和第二次访问中的相同路径操作，然后排除页面F，直接转到目标产品页面G。 |

## 过滤器容器 {#containers}

过滤器使用嵌套容器模型，并基于人员、会话和事件级别的层次结构。 您可以使用嵌套的容器，根据各容器之间和容器内的规则定义人员属性和操作。


<table style="table-layout: fixed; border: none;">

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
>“人员”容器以前称为“访客”容器。“会话”容器以前称为“访问”容器，“事件”容器以前则称为“点击”容器。

过滤器根据人员的属性或与您的网站、移动设备应用程序或从中收集数据的其他设备类型的交互来设置条件以过滤人员。 要在过滤器中设置条件，您需要设置规则以根据人员特征和/或导航特征来过滤人员。 要进一步划分人员数据，您可以根据每个人员的特定访问和/或页面查看点击、屏幕点击、机顶盒上的菜单选项进行过滤。 但也会根据您从CRM或忠诚度系统中摄取的属性进行过滤。 过滤器生成器提供了一个简单的架构来生成这些子集，并将规则应用为嵌套的分层“人员”、“会话”或“事件”容器。

过滤器生成器中使用的容器架构将“人员”定义为最外部的容器。 容器包含特定于某个人员的总体数据，该数据在机顶盒上的访问和页面查看、移动应用程序屏幕或菜单屏幕之间有效。 通过嵌套的“会话”容器可设置规则来根据会话对人员的数据进行划分，通过嵌套的“事件”容器可根据各个交互对人员信息进行划分。 通过每个容器，可跨人员的历史记录和按会话划分的交互进行报告，或者对各个体验事件进行划分。

### 人员容器 {#person}

人员容器包括指定时间段内人员的每次访问和页面查看、移动设备应用程序屏幕、机顶盒或主机游戏交互。 基本上，每个Experience Event都是您在Customer Journey Analytics连接中定义的数据集的一部分。 人员级别的过滤器会返回符合条件的页面查看次数、移动设备应用程序或机顶盒屏幕。 加上同一人在线上和线下渠道的所有其他交互（且仅受定义的日期范围的约束）。 作为定义最为广泛的容器，在人员容器级别生成的报表可返回跨所有访问的页面查看次数、移动设备应用程序屏幕等，并允许您生成多访问跨渠道分析。 因此，根据定义的日期范围，人员容器是最容易更改的。
人员容器可以包含基于人员整体历史记录的值：

- 首次购买间隔天数
- 原始登录页面或移动设备应用程序主屏幕
- 原始反向链接域名

### 会话容器 {#session}

通过会话容器可以识别页面交互或移动设备应用程序交互、促销活动或特定会话的转化。 会话容器是最常使用的容器，因为每当符合规则，会话容器便会立即捕获整个访问会话的行为。 通过会话容器，还可定义在生成和应用过滤器时要包含或排除的会话。 它可以帮助您回答以下问题：

- 有多少会话同时使用 Web 和呼叫中心数据源？
- 哪些页面有助于成功转化为销售？

会话包含的值以每次会话的发生次数为基础：

- 会话类型
- 登录页面
- 回访频度
- 参与率指标
- 线性分配的指标

通过Customer Journey Analytics中的数据视图，可决定会话的持续时间以及应创建新会话的时间。 例如，您可以根据用户每次启动您的移动设备应用程序时定义一个新的移动设备应用程序会话。 有关详细信息，请参阅[会话设置](/help/data-views/session-settings.md)。

### 事件容器 {#event}

事件容器定义要在过滤器中包含或排除的页面、移动应用程序或其他类型事件。 这是可用容器中最窄的一个，可用于识别条件为true的移动应用程序中的特定点击、页面查看、点按按钮的情况。 事件容器允许您查看单个跟踪代码，或隔离移动应用程序特定区域中的行为。 当出现某个行为时，您也可能需要准确查明某个特定值，比如下订单时的市场营销渠道。

事件容器包含基于值的单页划分，用于：

- 产品
- 列表属性
- 列表维度
- 促销维度（在事件上下文中）

## 现成的过滤器模板 {#template}

传统Analytics提供大量现成的模板和计算量度。 其中许多在Customer Journey Analytics中不适用，或者必须重命名或重新创建。 其他则依赖于Customer Journey Analytics中的上下文感知变量的解决方案。

| 过滤器名称 | 描述 |
| --- | --- |
| 所有数据 | “所有数据”是一个必需过滤器，当有指标添加到自由格式表的行时，即动态地将此过滤器添加到报表。 |
