---
title: 摘要数据组组件设置
description: 详细信息以及如何配置数据集中的维度，以确保您可以正确报告摘要数据。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c39ee568-97f6-4925-ae18-3d4a9dfdb6f5
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 89%

---

# [!UICONTROL 摘要数据组]组件设置 {#summary-data-group-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_summarydatagroup"
>title="摘要数据组"
>abstract="摘要数据组在分组中的所有维度之间创建关联，并用于将摘要数据集中的维度与其他维度相结合以进行报告。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_summarydatagroup_hideinreporting"
>title="在报告中隐藏"
>abstract="选择此选项将为该维度启用&#x200B;**[!UICONTROL “在报告中隐藏组件”]**，并阻止该组件显示在 Analysis Workspace 和其他 Customer Journey Analytics 报告工具中。"

<!-- markdownlint-enable MD034 -->



摘要数据组在分组中的所有维度之间创建关联，并用于将摘要数据集中的维度与其他维度相结合以进行报告。

![摘要数据组组件设置](/help/data-views/assets/summary-data-group.png)

要创建维度分组：

1. 选择一个维度.
1. 选择 ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 摘要数据组]**。
1. 启用&#x200B;**[!UICONTROL 创建分组]**。
1. 从&#x200B;**[!UICONTROL Dimension]**&#x200B;下拉菜单中选择一个维度，您从第一步中将其与所选维度分组。 请注意，只有已添加到数据视图的维度才从下拉菜单中可用。
1. 此外，可以启用&#x200B;**[!UICONTROL 在报告中隐藏]**，以在报告中隐藏分组维度。启用此选项与单独在分组维度上配置&#x200B;**[!UICONTROL 在报告中隐藏]**&#x200B;类似。有关更多信息，请参阅[组件设置](overview.md)。
1. 或者，若要向分组添加其他维度，请选择 ![添加](/help/assets/icons/Add.svg) **[!UICONTROL 向组添加维度]**。<br/>您最多可以添加九个维度，因为摘要数据组的上限是十个维度。

## 相同的组件设置 

在对维度进行分组时，对于组中的每个维度，必须确保[!UICONTROL 子字符串]、[!UICONTROL 行为（小写）]和[!UICONTROL 包括排除值]设置都是相同的。否则，组中的每个维度在分组之前都可能会返回不同的结果。
例如：

1. 您已为 `campaign_code`（摘要数据的一部分）和 `tracking_code`（事件数据的一部分）创建了摘要数据组。
1. 您已对 `campaign_code` 应用了[!UICONTROL 行为（小写）]，当未应用于 `tracking_code` 维度。

`tracking_code` 中的值可能会表现得不同于 `campaign_code`。

>[!IMPORTANT]
>
>请确保仅从一个维度对维度进行分组，而不要从多个维度进行分组。例如，如果您通过将 `campaign_name` 维度添加到 `tracking_code` 维度来创建分组，请不要同时为 `campaign_name` 维度创建分组。
>
