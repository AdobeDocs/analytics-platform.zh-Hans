---
description: 了解量度类型和归因
title: 量度类型和归因
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 39%

---

# 量度类型和归因

您可以在计算量度定义中配置量度的量度类型和[归因模型](#attribution-models)。

1. 在量度组件中选择![设置](/help/assets/icons/Setting.svg)。
1. 在弹出对话框中：

   ![量度类型和归因](assets/cm-type-alloc.png)

   * 指定&#x200B;**[!UICONTROL 度量类型]**：

     | 指标类型 | 定义 |
     |---|---|
     | **[!UICONTROL 标准]** | 如果公式包含一个标准指标，它会显示与其对应的非计算指标的相同数据。 标准量度可用于创建特定于每个单独行项目的计算量度。 <p>例如，![Event](/help/assets/icons/Event.svg) **[!UICONTROL Orders]** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Sessions]**&#x200B;接受该特定行项的订单，然后除以该特定行项的会话数。 |
     | 总计&#x200B;**[!UICONTROL 个]** | 在每个行项中对报告期间使用&#x200B;**[!UICONTROL 总计]**。 如果公式包含单个总计量度，则计算量度会在每个行项目上显示相同的总计数字。 当您要创建与总数据相比较的计算量度时，“总计”量度非常有用。 <p>例如，![Event](/help/assets/icons/Event.svg) **[!UICONTROL Orders]** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Total Sessions]**&#x200B;显示订单相对于所有会话的比例，而不只是相对于特定行项目的会话。 在此示例中，您为计算量度中的![事件](/help/assets/icons/Event.svg) **[!UICONTROL 会话]**&#x200B;量度指定了&#x200B;**[!UICONTROL 总计]**，这会将其自动转换为![事件](/help/assets/icons/Event.svg) **[!UICONTROL 会话总数]**。 |

   * 指定&#x200B;**[!UICONTROL 归因]**。

      1. 您可以：

         * 禁用&#x200B;**[!UICONTROL 使用非默认归因模型]**&#x200B;以使用回顾时间范围为30天的默认列归因模型，即“最近联系”。
         * 启用&#x200B;**[!UICONTROL 使用非默认归因模型]**。 在&#x200B;**[!UICONTROL 列归因模型]**&#x200B;对话框中，

            * 从归因模型中选择&#x200B;**[!UICONTROL 模型]**。
            * 选择&#x200B;**[!UICONTROL 回顾时间范围]**。 如果选择&#x200B;**[!UICONTROL 自定义时间]**，则可以定义从&#x200B;**[!UICONTROL 分钟]**&#x200B;到&#x200B;**[!UICONTROL 季度]**&#x200B;的时间段。 有关详细信息，请参阅[回顾窗口](#lookback-window)

      1. 选择&#x200B;**[!UICONTROL 应用]**&#x200B;以应用非默认归因模型。 选择“取消”以取消。

     如果已定义非默认归因模型，请选择&#x200B;**[!UICONTROL 编辑]**&#x200B;以修改所选内容。

有关使用归因模型和回顾时间范围的示例，请参阅[示例](#example)。


## 归因 {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="使用非默认的属性模型"
>abstract="为所选量度启用非默认归因模型。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="模型"
>abstract="选择量度的归因模型。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="最后接触"
>abstract="100% 的积分归于访客看到的最后一个维度值。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="首次接触"
>abstract="100% 的积分归于访客看到的第一个维度值。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="线性"
>abstract="积分均匀分布于所有维度值上。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="参与率"
>abstract="100% 的积分归于访客所见的每个维度值。<br/>列总数被夸大了。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="同一接触"
>abstract="仅对与转化发生在同一事件上的维度值给予积分。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="U 型"
>abstract="第一个维度值占 40%，最后一个维度值占 40%，中间维度值占 20%。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="J 曲线"
>abstract="最后一个维度值占 60%，第一个维度值占 20%，中间维度值占 20%。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="反向 J"
>abstract="第一个维度值占 60%，最后一个维度值占 20%，中间维度值占 20%。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="时间衰减"
>abstract="距离转化时间最近的维度值将获得最多的积分。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="自定义"
>abstract="根据归因权重，自行定义您的位置。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="算法"
>abstract="积分是根据统计算法动态确定的。"

<!-- markdownlint-enable MD034 -->


{{attribution-models-details}}


### 回顾时间范围 {#lookback-window}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="回顾时间范围"
>abstract="此设置可以确定将要对每次转化应用的数据归因时间窗口。"

<!-- markdownlint-enable MD034 -->

{{attribution-lookback-window}}


### 归因示例 {#attribution-example}

请仔细研究下面的示例：

1. 9月15日，用户通过付费搜索广告访问您的网站后离开。
1. 9月18日，该用户通过朋友提供的社交媒体链接再次访问您的网站。 他将多个物品添加到购物车，但没有购买任何物品。
1. 9 月 24 日，您的营销团队向他们发送一封电子邮件，其中包含购物车中某些物品的优惠券。他应用了优惠券，但访问了其他几个网站，查看是否有其他优惠券可用。他通过展示广告找到另一个网站，并最终购买了价值 50 美元的物品。

根据您的回顾窗口和归因模型，渠道会收到不同比例的点数。以下是一些示例：

* 使用&#x200B;**首次联系**&#x200B;和&#x200B;**会话回顾窗口**，归因仅考虑第三次访问。 在电子邮件与展示广告之间，电子邮件是首次接触点，因此电子邮件在 50 美元的购买中获得 100% 的点数。

* 使用&#x200B;**首次联系**&#x200B;和&#x200B;**人员回顾窗口**，归因会考虑所有三次访问。 付费搜索是首次接触点，因此它在 50 美元的购买中获得 100% 的点数。

* 使用&#x200B;**线性**&#x200B;和&#x200B;**会话回顾窗口**，点数在电子邮件和显示广告之间分配。 这两个渠道各自获得25美元的点数。
使用**线性**&#x200B;和&#x200B;**人员回顾窗口**，点数在付费搜索、社交、电子邮件和展示广告之间分配。 每个渠道各自获得此次购买中贡献 12.50 美元的点数。

* 使用&#x200B;**J型**&#x200B;和&#x200B;**人员回顾窗口**，点数在付费搜索、社交、电子邮件和展示广告之间分配。

   * 将 60% 的点数分给展示广告，其贡献价值是 30 美元。
   * 将 20% 的点数分给付费搜索，贡献价值是 10 美元。
   * 剩余的 20% 点数分给社交和电子邮件，二者的贡献价值均为 5 美元。

* 使用&#x200B;**时间衰减**&#x200B;和&#x200B;**人员回顾时间范围**，点数在付费搜索、社交、电子邮件和展示广告之间分配。 使用默认的 7 天半衰期：

   * 显示接触点与转化之间的间隔为0天。`2^(-0/7) = 1`
   * 电子邮件接触点与转化之间的间隔为零天。`2^(-0/7) = 1`
   * 社交接触点与转化之间的间隔为6天。`2^(-6/7) = 0.552`
   * 付费搜索接触点与转化之间的间隔为9天。`2^(-9/7) = 0.41`
   * 将这些值标准化处理之后得到以下结果：

      * 展示广告：33.8%，贡献价值是 16.88 美元
      * 电子邮件：33.8%，贡献价值是 16.88 美元
      * 社交：18.6%，贡献价值是 9.32 美元
      * 付费搜索：13.8%，贡献价值是 6.92 美元

如果点数属于多个渠道，则通常具有整数的转化事件会被划分。 例如，如果使用线性归因模型分析得出两个渠道对某个订单都有贡献，则两个渠道得到的订单都是0.5。 这些局部量度在所有人员中相加，然后在报表中四舍五入到最接近的整数。


>[!MORELIKETHIS]
>
>[归因组件设置](/help/data-views/component-settings/attribution.md)
>[参与率量度](participation-metric.md)
>

