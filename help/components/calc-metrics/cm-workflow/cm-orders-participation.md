---
description: 说明如何创建量度，以显示哪些营销渠道有助于推动订单。
title: 构建更复杂的计算量度
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
TQID: https://experienceleague.adobe.com/T5hA3-IeRUfDR53RL6TnJUslUI7XxRSZN2KpPKAz7k0
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 3%

---

# 构建更复杂的计算量度

本文介绍了计算指标的更复杂示例。 此计算量度显示哪些营销渠道有助于推动订单。 此类计算量度可适用于任何维度或成功事件。

1. 开始生成计算量度，如[生成量度](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)中所述。

1. 在计算量度生成器中，将量度命名为`Assisted Online Orders`或类似名称。

1. 从&#x200B;**[!UICONTROL Metrics]**&#x200B;组件中选择&#x200B;**[!UICONTROL 在线订单]**&#x200B;量度，并将该量度拖动到&#x200B;**[!UICONTROL Definition]**&#x200B;区域。

   1. 为量度选择![设置](/help/assets/icons/Setting.svg)。
   1. 选择&#x200B;**[!UICONTROL 使用非默认归因模型]**。
   1. 调整&#x200B;**[!UICONTROL 列归因模型]**&#x200B;中的归因模型。
      1. 为&#x200B;**[!UICONTROL 模型]**&#x200B;选择&#x200B;**[!UICONTROL 自定义]**。 将&#x200B;**[!UICONTROL Starter]**&#x200B;设置为`0`，将&#x200B;**[!UICONTROL Player]**&#x200B;设置为`100`，将&#x200B;**[!UICONTROL Closer]**&#x200B;设置为`0`。
      1. 为&#x200B;**[!UICONTROL 容器]**&#x200B;选择&#x200B;**[!UICONTROL 访客]**。
      1. 为&#x200B;**[!UICONTROL 回顾时间范围]**&#x200B;选择&#x200B;**[!UICONTROL 30天]**。

      1. 选择&#x200B;**[!UICONTROL 应用]**。

      ![列归因模型](assets/complex-calculated-metric.png)

1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存计算量度。

要使用计算量度，请执行以下操作：

1. 在Analysis Workspace中，创建一个包含&#x200B;**[!UICONTROL 营销渠道]**&#x200B;维度、**[!UICONTROL 在线订单]**&#x200B;和新&#x200B;**[!UICONTROL 辅助在线订单]**&#x200B;量度的自由格式表。

   ![营销渠道辅助在线订单](assets/marketing-channel-assists.png)

1. （可选）与组织中的其他用户共享该量度，如[共享计算量度](/help/components/calc-metrics/cm-workflow/cm-sharing.md)中所述。

这是分辨哪些营销渠道有助于提升订单的简单方法。 或者，从自由格式表中，您可以选择任何量度，然后从上下文菜单中直接从表中调整归因模型。
