---
title: 从Adobe Analytics升级到Customer Journey Analytics时推荐的路径
description: 了解从Adobe Analytics升级到Customer Journey Analytics时推荐的路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: dbeb3cabeaa7586e8a024a46e7ae42984e9c1c09
workflow-type: tm+mt
source-wordcount: '1499'
ht-degree: 5%

---

# 从Adobe Analytics升级到Customer Journey Analytics

从Adobe Analytics升级到Customer Journey Analytics时，Adobe建议与Analytics源连接器一起实施新的Experience PlatformWeb SDK，如[为大多数组织推荐的升级步骤](#recommended-upgrade-steps-for-most-organizations)中所述。

根据时间表和资源限制等多个因素，建议的升级步骤可能对您的组织不实用。 在这种情况下，请使用[Adobe AnalyticsCustomer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)来动态生成针对贵组织独特环境量身定制的升级步骤。

## 为大多数组织推荐的升级步骤

>[!NOTE]
>
>此部分中描述的升级步骤是推荐的升级步骤，任何组织都可以使用该步骤成功从Adobe Analytics升级到Customer Journey Analytics。
>
>但是，根据时间表和资源限制等多个因素，建议的升级步骤可能对您的组织不实用。 在这种情况下，请使用[Adobe AnalyticsCustomer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)来动态生成针对贵组织独特环境量身定制的升级步骤。

建议的从Adobe Analytics升级到Customer Journey Analytics的过程是Experience PlatformWeb SDK的新实现，该方法是Customer Journey Analytics的首选数据收集方法。 在与Web SDK结合使用时，Adobe还建议使用Analytics源连接器来帮助您过渡到Customer Journey Analytics。 使用Analytics Source Connector保留Adobe Analytics历史数据并执行并排数据比较。

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

以下步骤概述了从Adobe Analytics升级到Customer Journey Analytics的推荐过程。

每个步骤都提供了对更详细过程的高级解释。 按照每个步骤的链接完成其相关任务，然后返回此页面并继续流程中的下一步。

1. [规划XDM架构架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)。

1. [在Adobe Experience Platform中创建所需的自定义架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

   创建架构时，请考虑以下选项：

   * 如果要将Customer Journey Analytics与RTCDP集成，必须在架构上启用&#x200B;**[!UICONTROL 配置文件]**&#x200B;选项，如[创建要与Customer Journey Analytics一起使用的XDM架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)中所述。 启用此选项后，如果数据被摄取到基于此架构的数据集中，则该数据会合并到实时客户个人资料中。

   * 如果要包含流媒体数据，您必须[将架构配置为摄取和使用流媒体数据](/help/data-ingestion/streaming.md)。

1. [在Adobe Experience Platform中创建数据集](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)。

1. （可选）如果在Adobe Analytics中使用分类数据，则可以在Customer Journey Analytics中将分类数据添加到数据集。

   为此，[为每个包含分类数据的维度创建一个查找数据集](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)。

1. 对于使用AppMeasurement或Analytics扩展（标记）的Adobe Analytics实施，[在Adobe Experience Platform中创建数据流](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)。<!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   对于使用Web SDK的Adobe Analytics实施，已存在数据流。

1. [将Adobe Experience Platform作为服务添加到您的数据流](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)。

1. （可选）如果要将Customer Journey Analytics与Adobe Journey Optimizer集成，请在实施中使用个性化对象，以便在Adobe Journey Optimizer中使用。

1. （可选）使用Analytics Source Connector从Adobe Analytics引入历史数据：

   1. [为Analytics源连接器创建架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

   1. [创建Analytics源连接器并映射字段](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

   1. [将Analytics源连接器数据集添加到连接](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)。

1. 展开描述如何为Customer Journey Analytics实施实施Experience PlatformWeb SDK的部分，然后完成相关步骤：

   +++手动实施（JS文件）

   1. [将alloy.js添加到您的站点](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22)。

   1. 填充XDM对象并将其发送到数据流。

+++

   +++标记

   1. [在您的网站上实施加载器标记](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md)。

   1. [创建标记属性并添加Adobe Experience Platform Web SDK扩展](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)。

   1. [将XDM数据收集逻辑添加到您的标记](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md)。

+++

+++ API

   1. 使用Edge NetworkAPI将数据发送到所需的数据流。

+++

1. 验证Web SDK实施是否向数据集发送数据。

1. [在Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)中创建连接。

1. （可选）将Web数据与来自其他渠道的数据（例如呼叫中心数据）绑定。

   您可以通过向Customer Journey Analytics连接添加其他数据集来实现这一点。

1. [在Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)中创建数据视图。

1. [验证数据是否流入Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)。

1. [迁移项目和组件](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)。

1. （可选）如果您在Adobe Analytics中使用营销渠道，则可以[在Customer Journey Analytics](/help/data-views/derived-fields/derived-fields.md#marketing-channels)中创建营销渠道派生的字段。

   派生字段是Customer Journey Analytics中实时报表的一个重要方面。 利用派生字段，可通过可自定义的规则生成器，即时定义（通常非常复杂的）数据操作。

   派生字段的一种用法是定义派生营销渠道字段，该字段根据一个或多个条件（例如，URL参数、页面URL、页面名称）确定正确的营销渠道。

   在派生字段中使用[营销渠道函数模板](/help/data-views/derived-fields/derived-fields.md#marketing-channels)快速创建营销渠道的派生字段。

1. 比较旧实施与新实施的数据，确保您了解任何差异及其存在原因。

1. 了解Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)中的[功能支持。 Customer Journey Analytics支持大多数Adobe Analytics功能，Customer Journey Analytics还提供了许多其他功能。

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
