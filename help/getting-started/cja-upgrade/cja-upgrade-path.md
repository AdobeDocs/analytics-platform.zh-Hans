---
title: 选择 Customer Journey Analytics 升级路径
description: 了解升级到 Customer Journey Analytics 时潜在升级路径的优缺点
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '2981'
ht-degree: 98%

---

# 步骤 2：选择您的升级路径

+++展开此部分可查看此页面上的信息在较大的升级过程中的位置。 确保所有先前的升级步骤均已完成。

在继续本部分之前，请首先确保您已完成所有先前的升级任务。

该页面上的信息涵盖升级过程中的第 2 步，如下表所示：

| 升级任务 | 详细信息 |
|---------|----------|
| **步骤 1：[开始升级](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | 了解升级到 Customer Journey Analytics 的好处以及基本升级流程。 |
| <span class="preview">**步骤 2：选择升级路径**</span> | <span class="preview">有多种方法可以升级到 Customer Journey Analytics。根据您组织当前的 Adobe Analytics 环境和长期目标，选择最适合您组织的方法。</span> |
| **步骤 3：[将数据发送到 Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | 将数据发送到 Adobe Experience Platform 的流程因您在步骤 2 中选择的升级路径而异。 |
| **步骤 4：[保留历史数据](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | 大多数组织需要在一定时间内保留其 Adobe Analytics 的历史数据。有多种选项可以实现此目的。 |
| **步骤 5：[执行额外的实施任务](/help/getting-started/cja-getting-started.md)** | 在升级流程的这个阶段，您需要执行各种任务，然后您的 Customer Journey Analytics environment 环境才可供使用。<p>这些额外的任务适用于从 Adobe Analytics 进行升级，以及新的 Customer Journey Analytics 实施。</p><p>这些任务包括：</p><ul><li>将其他数据引入 Experience Platform</li><li>在 Platform 数据集与 Customer Journey Analytics 之间创建连接</li><li>创建数据视图</li><li>移植报告 API 使用情况</li><li>数据源和 Data Warehouse 的核算</li><li>迁移项目和组件</li><li>规划用户加入流程</li></ul> <p>有关更多信息，请参阅 [Customer Journey Analytics 快速入门](/help/getting-started/cja-getting-started.md)。 |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>此页面上的信息将被以下更全面的升级信息取代： <ul><li>**建议的升级步骤**<p>有关详细信息，请参阅[从 Adobe Analytics 升级到 Customer Journey Analytics 时的推荐路径](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。</p></li><li>**Customer Journey Analytics 升级指南**<p>现有新的升级指南可用，用于动态生成适合您的组织和独特情况的升级步骤。</p><p>要从 Customer Journey Analytics 访问升级指南，请选择&#x200B;**[!UICONTROL 工作区]**&#x200B;选项卡，然后在左侧面板中选择&#x200B;**[!UICONTROL 升级到 Customer Journey Analytics]**。按照屏幕上的说明操作。</p></li></ul>


在您决定升级到 Customer Journey Analytics 后，您需要确定适合您组织的最佳升级路径。

您选择从 Adobe Analytics 升级到 Customer Journey Analytics 的路径取决于以下因素：

* 您现有的 Adobe Analytics 实施

* 您未来的目标

使用此页面上的信息来确定哪种 Customer Journey Analytics 升级路径最符合您组织的当前的实施以及未来的目标。

为了确定适合您组织的最佳升级路径，应按顺序阅读以下部分：

1. 第一，[了解可用的升级路径](#understand-upgrade-paths)。

1. 然后，[评估哪些升级路径可供您选择](#assess-the-upgrade-paths-available-to-you-based-on-your-current-adobe-analytics-implementation)。

1. 最后，[权衡每种升级路径的优缺点](#weigh-the-advantages-and-disadvantages-of-the-upgrade-paths-available-to-you)。

## 了解升级路径

从 Adobe Analytics 升级到 Customer Journey Analytics 有多种升级路径可供选择。

一般来说，每条升级路径在执行升级时所需的工作量以及升级完成后取得的长期可行性方面有所不同。

下表列出了每条升级路径、其工作量以及长期可行性：

| 升级路径 | 工作量 | 长期可行性 |
|---------|----------|---------|
| **使用 Analytics 源连接器进行的 Experience Platform Web SDK 的新实施**</br>&#x200B;您可以通过重新实施 Experience Platform Web SDK 来开始使用 Customer Journey Analytics。这使您能够开始向 Adobe Experience Platform Edge Network 和 Customer Journey Analytics 发送数据。此外，您可以使用 Analytics 源连接器将历史数据引入 Customer Journey Analytics。<p>对于尚未使用 Web SDK 的组织，此升级路径可能是将数据传输到 Edge Network 最直接的途径，这是因为它需要的步骤最少；但是，由于所有工作都是提前完成的（例如创建 XDM 架构），因此需要投入更多的初始精力。</p><p>基本步骤如下：</p><ol><li>为您的组织创建一个 XDM 架构。</li><li>实施 Web SDK。</li><li>向 Platform 发送数据。</li><li>设置 Analytics 源连接器。</br>Analytics 源连接器用于将历史 Adobe Analytics 数据带入 Customer Journey Analytics。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--></li></ol><p><!-- **Note:** This is the recommended upgrade path when upgrading to Customer Journey Analytics. For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). --></p> | 高 | 高 |
| **Experience Platform Web SDK 的新实施**</br>&#x200B;您可以通过重新实施 Experience Platform Web SDK 来开始使用 Customer Journey Analytics。这使您能够开始向 Adobe Experience Platform Edge Network 和 Customer Journey Analytics 发送数据。 <p>对于尚未使用 Web SDK 的组织，此升级路径可能是将数据传输到 Edge Network 最直接的途径，这是因为它需要的步骤最少；但是，由于所有工作都是提前完成的（例如创建 XDM 架构），因此需要投入更多的初始精力。</p><p>基本步骤如下：</p><ol><li>为您的组织创建一个 XDM 架构。</li><li>实施 Web SDK。</li><li>向 Platform 发送数据。</li></ol> | 高 | 高 |
| **迁移您的 Adobe Analytics 实施，以使用 Web SDK**</br>&#x200B;如果您的 Adobe Analytics 实施是 AppMeasurement 或 Analytics 扩展，则可以对其进行迁移，以使用 Adobe Experience Platform Web SDK 开始将数据发送到 Edge Network 和 Adobe Analytics，然后再将其发送到 Customer Journey Analytics。<p>对于尚未使用 Web SDK 的组织而言，这是将数据传送到 Edge Network 的最简单、最顺畅的方式；虽然需要更多步骤，但它能更系统地实现从 Adobe Analytics 到 Customer Journey Analytics 的过渡，并设有更多切实的里程碑。</p><p>基本步骤如下：</p><ol><li>将现有的 Adobe Analytics 实施移至 Web SDK 并验证 Adobe Analytics 中的所有功能是否正常工作。</li><li>时间允许时为您的组织创建一个 XDM 架构。</li><li>使用数据流映射将数据对象中的所有字段映射到您的 XDM 架构。</li><li>向 Platform 发送数据。</li></ol> | 中 | 高 |
| **配置您现有的 Adobe Analytics Web SDK 实现**</br>&#x200B;如果您的 Adobe Analytics 实施已经在使用 Adobe Experience Platform Web SDK，则可以通过设置数据流来开始将数据发送到 Platform。或者，如果您已经将数据发送到 Platform，则只需在 Platform 数据集和 Customer Journey Analytics 之间创建连接。<p>在将数据发送到 Platform 以供 Customer Journey Analytics 使用之前，请考虑根据组织的特定需求以及您使用的任何其他 Platform 应用程序更新 Adobe Analytics 架构。</p><p>基本步骤如下：</p><ol><li>开始向 Platform 发送数据。<p>如果您已经在使用 Adobe Analytics 实施向 Platform 发送数据，则不需要此步骤。您只需要在 Platform 数据集和 Customer Journey Analytics 之间创建连接即可，如本流程后面所述。</p></li><li>（可选）时间允许时为您的组织创建一个 XDM 架构。</li><li>（可选）如果您创建了一个 XDM 架构，请使用数据流映射将数据对象中的所有字段映射到您的 XDM 架构中。</li></ol> | 低 | 高 |
| **使用 Analytics 源连接器**</br>&#x200B;如果您的 Adobe Analytics 实施是 AppMeasurement 或 Analytics 扩展，则可以开始将数据发送到 Customer Journey Analytics 中的数据视图中。<p>这是将数据传送至 Customer Journey Analytics 的最简单方法，但从长远来看却是最不可行的方法。</p> <p>**注释：**&#x200B;此升级路径可独立使用。但为了获得最佳效果，我们建议将此升级路径与 Experience Platform WebSDK 的新实施结合使用。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--> </p> | 低 | 低 |

{style="table-layout:auto"}

请参考以下图表，以直观了解各升级路径在工足量和长期可行性方面的分布情况：

![cja 升级路径](assets/cja-upgrade-path-chart.png)

## 根据您当前的 Adobe Analytics 实施情况评估可用的升级路径

并非所有升级路径都适用于每种类型的 Adobe Analytics 实施。

使用以下信息帮助您了解哪种升级路径最适合您的组织。

如果您需要更具体的建议、指导或支持，请联系您的 Adobe 代表。

| 现有的 Adobe Analytics 实施 | 可用的升级路径 |
|---------|----------|
| AppMeasurement | <ul><li>Experience Platform Web SDK 的新实施 </li><li>将 Adobe Analytics 迁移到 Web SDK</li><li>Analytics 源连接器</li><li>（推荐）使用 Analytics 源连接器重新实施 Experience Platform Web SDK</li></ul> |
| Adobe Analytics 扩展 | <ul><li>Experience Platform Web SDK 的新实施 </li><li>将 Adobe Analytics 迁移到 Web SDK</li><li>Analytics 源连接器</li><li>（推荐）使用 Analytics 源连接器重新实施 Experience Platform Web SDK</li></ul> |
| Web SDK | <ul><li>配置 Adobe Analytics Web SDK 实施，以将数据发送到 Platform</li><li>（推荐）使用 Analytics 源连接器重新实施 Experience Platform Web SDK</li></ul> |

{style="table-layout:auto"}

## 权衡可用的升级路径的优缺点

给定升级路径的优缺点因您现有的 Adobe Analytics 实施而异。

在使用以下信息确定哪种升级路径适合您之前，请先查看[了解升级路径](#understand-migration-methods)中的信息（如果还没有查看）。

>[!NOTE]
>
>尽管以下各部分中描述的每种升级途径均可独立使用，但 Adobe 建议在从 Adobe Analytics 升级到 Customer Journey Analytics 时采用双管齐下的升级方法，无论您当前的 Adobe Analytics 实施情况如何均是如此：**Adobe Analytics 源连接器**&#x200B;和 **Experience Platform WebSDK 的新实施**。
><!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) -->

### 适用于使用 AppMeasurement 和 Adobe Analytics 扩展程序的 Adobe Analytics 实施

以下是已使用 AppMeasurement 或 Adobe Analytics 扩展程序实施 Adobe Analytics 的组织可用的升级途径。展开每个部分可以查看每条升级路径的优点和缺点。

#### 升级路径

+++Experience Platform Web SDK 的新实施 

| 优点 | 缺点 |
|----------|---------|
| <ul><li>**提供在 Experience Edge Network 中托管数据的所有优点**： <p>这些优点包括：</p><ul><li>Adobe Experience Platform 专为支持[实时个性化用例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=zh-Hans)而构建，因此具有高性能报告和数据可用性</li><li>在其他 Experience Cloud 产品（AJO、RTCDP 等）之间整合对 Adobe Experience Cloud 数据收集的实施</li><li>不依赖于 Adobe Analytics 命名法（属性、eVar、事件等）</li></ul></li><li>**面向未来**：未来的实施更新将更加容易。</li></ul> | <ul><li>**需要从头开始进行新的实施**：从头开始进行新实施的要求意味着以下缺点： </li><ul><li>**耗时**：这是最耗时且要求最高的升级路径，因为它要求您重新开始新的实施。</li><li>**必须在 XDM 中重新创建完整架构**：在开始实施 Web SDK 之前，您必须在 XDM 中重新创建完整的架构。</li><li>**必须重新创建规则和数据元素**：在开始实施 Web SDK 之前，您必须从 Adobe Analytics 实施中重新创建所有规则条件和数据元素。</li></ul><li>**不考虑保留历史数据：** Adobe 建议将 Analytics 源连接器与 Experience Platform Web SDK 的新实施结合使用，以便在升级到 Customer Journey Analytics 后保留历史数据。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li><li>**不考虑将原始实施的数据与新实施的数据进行比较：** Adobe 建议将 Analytics 源连接器与 Experience Platform Web SDK 的新实施结合使用，以便在升级到 Customer Journey Analytics 后比较数据。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li></ul> |

{style="table-layout:auto"}

+++

+++将Adobe Analytics迁移到Experience Platform Web SDK

| 优点 | 缺点 |
|----------|---------|
| <ul><li>**提供在 Experience Edge Network 中托管数据的所有优点**： <p>这些优点包括：</p><ul><li>Adobe Experience Platform 专为支持[实时个性化用例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=zh-Hans)而构建，因此具有高性能报告和数据可用性</li><li>在其他 Experience Cloud 产品（AJO、RTCDP 等）之间整合对 Adobe Experience Cloud 数据收集的实施</li><li>不依赖于 Adobe Analytics 命名法（属性、eVar、事件等）</li></ul><li>**使用您现有的实施**：虽然这种方法需要进行一些实施方面的变更，但它并不需要从头开始进行全新的实施。您可以使用现有的数据层和代码，只需对实施逻辑进行最少的更改，而不会影响现有的 Adobe Analytics 报告。</li><li>**在未来可以灵活地为您的组织创建 XDM 架构**：您可以迁移现有的 Adobe Analytics 实施，以使用 Web SDK 并验证 Adobe Analytics 中的所有功能是否正常运行，然后再创建 XDM 架构。这种灵活性使得向 Customer Journey Analytics 的升级更加系统和周到。</li></ul> | <ul><li>**需要映射才能将数据发送到 Platform**：当您的组织准备好使用 Customer Journey Analytics 时，您必须将数据发送到 Adobe Experience Platform 中的数据集。此操作要求数据对象中的每个字段都是数据流映射工具中的一个条目，并且该条目会将其分配给一个 XDM 架构字段。对于此工作流程，仅需进行一次映射，并且不涉及对实施进行更改。但是，这是一个额外的步骤，在 XDM 对象中发送数据时并不需要该步骤。</li><li>**技术债务**：由于这种方法使用的是现有实施的修改形式，因此在将来需要时，跟踪实施逻辑和执行更改可能会更加困难。 </li></ul> |

{style="table-layout:auto"}

+++

+++使用 Analytics 源连接器

| 优点 | 缺点 |
|----------|---------|
| <ul><li>最省时、最省力的升级途径。 <p>只需最少的投资即可快速将数据迁移到 Customer Journey Analytics</p></li></ul> | <ul><li>**数据未发送到 Edge Network**： <p>这会导致以下缺点：</p><ul><li>在所有升级路径中，报告[延迟](/help/technotes/guardrails.md#latencies)级别最高；未针对实时个性化用例进行优化。</li><li>数据无法与其他 Adobe Experience Platform 应用程序共享；仅限于 Customer Journey Analytics</li><li>依赖于 Adobe Analytics 命名法（属性、eVar、事件等）</li></ul><li>**未来很难迁移到 Web SDK**：您最终可能会希望获得 Experience Platform Web SDK 提供的优势。若要开始使用 Experience Platform Web SDK，您必须进行新的实施。</li><li>**使用架构中的 Analytics Experience Event 字段组**：此字段组添加了许多在您的 Customer Journey Analytics 架构中不需要的 Adobe Analytics 事件。这可能会导致架构比 Customer Journey Analytics 实际所需的更加混乱和复杂。</li></ul><p>鉴于这些缺点，Adobe 建议将 Analytics 源连接器与 Experience Platform Web SDK 的新实施结合使用。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></p> |

{style="table-layout:auto"}

+++

### 对于使用 Web SDK 的 Adobe Analytics 实施

以下升级路径适用于已使用 Experience Platform Web SDK 实施 Adobe Analytics 的组织。

当选择此升级路径时，您还需要选择架构。

#### 升级路径

+++配置 Adobe Analytics Web SDK 实施，以将数据发送到 Platform

| 优点 | 缺点 |
|----------|---------|
| 如果您的 Adobe Analytics 实施已经在使用 Web SDK，则这是首选的升级路径。<ul><li>**提供在 Experience Edge Network 中托管数据的所有优点**： <p>这些优点包括：</p><ul><li>Adobe Experience Platform 专为支持[实时个性化用例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=zh-Hans)而构建，因此具有高性能报告和数据可用性</li><li>在其他 Experience Cloud 产品（AJO、RTCDP 等）之间整合对 Adobe Experience Cloud 数据收集的实施</li><li>不依赖于 Adobe Analytics 命名法（属性、eVar、事件等）</li></ul><li>**使用您现有的实施**：虽然这种方法需要进行一些实施方面的变更，但它并不需要从头开始进行全新的实施。您可以使用现有的数据层和代码，只需对实施逻辑进行最少的更改，而不会影响现有的 Adobe Analytics 报告。</li><li>**提供使用 XDM 架构的选项**：您可以选择使用现有的 Adobe Analytics 架构，或者创建一个 XDM 架构，并将数据对象中的字段映射到该 XDM 架构。[XDM 架构](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/home#xdm-schemas)是一种灵活的架构，它可以定义您需要的任何字段，并且仅会定义相关的字段。 <p>有关使用您自己的 XDM 架构的优势的更多信息，请参阅下面的“使用您自己的 XDM 架构”。</p></li><li>**保留规则和数据元素**：虽然这确实需要新的规则操作，但您只需进行最小的更改，即可重复使用现有的数据元素和规则条件。</li><li>**面向未来**：如果您选择使用自己的 XDM 架构，那么未来的实施更新将会更容易。</li></ul> | 无 |

{style="table-layout:auto"}

+++

#### 选择您的架构

如果您选择的升级路径允许配置 Adobe Analytics Web SDK 实施以向 Platform 发送数据，则您可以选择要使用的架构。

您可以选择使用现有的 Adobe Analytics 架构，也可以升级到您自己的 XDM 架构，以便在开始使用其他 Platform 服务时更好地满足组织的需求。

+++将Adobe Analytics架构用于Adobe Analytics Web SDK实施

| 优点 | 缺点 |
|----------|---------|
| <p>使用 Adobe Analytics 架构的优势包括：</p><ul><li>易于升级<p>如果您已经在使用 Adobe Experience Platform Web SDK 将数据发送到 Adobe Analytics，则可以向数据流添加附加服务，以将数据发送到 Adobe Experience Platform（然后可以在您的 Customer Journey Analytics 配置中使用）。</p></li></ul> | <p>使用 Adobe Analytics 架构的缺点包括：</p><ul><li>虽然使用 Adobe Analytics 架构不会限制您将其与其他 Platform 应用程序结合使用的方式，但它会使架构变得比原本更复杂。这是因为 Adobe Analytics 架构包含许多特定于 Adobe Analytics 的对象，而您的组织不太可能会使用这些对象。<p>当需要更改架构时，您必须筛选数千个未使用的字段来找到需要更新的字段。</p></li></ul> |

+++

+++在Adobe Analytics Web SDK实施中使用您自己的XDM架构

| 优点 | 缺点 |
|----------|---------|
| <ul><p>升级到您自己的 XDM 架构的优点包括：</p><ul><li>根据您的组织需求和您使用的特定 Platform 应用程序量身定制的简化架构。</li><p>当需要更改架构时，您无需筛选数千个未使用的字段来找到需要更新的字段。</p></ul> | <p>升级到您自己的 XDM 架构的缺点包括：</p><ul><li>更新架构是一个耗时的过程，并且必须在开始向 Platform 发送数据之前进行。</li></ul> |

+++

## 接下来，将数据发送到 Adobe Experience Platform

利用上述信息选择升级路径后，请根据您所选的升级路径，了解如何[向 Adobe Experience Platform 发送数据](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)。
