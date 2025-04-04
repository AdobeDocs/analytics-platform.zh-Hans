---
title: 归因组件设置
description: 使您可设置指标的默认归因。
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 29%

---

# 归因组件设置 {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_attribution"
>title="归因"
>abstract="配置应用于报表中某个量度的默认归因模型。"

<!-- markdownlint-enable MD034 -->


通过归因，可自定义维度项目获取成功事件点数的方式。

突出显示“设置归因”选项的![数据视图窗口](../assets/attribution-settings.png)

例如：

1. 您网站上的人员单击指向您的某个产品页面的付费搜索链接。 他们将产品添加到购物车，但不购买。
2. 第二天，他们看到了朋友的社交媒体帖子。 他们单击链接，然后完成购买。

在某些报告中，您可能希望将订单归因到“付费”搜索。在其他报告中，您可能希望将订单归因到社交。通过归因，您能够控制报告的这一方面。

## 设置组件的默认归因模型

您可以通过更新数据视图中量度的设置，为给定量度设置默认归因模型。 只要量度在Analysis Workspace中使用，这样做就会覆盖该量度的归因模型。

>[!NOTE]
>
>对量度启用归因时，请考虑以下事项：
>
>* **在具有&#x200B;*单个维度*：**&#x200B;的报表中使用组件时，如果使用非默认归因模型，组件的归因将忽略分配模型。
>
>* **在具有&#x200B;*多个维度*：**&#x200B;的报表中使用组件时，如果使用了非默认归因模型，则组件的归因将保留分配模型。
>
>   仅当[将数据导出到云](/help/analysis-workspace/export/export-cloud.md)时，多个维度才可用。
>
> 有关分配的更多信息，请参阅[持久性组件设置](/help/data-views/component-settings/persistence.md)。

要更新组件的默认归因模型，请执行以下操作：

1. 转到包含要更新其默认归因模型的组件的数据视图。

1. 选择组件，然后展开屏幕右侧的归因部分。

   突出显示“设置归因”选项的![数据视图窗口](../assets/attribution-settings.png)

1. 选择&#x200B;[!UICONTROL **设置归因**]，然后在&#x200B;[!UICONTROL **归因模型**]&#x200B;下拉菜单中选择归因模型。

   请参阅[归因模型](#attribution-models)以了解每个归因模型。

1. 选择&#x200B;[!UICONTROL **保存并继续**]。

>[!TIP]
>
>如果您的组织要求一个量度具有多个归因设置，您可以执行以下操作之一：
>
> * 使用每个所需的归因设置复制数据视图中的量度。 您可以在一个数据视图中包含多次相同的量度，从而为每个量度提供不同的设置。 确保适当地标记每个量度，以便分析师在生成报表时了解这些量度之间的差异。
>
> * 覆盖Analysis Workspace中的量度。 在量度的[列设置](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)中，选择&#x200B;**[!UICONTROL 使用非默认归因模型]**&#x200B;以更改该特定报表的量度归因模型和回溯时段。

## 归因模型 {#attribution-models}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataviews_component_attribution_attributionmodels"
>title="模型"
>abstract="选择量度的归因模型。"

<!-- markdownlint-enable MD034 -->

{{attribution-models-details}}


## 回顾时间范围

{{attribution-lookback-window}}



## 归因示例 {#attribution-example}

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


