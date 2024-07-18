---
description: 借助计算量度生成器，任何人都可以创建参与量度。
title: 参与率量度
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 5%

---

# 生成参与率量度

本文介绍如何创建参与率量度。 参与率量度显示维度的各个值（如页面查看次数、营销渠道）如何参与或参与包含特定量度（如“订单”）的会话。

此类信息对任何内容所有者都很有用。

>[!NOTE]
>
>具有其他归因模型（例如参与率）的量度也可以由管理员作为[数据视图](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html)的一部分创建。 有关更多详细信息，请参阅[归因组件设置](../../../data-views/component-settings/attribution.md)。<br/>以下示例显示了如何由任何有权访问Workspace中的计算量度生成器的用户创建参与率量度。


1. 开始生成量度，如[生成量度](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)中所述。
1. 在计算量度生成器中，将量度命名为`Participation`或类似名称。
1. 将包含成功事件的量度（例如[!DNL Orders]）拖到[!UICONTROL 定义]画布中。
1. 为量度选择![齿轮](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg)。
1. 在出现的弹出窗口中，选择&#x200B;**[!UICONTROL 使用非默认归因模型]**&#x200B;将该事件的[归因模型](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md)定义为&#x200B;**[!UICONTROL 参与率]**，并为[!UICONTROL 回顾窗口]选择&#x200B;**[!UICONTROL 会话]**。 选择&#x200B;**[!UICONTROL 应用]**&#x200B;以确认。

   在“定义”框中，通过将&#x200B;**(Partipation|Session)**&#x200B;附加到其名称来更新所选度量。

   ![列归因模型弹出窗口，其中显示已选择参与作为模型和已选择用于回溯窗口的会话。](assets/participation-setup.png)



1. 选择&#x200B;[!UICONTROL **保存**]&#x200B;以保存指标。
1. 在报表中使用计算量度。 例如，在报表中使用计算的[!DNL Orders (Session Participation)]量度（如步骤5中所定义）来显示哪个客户层促成了（或参与了）包含订单的会话。

   ![显示客户层和订单的自由格式表。](assets/participation-pages-customer-tier.png)

1. （可选）与组织中的其他用户共享该量度，如[共享计算量度](/help/components/calc-metrics/cm-workflow/cm-sharing.md)中所述。
