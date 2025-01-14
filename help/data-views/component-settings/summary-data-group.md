---
title: 摘要数据组组件设置
description: 详细信息以及如何配置数据集中的维度以确保您可以正确报告摘要数据。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c39ee568-97f6-4925-ae18-3d4a9dfdb6f5
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 25%

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

要创建维分组，请执行以下操作：

1. 选择维。
1. 选择![V形向下](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 摘要数据组]**。
1. 启用&#x200B;**[!UICONTROL 创建分组]**。
1. 从&#x200B;**[!UICONTROL Dimension]**&#x200B;下拉列表中选择一个维度，以便从第一步中将它分组为选定的维度。 请注意，只有已添加到数据视图的维度才从下拉列表中可用。
1. （可选）启用&#x200B;**[!UICONTROL 在报表中隐藏]**&#x200B;以隐藏已分组的维度。 启用此选项与对分组维度单独配置&#x200B;**[!UICONTROL 隐藏报表]**&#x200B;类似。 有关详细信息，请参阅[组件设置](overview.md)。
1. 或者，若要向分组中添加其他维度，请选择![添加](/help/assets/icons/Add.svg) **[!UICONTROL 将维度添加到组]**。<br/>您最多可以添加9个维度，因为概要数据组最多只能添加10个维度。

## 相同的组件设置

在对维度进行分组时，必须确保组内每个维度的[!UICONTROL Substring]、[!UICONTROL Behavior （小写）]和[!UICONTROL Include exclude values]设置相同。 否则，在分组之前，组的每个维度都可能会返回不同的结果。
例如：

1. 您已为`campaign_code`（摘要数据的一部分）和`tracking_code`（事件数据的一部分）创建摘要数据组。
1. 您已将[!UICONTROL 行为（小写）]应用于`campaign_code`，但未应用于`tracking_code`维度。

`tracking_code`中的值可能显示为`campaign_code`以外的值。

>[!IMPORTANT]
>
>确保仅从一个维度对维度进行分组，而不应用来自多个维度的分组。 例如，如果通过将`campaign_name`维度添加到`tracking_code`维度来创建分组，则不要同时为`campaign_name`维度创建分组。
>
