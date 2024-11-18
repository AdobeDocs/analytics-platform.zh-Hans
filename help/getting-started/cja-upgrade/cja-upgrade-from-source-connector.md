---
title: 从Analytics Source Connector移动到Web SDK以进行Customer Journey Analytics
description: 了解在升级到Customer Journey Analytics时如何从Analytics源连接器移至Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 5ce69400a01566728f374d68ac08a981adfd8b6e
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# 从Analytics Source Connector移动到Web SDK以进行Customer Journey Analytics

>[!NOTE]
> 
>在回答[Customer Journey Analytics升级核对清单](https://gigazelle.github.io/cja-ttv/)中的问题时，使用此页上的信息。

使用Analytics Source Connector作为Customer Journey Analytics的唯一实施存在一些固有缺点。 如果贵组织已升级到仅使用Analytics Source Connector实现Customer Journey Analytics，则应考虑改用Web SDK实现。

Adobe建议将Analytics源连接器（用于引入历史数据）与Web SDK的新实施（用于持续数据收集）结合使用。

## 了解专门使用Analytics Source Connector的优缺点

有关使用Analytics源连接器的优缺点的信息，请参阅[专门使用Analytics源连接器升级到Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)。

## 从Analytics源连接器移动到Web SDK

以下是从Analytics源连接器移动到由Analytics源连接器和Web SDK实施组成的实施的高级流程：

1. 创建Web SDK实现，如[详细推荐的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) (在文章[从Adobe Analytics升级到Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)中)中所述。

   配置Web SDK实施后，继续执行以下步骤。

1. 决定您在Web SDK实施中是使用Adobe Analytics模式还是XDM模式。

   有关详细信息，请参阅[为Customer Journey Analytics选择架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)。

1. （视情况而定）如果您计划使用Adobe Analytics架构，请将Analytics源连接器自动创建的数据集添加到您的Customer Journey Analytics连接。

   有关详细信息，请参阅[将Analytics源连接器数据集添加到连接](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)。

1. （视情况而定）如果您计划创建XDM架构：

   1. [为Analytics源连接器创建XDM架构](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)。

   1. 将使用原始Analytics Source Connector自动创建的数据集添加到Customer Journey Analytics连接中。

      有关详细信息，请参阅[将当前Analytics源连接器的数据集添加到连接](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)。

   1. 删除原始Analytics源连接器。<!-- need to add steps somewhere about how to do this -->

   1. [创建新的Analytics Source Connector并映射字段](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。








