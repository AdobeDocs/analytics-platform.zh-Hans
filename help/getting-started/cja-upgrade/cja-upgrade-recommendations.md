---
title: 从Adobe Analytics升级到Customer Journey Analytics时推荐的路径
description: 了解从Adobe Analytics升级到Customer Journey Analytics时推荐的路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%

---

# 从Adobe Analytics升级到Customer Journey Analytics

在开始从Adobe Analytics升级到Customer Journey Analytics的升级过程之前，请先了解建议的升级步骤。

根据时间表和资源限制等多个因素，建议的升级步骤可能对您的组织不实用。 了解建议的升级步骤后，请完成调查表以动态生成针对贵组织独特环境定制的升级步骤。

## 1.了解建议的升级步骤

>[!NOTE]
>
>此部分中描述的升级步骤是推荐的升级步骤，任何组织都可以使用该步骤成功从Adobe Analytics升级到Customer Journey Analytics。
>
>但是，根据时间表和资源限制等多个因素，建议的升级步骤可能对您的组织不实用。 了解建议的升级步骤后，请完成[Adobe Analytics以Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)以动态生成针对贵组织独特环境量身定制的升级步骤。

从Adobe Analytics升级到Customer Journey Analytics时，建议的步骤是实施Experience PlatformWeb SDK的新步骤，此方法是Customer Journey Analytics的首选数据收集方法。 在与Web SDK结合使用时，Adobe还建议使用Analytics源连接器，以便保留Adobe Analytics历史数据并执行并排数据比较。

完全过渡到Customer Journey Analytics后，可以关闭Analytics源连接器，并且可以专门使用Experience PlatformWeb SDK。

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

## 2.为您的组织动态生成升级步骤

根据时间表和资源限制等多个因素，[了解建议的升级步骤](#1-understand-the-recommended-upgrade-steps)中所述的建议升级步骤可能对您的组织不实用。

要查看针对贵组织独特环境动态生成的升级步骤，请执行以下操作：

1. 完成[Adobe Analytics以Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。

   完成此调查表后，系统会向您提供分步说明，概述组织特有的优化升级步骤。 这些升级步骤最符合您现有的Adobe Analytics环境和Customer Journey Analytics目标。

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









