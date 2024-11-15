---
title: 选择您的Customer Journey Analytics升级路径
description: 了解升级到Customer Journey Analytics时可能升级路径的优缺点
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 84bdb6044dead11cdb7718179b8eb32917b1c8de
workflow-type: tm+mt
source-wordcount: '2895'
ht-degree: 0%

---

# 第2步：选择升级路径

+++展开此部分，查看此页面上的信息在较大的升级过程中的位置。 确保已完成所有以前的升级步骤。

在继续此部分之前，请先确保已完成所有以前的升级任务。

此页面上的信息介绍了升级过程的步骤2，如下表所示：

| 升级任务 | 详细信息 |
|---------|----------|
| **步骤1：[开始升级](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | 了解升级到Customer Journey Analytics的好处以及基本的升级过程。 |
| <span class="preview">**步骤2：选择升级路径**</span> | <span class="preview">有多种方法可用于升级到Customer Journey Analytics。 根据贵组织当前的Adobe Analytics环境和长期目标，选择最适合贵组织的方法。</span> |
| **步骤3：[将数据发送到Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | 将数据发送到Adobe Experience Platform的过程因您在步骤2中选择的升级路径而异。 |
| **步骤4：[保留历史数据](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | 大多数组织都需要将其历史Adobe Analytics数据保留一定时间。 可以使用各种选项来完成此操作。 |
| **步骤5：[执行其他实施任务](/help/getting-started/cja-getting-started.md)** | 在升级过程的这一阶段，您需要在Customer Journey Analytics环境准备就绪之前执行各种任务。<p>这些附加任务适用于从Adobe Analytics升级以及新的Customer Journey Analytics实施。</p><p>这些任务包括：</p><ul><li>将其他数据引入Experience Platform</li><li>在Platform数据集与Customer Journey Analytics之间创建连接</li><li>创建数据视图</li><li>移植报表API使用情况</li><li>考虑数据馈送和Data Warehouse</li><li>迁移项目和组件</li><li>Planning用户载入</li></ul> <p>有关详细信息，请参阅[Customer Journey Analytics快速入门](/help/getting-started/cja-getting-started.md)。 |

{style="table-layout:auto"}

+++

在决定升级到Customer Journey Analytics后，您需要确定组织的最佳升级路径。

为从Adobe Analytics升级到Customer Journey Analytics而选择的路径取决于以下因素：

* 您现有的Adobe Analytics实施

* 您的未来目标

使用此页上的信息可确定哪种Customer Journey Analytics升级路径最符合贵组织的当前实施和未来目标。

要确定组织的最佳升级路径，应按顺序阅读以下部分：

1. 首先，[了解可用的升级路径](#understand-upgrade-paths)。

1. 然后，[评估您可用的升级路径](#assess-the-upgrade-paths-available-to-you-based-on-your-current-adobe-analytics-implementation)。

1. 最后，[权衡每个升级路径](#weigh-the-advantages-and-disadvantages-of-the-upgrade-paths-available-to-you)的优缺点。

## 了解升级路径

从Adobe Analytics升级到Customer Journey Analytics存在各种升级路径。

通常，每个升级路径在执行升级所需的工作量级别以及升级完成后实现的长期可行性方面有所不同。

下表列出了每种升级路径、其工作量级别及其长期可行性：

| 升级路径 | 工作量 | 长期生存能力 |
|---------|----------|---------|
| **使用Analytics源连接器的Experience PlatformWeb SDK的新实现**</br>&#x200B;您可以通过执行Experience PlatformWeb SDK的新实现来开始使用Customer Journey Analytics。 这样，您就可以开始向Adobe Experience PlatformEdge Network和Customer Journey Analytics发送数据。 此外，还可使用Analytics Source Connector将历史数据纳入Customer Journey Analytics。<p>对于尚未使用Web SDK的组织，此升级路径可能是将数据导入Edge Network的最直接方法，因为它所需的步骤最少；但是，由于所有工作都是预先完成的（例如创建XDM架构），因此它需要更大的初始工作。</p><p>基本步骤为：</p><ol><li>为您的组织创建XDM架构。</li><li>实施Web SDK。</li><li>将数据发送到Platform。</li><li>设置Analytics源连接器。</br>Analytics Source Connector用于将历史Adobe Analytics数据引入Customer Journey Analytics。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--></li></ol><p><!-- **Note:** This is the recommended upgrade path when upgrading to Customer Journey Analytics. For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). --></p> | 高 | 高 |
| **Experience PlatformWeb SDK的新实现**</br>&#x200B;您可以通过执行Customer Journey AnalyticsWeb SDK的新实现来开始使用Experience Platform。 这样，您就可以开始向Adobe Experience PlatformEdge Network和Customer Journey Analytics发送数据。 <p>对于尚未使用Web SDK的组织，此升级路径可能是将数据导入Edge Network的最直接方法，因为它所需的步骤最少；但是，由于所有工作都是预先完成的（例如创建XDM架构），因此它需要更大的初始工作。</p><p>基本步骤为：</p><ol><li>为您的组织创建XDM架构。</li><li>实施Web SDK。</li><li>将数据发送到Platform。</li></ol> | 高 | 高 |
| **迁移您的Adobe Analytics实施以使用Web SDK**</br>&#x200B;如果您的Adobe Analytics实施AppMeasurement或Analytics扩展，您可以迁移它以使用Adobe Experience Platform Web SDK在将数据发送到Customer Journey Analytics之前开始将数据发送到Edge Network和Adobe Analytics。<p>对于尚未使用Web SDK的组织来说，这是将数据导入Edge Network的最简单、最顺畅的方法；它需要更多步骤，但提供了从Adobe Analytics到Customer Journey Analytics的更系统化的过渡，并且可实现更具体的里程碑。</p><p>基本步骤为：</p><ol><li>将您现有的Adobe Analytics实施移动到Web SDK中，并验证所有内容在Adobe Analytics中均可正常工作。</li><li>根据需要为您的组织创建XDM架构。</li><li>使用数据流映射将数据对象中的所有字段映射到您的XDM架构。</li><li>将数据发送到Platform。</li></ol> | 审核 | 高 |
| **配置您现有的Adobe Analytics Web SDK实施**</br>&#x200B;如果您的Adobe Analytics实施已经在使用Adobe Experience Platform Web SDK，则可以通过设置数据流开始向Platform发送数据。 或者，如果您已经将数据发送到Platform，则只需在Platform数据集和Customer Journey Analytics之间创建连接即可。<p>在将数据发送到Platform以用于Customer Journey Analytics之前，请考虑更新您的Adobe Analytics架构以满足您组织的特定需求以及您使用的任何其他平台应用程序。</p><p>基本步骤为：</p><ol><li>开始将数据发送到Platform。<p>如果您已经使用Adobe Analytics实施将数据发送到Platform，则不需要执行此步骤。 您只需在Platform数据集与Customer Journey Analytics之间创建连接即可，如本流程后面部分所述。</p></li><li>（可选）根据需要为您的组织创建XDM架构。</li><li>（视情况而定）如果您创建了XDM架构，请使用数据流映射将数据对象中的所有字段映射到XDM架构。</li></ol> | 低 | 高 |
| **使用Analytics Source Connector**</br>&#x200B;如果您的Adobe Analytics实施AppMeasurement或Analytics扩展，则可以开始以Customer Journey Analytics将数据发送到数据视图。<p>这是将数据导入Customer Journey Analytics的最简单方法，但长期而言是最不可行的方法。</p> <p>**注意：**&#x200B;此升级路径可以单独使用。 但是，为获得最佳结果，我们建议将此升级路径与Experience PlatformWebSDK的新实现结合使用。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--> </p> | 低 | 低 |

{style="table-layout:auto"}

使用下图帮助可视化每个升级路径在工作量级别和长期可行性方面所处的范围：

![cja升级路径](assets/cja-upgrade-path-chart.png)

## 根据您当前的Adobe Analytics实施情况评估可用的升级路径

并非所有升级路径都适用于每种类型的Adobe Analytics实施。

请通过以下信息帮助您了解哪种升级路径最适合您的组织。

如果您需要更具体的建议、指导或支持，请联系您的Adobe代表。

| 现有Adobe Analytics实施 | 可用的升级路径 |
|---------|----------|
| AppMeasurement | <ul><li>Experience PlatformWeb SDK的新实施</li><li>将Adobe Analytics迁移到Web SDK</li><li>Analytics Source Connector</li><li>（推荐）使用Analytics Source Connector实现Experience PlatformWeb SDK的新实施</li></ul> |
| Adobe Analytics 扩展 | <ul><li>Experience PlatformWeb SDK的新实施</li><li>将Adobe Analytics迁移到Web SDK</li><li>Analytics Source Connector</li><li>（推荐）使用Analytics Source Connector实现Experience PlatformWeb SDK的新实施</li></ul> |
| Web SDK | <ul><li>配置Adobe Analytics Web SDK实施以将数据发送到Platform</li><li>（推荐）使用Analytics Source Connector实现Experience PlatformWeb SDK的新实施</li></ul> |

{style="table-layout:auto"}

## 权衡可供您使用的升级路径的优缺点

给定升级路径的优缺点因您现有的Adobe Analytics实施而异。

在使用以下信息确定适合您的升级路径之前，请查看[了解升级路径](#understand-migration-methods)（如果尚未了解）中的信息。

>[!NOTE]
>
>虽然以下部分中描述的每个升级路径都可以单独使用，但Adobe建议在从Adobe Analytics升级到Customer Journey Analytics时采用双管齐下的升级方法，而不考虑您当前的Adobe Analytics实施： **Adobe Analytics源连接器**&#x200B;和&#x200B;**Experience PlatformWebSDK的新实施**。
><!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) -->

### 对于使用的Adobe Analytics实施：AppMeasurement和Adobe Analytics扩展

以下是适用于已使用AppMeasurement或Adobe Analytics扩展实施了Adobe Analytics的组织可用的升级路径。 展开每个部分可查看每个升级路径的优缺点。

#### 升级路径

+++Experience PlatformWeb SDK的新实现

| 优势 | 缺点 |
|----------|---------|
| <ul><li>**提供在ExperienceEdge Network中托管数据的所有优点**： <p>这些优势包括：</p><ul><li>高性能报表和数据可用性，因为Adobe Experience Platform旨在支持[实时个性化用例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>在其他Experience Cloud产品(AJO、RTCDP等)之间整合Adobe Experience Cloud数据收集的实施</li><li>不依赖于Adobe Analytics命名法(属性、eVar、事件等)</li></ul></li><li>**未来校对**：未来实施更新更容易。</li></ul> | <ul><li>**需要从头开始的新实施**：要求从头开始执行新实施意味着以下缺点： </li><ul><li>**耗时**：这是最耗时、要求最高的升级路径，因为它要求您从新的实施重新开始。</li><li>**必须在XDM中重新创建完整架构**：必须先在XDM中重新创建完整架构，然后才能开始实施Web SDK。</li><li>**必须重新创建规则和数据元素**：在开始实施Web SDK之前，必须从Adobe Analytics实施重新创建任何规则条件和数据元素。</li></ul><li>**不考虑保留历史数据：** Adobe建议将Analytics源连接器与Experience PlatformWeb SDK的新实现结合使用，以便在升级到Customer Journey Analytics后保留历史数据。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li><li>**不考虑将原始实施的数据与新实施的数据进行比较：** Adobe建议将Analytics源连接器与Experience PlatformWeb SDK的新实施结合使用，以便比较升级到Customer Journey Analytics后的数据。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li></ul> |

{style="table-layout:auto"}

+++

+++将Adobe Analytics迁移到Experience PlatformWeb SDK

| 优势 | 缺点 |
|----------|---------|
| <ul><li>**提供在ExperienceEdge Network中托管数据的所有优点**： <p>这些优势包括：</p><ul><li>高性能报表和数据可用性，因为Adobe Experience Platform旨在支持[实时个性化用例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>在其他Experience Cloud产品(AJO、RTCDP等)之间整合Adobe Experience Cloud数据收集的实施</li><li>不依赖于Adobe Analytics命名法(属性、eVar、事件等)</li></ul><li>**使用您现有的实施**：虽然此方法需要一些实施更改，但它不需要从头开始的全新实施。 您可以在不影响现有Adobe Analytics报表的情况下，使用现有数据层和代码，只需对实施逻辑进行最低限度的更改即可。</li><li>**提供灵活性，以便稍后为您的组织创建XDM架构**：您可以迁移现有的Adobe Analytics实施以使用Web SDK并验证所有内容在Adobe Analytics中是否都正常工作，然后创建XDM架构。 这种灵活性使得升级到Customer Journey Analytics的过程更加有条不紊，而且更加深思熟虑。</li></ul> | <ul><li>**需要映射才能将数据发送到Platform**：当您的组织准备好使用Customer Journey Analytics时，您必须将数据发送到Adobe Experience Platform中的数据集。 此操作要求数据对象中的每个字段都是数据流映射工具中的条目，并将其分配给XDM架构字段。 此工作流的映射只需执行一次，并且不涉及对实施进行更改。 但是，这是一个额外的步骤，在XDM对象中发送数据时不需要执行此步骤。</li><li>**技术债务**：由于此方法使用现有实施的修改形式，因此将来需要跟踪实施逻辑和执行更改会更加困难。 </li></ul> |

{style="table-layout:auto"}

+++

+++使用Analytics Source Connector

| 优势 | 缺点 |
|----------|---------|
| <ul><li>最省时和最苛刻的升级路径。 <p>以最少的投资将数据快速迁移到Customer Journey Analytics</p></li></ul> | <ul><li>**数据未发送到Edge Network**： <p>这会导致以下缺点：</p><ul><li>在所有升级路径上的报表中达到[延迟](/help/technotes/guardrails.md#latencies)的最高级别；未针对实时个性化用例进行优化。</li><li>数据不能与其他Adobe Experience Platform应用程序共享；它只限于Customer Journey Analytics</li><li>依赖于Adobe Analytics命名法(属性、eVar、事件等)</li></ul><li>**将来难以迁移到Web SDK**：最终，您可能希望访问Experience PlatformWeb SDK提供的优势。 要开始使用Experience PlatformWeb SDK，您必须进行新的实施。</li><li>**在您的架构中使用Analytics Experience Event字段组**：此字段组添加了许多Customer Journey Analytics架构中不需要的Adobe Analytics事件。  这可能会导致Customer Journey Analytics所需的架构更加杂乱、复杂。</li></ul><p>由于这些缺点，Adobe建议将Analytics源连接器与Experience PlatformWeb SDK的新实现结合使用。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></p> |

{style="table-layout:auto"}

+++

### 对于使用的Adobe Analytics实施： Web SDK

以下升级路径适用于已使用Experience PlatformWeb SDK实施Adobe Analytics的组织。

选择此升级路径时，您还需要选择架构。

#### 升级路径

+++配置Adobe Analytics Web SDK实施以将数据发送到Platform

| 优势 | 缺点 |
|----------|---------|
| 如果您的Adobe Analytics实施已经在使用Web SDK，则这是首选升级路径。<ul><li>**提供在ExperienceEdge Network中托管数据的所有优点**： <p>这些优势包括：</p><ul><li>高性能报表和数据可用性，因为Adobe Experience Platform旨在支持[实时个性化用例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>在其他Experience Cloud产品(AJO、RTCDP等)之间整合Adobe Experience Cloud数据收集的实施</li><li>不依赖于Adobe Analytics命名法(属性、eVar、事件等)</li></ul><li>**使用您现有的实施**：虽然此方法需要一些实施更改，但它不需要从头开始的全新实施。 您可以在不影响现有Adobe Analytics报表的情况下，使用现有数据层和代码，只需对实施逻辑进行最低限度的更改即可。</li><li>**提供使用XDM架构的选项**：您可以选择使用现有的Adobe Analytics架构，也可以创建XDM架构并将数据对象中的字段映射到XDM架构。 [XDM架构](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas)是一个灵活的架构，用于定义您需要的任何字段，并且只定义相关的字段。 <p>请参阅下面的“使用您自己的XDM架构”，详细了解使用您自己的XDM架构的优势。</p></li><li>**保留规则和数据元素**：虽然它确实需要新的规则操作，但您可以重复使用现有的数据元素和规则条件，只需很少的更改。</li><li>**未来验证**：如果您选择使用自己的XDM架构，则未来实施更新会更轻松。</li></ul> | 无 |

{style="table-layout:auto"}

+++

#### 选择您的架构

如果选择了Adobe Analytics Web SDK实施配置为将数据发送到Platform的升级路径，则可以选择要使用的架构。

您可以选择是否使用现有Adobe Analytics架构，也可以更新到您自己的XDM架构，以便在您开始使用其他Platform服务时更好地满足贵组织的需求。

+++将Adobe Analytics架构用于Adobe Analytics Web SDK实施

| 优势 | 缺点 |
|----------|---------|
| <p>使用Adobe Analytics架构的优势包括：</p><ul><li>易于升级<p>如果您已使用Adobe Experience Platform Web SDK将数据发送到Adobe Analytics，则可以将其他服务添加到您的数据流以将数据发送到Adobe Experience Platform(然后可以在您的Customer Journey Analytics配置中使用)。</p></li></ul> | <p>使用Adobe Analytics架构的缺点包括：</p><ul><li>虽然使用Adobe Analytics架构不会限制您如何将其与其他Platform应用程序一起使用，但它的确会导致架构比不使用该架构时复杂得多。 这是因为Adobe Analytics架构包含许多特定于Adobe Analytics的对象，您的组织不太可能使用这些对象。<p>当需要对架构进行更改时，您必须筛选成千上万个未使用的字段以查找需要更新的字段。</p></li></ul> |

+++

+++在Adobe Analytics Web SDK实施中使用您自己的XDM架构

| 优势 | 缺点 |
|----------|---------|
| <ul><p>更新到您自己的XDM架构的优势包括：</p><ul><li>简化架构，根据贵组织的需求以及您使用的特定平台应用程序量身定制。</li><p>当需要对架构进行更改时，您不必在数千个未使用的字段中进行筛选，即可找到需要更新的字段。</p></ul> | <p>更新到您自己的XDM架构的缺点包括：</p><ul><li>在开始向Platform发送数据之前，需要更新架构，这是一个非常耗时的过程。</li></ul> |

+++

## 接下来，将数据发送到Adobe Experience Platform

使用上述信息选择升级路径后，了解如何根据您选择的升级路径[将数据发送到Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)。
