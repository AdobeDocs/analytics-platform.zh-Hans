---
title: 从Adobe Analytics升级到Customer Journey Analytics时推荐的路径
description: 了解从Adobe Analytics升级到Customer Journey Analytics时推荐的路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: ea16705e96047cbcf41e428d2018ea7c72b2afac
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 6%

---

# 从Adobe Analytics升级到Customer Journey Analytics

在开始从Adobe Analytics升级到Customer Journey Analytics的升级过程之前，请先了解建议的升级步骤。

>[!NOTE]
>
>此部分中描述的升级步骤是推荐的升级步骤，任何组织都可以使用该步骤成功从Adobe Analytics升级到Customer Journey Analytics。
>
>但是，根据时间表和资源限制等多个因素，建议的升级步骤可能对您的组织不实用。 在这种情况下，请使用[Adobe AnalyticsCustomer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)来动态生成针对贵组织独特环境量身定制的升级步骤。

## 为大多数组织推荐的升级步骤

从Adobe Analytics升级到Customer Journey Analytics时，建议的步骤是实施Experience PlatformWeb SDK的新步骤，此方法是Customer Journey Analytics的首选数据收集方法。 在与Web SDK结合使用时，Adobe还建议使用Analytics源连接器，以便保留Adobe Analytics历史数据并执行并排数据比较。

完全过渡到Customer Journey Analytics后，可以关闭Analytics源连接器，并且可以专门使用Experience PlatformWeb SDK。

### 高级别建议的升级过程

1. **实施Experience PlatformWeb SDK**

   新实施的Experience PlatformWeb SDK是收集数据以进行Customer Journey Analytics的最佳方式。 它提供了充分利用Customer Journey Analytics的最佳基础，因为它是用于实现Customer Journey Analytics的最高性能、最简单且经得起未来考验的方法。

   * 高性能报表和数据可用性，因为Adobe Experience Platform构建用于支持实时个性化用例

   * 在其他Experience Cloud产品(AJO、RTCDP等)之间整合Adobe Experience Cloud数据收集的实施

   * 不依赖于Adobe Analytics命名法(属性、eVar、事件等)

1. **设置Adobe Analytics源连接器**

   为了帮助顺利过渡到在Customer Journey Analytics中使用Experience PlatformWeb SDK，Adobe还建议使用Adobe Analytics源连接器。 这样，您就可以保留历史数据，并Customer Journey Analytics查看现有Adobe Analytics实施的数据，以及新Experience PlatformWeb SDK实施的数据。

   Analytics源连接器允许您：

   * 将您的Adobe Analytics历史报表包数据引入Adobe Experience Platform并Customer Journey Analytics。

     您可以保持Analytics Source Connector运行，只要您需要保留Adobe Analytics历史数据即可。

   * 在Customer Journey Analytics中查看通过原始Adobe Analytics实施(AppMeasurement、Analytics扩展或Web SDK扩展)收集的数据。 您可以并排比较此数据与新的Web SDK实施数据。

     您可以保持Analytics Source Connector运行，直到您熟悉并熟悉这些差异为止。<!--elaborate on what those differences are? -->

   建议不要将Analytics Source Connector作为独立实施长期用于Customer Journey Analytics。 这是由于高延迟、架构复杂杂乱、依赖于Adobe Analytics命名法(属性、eVar等)，以及最终从源连接器移动到推荐的Web SDK实施方面的困难。

### 详细的建议升级步骤

以下步骤显示了从Adobe Analytics升级到Customer Journey Analytics的建议流程。

根据您组织的独特环境和要求，这些建议的步骤可能不适合您的组织。 在这种情况下，请使用[Adobe AnalyticsCustomer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)来动态生成针对贵组织独特环境量身定制的升级步骤。

1. [规划XDM架构架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)。

1. [在Adobe Experience Platform中创建所需的自定义架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

1. [在Adobe Experience Platform中创建数据集](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)。

1. 展开描述当前Adobe Analytics实施的部分，然后完成相关步骤：

   +++对于使用AppMeasurement的Adobe Analytics实施

   1. [在Adobe Experience Platform中创建数据流](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)。<!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

+++

   +++对于使用Analytics扩展的Adobe Analytics实施（标记）

   1. [在Adobe Experience Platform中创建数据流](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)。<!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

+++

+++ 对于使用Web SDK的Adobe Analytics实施

   无需执行其他步骤。

+++

1. [将Adobe Experience Platform作为服务添加到您的数据流](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)。

1. 使用下表确定要继续在Customer Journey Analytics中使用的任何Adobe Analytics功能，然后使用提供的信息了解如何在升级到Customer Journey Analytics的过程中配置这些功能：

   | Adobe Analytics功能 | Customer Journey Analytics的实施要求 | 其他信息 |
   |---------|----------|---------|
   | 分类数据 | 为包含分类数据的每个维度创建查找数据集。 |  |
   | 营销渠道 | 创建营销渠道派生的字段。 |  |
   | Activity Map叠加图和链接跟踪 | 不适用 | Adobe当前正在努力支持Customer Journey Analytics的Activity Map叠加。 |
   | 数据馈送 | 实施期间无需配置。<br/>[了解Customer Journey Analytics](/help/analysis-workspace/export/export-project-overview.md)中的各种导出选项。 | 虽然Customer Journey Analytics尚无法直接取代数据馈送，但您可以从Analysis Workspace导出Customer Journey Analytics报表，以供在第三方工具中使用或与外部数据组合。 |
   | Data Warehouse | 实施期间无需配置。<br/>[了解Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md)中的完整表导出。 | Customer Journey Analytics完整表格导出是Adobe Analytics中Data Warehouse报表的演变，具有许多现在在Data Warehouse中不可用的经常请求的新功能。 |
   | 流媒体数据 |  |  |

1. （可选）使用Analytics Source Connector从Adobe Analytics引入历史数据。

   有关详细信息，请参阅[使用源连接器](/help/data-ingestion/sources.md)摄取和使用数据[使用源连接器](/help/data-ingestion/sources.md#use-a-source-connector)。

1. 使用下表确定所需的任何Customer Journey Analytics功能，然后使用提供的信息了解如何在升级到Customer Journey Analytics的过程中配置这些功能：

   | 您想要的Customer Journey Analytics功能 | Customer Journey Analytics的实施要求 | 其他信息 |
   |---------|----------|---------|
   | 将Web数据与其他渠道的数据（如呼叫中心数据）相关联 | 创建连接后（如后面步骤中所述），在Customer Journey Analytics中将其他数据集添加到您的连接。 |  |
   | 与RTCDP集成 | 在架构中启用配置文件并创建配置文件数据集以在RTCDP中使用 | 必须在创建XDM架构时执行此操作。 |
   | 与Adobe Journey Optimizer集成 | 在实施中使用个性化对象，以便在Adobe Journey Optimizer中使用 |  |

1. 展开描述所需Customer Journey Analytics实施的部分，然后完成相关步骤：

   +++手动实施（JS文件）

   1. [将alloy.js添加到您的站点](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22)。

+++

   +++标记

   1. [在Adobe Experience Platform数据收集中创建标记属性](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/quick-start#create-a-property)。

+++

+++ API

   1. 使用Edge NetworkAPI将数据发送到所需的数据流。

+++

1. [在Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)中创建连接。

1. [在Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)中创建数据视图。

1. [验证数据是否流入Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)。

1. [迁移项目和组件](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)。

1. 比较旧实施与新实施的数据，确保您了解任何差异及其存在原因。

1. 规划用户入门。

   与 Adobe Analytics 一样，Analysis Workspace 是 Customer Journey Analytics 中面向用户的主要工具。但是，用户需要注意在 Customer Journey Analytics 中使用 Analysis Workspace 时的一些关键差异。

   您应该给予用户充足的时间（3 - 6 个月）来熟悉 Customer Journey Analytics 中 Analysis Workspace 的主要区别。

   有关 Adobe Analytics 和 Customer Journey Analytics 之间的一些主要差异的信息，请参阅 [Adobe Analytics 用户指南](/help/getting-started/aa-to-cja-user.md)。

1. 禁用AppMeasurement数据收集。

1. 禁用Analytics源连接器。

   对于Experience PlatformWeb SDK实施，仅需要Analytics Source Connector才能使用Adobe Analytics历史数据，并且将原始实施的数据与新实施的数据进行比较。

   当您的新实施中有足够的历史数据并且熟悉Customer Journey Analytics中的报表差异时，您应该关闭Analytics Source Connector。

## 为您的组织动态生成升级步骤

根据时间表和资源限制等多个因素，[了解建议的升级步骤](#1-understand-the-recommended-upgrade-steps)中所述的建议升级步骤可能对您的组织不实用。

要针对贵组织的独特环境动态生成升级步骤，请执行以下操作：

1. 完成[Adobe Analytics以Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。

   完成此调查表后，系统会为您提供分步说明，概述组织要求所特有的最佳升级步骤。 这些升级步骤最符合您现有的Adobe Analytics环境和Customer Journey Analytics目标。

1. 按照生成的分步说明升级到Customer Journey Analytics。

<!--

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 



When upgrading from Adobe Analytics to Customer Journey Analytics, no single set of upgrade steps exist that are optimal for every organization.

Adobe recommends using the dynamically generated upgrade steps that are unique to your organization. These upgrade steps are generated after you complete an upgrade questionnaire, which helps you understand the best way for your organization to upgrade to Customer Journey Analytics. 

Generic upgrade steps are also available.

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK provides the best foundation to get the most out of Customer Journey Analytics. 
   
   It is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics:

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   The Analytics source connector is a recommended part of the piece when upgrading to Customer Journey Analytics. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->

<!--

   When you no longer need the Analytics source connector because you have enough historical data from your new implementation and you are familiar with the reporting differences in Customer Journey Analytics, you should turn off the Analytics source connector. With the Experience Platform Web SDK implementation, the Analytics source connector is not needed.  
   
   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 
   
-->









