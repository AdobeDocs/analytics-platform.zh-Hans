---
title: 从 Adobe Analytics 升级到 Customer Journey Analytics
description: 了解从 Adobe Analytics 升级到 Customer Journey Analytics 时的推荐步骤
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: 105b235c1a4791fd59cf65ae7f543a5fc08fc55d
workflow-type: tm+mt
source-wordcount: '3281'
ht-degree: 99%

---

# 从 Adobe Analytics 升级到 Customer Journey Analytics

从 Adobe Analytics 升级到 Customer Journey Analytics 时，您可以按照[建议的升级步骤](#recommended-upgrade-steps-for-most-organizations)操作。或者您可以为您组织的独特情况[动态生成升级步骤](#dynamically-generate-upgrade-steps-for-your-organization)。

## 适用于大多数组织的建议升级步骤 {#upgrade-process}

从 Adobe Analytics 升级到 Customer Journey Analytics 的推荐流程是对 Experience Platform Web SDK 进行新的实施，这是 Customer Journey Analytics 的首选数据收集方法。在结合使用 Web SDK 的同时，Adobe 还建议使用 Analytics 源连接器来帮助您过渡到 Customer Journey Analytics。使用 Analytics 源连接器来保留 Adobe Analytics 历史数据，并执行并排数据比较。

在您使用 Experience Platform Web SDK 获得足够的历史数据，并完全过渡到 Customer Journey Analytics 后，可以关闭 Analytics 源连接器，仅使用 Web SDK。

>[!NOTE]
>
>如果本节中描述的升级步骤不适合您的组织，请使用 Customer Journey Analytics 升级指南以动态生成适合您组织独特情况的升级步骤。（要从 Customer Journey Analytics 访问升级指南，请选择&#x200B;**[!UICONTROL 工作区]**&#x200B;选项卡，然后在左侧面板中选择&#x200B;**[!UICONTROL 升级到 Customer Journey Analytics]**。按照屏幕上的说明操作。）

### 高层建议升级流程 {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="从 Adobe Analytics 获取历史数据"
>abstract="将历史 Adobe Analytics 报告包数据引入 Adobe Experience Platform 和 Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

1. **实施 Experience Platform Web SDK（用于持续数据收集）**

   对 Experience Platform Web SDK 进行新的实施是收集 Customer Journey Analytics 数据的最佳方式。它为充分利用 Customer Journey Analytics 提供了最佳基础，因为它是实施 Customer Journey Analytics 的最高效、最直接、最具前瞻性的方法。

   * Adobe Experience Platform 专为支持实时个性化用例而构建，因此具有高性能报告和数据可用性

   * 在其他 Experience Cloud 产品（AJO、RTCDP 等）之间整合对 Adobe Experience Cloud 数据收集的实施

   * 不依赖于 Adobe Analytics 命名法（属性、eVar、事件等）

1. **设置 Adobe Analytics 源连接器（用于传输历史数据）**

   为了帮助顺利过渡到使用带有 Customer Journey Analytics 的 Experience Platform Web SDK，Adobe 还建议使用 Adobe Analytics 源连接器。这样，您就可以在 Customer Journey Analytics 中保留历史数据并查看现有 Adobe Analytics 实施中的数据，同时还能查看新 Experience Platform Web SDK 实施中的数据。

   Analytics 源连接器允许您：

   * 将 Adobe Analytics 历史报告包数据引入 Adobe Experience Platform 和 Customer Journey Analytics。

     只要您需要保留 Adobe Analytics 历史数据，就可以让 Analytics 源连接器一直运行。

   * 在 Customer Journey Analytics 中查看使用原始 Adobe Analytics 实施（AppMeasurement、Analytics 扩展或 Web SDK 扩展）收集的数据。您可以将此数据与新的 Web SDK 实施的数据进行对比。

     您可以让 Analytics 源连接器一直运行，直到您熟悉并适应这些差异为止。<!--elaborate on what those differences are? -->

   独立实施的 Analytics 源连接器不是使用 Customer Journey Analytics 的长期推荐方法。这是因为其存在高延迟、架构混乱且复杂、依赖于 Adobe Analytics 命名法（prop、eVar 等），以及最终难以从 Analytics 源连接器迁移到推荐使用的 Web SDK 实施。

### 详细的建议升级步骤

以下步骤概述了从 Adobe Analytics 升级到 Customer Journey Analytics 的推荐流程。

每一步都提供了一个更详细流程的高级解释。按照每个步骤的链接完成其相关任务，然后返回此页面，并继续执行该流程的下一步。

1. [规划您的 XDM 模式架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md){target="_blank"}。

1. [在 Adobe Experience Platform 中创建所需的自定义架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}。

   创建架构时请考虑以下选项：

   * 如果要将 Customer Journey Analytics 与 RTCDP 集成，则必须在架构上启用&#x200B;**[!UICONTROL 轮廓]**&#x200B;选项，如[创建用于 Customer Journey Analytics 的 XDM 架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}中所述。在启用该选项后，当数据被引入基于此架构的数据集中时，该数据将合并到实时客户轮廓。

   * 如果您想要包含流式处理媒体数据，则必须[将您的架构配置为可以摄取和使用流式传输数据](/help/data-ingestion/streaming.md){target="_blank"}。

1. [在 Adobe Experience Platform 中创建数据集](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md){target="_blank"}。

1. （可选）如果您在 Adobe Analytics 中使用分类数据，则可以将分类数据添加到 Customer Journey Analytics 中的数据集中。

   若要执行此操作，请[为包含分类数据的每个维度创建一个查找数据集](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md){target="_blank"}。

1. 对于使用 AppMeasurement 或 Analytics 扩展（标记）的 Adobe Analytics 实施，请[在 Adobe Experience Platform 中创建一个数据流](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md){target="_blank"}。<!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   对于使用 Web SDK 的 Adobe Analytics 实施，已经存在数据流。更多信息请参阅[配置现有的 Adobe Analytics Web SDK 实施，以将数据发送到 Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md){target="_blank"}。

1. [将 Adobe Experience Platform as a Service 添加到数据流中](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md){target="_blank"}。

1. （可选）如果您想将 Customer Journey Analytics 与 Adobe Journey Optimizer 集成，请在实施中使用个性化对象，以便在 Adobe Journey Optimizer 中使用。

1. 请扩展描述您希望如何为 Customer Journey Analytics 实施部署 Experience Platform Web SDK 的部分，然后完成相关步骤：

   +++手动实施（JS 文件）

   1. [将 alloy.js 添加到您的网站](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22){target="_blank"}。

   1. 填充 XDM 对象并将其发送到数据流。

   +++

   +++标记

   1. [创建一个标记属性，然后添加 Adobe Experience Platform Web SDK 扩展](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md){target="_blank"}。

   1. [将Adobe Experience Platform Web SDK扩展添加到标记属性](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md){target="_blank"}。

   1. [在您的网站上实施加载器标记](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md)。

   1. [将 XDM 数据收集逻辑添加到您的标记中](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md){target="_blank"}。

   +++

+++ API

   1. 使用 Edge Network API 将数据发送到所需的数据流。

+++

1. [验证您的 Web SDK 实施是否在将数据发送到数据集](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md){target="_blank"}。

1. [在 Customer Journey Analytics 中创建连接](/help/getting-started/cja-upgrade/cja-upgrade-connection.md){target="_blank"}。

1. （可选）将网络数据与来自其他渠道的数据（例如呼叫中心数据）联系起来。

   您可以通过在 Customer Journey Analytics 连接中添加其他数据集来实现此目的，如[导入呼叫中心和网络数据](/help/use-cases/cross-channel/call-center.md){target="_blank"}中所述。

1. [在 Customer Journey Analytics 中创建数据视图](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md){target="_blank"}。

1. [验证数据是否在流入 Customer Journey Analytics 中的数据视图](/help/getting-started/cja-upgrade/cja-upgrade-validate.md){target="_blank"}。

1. 在您的 Adobe Analytics 环境中，[使用 Analytics Inventory](https://experienceleague.adobe.com/zh-hans/docs/analytics/admin/admin-tools/analytics-inventory){target="_blank"} 了解 Adobe Analytics 环境的全面概述，包括项目和组件的数量、报告包、用户等。

1. [迁移项目和组件](https://experienceleague.adobe.com/zh-hans/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration){target="_blank"}。

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. （可选）如果您使用 Adobe Analytics 中的营销渠道，则可以[在 Customer Journey Analytics 中创建营销渠道派生字段](/help/data-views/derived-fields/derived-fields.md#marketing-channels){target="_blank"}。

   派生字段是 Customer Journey Analytics 中实时报告功能的一个重要方面。通过派生字段和可自定义的规则生成器，即可迅速定义（一般较为复杂的）数据操作。

   派生字段的一个用途是定义派生营销渠道字段，该字段会根据一个或多个条件（例如，URL 参数、页面 URL 或页面名称）确定适当的营销渠道。

   使用派生字段中的[营销渠道功能模板](/help/data-views/derived-fields/derived-fields.md#marketing-channels){target="_blank"}可以为营销渠道快速创建一个派生字段。

1. 将旧的实施中 Adobe Analytics 内的数据与新实施中 Customer Journey Analytics 内的数据进行比较，确保您了解所有差异及其存在的原因。<!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. 使用 Analytics 源连接器从 Adobe Analytics 中提取历史数据：

   >[!NOTE]
   >
   >如果您之前尚未创建 Analytics 源连接器，请按照以下步骤操作。
   >
   >如果您已将 Analytics 源连接器与 Customer Journey Analytics 结合使用，请按照[从 Analytics 源连接器过渡到 Customer Journey Analytics 的 Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md){target="_blank"}。

   1. [为 Analytics 源连接器创建 XDM 架构](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md){target="_blank"}。

   1. 如果您尚未拥有 Analytics 源连接器，请[创建 Analytics 源连接器并将字段映射到您的 XDM 架构](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md){target="_blank"}。

      或

      如果您已拥有 Analytics 源连接器，[则将字段从源连接器映射到 XDM 架构](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md){target="_blank"}。

   1. [将 Analytics 源连接器数据集添加到该连接](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md){target="_blank"}。

1. 规划用户加入流程。

   与 Adobe Analytics 一样，Analysis Workspace 是 Customer Journey Analytics 中面向用户的主要工具。但是，用户需要注意在 Customer Journey Analytics 中使用 Analysis Workspace 时的一些关键差异。

   您应该给予用户充足的时间（3 - 6 个月）来熟悉 Customer Journey Analytics 中 Analysis Workspace 的主要区别。

   有关 Adobe Analytics 和 Customer Journey Analytics 之间的一些主要差异的信息，请参阅 [Adobe Analytics 用户指南](/help/getting-started/aa-to-cja-user.md){target="_blank"}。

1. 了解[ Customer Journey Analytics 中的功能支持](/help/getting-started/aa-vs-cja/cja-aa.md){target="_blank"}。 Customer Journey Analytics 支持大多数 Adobe Analytics 功能，并且 Customer Journey Analytics 还提供了许多附加功能。

1. 当您的 Customer Journey Analytics Web SDK 完成实施并且您对所收集的数据感到满意时，请禁用 Adobe Analytics。

   Adobe 建议您在实施 Customer Journey Analytics 后让 Adobe Analytics 环境保持运行一段时间。

   有关升级期间和升级后 Adobe Analytics 的使用，以及禁用 Adobe Analytics 的建议时间的更多信息，请参阅[评估升级到 Customer Journey Analytics 后需要使用 Adobe Analytics 多长时间](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md){target="_blank"}。

## 为您的组织动态生成升级步骤

根据时间表和资源限制等多个因素，在[了解推荐的升级步骤](#recommended-upgrade-steps-for-most-organizations)中描述的推荐升级步骤可能并不适合您的组织。在这种情况下，您可以为您组织的独特情况动态生成升级步骤。生成这些步骤的过程会有所不同，具体取决于您是否有权访问 Customer Journey Analytics。

### 对于有权访问 Customer Journey Analytics 的客户

要为您组织的独特情况动态生成升级步骤：

1. 完成 Customer Journey Analytics 升级指南。

   在 Customer Journey Analytics 中选择&#x200B;**[!UICONTROL 工作区]**&#x200B;选项卡，然后在左侧面板中选择&#x200B;**[!UICONTROL 升级到 Customer Journey Analytics]**。按照屏幕上的说明操作。

   完成此升级指南后，会为您提供包含适合您组织要求的最佳升级步骤的分步说明。这些升级步骤最符合您现有的 Adobe Analytics 环境以及您在 Customer Journey Analytics 方面的目标。升级步骤可以提供为一个可共享链接或一个可下载的 .csv 文件。

1. 按照生成的分步说明升级到 Customer Journey Analytics。

### 对于无权访问 Customer Journey Analytics 的客户

要为您组织的独特情况动态生成升级步骤：

1. 请联系您的 Adobe 帐户团队以完成 Customer Journey Analytics 升级指南。

   您的 Adobe 帐户团队可以指导您完成升级指南，为您提供一个 .csv 文件，其中包含问题、您的回答以及为您的组织动态生成的独特的升级步骤。

   在联系您的 Adobe 帐户团队之前，请先熟悉 Customer Journey Analytics 升级指南中包含的问题，并确定您的回答。Customer Journey Analytics 升级指南包含以下问题和可能的回答：


   | 问题 | 可用的回答 | 其他信息 |
   |---------|----------|---------|
   | 选择描述您当前 Adobe Analytics 实施的选项。此信息可能会影响升级到 Customer Journey Analytics 时可能可用的其他可选的升级选项。 | 选择一个： <ul><li>**AppMeasurement：**<br/> JavaScript 实施方法，即在页面上加载 AppMeasurement.js，然后使用 s 对象（例如，s.eVar1）将数据发送给 Adobe。</li><li>**Adobe Analytics 扩展（标记）：**<br/>标记实施方法，即加载 Adobe Experience Platform 数据收集 (以前称为 Launch)。标记已安装 Adobe Analytics 扩展。</li><li>**Experience Platform Web SDK 扩展（标记）：**<br/>&#x200B;标记实施方法，即加载 Adobe Experience Platform 数据收集（以前称为 Launch）。标记已安装 Web SDK 扩展。</li><li>**Experience Platform Web SDK (alloy.js)：** JavaScript 实施方法，即在页面上加载 Web SDK 库 (alloy.js)，然后使用 JSON 负载将数据发送给 Adobe。</li><li>**批量数据插入 API：**<br/>&#x200B;这种实施方法使用数据插入 API 或批量数据插入 API。</li><li>**Experience Platform Mobile SDK：**<br/>&#x200B;这种实施方法使用 Adobe Experience Platform Mobile SDK。</li><li>**使用第三方标记管理工具的 AppMeasurement：**<br/>&#x200B;这种实施方法使用一个第三方标记管理工具。</li><li>**非 Adobe Analytics 产品：**<br/>&#x200B;这种实施方法为 Adobe Analytics 以外的产品（如 Google Analytics）收集数据。从非 Adobe Analytics 产品升级到 Customer Journey Analytics 时，选择此选项将禁用升级指南中不适用的几个选项。 </li><li>**我不知道：**<br/>&#x200B;如果您不是负责管理实施的人员，可以暂时选择此选项。</li></ul><p>如果适用，请选择：<ul><li>**我们的实施方法目前使用 Analytics 源连接器：**<br/> Analytics 源连接器可让您轻松获得 Customer Journey Analytics 的价值，但要求您同时支付 Adobe Analytics 和 Customer Journey Analytics 的费用。本指南可帮助您转向独立的 Web SDK 实施。</li></ul></p> | <ul><li>[了解您的 Adobe Analytics 实施情况及其对升级到 Customer Journey Analytics 的影响](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md#understand-your-adobe-analytics-implementation-and-how-it-affects-your-upgrade-to-customer-journey-analytics)</li><li>[从 Analytics 源连接器过渡到 Customer Journey Analytics 的 Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)</li></ul> |
   | 大多数 Adobe Analytics 功能在 Customer Journey Analytics 中已经可用。但是，在升级过程中需要考虑以下功能。请选择您计划使用的任何功能。 | 请选择所有适用项：<ul><li>**来自 Adobe Analytics 的历史数据：**</br>&#x200B;将您的 Adobe Analytics 报告包历史数据带入 Adobe Experience Platform 和 Customer Journey Analytics。</li><li>**来自 Adobe Analytics 的组件和项目：**</br>&#x200B;来自 Adobe Analytics 的组件包括：项目（及其相关的自由格式表和可视化图表）、区段和计算量度。</li><li>**Activity Map 叠加和链接跟踪：**</br>&#x200B;浏览器扩展，您可在网站上以叠加方式查看链接跟踪数据。</li><li>**分类数据：**</br>&#x200B;将数据分组或分类为单独的维度。</li><li>**营销渠道：**</br>&#x200B;创建对客户接触到网站的方式进行分类的规则。</li><li>**数据仓库：**</br>&#x200B;以电子表格格式从 Adobe Analytics 导出经过处理的数据。</li><li>**数据馈送：**&#x200B;Customer Journey Analytics 中尚未提供数据馈送的准确替代物。不过，也可以通过全表导出、平台数据集导出、BI 工具集成和报告 API 等功能实现类似的功能。</br></li><li>**流媒体数据：**</br> Adobe Analytics 和 Customer Journey Analytics 的附加组件，专门用于音频、视频或流式处理内容等媒体数据收集。</li></ul> | <ul><li>[了解升级到 Customer Journey Analytics 时对 Adobe Analytics 功能的支持](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)</li></ul> |
   | 大多数新功能在 Customer Journey Analytics 中已经可用。但是，在升级过程中需要考虑以下功能。请选择您计划使用的任何功能。 | 请选择所有适用项：<ul><li>**将收集的数据与其他来源的数据（例如联系中心的数据）结合起来：**</br>（推荐）将来自各种网络、移动和线下属性的数据结合起来，以创建关于客户行为的一个综合视图。将来自其他渠道的分析数据结合起来的能力是 Customer Journey Analytics 的主要用例。</li><li>**使用自定义维度拼接来自其他数据集的匹配项：**<br/>&#x200B;如果您的任何数据集不共享主要身份标识符（例如 Experience Cloud ID），您仍然可以使用其他维度（例如登录用户名或电子邮件地址）将该数据拼接在一起。</li><li>**与 Adobe Journey Optimizer 集成：**<br/>&#x200B;为客户传递贴合心意的、情境式、个性化的体验。</li><li>**与 Adobe Real-Time CDP 集成：**<br/>&#x200B;合并来自多个来源的轮廓数据，根据用户特征生成受众和区段。</li><li>**与 Adobe Target (A4T) 集成：**<br/> Adobe 建议与 Adobe Journey Optimizer 集成以实现个性化用例。可以与 Adobe Target 集成，但这只是短期的解决方案。</li><li>**与 Adobe Audience Manager 集成：**<br/> Adobe 建议与 Adobe Real-time CDP 集成，以实现基于受众的用例。可以与 Audience Manager 集成，但这只是短期的解决方案。</li></ul> | [了解 Customer Journey Analytics 独有的功能](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md) |
   | 选择您最终计划如何使用 Adobe Analytics 和 Customer Journey Analytics： | 选择一个： <ul><li>**我打算从 Adobe Analytics 完全换到 Customer Journey Analytics：**<br/>（推荐）Adobe 建议您从 Adobe Analytics 完全过渡到 Customer Journey Analytics。在过渡期间，您应该计划同时运行 Adobe Analytics 和 Customer Journey Analytics，以便执行并排数据比较。当您对数据满意时，可以禁用 Adobe Analytics。</li><li>**我打算保留这两种 Analytics 产品：**<br/>（不推荐）如果您选择此选项，您与 Adobe 签订的合同将同时包含 Adobe Analytics 和 Customer Journey Analytics，时间长了会增加您组织的开支。</li></ul> | [评估升级到 Customer Journey Analytics 后何时禁用 Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md) |
   | 选择如何配置 Customer Journey Analytics 架构： | 选择一个： <ul><li>**我想使用专门适合我的组织的架构：**</br>（推荐）自定义架构可让您的组织仅跟踪您需要的内容，避免那些与混乱和不需要的领域相关的开支。此选项包括 Web SDK 添加的字段组和您的组织自定义的字段组。</li><li>**我想使用默认的 Adobe Analytics 架构：**</br>（不推荐）Adobe Analytics 架构包含一千多个字段，这可能会导致架构混乱、复杂。您的组织将不得不继续遵守 props 和 eVars 的概念，这个旧版概念在 Customer Journey Analytics 不使用。与其他 Adobe Experience Platform 服务的集成更加困难。</li></ul> | [选择 Customer Journey Analytics 的架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) |
   | 选择您首选的实施 Customer Journey Analytics 的方式： | <ul><li>**手动实施（alloy.js）：**<br/>&#x200B;在您网站的每个页面上包含 Web SDK 库（alloy.js）。</li><li>**标记：**<br/>（推荐）如果您尚未使用标记，请在您的网站上安装标记加载器。如果您已经使用标记，可以将 Web SDK 扩展添加到您的标记属性。此选项包括使用 Adobe Experience Platform 数据收集和第三方标记管理系统中的标记的实施。</li><li>**API：**<br/>&#x200B;使用数据收集 API 将数据直接发送到数据流。支持非身份验证（客户端到服务器）和身份验证（服务器到服务器）两种类型。</li></ul> | [了解升级到 Customer Journey Analytics 的 Web SDK 实施选项](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md) |
   | （可选）选择另一个升级方法 | <ul><li>**仅使用 Analytics 源连接器：**<br/>（不推荐）您可以使用 Analytics 源连接器作为 Customer Journey Analytics 的唯一实施路径。<p>此选项通过快速将数据发送到 Customer Journey Analytics 来节省实施时间。不过，它也有各种不足之处，例如延迟较高，将来难以脱离 Adobe Analytics。</p></li><li>**我想将我的 AppMeasurement 逻辑与 Web SDK 结合使用：**<br/>&#x200B;通过数据对象以 AppMeasurement 格式发送所有变量，而不是通过 XDM 对象发送数据。<p>此选项允许您将 AppMeasurement 逻辑映射到 XDM，而不是从头开始填充 XDM 对象，从而节省实施时间。但是，随着时间的推移，它会带来更多的复杂性，因为您将来添加的任何字段都必须映射到数据流中的 XDM。</p></li><li>**我想将我的数据层发送给 Adobe，而无需进行额外的配置：**<br/>&#x200B;您可以通过数据对象将整个数据层发送给 Adobe，而不是通过 XDM 对象发送数据。<p>此选项允许您将数据层映射到 XDM，而不是从头开始填充 XDM 对象，从而节省实施时间。不过，这种映射的工作量很大，因为会有大量数据 Adobe 无法轻易解释。随着时间的推移，此选项还会带来更多的复杂性，因为您将来添加到数据中的任何字段都必须映射到数据流中的 XDM。</p></li></ul> | <ul><li>[升级替代方案：仅使用 Analytics 源连接器升级到 Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li><li>[升级替代方案：将 AppMeasurement 数据收集与 Experience Platform Web SDK 和 Customer Journey Analytics 结合使用](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[升级替代方案：将数据层发送到 Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)</li></ul> |

   与您的 Adobe 帐户团队一起完成此升级指南后，您将获得一个 .csv 文件，其中包含问题、您的回答以及最符合您现有的 Adobe Analytics 环境及 Customer Journey Analytics 目标的动态生成的升级步骤。

1. 按照 .csv 文件中生成的分步说明升级到 Customer Journey Analytics。

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
