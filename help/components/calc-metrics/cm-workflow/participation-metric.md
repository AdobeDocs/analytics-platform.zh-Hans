---
description: 了解如何创建参与率量度。
title: 参与率度量
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 1%

---

# 参与率量度

参与率量度用于量化维度的各个值（如页面查看次数）对包含特定量度（如订单数）的会话的贡献或参与情况。

>[!NOTE]
>
>管理员可以使用非默认归因模型（如参与率）创建指标，作为[数据视图](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/data-views)的一部分。 有关更多详细信息，请参阅[归因组件设置](../../../data-views/component-settings/attribution.md)。

以下步骤显示具有[创建计算量度权限](/help/technotes//access-control.md#user-level-access)的任何用户如何创建参与率量度。

1. [创建计算量度](cm-workflow.md)，在[计算量度生成器](cm-build-metrics.md)中，将量度命名为`Participation`或类似名称。
1. 将包含成功事件的量度（例如[!DNL Orders]）拖入[!UICONTROL **[!UICONTROL 定义]**]区域。
1. 为量度选择![齿轮](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg)。
1. 在出现的弹出窗口中，选择&#x200B;**[!UICONTROL 使用非默认归因模型]**&#x200B;将该事件的[归因模型](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md)定义为&#x200B;**[!UICONTROL 参与率]**，并为&#x200B;**[!UICONTROL 容器]**&#x200B;选择[!UICONTROL 会话]。 选择&#x200B;**[!UICONTROL 应用]**&#x200B;以确认。


   ![列归因模型弹出窗口，其中显示已选择参与作为模型和已选择用于回溯窗口的会话。](assets/participation-setup.png)

   **(Partipation|Session)**&#x200B;已添加到量度组件名称。



1. 选择&#x200B;[!UICONTROL **保存**]&#x200B;以保存指标。
1. 在报表中使用计算量度。 例如，在报表中使用计算的[!DNL Orders (Session Participation)]量度来显示哪个客户层促成了（或参与了）包含订单的会话。

   ![显示客户层和订单的自由格式表。](assets/participation-pages-customer-tier.png)
