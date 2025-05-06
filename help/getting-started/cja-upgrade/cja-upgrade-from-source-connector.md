---
title: 从 Analytics 源连接器渡到 Customer Journey Analytics 的 Web SDK
description: 了解升级到 Customer Journey Analytics 时如何从 Analytics 源连接器过渡到 Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '538'
ht-degree: 100%

---

# 从 Analytics 源连接器渡到 Customer Journey Analytics 的 Web SDK {#transition-from-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector"
>title="Analytics Source Connector 实施"
>abstract="Analytics Source Connector 可让您轻松获得 Customer Journey Analytics 的价值，但要求您同时支付 Adobe Analytics 和 Customer Journey Analytics 的费用。本指南可帮助您转向独立的 Web SDK 实施。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-delete"
>title="删除现有的 Analytics 源连接器"
>abstract="您当前拥有的 Analytics 源连接器与您组织的自定义架构不兼容。但是，Analytics 报告包中仍然存在数据。此步骤会移除当前的 Analytics 源连接器，以便您可以在后续步骤中使用正确的架构重新创建它。<br><br>在删除源连接器之前，您可能需要与组织中的其他人员进行协调，以确保删除源连接器不会影响组织内的报告。这一协调工作可能需要数周时间才能完成。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

使用 Analytics 源连接器作为 Customer Journey Analytics 的唯一实施时存在着固有的缺点。

如果您的组织已升级到 Customer Journey Analytics 且仅使用 Analytics 源连接器实施，Adobe 建议过渡到新的 Web SDK 实施用于持续收集数据，而将 Analytics 源连接器仅用于历史数据。

## 了解单独使用 Analytics 源连接器的优缺点

有关使用 Analytics 源连接器的优缺点的信息，请参阅[仅使用 Analytics 源连接器升级到 Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)。

## 从 Analytics 源连接器过渡至 Web SDK

以下是从仅使用 Analytics 源连接器过渡到同时使用 Analytics 源连接器和 Web SDK 实施的高级流程：

1. 创建一个 Web SDK 实施，具体内容如本文中[详细的建议升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps)所述，[从 Adobe Analytics 升级到 Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。

   在完成对 Web SDK 实施的配置后，继续以下步骤。

1. [为 Analytics 源连接器创建 XDM 架构](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)。

1. 将 Analytics 源连接器中的每个 Adobe Analytics 维度映射到 Web SDK 架构中的维度。

   1. 
      <!-- how do you get here -->

   1. 在&#x200B;**[!UICONTROL 映射标准字段]**&#x200B;部分中，选择&#x200B;**[!UICONTROL 自定义]**&#x200B;选项卡。

   1. 选择&#x200B;**[!UICONTROL 添加新映射]**。

      ![映射架构字段](assets/schema-mapping.png)

   1. 在&#x200B;**[!UICONTROL 源字段]**&#x200B;中，从 Adobe Analytics ExperienceEvent 模板字段组中选择一个 Adobe Analytics 字段。然后，在&#x200B;**[!UICONTROL 目标字段]**&#x200B;中，选择要映射到的 XDM 字段。

   1. 对用于在 Adobe Analytics 中收集数据的 Adobe Analytics ExperienceEvent 模板字段组中的每个字段重复此过程。

1. 将使用原始 Analytics 源连接器自动创建的数据集添加到 Customer Journey Analytics 连接。

   有关详细信息，请参阅[将当前 Analytics 源连接器中的数据集添加到连接](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)。

1. （有条件）如果您正在使用查找数据集，则必须创建查找数据集并将其添加到您的连接中。有关详细信息，请参阅 [创建查找数据集，以对 Customer Journey Analytics 中的数据进行分类](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)。

1. 删除原始 Analytics 源连接器。<!-- need to add steps somewhere about how to do this -->

1. [创建一个新的 Analytics 源连接器并映射字段](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

{{upgrade-final-step}}
