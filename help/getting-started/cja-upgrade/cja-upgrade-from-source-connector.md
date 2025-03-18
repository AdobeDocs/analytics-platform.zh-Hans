---
title: 从 Analytics Source Connector 过渡到 Customer Journey Analytics 的 Web SDK
description: 了解在升级到Customer Journey Analytics时如何从Analytics源连接器转换到Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 30%

---

# 从 Analytics Source Connector 过渡到 Customer Journey Analytics 的 Web SDK {#transition-from-source-connector}

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

使用Analytics Source Connector作为Customer Journey Analytics的唯一实施存在一些固有缺点。

如果您的组织已仅使用Analytics Source Connector实施升级到Customer Journey Analytics，则Adobe建议转换为新的Web SDK实施以进行持续数据收集，并仅对历史数据使用Analytics Source Connector。

## 了解专门使用Analytics Source Connector的优缺点

有关使用Analytics源连接器的优缺点的信息，请参阅[专门使用Analytics源连接器升级到Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)。

## 从Analytics源连接器过渡到Web SDK

下面是从专门使用Analytics源连接器过渡到由Analytics源连接器和Web SDK实施组成的实施的高级流程：

1. 创建Web SDK实施，如[从Adobe Analytics升级到Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)一文中的[详细的建议升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps)中所述。

   配置Web SDK实施后，请继续执行以下步骤。

1. [为Analytics源连接器创建XDM架构](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)。

1. 将Analytics源连接器中的每个Adobe Analytics维度映射到Web SDK架构中的维度。

   1. 
      <!-- how do you get here -->

   1. 在&#x200B;**[!UICONTROL 映射标准字段]**&#x200B;部分中，选择&#x200B;**[!UICONTROL 自定义]**&#x200B;选项卡。

   1. 选择&#x200B;**[!UICONTROL 添加新映射]**。

      ![映射架构字段](assets/schema-mapping.png)

   1. 在&#x200B;**[!UICONTROL Source字段]**&#x200B;中，从“Adobe Analytics ExperienceEvent模板”字段组中选择一个Adobe Analytics字段。 然后，在&#x200B;**[!UICONTROL 目标字段]**&#x200B;中，选择要将其映射到的XDM字段。

   1. 为您用于在Adobe Analytics中收集数据的Adobe Analytics ExperienceEvent Template字段组中的每个字段重复此过程。

1. 将使用原始Analytics源连接器自动创建的数据集添加到您的Customer Journey Analytics连接中。

   有关详细信息，请参阅[将当前Analytics源连接器的数据集添加到连接](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)。

1. （视情况而定）如果您使用的是查找数据集，则必须创建查找数据集并将其添加到连接中。 有关详细信息，请参阅[创建查找数据集以在Customer Journey Analytics中对数据进行分类](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)。

1. 删除原始Analytics源连接器。<!-- need to add steps somewhere about how to do this -->

1. [创建新的Analytics Source Connector并映射字段](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

{{upgrade-final-step}}
