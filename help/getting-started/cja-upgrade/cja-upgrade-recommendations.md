---
title: 从Adobe Analytics升级到Customer Journey Analytics
description: 了解从Adobe Analytics升级到Customer Journey Analytics时推荐的步骤
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: dafd4360d12c5b8a6b9ce99799722cecbca9768c
workflow-type: tm+mt
source-wordcount: '3249'
ht-degree: 18%

---

# 从Adobe Analytics升级到Customer Journey Analytics

从Adobe Analytics升级到Customer Journey Analytics时，您可以按照[建议的升级步骤](#recommended-upgrade-steps-for-most-organizations)操作。 或者，您可以[针对贵组织的独特情况动态生成升级步骤](#dynamically-generate-upgrade-steps-for-your-organization)。

## 为大多数组织推荐的升级步骤 {#upgrade-process}

建议的从Adobe Analytics升级到Customer Journey Analytics的过程是Experience Platform Web SDK的新实施，它是Customer Journey Analytics的首选数据收集方法。 在与Web SDK结合使用时，Adobe还建议使用Analytics Source Connector来帮助过渡到Customer Journey Analytics。 使用Analytics Source Connector保留Adobe Analytics历史数据并执行并排数据比较。

在使用Experience Platform Web SDK获得足够的历史数据并完全过渡到Customer Journey Analytics后，可以关闭Analytics源连接器并专门使用Web SDK。

>[!NOTE]
>
>如果本节所述的升级步骤对贵组织不实用，请使用Customer Journey Analytics升级指南动态生成针对贵组织独特环境定制的升级步骤。 (要从Customer Journey Analytics访问指南，请选择&#x200B;**[!UICONTROL Workspace]**&#x200B;选项卡，然后在左侧面板中选择&#x200B;**[!UICONTROL 升级到Customer Journey Analytics]**。 按照屏幕上的说明操作。)

### 高层建议升级流程 {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="从 Adobe Analytics 获取历史数据"
>abstract="将历史 Adobe Analytics 报告包数据引入 Adobe Experience Platform 和 Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

1. **实施Experience Platform Web SDK（用于持续的数据收集）**

   Experience Platform Web SDK的新实施是为Customer Journey Analytics收集数据的最佳方式。 它提供了充分利用Customer Journey Analytics的最佳基础，因为它是用于实施Customer Journey Analytics的最高性能、最直接且最符合未来需求的方法。

   * 高性能报表和数据可用性，因为Adobe Experience Platform构建用于支持实时个性化用例

   * 在其他Adobe Experience Cloud产品(AJO、RTCDP等)之间整合Experience Cloud数据收集的实施

   * 不依赖于Adobe Analytics命名法(属性、eVar、事件等)

1. **设置Adobe Analytics源连接器（用于引入历史数据）**

   为了帮助顺利过渡到将Experience Platform Web SDK与Customer Journey Analytics结合使用，Adobe还建议使用Adobe Analytics源连接器。 这样，您就可以在Customer Journey Analytics中保留现有Adobe Analytics实施的历史数据和查看数据，并与新的Experience Platform Web SDK实施中的数据并存。

   Analytics源连接器允许您：

   * 将历史 Adobe Analytics 报告包数据引入 Adobe Experience Platform 和 Customer Journey Analytics。

     您可以保持Analytics Source Connector运行，只要您需要保留Adobe Analytics历史数据即可。

   * 在Customer Journey Analytics中查看通过原始Adobe Analytics实施(AppMeasurement、Analytics扩展或Web SDK扩展)收集的数据。 您可以并排比较此数据与新的Web SDK实施数据。

     您可以保持Analytics Source Connector运行，直到您熟悉并熟悉这些差异为止。<!--elaborate on what those differences are? -->

   建议不要将Analytics Source Connector作为独立实施来长期使用Customer Journey Analytics。 这是由于高延迟、架构复杂杂乱、依赖于Adobe Analytics命名法(prop、eVar等)，以及难以最终从Analytics源连接器迁移到建议的Web SDK实施。

### 详细的建议升级步骤

以下步骤概述了从Adobe Analytics升级到Customer Journey Analytics的推荐过程。

每个步骤都提供了对更详细过程的高级解释。 按照每个步骤的链接完成其相关任务，然后返回此页面并继续流程中的下一步。

1. [规划XDM架构架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)。

1. [在Adobe Experience Platform中创建所需的自定义架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

   创建架构时，请考虑以下选项：

   * 如果要将Customer Journey Analytics与RTCDP集成，则必须在架构上启用&#x200B;**[!UICONTROL 配置文件]**&#x200B;选项，如[创建要与Customer Journey Analytics一起使用的XDM架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)中所述。 启用此选项后，如果数据被摄取到基于此架构的数据集中，则该数据会合并到实时客户个人资料中。

   * 如果要包含流媒体数据，您必须[将架构配置为摄取和使用流媒体数据](/help/data-ingestion/streaming.md)。

1. [在Adobe Experience Platform中创建数据集](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)。

1. （可选）如果在Adobe Analytics中使用分类数据，则可以在Customer Journey Analytics中将分类数据添加到数据集。

   为此，[为每个包含分类数据的维度创建一个查找数据集](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)。

1. 对于使用AppMeasurement或Analytics扩展（标记）的Adobe Analytics实施，[在Adobe Experience Platform中创建数据流](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)。<!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   对于使用Web SDK的Adobe Analytics实施，已存在数据流。 有关详细信息，请参阅[配置现有Adobe Analytics Web SDK实施以将数据发送到Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)。

1. [将Adobe Experience Platform作为服务添加到您的数据流](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)。

1. （可选）如果要将Customer Journey Analytics与Adobe Journey Optimizer集成，请在实施中使用个性化对象，以便在Adobe Journey Optimizer中使用。

1. 展开描述如何为Customer Journey Analytics实施实施Experience Platform Web SDK的部分，然后完成相关步骤：

   +++手动实施（JS文件）

   1. [将alloy.js添加到您的站点](https://experienceleague.adobe.com/en/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22)。

   1. 填充XDM对象并将其发送到数据流。

+++

   +++标记

   1. [创建标记属性并添加Adobe Experience Platform Web SDK扩展](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)。

   1. [将 Adobe Experience Platform Web SDK 扩展添加到您的标记属性](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)

   1. [在您的网站上实施加载器标记](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md)。

   1. [将XDM数据收集逻辑添加到您的标记](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md)。

+++

+++ API

   1. 使用Edge Network API将数据发送到所需的数据流。

+++

1. [验证您的Web SDK实施是否正在将数据发送到数据集](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md)。

1. [在Customer Journey Analytics中创建连接](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)。

1. （可选）将Web数据与来自其他渠道的数据（例如呼叫中心数据）绑定。

   如[导入呼叫中心和Web数据](/help/use-cases/cross-channel/call-center.md)中所述，您可以通过向Customer Journey Analytics连接添加其他数据集来实现这一点。

1. [在Customer Journey Analytics中创建数据视图](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)。

1. [验证数据是否流入Customer Journey Analytics中的数据视图](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)。

1. [迁移项目和组件](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)。

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. （可选）如果您在Adobe Analytics中使用营销渠道，则可以[在Customer Journey Analytics](/help/data-views/derived-fields/derived-fields.md#marketing-channels)中创建派生营销渠道字段。

   派生字段是Customer Journey Analytics中实时报表的一个重要方面。 利用派生字段，可通过可自定义的规则生成器，即时定义（通常非常复杂的）数据操作。

   派生字段的一种用法是定义派生营销渠道字段，该字段根据一个或多个条件（例如，URL参数、页面URL或页面名称）确定正确的营销渠道。

   在派生字段中使用[营销渠道函数模板](/help/data-views/derived-fields/derived-fields.md#marketing-channels)快速创建营销渠道的派生字段。

1. 比较Adobe Analytics中旧实施的数据与Customer Journey Analytics中新实施的数据，确保您了解任何差异及其存在原因。<!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. 使用Analytics Source Connector从Adobe Analytics引入历史数据：

   >[!NOTE]
   >
   >如果之前未创建Analytics源连接器，请使用以下步骤。
   >
   >如果您已将Analytics Source Connector与Customer Journey Analytics一起使用，请按照[从Analytics Source Connector过渡到Customer Journey Analytics的Web SDK ](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)中的步骤操作。

   1. [为 Analytics 源连接器创建 XDM 架构](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

   1. 如果您还没有Analytics源连接器，请[创建Analytics源连接器并将字段映射到XDM架构](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

      或

      如果您已有Analytics源连接器，请将源连接器中的[字段映射到XDM架构](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)。

   1. [将Analytics源连接器数据集添加到连接](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)。

1. 规划用户入门。

   与 Adobe Analytics 一样，Analysis Workspace 是 Customer Journey Analytics 中面向用户的主要工具。但是，用户需要注意在 Customer Journey Analytics 中使用 Analysis Workspace 时的一些关键差异。

   您应该给予用户充足的时间（3 - 6 个月）来熟悉 Customer Journey Analytics 中 Analysis Workspace 的主要区别。

   有关 Adobe Analytics 和 Customer Journey Analytics 之间的一些主要差异的信息，请参阅 [Adobe Analytics 用户指南](/help/getting-started/aa-to-cja-user.md)。

1. 了解Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)中的[功能支持。 Customer Journey Analytics支持大多数Adobe Analytics功能，Customer Journey Analytics还提供了许多其他功能。

1. 在Customer Journey Analytics Web SDK实施完成并对收集的数据感到满意时禁用Adobe Analytics。

   Adobe建议您在实施Adobe Analytics后的一段时间内保持Customer Journey Analytics环境运行。

   有关升级期间和升级后使用Adobe Analytics以及禁用Adobe Analytics的建议时间的更多信息，请参阅[评估升级到Customer Journey Analytics后需要Adobe Analytics多久](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md)。

## 为您的组织动态生成升级步骤

根据时间表和资源限制等多个因素，[了解建议的升级步骤](#recommended-upgrade-steps-for-most-organizations)中所述的建议升级步骤可能对您的组织不实用。 在这种情况下，您可以针对组织的独特环境动态生成升级步骤。 根据您是否已访问Customer Journey Analytics，生成这些步骤的过程会有所不同。

### 适用于有权访问Customer Journey Analytics的客户

要针对贵组织的独特环境动态生成升级步骤，请执行以下操作：

1. 完成Customer Journey Analytics升级指南。

   在Customer Journey Analytics中，选择&#x200B;**[!UICONTROL Workspace]**&#x200B;选项卡，然后在左侧面板中选择&#x200B;**[!UICONTROL 升级到Customer Journey Analytics]**。 按照屏幕上的说明操作。

   完成本升级指南后，将向您提供分步说明，概述组织要求所特有的最佳升级步骤。 这些升级步骤最符合您现有的Adobe Analytics环境和Customer Journey Analytics目标。 升级步骤以可共享链接或可下载.csv文件的形式提供。

1. 按照生成的分步说明升级到Customer Journey Analytics。

### 适用于尚未有权访问Customer Journey Analytics的客户

要针对贵组织的独特环境动态生成升级步骤，请执行以下操作：

1. 请联系您的Adobe客户团队以完成《Customer Journey Analytics升级指南》。

   您的Adobe客户团队可以帮助您完成升级指南，并为您提供一个.csv文件，其中包含您的问题、您的答案以及特定于贵组织的动态生成的升级步骤。

   在联系您的Adobe客户团队之前，请熟悉《Customer Journey Analytics升级指南》中包含的问题并确定您的答案。 《Customer Journey Analytics升级指南》包含以下问题和可能的答案：


   | 问题 | 可用答案 | 其他信息 |
   |---------|----------|---------|
   | 选择描述您当前 Adobe Analytics 实施的选项。此信息可能会影响升级到 Customer Journey Analytics 时可能可用的其他可选的升级选项。 | 选择一个： <ul><li>**AppMeasurement：**<br/>&#x200B;在页面上加载AppMeasurement.js并使用s对象(例如，s.eVar1)将数据发送到Adobe的JavaScript实施。</li><li>**Adobe Analytics扩展（标记）：** <br/>加载Adobe Experience Platform数据收集（以前称为Launch）的标记实现。 标记已安装 Adobe Analytics 扩展。</li><li>**Experience Platform Web SDK扩展（标记）：**<br/>&#x200B;加载Adobe Experience Platform数据收集（以前称为Launch）的标记实施。 标记已安装 Web SDK 扩展。</li><li>**Experience Platform Web SDK (alloy.js)：**&#x200B;一种JavaScript实现，可在页面上加载Web SDK库(alloy.js)，并使用JSON有效负载将数据发送到Adobe。</li><li>**批量数据插入API：**<br/>&#x200B;使用数据插入API或批量数据插入API的实现。</li><li>**Experience Platform Mobile SDK：**<br/>&#x200B;使用Adobe Experience Platform Mobile SDK的实现。</li><li>**使用第三方标记管理工具的AppMeasurement：**<br/>&#x200B;使用第三方标记管理工具的实现。</li><li>**非Adobe Analytics产品：**<br/>&#x200B;为Adobe Analytics以外的产品(如Google Analytics)收集数据的实现。 从非 Adobe Analytics 产品升级到 Customer Journey Analytics 时，选择此选项将禁用升级指南中不适用的几个选项。 </li><li>**我不知道：**<br/>&#x200B;如果您不是实施的管理人，则可以临时选择此选项。</li></ul><p>如果适用，请选择：<ul><li>**我们的实施当前使用Analytics Source Connector：**<br/> Analytics Source Connector允许您轻松地从Customer Journey Analytics中获得价值，但需要您同时为Adobe Analytics和Customer Journey Analytics付费。 本指南可帮助您转向独立的 Web SDK 实施。</li></ul></p> | <ul><li>[了解您的Adobe Analytics实施以及它如何影响您升级到Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md#understand-your-adobe-analytics-implementation-and-how-it-affects-your-upgrade-to-customer-journey-analytics)</li><li>[从Analytics源连接器过渡到Customer Journey Analytics的Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)</li></ul> |
   | 大多数 Adobe Analytics 功能在 Customer Journey Analytics 中已经可用。但是，在升级过程中需要考虑以下功能。请选择您计划使用的任何功能。 | 请选择所有适用项：<ul><li>**来自Adobe Analytics的历史数据：**</br>&#x200B;将您的Adobe Analytics历史报表包数据引入Adobe Experience Platform和Customer Journey Analytics。</li><li>Adobe Analytics中的&#x200B;**组件和项目：**</br> Adobe Analytics中的组件包括：项目（及其相关自由格式表和可视化图表）、区段和计算量度。</li><li>**活动图叠加和链接跟踪：**</br>&#x200B;一种浏览器扩展，允许您在网站上将链接跟踪数据显示为叠加图。</li><li>**分类数据：**</br>&#x200B;将数据分组或分类为单独的维度。</li><li>**营销渠道：**</br>&#x200B;创建规则以分类客户如何到达您的网站。</li><li>**Data Warehouse：**</br>&#x200B;以电子表格格式从Adobe Analytics导出已处理数据。</li><li>**数据馈送：**Customer Journey Analytics中尚未提供数据馈送的确切替代项。 但是，使用完整的表导出、Platform数据集导出、BI工具集成和报告API等功能可以实现类似的功能。</br></li><li>**流媒体数据：**</br> Adobe Analytics和Customer Journey Analytics的附加产品，专门用于收集媒体（如音频、视频或流式内容）数据。</li></ul> | <ul><li>[了解升级到Customer Journey Analytics时Adobe Analytics功能支持](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)</li></ul> |
   | 大多数新功能在 Customer Journey Analytics 中已经可用。但是，在升级过程中需要考虑以下功能。请选择您计划使用的任何功能。 | 请选择所有适用项：<ul><li>**将收集的数据与来自其他来源的数据（如联系中心数据）绑定：**</br>（推荐）将来自各种Web、移动和离线属性的数据绑定以创建单个整合的客户行为视图。 将来自其他渠道的分析数据结合起来的能力是 Customer Journey Analytics 的主要用例。</li><li>**使用自定义维度拼接来自其他数据集的点击：**<br/>&#x200B;如果任何数据集不共享主标识符(如Experience Cloud ID)，您仍然可以使用其他维度（如登录用户名或电子邮件地址）将该数据拼接在一起。</li><li>**与Adobe Journey Optimizer集成：**<br/>&#x200B;为客户提供互联、情境式和个性化的体验。</li><li>**与Adobe Real-Time CDP集成：**<br/>&#x200B;合并来自多个来源的配置文件数据以根据用户特征生成受众和区段。</li><li>**与Adobe Target (A4T)集成：**<br/> Adobe建议与Adobe Journey Optimizer集成以提供个性化用例。 可以与 Adobe Target 集成，但这只是短期的解决方案。</li><li>**与Adobe Audience Manager集成：**<br/> Adobe建议基于受众用例与Adobe Real-time CDP集成。 可以与 Audience Manager 集成，但这只是短期的解决方案。</li></ul> | [了解Customer Journey Analytics独有的功能](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md) |
   | 选择您最终计划如何使用 Adobe Analytics 和 Customer Journey Analytics： | 选择一个： <ul><li>**我打算从Adobe Analytics完全迁移到Customer Journey Analytics：**<br/>（推荐）Adobe建议您从Adobe Analytics完全迁移到Customer Journey Analytics。 在过渡期间，您应该计划同时运行 Adobe Analytics 和 Customer Journey Analytics，以便执行并排数据比较。当您对数据满意时，可以禁用 Adobe Analytics。</li><li>**我打算保留两个Analytics产品：**<br/>（不推荐）如果选择此选项，则您与Adobe签订的合同将同时包括Adobe Analytics和Customer Journey Analytics，这可能会使贵组织在一段时间内更加昂贵。</li></ul> | [评估升级到Customer Journey Analytics后何时禁用Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md) |
   | 选择如何配置 Customer Journey Analytics 架构： | 选择一个： <ul><li>**我想使用为我的组织量身定制的架构：**</br>（推荐）自定义架构可让您的组织仅跟踪您需要的内容，并避免与混乱和不需要的字段相关的开销。 此选项包括 Web SDK 添加的字段组和您的组织自定义的字段组。</li><li>**我想使用默认的Adobe Analytics架构：**</br>（不推荐） Adobe Analytics架构包含一千个以上的字段，这可能会导致架构混乱而复杂。 您的组织将不得不继续遵守 props 和 eVars 的概念，这个旧版概念在 Customer Journey Analytics 不使用。与其他 Adobe Experience Platform 服务的集成更加困难。</li></ul> | [选择您的Customer Journey Analytics架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) |
   | 选择您首选的实施 Customer Journey Analytics 的方式： | <ul><li>**手动实施(alloy.js)：**<br/>&#x200B;在网站的每个页面上包含Web SDK库(alloy.js)。</li><li>**标记：**<br/>（推荐）如果您尚未使用标记，请在您的网站上安装标记加载器。 如果您已经使用标记，可以将 Web SDK 扩展添加到您的标记属性。此选项包括使用 Adobe Experience Platform 数据收集和第三方标记管理系统中的标记的实施。</li><li>**API：**<br/>&#x200B;使用数据收集API将数据直接发送到数据流。 支持非身份验证（客户端到服务器）和身份验证（服务器到服务器）两种类型。</li></ul> | [了解升级到Customer Journey Analytics时的Web SDK实施选项](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md) |
   | （可选）选择替代升级方法 | <ul><li>**Soley使用Analytics Source Connector：**<br/>（不推荐）您可以将Analytics Source Connector用作Customer Journey Analytics的唯一实施路径。<p>此选项通过快速向Customer Journey Analytics发送数据来节省实施时间。 不过，它也有各种不足之处，例如延迟较高，将来难以脱离 Adobe Analytics。</p></li><li>**我希望在Web SDK中使用我的AppMeasurement逻辑：**<br/>&#x200B;不要通过XDM对象发送数据，而要通过数据对象以AppMeasurement格式发送所有变量。<p>此选项允许您将AppMeasurement逻辑映射到XDM，而不是从头开始填充XDM对象，从而节省实施时间。 但是，随着时间的推移，它会带来更多的复杂性，因为您将来添加的任何字段都必须映射到数据流中的 XDM。</p></li><li>**我想在不进行额外配置的情况下将数据层发送到Adobe：**<br/>&#x200B;您可以通过数据对象将整个数据层发送到Adobe，而不是通过XDM对象发送数据。<p>此选项允许您将数据层映射到XDM，而不是从头开始填充XDM对象，从而节省实施时间。 不过，这种映射的工作量很大，因为会有大量数据 Adobe 无法轻易解释。随着时间的推移，此选项还会带来更多的复杂性，因为您将来添加到数据中的任何字段都必须映射到数据流中的 XDM。</p></li></ul> | <ul><li>[升级替代方案：仅使用Analytics Source Connector升级到Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li><li>[升级替代方案：将AppMeasurement数据收集与Experience Platform Web SDK和Customer Journey Analytics结合使用](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[升级替代方案：将数据层发送到Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)</li></ul> |

   与您的Adobe客户团队完成本升级指南后，将为您提供一个.csv文件，其中包含问题、您的答案以及动态生成的升级步骤，这些步骤最符合您的现有Adobe Analytics环境和Customer Journey Analytics的目标。

1. 按照.csv文件中生成的分步说明升级到Customer Journey Analytics。

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
