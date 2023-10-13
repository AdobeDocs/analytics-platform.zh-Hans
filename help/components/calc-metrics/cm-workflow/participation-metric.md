---
description: 借助计算量度生成器，任何人都可以创建参与量度。
title: 参与率量度
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: d95d324350a2f8aa77032e7cac1c924d161d47ce
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 17%

---

# 生成“参与率”量度

本文介绍如何创建一个量度，以显示选定维度（如页面查看次数、营销渠道、应用程序版本）的单个值如何参与（或参与）包含订单的会话。

此类信息对任何内容所有者都很有用。

>[!NOTE]
>
>具有其他归因模型（例如参与率）的量度也可以由管理员作为的一部分创建。 [数据视图](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html). 以下示例显示了任何有权访问工作区中的计算量度生成器的用户可怎样创建这些量度。

1. 开始构建量度，如中所述 [生成量度](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. 在计算量度生成器中，将量度命名为“参与率”或类似名称
1. 将成功事件“订购”拖到“定义”画布。
1. 选择 ![齿轮](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) 对于 [!DNL Orders] 量度。
1. 在显示的弹出窗口中，选择 **[!UICONTROL 使用非默认归因模型]** 以定义 [归因模型](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) ，结束该事件 **[!UICONTROL 参与率]** 并选择 **[!UICONTROL 会话]** 对于 [!UICONTROL 回看窗口期]. 选择 **[!UICONTROL 应用]** 以确认。

   在“定义”框中， ![事件](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) **订购** 已更新至 ![事件](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) **订单（参与|会话）**.

   ![](assets/participation-setup.png)



1. 选择 [!UICONTROL **保存**] 以保存指标。
1. 在报表中使用计算量度。 以下计算量度用在报表中，以显示哪些客户层促成了（或参与了）包含订单的会话。

   ![](assets/participation-pages-customer-tier.png)

1. （可选）与组织中的其他用户共享该量度，如中所述 [共享计算量度](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
