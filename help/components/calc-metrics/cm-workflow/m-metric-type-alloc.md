---
description: 了解量度类型和归因。
title: 量度类型和归因
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 98%

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

         * 禁用&#x200B;**[!UICONTROL 使用非默认归因模型]**&#x200B;来使用默认的列归因模型，即“上次接触”，其回溯期为 30 天。
         * 启用&#x200B;**[!UICONTROL 使用非默认的归因模型]**。在&#x200B;**[!UICONTROL 列归因模型]**&#x200B;对话框中，

            * 从[归因模型](#attribution-models)中选择一个&#x200B;**[!UICONTROL 模型]**。
            * 从[容器](#container)选项中选择一个&#x200B;**[!UICONTROL 容器]**。
            * 从[回溯时间范围](#lookback-window)选项中选择&#x200B;**[!UICONTROL 回溯时间范围]**。如果您选择&#x200B;**[!UICONTROL 自定义时间]**，则可定义时段，单位为&#x200B;**[!UICONTROL 分钟]**&#x200B;至&#x200B;**[!UICONTROL 季度]**。

      1. 选择&#x200B;**[!UICONTROL 应用]**&#x200B;来应用非默认归因模型。选择“取消”即可取消。

     如果您已定义非默认归因模型，请选择&#x200B;**[!UICONTROL 编辑]**&#x200B;来修改选择。

请参阅[示例](#example)，了解如何使用归因模型、容器和回溯时间范围。


## 归因模型 {#attribution-models}

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

{{attribution-models-details}}


## 容器 {#container}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="容器"
>abstract="选择一个容器来设置所需的归因范围。"

{{attribution-container}}


## 回溯时间范围 {#lookback-winwow}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="回溯时间范围"
>abstract="此设置可以确定将要对每次转化应用的数据归因时间范围。"

{{attribution-lookback-window}}




## 示例

{{attribution-example}}

>[!MORELIKETHIS]
>
>[归因组件设置](/help/data-views/component-settings/attribution.md)
>>[参与量度](participation-metric.md)
>

