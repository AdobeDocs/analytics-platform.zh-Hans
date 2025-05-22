---
source-git-commit: c936ebbc191353d9993cc3c56892df3f29a1a1df
workflow-type: tm+mt
source-wordcount: '5163'
ht-degree: 89%

---
# 片段

## 发布的有限测试阶段 {#release-limited-testing}

>[!AVAILABILITY]
>
>本文中描述的功能处于发布的有限测试阶段，因此可能在您的环境中尚不可用。当该功能正式发布时，将删除此说明。有关 Customer Journey Analytics 发布流程的信息，请参阅 [Customer Journey Analytics 功能版本](/help/release-notes/releases.md)。

## 发布的有限测试阶段部分 {#release-limited-testing-section}

>[!AVAILABILITY]
>
>本部分描述的功能处于发布的有限测试阶段，因此可能在您的环境中尚不可用。当该功能正式发布时，将删除此说明。有关 Customer Journey Analytics 发布流程的信息，请参阅 [Customer Journey Analytics 功能版本](/help/release-notes/releases.md)。

## Select 包 {#select-package}

>[!NOTE]
>
>您必须拥有 **Select** 包或更高版本才能使用本节中描述的功能。如果您不确定您拥有的是哪个 Customer Journey Analytics 包，请联系您的管理员。

## Prime 包 {#prime-package}

>[!NOTE]
>
>您必须拥有 **Prime** 包或更高版本才能使用本节中描述的功能。如果您不确定您拥有的是哪个 Customer Journey Analytics 包，请联系您的管理员。

## Ultimate 包 {#ultimate-package}

>[!NOTE]
>
>您必须拥有 **Ultimate** 包或更高版本才能使用本节中描述的功能。如果您不确定您拥有的是哪个 Customer Journey Analytics 包，请联系您的管理员。

## 组件排序选项 {#components-sort-options}

| 选项 | 功能 |
|---------|----------|
| **[!UICONTROL 建议]** | 根据其推荐对每种类型（维度、量度、区段和日期范围）的组件进行排序。您或您组织中的其他人最常用和最近使用过的组件显示在每个列表的靠前位置。 |
| **[!UICONTROL 上次修改时间]** | 根据上次修改日期对每种类型（维度、量度、区段和日期范围）的组件进行排序。最近更改过的组件显示在每个列表的靠前位置。 |
| **[!UICONTROL 按字母顺序]** | 按字母升序对每种类型（维度、量度、区段和日期范围）的组件进行排序。 |
| **[!UICONTROL 分类]** | 根据其类别对每种类型（维度、量度、区段和日期范围）的组件进行排序。例如，策划的与非策划的数据视图组件。 |

{style="table-layout:auto"}

## 时间比较 {#apply-time-comparison}

您可以将当前时段与之前的时段进行比较。如果您在此菜单中选择一个选项，每个数据点就都会收到一个相似颜色虚线的对应项。此对应项代表了选定的先前日期范围内的相同量度。设置此选项后，图表上的项数和表格中的行数都将加倍。

可用的时间比较选项包括前一个时段、13 周前、52 周前以及自定义日期范围。如果您选择自定义日期范围，就会出现其他选项供您选择数量和粒度。如果选择“无”，就会删除日期比较。


## 视频演示 Adobe Analytics {#videoaa}

*该视频演示了使用 Adobe Analytics 的功能。然而，该功能在 Customer Journey Analytics 中同样可用。请注意 Adobe Analytics 和 Customer Journey Analytics 之间的术语差异（例如“访问”与“会话”）。*


## 标记过滤器部分 {#tagfiltersection}

| 标记 | 描述 |
|---|---|
| ![标记](/help/assets/filter-tag.png){width="300"} | 您可以使用&#x200B;**[!UICONTROL 标记]**&#x200B;部分按标记进行过滤。 <ul><li>您可以![搜索](/help/assets/icons/Search.svg) *搜索标记*&#x200B;来搜索可以用于过滤的标记。</li><li>您可以选择多个标记。可用的标记取决于在过滤器面板中对其他部分的选择。</li><li>这些数字表明：<ul><li>**(1)**：选定标记的数量（如果选择了一个或多个标记）。</li><li>**2︎⃣**：当前过滤器产生的项目可用的标记数量。</li><li>7︎⃣：与特定标记相关的项目数量。</li></ul></li></ul> |


## 数据视图过滤器部分 {#dataviewfiltersection}

| 数据视图 | 描述 |
|---|---|
| ![数据视图](/help/assets/filter-dataview.png){width="300"} | 您可以使用&#x200B;**[!UICONTROL 数据视图]**&#x200B;部分按数据视图进行过滤。 <ul><li>您可以![搜索](/help/assets/icons/Search.svg) *搜索数据视图*&#x200B;来搜索可以用于过滤的数据视图。</li><li>您可以选择多个数据视图。可用的数据视图取决于在过滤器面板中对其他部分的选择。</li><li>这些数字表明：<ul><li>**(2)**：选定数据视图的数量（如果选择了一个或多个数据视图）。</li><li>**3︎⃣**：当前过滤器产生的项目可用的数据视图数量。</li><li>4︎⃣：与特定数据视图相关的项目数量。</li></ul></li></ul> |

## 已启用状态过滤器部分 {#enabledstatusfiltersection}

| 已启用状态 | 描述 |
|---|---|
| ![已启用状态](/help/assets/filter-enabledstatus.png){width="300"} | 您可以使用&#x200B;**[!UICONTROL 已启用状态]**&#x200B;部分按已启用状态进行过滤。 <ul><li>您可以选择多个状态。</li><li>这些数字表明：<ul><li>**(2)**：选定状态的数量（如果选择了一个或多个状态）。</li><li>**2︎⃣**：当前过滤器产生的项目可用的状态数量。</li><li>1︎⃣：与特定状态相关的项目数量。</li></ul></li></ul> |

## 类型过滤器部分 {#typefiltersection}

| 类型 | 描述 |
|---|---|
| ![Type](/help/assets/filter-type.png){width="300"} | 您可以使用&#x200B;**[!UICONTROL 类型]**&#x200B;部分按类型进行过滤。 <ul><li>您可以选择多个类型。</li><li>这些数字表明：<ul><li>**(2)**：选定类型的数量（如果选择了一个或多个类型）。</li><li>**1︎⃣**：当前过滤器产生的项目可用的类型数量。</li><li>3︎⃣：与特定类型相关的项目数量。</li></ul></li></ul> |

## 所有者过滤器部分 {#ownerfiltersection}

| 所有者 | 描述 |
|---|---|
| ![所有者](/help/assets/filter-owners.png){width="300"} | 您可以使用&#x200B;**[!UICONTROL 所有者]**&#x200B;部分按所有者进行过滤。 <ul><li>您可以![搜索](/help/assets/icons/Search.svg) *搜索所有者*&#x200B;来搜索可以用于过滤的所有者。</li><li>您可以选择多个所有者。可用的所有者取决于在过滤器面板中对其他部分的选择。</li><li>这些数字表明：<ul><li>**(2)**：选定所有者的数量（如果选择了一个或多个所有者）。</li><li>**3︎⃣**：当前过滤器产生的项目可用的所有者数量。</li><li>4︎⃣：与特定所有者相关的项目数量。</li></ul></li></ul> |

## 其他过滤器过滤器部分 {#otherfiltersfiltersection}

| 其他过滤器 | 描述 |
|---|---|
| ![其他过滤器](/help/assets/filter-other.png){width="300"} | 您可以使用&#x200B;**[!UICONTROL 其他过滤器]**&#x200B;部分按其他预定义过滤器进行过滤。<ul><li>您可以选择以下一个或多个选项：<ul><li> **[!UICONTROL 显示所有]**</li><li>**[!UICONTROL 与我共享]**</li><li>**[!UICONTROL 我的]**</li><li>**[!UICONTROL 已批准]**</li><li>**[!UICONTROL 收藏夹]**</li></ul> 您可以选择的内容取决于您的角色和权限。</li><li>您可以选择多个其他过滤器。可用的其他过滤器取决于在过滤器面板中对其他部分的选择。</li><li>这些数字表明：<ul><li>**(1)**：选定其他过滤器的数量（如果选择了一个或多个其他过滤器）。</li><li>**5︎⃣**：当前过滤器产生的项目可用的其他过滤器数量。</li><li>4︎⃣：与特定的其他过滤器相关的项目数量。</li></ul></li></ul> |

## 日期范围过滤器部分  {#daterangefiltersection}

| 应用的日期范围 | 描述 |
|---|---|
| ![日期范围](/help/assets/filter-daterange.png){width="300"} | 您可以使用应用的日期范围部分按适用于项目的日期范围进行过滤。<ol><li>选择日期范围。</li><li>在日程表弹出窗口中定义一个日期范围，或选择一个可用的预设。<br>或者，您也可以直接在过滤器面板的日期范围部分指定一个日期范围。</li></ol><ul><li>这些数字表明：<ul><li>**(1)**：对默认预设更改后已更改日期范围的数量。</li><li>**5︎⃣**：当前过滤器产生的项目可用的日期范围数量。</li></ul> |


## 归因模型 {#attribution-models-details}

当某个量度的回顾窗口内出现多个值时，归因模型决定了哪些维度项获得量度的点数。只有在回顾窗口中设置了多个维度项的情况下，归因模型才适用。如果只设置了一个维度项，无论使用哪种归因模型，该维度项都会获得 100% 的点数。

| 图标 | 归因模型 | 定义 |
| :---: | :--- | --- |
| ![最后接触](/help/assets/icons/AttributeLastTouch.svg) | 最后接触 | 100% 归因于转化前最近发生的接触点。对于未另行指定归因模型的任何量度，此归因模型通常是默认值。组织通常在转化时间相对较短的情况下使用此模型，例如用于分析内部搜索关键字。 |
| ![首次接触](/help/assets/icons/AttributeFirstTouch.svg) | 首次接触 | 将 100% 的点数分配给归因回顾窗口中首次看到的接触点。组织通常使用此模型来了解品牌意识或客户获取。 |
| ![线性](/help/assets/icons/AttributeLinear.svg) | 线性 | 将点数平分给促成转化的每个接触点。当转化周期较长或需要更频繁的客户参与时，这个模型就很有用。组织通常使用此归因模型来衡量移动应用程序通知的有效性或用于基于订阅的产品。 |
| ![参与率](/help/assets/icons/AttributeParticipation.svg) | 参与率 | 将 100% 的点数分给所有独特的接触点。由于每个接触点都获得 100% 的点数，因此量度数据加起来通常会超过 100%。如果某个维度项多次出现而促成了转化，就会删除重复的值，直至 100%。如果您想要了解客户接触最多的接触点，此归因模型是理想的选择。媒体组织通常使用此模型来计算内容速度。零售组织通常使用此模型来了解其网站的哪些部分对于转化至关重要。 |
| ![同一接触](/help/assets/icons/AttributeSameTouch.svg) | 同一接触 | 100% 归因于发生转化的同一个事件。如果接触点没有在相同的事件上发生转化，它就被归类为“无”。这种归因模型有时相当于根本没有归因模型。如果您不希望来自其他事件的值影响一个量度如何给维度项分配点数，这种模型就很有价值。产品或设计团队可以使用此模型来对发生转化的页面的有效性进行评估。 |
| ![U 型](/help/assets/icons/AttributeUShaped.svg) | U 型 | 将 40% 的点数分给首次交互，40% 的点数分给最后交互，并将剩余 20% 的点数分给这两次交互之间的任意接触点。对于具有单一接触点的转化，它将分得 100% 的点数。对于有两个接触点的转化，这两个接触点各占 50% 的点数。这种归因模型最适合用于您最重视第一次和最后一次互动，同时又不想完全忽视这期间其他互动的情况。 |
| ![J 曲线](/help/assets/icons/AttributeJCurve.svg) | J 曲线 | 将 60% 的点数分给最后一次交互，20% 的点数分给首次交互，并将剩余 20% 的点数分给这两次交互之间的任意接触点。对于具有单一接触点的转化，它将分得 100% 的点数。对于有两个接触点的转化，最后一次互动占 75% 的点数，首次互动占 25% 的点数。与 U 型类似，此归因模型倾向于第一次和最后一次互动，但更大程度上倾向于最后一次互动。 |
| ![反向 J](/help/assets/icons/AttributeInverseJ.svg) | 反向 J | 将 60% 的点数分给首次接触点，20% 的点数分给最后接触点，并将剩余 20% 的点数分给这两次接触点之间的任意接触点。对于具有单一接触点的转化，它将分得 100% 的点数。对于有两个接触点的转化，第一次互动占 75% 的点数，最后一次互动占 25% 的点数。与 J 型类似，此归因模型倾向于第一次和最后一次互动，但更大程度上倾向于第一次互动。 |
| ![时间衰减](/help/assets/icons/AttributeTimeDecay.svg) | 时间衰减 | 采用具有自定义半衰期参数的指数衰减，默认值为 7 天。每个渠道的权重，取决于在接触点启动与最终转化之间流逝的时间。用于确定点数的公式是 `2^(-t/halflife)`，其中 `t` 是接触点与转化之间流逝的时间。然后，所有接触点均被标准化为 100%。非常适合您想要根据特定的重要事件衡量归因的情况。此事件后发生转化所需的时间越长，所占点数就越少。 |
| ![自定义](/help/assets/icons/AttributeCustom.svg) | 自定义 | 您可以指定要赋予“首次接触点”、“最后接触点”以及“这两次互动之间的任意接触点”的权重。即便输入的自定义数字相加之和并不等于 100，指定的值也会被标准化为 100%。对于具有单一接触点的转化，它将分得 100% 的点数。对于具有两个接触点的交互，中间参数会被忽略。然后，首次接触点和最后接触点会被标准化为 100%，并相应地分配点数。此模型非常适合那些希望完全控制其归因模型，并具有其他归因模型不能满足的特定需求的分析者。 |
| ![算法](/help/assets/icons/AttributeAlgorithmic.svg) | 算法 | 使用统计技巧，动态确定所选量度的最佳点数分配。归因算法基于合作博弈理论中的 Harsanyi Dividend 算法。Harsanyi Dividend 算法是对“沙普利值”解决方案（以诺贝尔经济学奖获得者罗伊德·沙普利 (Lloyd Shapley) 命名）的推广形式，用于为对结果具有不同贡献的各参与者分配功能值（点数）。<br>从一个较高的层面来看，归因通过参与者联盟的方法计算，剩余值必须公平地分配给这些参与者。每个联盟的剩余值分配都根据每个子联盟（或先前参与的维度项）先前产生的剩余值通过循环计算得出。有关更多详细信息，请参阅约翰·海萨尼 (John Harsanyi) 和罗伊德·沙普利（Lloyd Shapley）的原文：<br>Lloyd Shapley S. (1953)。A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## 归因回顾窗口 {#attribution-lookback-window}

回顾窗口是指转化应回顾以包含接触点所花费的时间。如果一个维度项设置在回顾窗口之外，该值就不包含在任何归因计算中。

* **14 天**：自转化发生后最多回顾 14 天。
* **30 天**：自转化发生后最多回顾 30 天。
* **60 天**：自转化发生后最多回顾 60 天。
* **90 天**：自转化发生后最多回顾 90 天。
* **13 个月** [!BADGE B2B Edition]{type=Informative}：自转化发生后最多回顾 13 个月。
* **会话**：回顾到发生转化的会话开始时间。会话回顾窗口遵循数据视图中被更改的[会话超时](/help/data-views/create-dataview.md#session-settings)。
* **人员（报告窗口）**：回顾直到当前日期范围当月 1 日的所有访问。例如，如果报告日期范围为 9 月 15 日到 9 月 30 日，人员回顾日期范围就是 9 月 1 日到 9 月 30 日。如果您使用此回顾窗口，您偶尔会看到维度项被归因于报告窗口之外的日期。
* **全局帐户（报告窗口）** [!BADGE B2B Edition]{type=Informative}：回顾直到当前日期范围当月 1 日的所有全局帐户。例如，如果报告日期范围为 9 月 15 日到 9 月 30 日，全局帐户回顾日期范围就是 9 月 1 日到 9 月 30 日。如果您使用此回顾窗口，您偶尔会看到维度项被归因于报告窗口之外的日期。
* **帐户（报告窗口）** [!BADGE B2B Edition]{type=Informative}：回顾直到当前日期范围当月 1 日的所有帐户。例如，如果报告日期范围为 9 月 15 日到 9 月 30 日，帐户日期范围就是 9 月 1 日到 9 月 30 日。如果您使用此回顾窗口，您偶尔会看到维度项被归因于报告窗口之外的日期。
* **机会（报告窗口）** [!BADGE B2B Edition]{type=Informative}：回顾直到当前日期范围当月 1 日的所有机会。例如，如果报告日期范围为 9 月 15 日到 9 月 30 日，机会回顾日期范围就是 9 月 1 日到 9 月 30 日。如果您使用此回顾窗口，您偶尔会看到维度项被归因于报告窗口之外的日期。
* **购买群组（报告窗口）** [!BADGE B2B Edition]{type=Informative}：回顾直到当前日期范围当月 1 日的所有购买群组。例如，如果报告日期范围为 9 月 15 日到 9 月 30 日，购买群组回顾日期范围就是 9 月 1 日到 9 月 30 日。如果您使用此回顾窗口，您偶尔会看到维度项被归因于报告窗口之外的日期。
* **自定义时间：**&#x200B;您可以设置一个转换发生后的自定义回顾窗口。您可以指定分钟数、小时数、天数、周数、月数或季度数。例如，如果转化发生在 2 月 20 日，五天回顾窗口就会在归因模型中评估从 2 月 15 日到 2 月 20 日的所有维度接触点。

## 归因举例   {#attribution-example}

请仔细研究下面的示例：

1. 9 月 15 日，某位人员通过付费搜索广告访问您的网站，然后离开。
1. 9 月 18 日，该人员通过朋友提供的社交媒体链接再次访问您的网站。他将多个物品添加到购物车，但没有购买任何物品。
1. 9 月 24 日，您的营销团队向他们发送一封电子邮件，其中包含购物车中某些物品的产品建议券。他应用了产品建议券，但访问了其他几个网站，查看是否有其他产品建议券可用。他通过展示广告找到另一个网站，并最终购买了价值 50 美元的物品。

根据您的回顾窗口和归因模型，渠道会收到不同比例的点数。以下是一些示例：

* 使用&#x200B;**首次接触**&#x200B;和&#x200B;**会话回顾窗口**&#x200B;时，归因功能仅会考虑第三次访问。在电子邮件与展示广告之间，电子邮件是首次接触点，因此电子邮件在 50 美元的购买中获得 100% 的点数。

* 使用&#x200B;**首次接触**&#x200B;和&#x200B;**人员回顾窗口**&#x200B;时，归因功能会考虑所有三次访问。付费搜索是首次接触点，因此它在 50 美元的购买中获得 100% 的点数。

* 使用&#x200B;**线性归因模型**&#x200B;和&#x200B;**会话回顾窗口**&#x200B;时，电子邮件与展示广告平分点数。这两个渠道各自获得贡献 25 美元的点数。使用&#x200B;**线性归因模型**&#x200B;和&#x200B;**人员回顾窗口**&#x200B;时，付费搜索、社交媒体、电子邮件与展示广告平分点数。每个渠道各自获得此次购买中贡献 12.50 美元的点数。

* 使用 **J 形归因模型**&#x200B;和&#x200B;**人员回顾窗口**&#x200B;时，付费搜索、社交媒体、电子邮件和展示广告均可获得点数。

   * 将 60% 的点数分给展示广告，其贡献价值是 30 美元。
   * 将 20% 的点数分给付费搜索，贡献价值是 10 美元。
   * 剩余的 20% 点数分给社交和电子邮件，二者的贡献价值均为 5 美元。

* 使用&#x200B;**时间衰减归因模型**&#x200B;和&#x200B;**人员回顾窗口**&#x200B;时，付费搜索、社交媒体、电子邮件和展示广告均可获得点数。使用默认的 7 天半衰期：

   * 展示广告接触点与转化之间的间隔为 0 天。`2^(-0/7) = 1`
   * 电子邮件接触点与转化之间的间隔为 0 天。`2^(-0/7) = 1`
   * 社交媒体接触点与转化之间的间隔为 6 天。`2^(-6/7) = 0.552`
   * 付费搜索接触点与转化之间的间隔为 9 天。`2^(-9/7) = 0.41`
   * 将这些值标准化处理之后得到以下结果：

      * 展示广告：33.8%，贡献价值是 16.88 美元
      * 电子邮件：33.8%，贡献价值是 16.88 美元
      * 社交：18.6%，贡献价值是 9.32 美元
      * 付费搜索：13.8%，贡献价值是 6.92 美元

如果点数归属于多个渠道，则通常具有整数个点数的转化事件会被拆分。例如，如果使用线性归因模型计算订单归因，并且两个渠道都对该订单有贡献，则这两个渠道将分别获得该订单 50% 的点数。这些部分量度会针对所有人进行汇总，然后四舍五入到最接近的整数以供报告。

## 历程可视化图表比较 {#journey-visualization-comparisons}

Customer Journey analytics 中的各种可视化图表旨在分析您为客户提供的各历程。

使用以下信息来选择最符合您需求的可视化图表。

| 功能 | 历程画布 | 流失 | 流量 |
|---------|----------|---------|---------|
| **页面预定义序列** | 是</br>预定义分析和探索性分析相结合。使用路径上的预定义节点时会使用最终路径（只要访客最终从一个预定义节点移动到另一个预定义节点，就会被计算在内）。还可以通过[基于现有节点显示顶部节点](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#show-the-top-nodes-based-on-existing-nodes)来显示紧邻的（而非最终的）下一个节点。 | 是</br>路径可以是最终路径，也可以被限制到下一个接触点 | 否 |
| **页面探索序列（临时分析）** | 是</br>预定义分析和探索性分析相结合。使用路径上的预定义节点时会使用最终路径（只要访客最终从一个预定义节点移动到另一个预定义节点，就会被计算在内）。还可以通过[基于现有节点显示顶部节点](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#show-the-top-nodes-based-on-existing-nodes)来显示紧邻的（而非最终的）下一个节点。 | 有限</br>您可以单击右键，在自由格式表中查看立即流失。 | 是</br>仅探索性分析。始终在节点之间的一个维度实例内。这意味着每个节点都显示路径上紧邻的（而非最终的）下一个接触点。 |
| **显示人们离开（流失）和继续通过（流过）的位置** | 是</br>显示预定义历程和探索性历程。 | 是</br>显示预定义历程 | 是</br>显示探索性历程 |
| **线性历程** | 是 | 是 | 否 |
| **具有多个入口点和路径的非线性历程** | 是 | 否 | 是 |
| **主要量度** | 任何量度，包括计算量度。 | 仅会话或人员 | 仅发生次数（路径视图） |
| **辅助量度** | 是<p>任何量度，包括计算量度。</p> | 否 | 否 |
| **节点或接触点中的组件支持** | 量度、维度项、区段和日期范围。 | 量度、维度项、区段和日期范围。 | 仅维度项（起始和结束接触点除外） |
| **比较区段** | 否 | 是<p>对同一个报告中的两个不同区段执行逐项比较。</p> | 否 |
| **拖放组件互动** | 是 | 是 | 否 |
| **Adobe Journey Optimizer 历程** | 是</br>从 Journey Optimizer 打开历程以进行更深入的分析和定制。 | 否 | 否 |

{style="table-layout:auto"}

## 升级清单说明 {#upgrade-note}

>[!NOTE]
> 
>回答 Customer Journey Analytics 升级指南中的问题时，请使用本页上的信息。<br><br>要从 Customer Journey Analytics 访问该指南，请选择&#x200B;**[!UICONTROL 工作区]**&#x200B;选项卡，然后在左侧面板中选择&#x200B;**[!UICONTROL 升级到 Customer Journey Analytics]**。按照屏幕上的说明操作。

## 升级清单说明后续步骤 {#upgrade-note-step}

>[!NOTE]
> 
>仅完成所有先前的升级步骤后，才可按照此页面上的步骤操作。您可以遵循推荐的升级步骤（建议大多数组织使用），也可以按照 Customer Journey Analytics 升级指南为您的组织动态生成的升级步骤进行操作。 <ul><li>**推荐的升级步骤**（建议大多数组织使用）<p>确保理想实施 Customer Journey Analytics 的一系列步骤。</p><p>有关详细信息，请参阅[从 Adobe Analytics 升级到 Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。</p></li><li>**Customer Journey Analytics 升级指南**（根据您组织的具体需求定制的步骤）<p>现有新的升级指南可用，用于动态生成适合您的组织和独特情况的升级步骤。</p><p>要从 Customer Journey Analytics 访问升级指南，请选择&#x200B;**[!UICONTROL 工作区]**&#x200B;选项卡，然后在左侧面板中选择&#x200B;**[!UICONTROL 升级到 Customer Journey Analytics]**。按照屏幕上的说明操作。</p></li></ul>

## 升级清单最后一步 {#upgrade-final-step}

1. 继续遵循[推荐的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或 Customer Journey Analytics 升级指南动态生成的升级步骤。要从 Customer Journey Analytics 访问升级指南，请选择&#x200B;**[!UICONTROL 工作区]**&#x200B;选项卡，然后在左侧面板中选择&#x200B;**[!UICONTROL 升级到 Customer Journey Analytics]**。按照屏幕上的说明操作。


## 草稿 Content Analytics 文档 {#draft-aca}

>[!WARNING]
>
>本文是草稿 Content Analytics 文档的一部分。所有草稿 Content Analytics 文档仍可能发生变化，本文的当前版本或 Content Analytics 文档中的任何其他文章均不产生任何法律义务。
>


## 草稿 Customer Journey Analytics B2B Edition 文档 {#draft-b2b}

>[!AVAILABILITY]
>
>本文中描述的功能以及任何其他带有[!BADGE B2B Edition]{type=Informative}标记的文章或功能均处于发布的有限测试阶段，在您的环境中可能尚未提供。<br/>此外，[!BADGE B2B Edition]{type=Informative}功能以及[!BADGE B2B Edition]{type=Informative}功能的文档可能会发生变化，由此不产生任何法律义务。<br/>当该功能正式发布时，将删除此说明。有关 Customer Journey Analytics 发布流程的信息，请参阅 [Customer Journey Analytics 功能版本](/help/release-notes/releases.md)。
>


## B2B Edition {#b2b-edition}

>[!INFO]
>
>在本文档中，仅通过 Customer Journey Analytics B2B Edition 提供的特定 B2B 文章或功能都标有[!BADGE B2B Edition]{type=Informative}。


## 常用数据集设置 {#common-dataset-settings}

| 设置 | 描述 |
|---|---|
| **[!UICONTROL 导入新数据]** | 如果您想建立持续连接，请启用此选项。通过持续的连接，添加到数据集的新数据批次会自动在工作区中提供。 |
| **[!UICONTROL 数据集回填]** | 启用&#x200B;**[!UICONTROL 回填所有现有数据]**&#x200B;以确保所有现有数据均已回填。<br/><br/>选择&#x200B;**[!UICONTROL 请求补填]**&#x200B;填充特定时期的历史数据。您最多可以定义 10 个数据集回填期。<ol><li>通过输入开始和结束数据或使用![日程表](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)选择日期来定义期间。</li><li>选择&#x200B;**[!UICONTROL 队列补填]**&#x200B;将回填内容添加到列表中，或&#x200B;**[!UICONTROL 取消]**&#x200B;取消。</li></ol>对于每个条目，选择 ![编辑](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) 编辑时段，或选择 ![删除](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg) 删除该条目。<br/><br/>在回填上：<ul><li>您可以单独回填每个数据集。</li><li>您会优先处理新添加到此连接中数据集的新数据，因此这些新数据的滞后时间最短。</li><li>任何回填（历史）数据的导入速度都会比较慢。历史数据的数量会影响延迟。</li><li>Analytics Source Connector 会为生产沙盒导入最多 13 个月的数据（无论大小）。非生产沙盒的回填期限为 3 个月。</li></ul> |
| **[!UICONTROL 批次状态]** | 可能的状态指示符有：<ul><li>成功</li><li>X 回填处理</li><li>关</li></ul> |
| **[!UICONTROL 数据集 ID]** | 此 ID 是自动生成的。 |
| **[!UICONTROL 描述]** | 创建数据集时给出的关于此数据集的描述。 |
| **[!UICONTROL 记录数]** | 数据集的大小。 |
| **[!UICONTROL 架构]** | 在 Adobe Experience Platform 中创建数据集所依据的架构。 |
| **[!UICONTROL 数据集]** | 数据集的名称。 |
| **[!UICONTROL 预览：*数据集名称&#x200B;*]** | 预览数据集的前 10 行和前 10 列。 |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL 移除]** | 您可以[删除数据集](/help/connections/create-connection.md#delete-a-dataset)而不必删除整个连接。从一个连接删除数据集可降低数据摄取以及重新创建整个连接和相关数据视图这一繁琐过程所涉及的成本。 |

## 标准维度 {#standard-dimensions}

| 组件名称 | 注释 |
|---|---|
| 15 分钟 | 发生给定事件的每15分钟（已向下取整）。 第一个维度项目是日期范围内的前15分钟，最后一个维度项目是日期范围内的最后15分钟。 |
| 30 分钟 | 发生给定事件的每30分钟（已向下取整）。 第一个维度项目是日期范围内的前30分钟，最后一个维度项目是日期范围内的最后30分钟。 |
| 5 分钟 | 发生给定事件的每5分钟（已向下取整）。 第一个维度项目是日期范围内的前15分钟，最后一个维度项目是日期范围内的最后5分钟。 |
| [!UICONTROL 日] | 发生给定事件的那一天。第一个维度项是日期范围内的第一天，最后一个维度项是日期范围内的最后一天。 |
| [!UICONTROL 每周时间] | 发生给定事件的那一周。 第一个维度项是日期范围内一周的第一天，最后一个维度项是日期范围内一周的最后一天。 |
| [!UICONTROL 日期] | 发生给定事件的那一个月中的第几天。 第一个维度项是日期范围内当月的第一天，最后一个维度项是日期范围内当月的最后一天。 |
| 事件深度 | 将顺序数值（1、2、3等）分配给会话中的每个事件交互。 通过此维度，您可以启用详细跟踪和分析，以跟踪和分析在为数据视图[&#128279;](/help/data-views/session-settings.md#session-settings)定义的受限体验会话中，特定事件在顺序的用户交互流中发生的位置。 您可以跟踪事件在有界会话中从开始到结束的进度。 例如：访客登陆您的主页（事件1，会话开始），使用搜索功能（事件2），查看产品详细信息页面（事件3），添加到购物车（事件4），进入结账（事件5），并完成购买（事件6，会话结束）。 现在，您可以在区段定义中使用[!UICONTROL 事件深度]来根据交互深度划分数据。 |
| [!UICONTROL 小时] | 发生给定事件的那一小时（已向下取整）。第一个维度项是日期范围中的第一小时，最后一个维度项是日期范围中的最后一小时。 |
| [!UICONTROL 小时] | 发生给定事件的那一小时（已向下取整）。 第一个维度项目是日期范围内一天的第一小时，最后一个维度项目是日期范围内一天的最后一小时。 |
| [!UICONTROL 分钟] | 发生给定事件的那一分钟（已向下取整）。第一个维度项是日期范围中的第一分钟，最后一个维度项是日期范围中的最后一分钟。 |
| [!UICONTROL 分钟（小时）] | 发生给定事件的那一分钟（已向下取整）。 第一个维度项目是日期范围内某小时的第一分钟，最后一个维度项目是日期范围内该小时的最后一分钟。 |
| [!UICONTROL 月] | 发生给定事件的那一个月。第一个维度项是日期范围内的第一个月，最后一个维度项是日期范围内的最后一个月。 |
| [!UICONTROL 月份] | 发生给定事件的那一年。 第一个维度项是日期范围内一年的第一个月，最后一个维度项是日期范围内的一年的最后一个月。 |
| [!UICONTROL 季度] | 发生给定事件的那一季。第一个维度项是日期范围内的第一个季度，最后一个维度项是日期范围内的最后一个季度。 |
| [!UICONTROL 季度] | 发生给定事件的那一季。 第一个维度项目是日期范围内一年的第一个季度，最后一个维度项目是日期范围内年的最后一个季度。 |
| [!UICONTROL 秒] | 发生给定事件的那一秒钟（已向下取整）。第一个维度项是日期范围内的第一秒，最后一个维度项是日期范围内的最后一秒。 |
| [!UICONTROL 周] | 发生给定事件的那一周。第一个维度项是日期范围内的第一周，最后一个维度项是日期范围内的最后一周。 |
| [!UICONTROL 一年中一周] | 发生给定事件的那一周。 第一个维度项是日期范围内一年的第一周，最后一个维度项是日期范围内年的最后一周。 |
| [!UICONTROL 年] | 发生给定事件的那一年。第一个维度项是日期范围中的第一年，最后一个维度项是日期范围中的最后一年。 |


## 标准量度 {#standard-metrics}

| 组件名称 | 注释 |
| --- | --- |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 帐户] | 基于在[!UICONTROL 连接]中指定的帐户 ID。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 购买群] | 购买群组，基于在[!UICONTROL 连接]中指定的购买群组 ID。 |
| [!UICONTROL 事件] | 来自[!UICONTROL 连接]中所有事件数据集的行数。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 全局帐户] | 基于在[!UICONTROL 连接]中指定的全球帐户 ID。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 机会] | 机会，基于在[!UICONTROL 连接]中指定的机会 ID。 |
| [!UICONTROL 人员] | 基于在[!UICONTROL 连接]中指定的人员 ID。 |
| [!UICONTROL 会话结束] | 会话的最后一个事件的事件数。与[!UICONTROL 会话开始]类似，它也可用在区段定义中，一直细分到每个会话的最后一个事件。<p>必须将此组件包含在您的数据视图中，才能在 Workspace 中使用[计算量度](/help/components/calc-metrics/default-calcmetrics.md)： <ul><li>会话结束比率</li></p> |
| [!UICONTROL 会话开始] | 会话的第一个事件的事件数。用在区段定义（例如，“[!UICONTROL 会话开始]”）中时，它会一直细分到每个会话的第一个事件。<p>必须将此组件包含在您的数据视图中，才能在 Workspace 中使用[计算量度](/help/components/calc-metrics/default-calcmetrics.md)： <ul><li>会话开始比率</li></p> |
| [!UICONTROL 会话] | 基于数据视图的会话设置。 |
| [!UICONTROL 逗留时间（秒）] | 累计两个不同的维度值之间的时间。<p>必须将此组件包含在您的数据视图中，才能在 Workspace 中使用[计算量度](/help/components/calc-metrics/default-calcmetrics.md)： <ul><li>每人逗留时间</li><li>每个会话逗留时间</li></p> |
