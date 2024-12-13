---
title: 专门使用Analytics Source Connector升级到Customer Journey Analytics
description: 了解如何创建Analytics源连接器和映射字段
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
source-git-commit: 701e3d3ce535318e3d3debcdcd591615ea9ca4a1
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---

# 专门使用Analytics Source Connector升级到Customer Journey Analytics

>[!NOTE]
> 
>在回答[Customer Journey Analytics升级核对清单](https://gigazelle.github.io/cja-ttv/)中的问题时，使用此页上的信息。

虽然不建议使用，但您可以使用Analytics Source Connector作为Customer Journey Analytics的唯一实施路径。 但是，由于此类升级存在固有缺点，Adobe建议将Analytics源连接器与Experience PlatformWeb SDK的新实施结合使用。 有关此建议升级路径的详细信息，请参阅[从Adobe Analytics升级到Customer Journey Analytics时建议路径](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。

使用下表中的信息了解单独使用源连接器的优点和缺点。

如果您决定使用Analytics源连接器作为Customer Journey Analytics的唯一实现路径，请按照[引入中的实现步骤并使用源连接器](/help/data-ingestion/sources.md)中的数据。

| 优势 | 缺点 |
|----------|---------|
| <ul><li>最省时和最苛刻的升级路径。 <p>数据可以快速轻松地迁移到Customer Journey Analytics中。</p></li></ul> | <ul><li>**数据未发送到Edge Network**： <p>这会导致以下缺点：</p><ul><li>在所有升级路径上的报表中达到[延迟](/help/technotes/guardrails.md#latencies)的最高级别；未针对实时个性化用例进行优化。</li><li>数据不能与其他Adobe Experience Platform应用程序共享；它只限于Customer Journey Analytics</li><li>依赖于Adobe Analytics命名法(属性、eVar、事件等)</li></ul><li>**将来很难迁移到Web SDK**：最终，您可能希望访问由Experience PlatformWeb SDK提供的优势。 要开始使用Experience PlatformWeb SDK，您必须进行新的实施。</li><li>**在您的架构中使用Analytics Experience Event字段组**：此字段组添加了许多Customer Journey Analytics架构中不需要的Adobe Analytics事件。  这可能会导致Customer Journey Analytics所需的架构更加杂乱、复杂。</li><li>**需要Adobe Analytics和Customer Journey Analytics的许可证**：使用Analytics源连接器需要您同时为Adobe Analytics和Customer Journey Analytics付费。</li></ul> |

{style="table-layout:auto"}
