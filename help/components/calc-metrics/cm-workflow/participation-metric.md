---
description: 借助计算量度生成器，任何人都可以创建参与量度。
title: 参与率量度
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: 6a9cae93011447fff0f74ca4ae15178e0a1f36aa
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 6%

---

# 构建参与率量度

本文介绍如何创建参与率量度。 参与率量度显示维度的各个值（如页面查看次数、营销渠道）如何参与或参与包含特定量度（如“订单”）的会话。

此类信息对任何内容所有者都很有用。

>[!NOTE]
>
>具有其他归因模型（例如参与率）的量度也可以由管理员作为的一部分创建。 [数据视图](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html). 以下示例显示了任何有权访问工作区中的计算量度生成器的用户可怎样创建这些量度。


1. 开始构建量度，如中所述 [生成量度](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. 在计算量度生成器中，将量度命名为“参与率”或类似名称。
1. 将包含成功事件的量度（例如“订单”）拖到“定义”画布中。
1. 选择 ![齿轮](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) 对于量度。
1. 在显示的弹出窗口中，选择 **[!UICONTROL 使用非默认归因模型]** 以定义 [归因模型](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) ，结束该事件 **[!UICONTROL 参与率]** 并选择 **[!UICONTROL 会话]** 对于 [!UICONTROL 回看窗口期]. 选择 **[!UICONTROL 应用]** 以确认。

   在“定义”框中，通过附加来更新选定的量度  **（参与|会话）** 到它的名字。

   ![](assets/participation-setup.png)



1. 选择 [!UICONTROL **保存**] 以保存指标。
1. 在报表中使用计算量度。 例如，使用计算的 [!DNL Orders (Session Participation)] 量度（如步骤5中所定义），用于显示哪些客户层促成了（或参与了）包含订单的会话。

   ![](assets/participation-pages-customer-tier.png)

1. （可选）与组织中的其他用户共享该量度，如中所述 [共享计算量度](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
