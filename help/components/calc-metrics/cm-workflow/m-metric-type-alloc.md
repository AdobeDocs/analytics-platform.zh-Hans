---
description: 了解量度类型和归因
title: 量度类型和归因
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 2b193e1ff612ab00335898164dc84afb08673fff
workflow-type: tm+mt
source-wordcount: '1017'
ht-degree: 100%

---

# 量度类型和归因

您可以为计算量度定义中的量度配置量度类型和[归因模型](#attribution-models)。

1. 选择量度组件中的![设置](/help/assets/icons/Setting.svg)。
1. 在弹出的对话框中：

   ![指标类型和归因](assets/cm-type-alloc.png)

   * 指定&#x200B;**[!UICONTROL 量度类型]**：

     | 量度类型 | 定义 |
     |---|---|
     | **[!UICONTROL 标准]** | 如果一个公式包含一个单一的标准量度，它会显示与其相对的非计算量度的相同数据。标准量度可用于创建特定于每个单独行项目的计算量度。 <p>例如，![事件](/help/assets/icons/Event.svg) **[!UICONTROL 订单]** ![划分](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **[!UICONTROL 会话]** 会获取该特定行项目的订单数，并将其除以该特定行项目的会话数。 |
     | **[!UICONTROL 全部总计]** | 使用每个行项目中报告时段的&#x200B;**[!UICONTROL 全部总计]**。如果一个公式是由单个全部总计量度组成的，则计算量度会在每个行项目上显示相同的“全部总计”数字。全部总计量度可用于创建与总计数据相比较的计算量度。 <p>例如，![事件](/help/assets/icons/Event.svg) **[!UICONTROL 订单]** ![划分](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **[!UICONTROL 总会话数]** 显示订单占所有会话的比例，而不仅仅是特定行项目的会话。在此示例中，您指定计算量度中![事件](/help/assets/icons/Event.svg)**[!UICONTROL 会话]**&#x200B;量度的&#x200B;**[!UICONTROL 全部总计]**，这将自动将其转换为![事件](/help/assets/icons/Event.svg)**[!UICONTROL 总会话数]**。 |

   * 指定&#x200B;**[!UICONTROL 归因]**。

      1. 您可以：

         * 禁用&#x200B;**[!UICONTROL 使用非默认归因模型]**&#x200B;来使用默认的列归因模型，即“上次接触”，其回顾期为 30 天。
         * 启用&#x200B;**[!UICONTROL 使用非默认的归因模型]**。在&#x200B;**[!UICONTROL 列归因模型]**&#x200B;对话框中，

            * 从归因模型中选择一个&#x200B;**[!UICONTROL 模型]**。
            * 选择一个&#x200B;**[!UICONTROL 回顾日期范围]**。如果您选择&#x200B;**[!UICONTROL 自定义时间]**，则可定义时段，单位为&#x200B;**[!UICONTROL 分钟]**&#x200B;至&#x200B;**[!UICONTROL 季度]**。请参阅[回顾时间范围](#lookback-window)，以了解更多信息

      1. 选择&#x200B;**[!UICONTROL 应用]**&#x200B;来应用非默认归因模型。选择“取消”即可取消。

     如果您已定义非默认归因模型，请选择&#x200B;**[!UICONTROL 编辑]**&#x200B;来修改选择。

请参阅[示例](#example)，了解如何使用归因模型和回溯时间范围。


## 归因 {#attribution}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="使用非默认的属性模型"
>abstract="为所选量度启用非默认归因模型。"


>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="模型"
>abstract="选择量度的归因模型。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="最后接触"
>abstract="100% 的点数归于访客看到的最后一个维度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="首次接触"
>abstract="100% 的点数归于访客看到的第一个维度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="线性"
>abstract="点数均匀分布于所有维度值上。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="参与率"
>abstract="100% 的点数归于访客所见的每个维度值。<br/>列总数被夸大了。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="同一接触"
>abstract="仅对与转化发生在同一事件上的维度值给予点数。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="同一接触"
>abstract="仅对与转化发生在同一事件上的维度值给予点数。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="U 型"
>abstract="第一个维度值占 40%，最后一个维度值占 40%，中间维度值占 20%。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="J 曲线"
>abstract="最后一个维度值占 60%，第一个维度值占 20%，中间维度值占 20%。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="J 曲线"
>abstract="最后一个维度值占 60%，第一个维度值占 20%，中间维度值占 20%。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="反向 J"
>abstract="第一个维度值占 60%，最后一个维度值占 20%，中间维度值占 20%。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="反向 J"
>abstract="第一个维度值占 60%，最后一个维度值占 20%，中间维度值占 20%。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="时间衰减"
>abstract="距离转化时间最近的维度值将获得最多的点数。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="自定义"
>abstract="根据归因权重，自行定义您的位置。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="自定义"
>abstract="根据归因权重，自行定义您的位置。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="算法"
>abstract="点数是根据统计算法动态确定的。"


>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="容器"
>abstract="选择一个容器来设置所需的归因范围。"


{{attribution-models-details}}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="回顾时间范围"
>abstract="此设置可以确定将要对每次转化应用的数据归因窗口。"


{{attribution-lookback-window}}


### 归因举例   {#attribution-example}

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


>[!MORELIKETHIS]
>
>[归因组件设置](/help/data-views/component-settings/attribution.md)
>>[参与量度](participation-metric.md)
>

