---
title: 从Analytics Source Connector过渡到Web SDK以进行Customer Journey Analytics
description: 了解在升级到Customer Journey Analytics时如何从Analytics源连接器转换到Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: f4fd3c1932a736577d480e86cad70f55de75cb21
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---

# 从Analytics Source Connector过渡到Web SDK以进行Customer Journey Analytics

>[!NOTE]
> 
>在回答[Customer Journey Analytics升级核对清单](https://gigazelle.github.io/cja-ttv/)中的问题时，使用此页上的信息。

使用Analytics Source Connector作为Customer Journey Analytics的唯一实施存在一些固有缺点。

如果您的组织已升级到Customer Journey Analytics仅使用Analytics Source Connector实施，则Adobe建议迁移到使用Analytics Source Connector（用于历史数据）的实施，然后再迁移到使用Web SDK的新实施（用于持续数据收集）。

## 了解专门使用Analytics Source Connector的优缺点

有关使用Analytics源连接器的优缺点的信息，请参阅[专门使用Analytics源连接器升级到Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)。

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

1. 将使用原始Analytics Source Connector自动创建的数据集添加到Customer Journey Analytics连接中。

   有关详细信息，请参阅[将当前Analytics源连接器的数据集添加到连接](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)。

1. （视情况而定）如果您使用的是查找数据集，则必须创建查找数据集并将其添加到连接中。 有关详细信息，请参阅[创建查找数据集以对Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)中的数据分类。

1. 删除原始Analytics源连接器。<!-- need to add steps somewhere about how to do this -->

1. [创建新的Analytics Source Connector并映射字段](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。
