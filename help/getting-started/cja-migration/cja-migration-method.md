---
title: 选择Customer Journey Analytics迁移方法
description: 了解迁移到Customer Journey Analytics时可能采用的迁移方法的优缺点
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 923dfac33fcde368392fe29c6530069cc0d8fb9d
workflow-type: tm+mt
source-wordcount: '1914'
ht-degree: 4%

---

# 步骤2：选择Customer Journey Analytics迁移方法

+++展开此部分可查看此页面上的信息在较大的迁移过程中所处的位置。 确保所有先前的迁移步骤均已完成。

在继续此部分之前，请先确保已完成所有以前的迁移任务。

此页面上的信息涵盖了步骤2，如下表所示：

| 迁移任务 | 详细信息 |
|---------|----------|
| **第1步： [迁移入门](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 了解迁移到Adobe Analytics的好处以及基本迁移过程。 |
| <span class="preview">**第2步： [选择迁移方法](/help/getting-started/cja-migration/cja-migration-method.md)**</span> | <span class="preview">可以使用各种方法迁移到Customer Journey Analytics。 根据贵组织当前的Adobe Analytics环境和长期目标，选择最适合贵组织的方法。</span> |
| **步骤3： [将数据发送到Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 将数据发送到Adobe Experience Platform的过程因您在步骤1中选择的迁移方法而异。 |
| **第4步： [将数据映射到XDM架构](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM架构](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重用的方式描述数据结构。 通过在系统中以一致的方式定义数据，更容易保留含义并因此从数据中获取价值。<p>大多数迁移方法都要求您创建新的XDM架构，或使用数据流映射将现有Adobe Analytics架构映射到XDM。</p> |
| **步骤5： [保留历史数据](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多数组织都需要将其历史Adobe Analytics数据保留一定时间。 可以使用各种选项来完成此操作。 |
| **步骤6： [计划用户载入](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 您应该给用户充足的时间（3 - 6个月），以熟悉Analysis Workspace在Customer Journey Analytics方面的主要差异。 |
| **步骤7： [移植报表API使用情况](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics报表API采用相同的格式，但使用不同的端点。 将报表API使用情况从Adobe Analytics报表API移植到Customer Journey Analytics报表API。 |
| **步骤8： [替换数据馈送并Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | 决定如何使用Customer Journey Analytics中可用的导出选项，以替换在Adobe Analytics中使用的数据馈送和Data Warehouse功能。 |
| **第9步： [迁移项目和组件](/help/getting-started/cja-migration/cja-migration-projects.md)** | 利用Adobe Analytics中的组件迁移区域，可将项目及其关联的组件从Adobe Analytics迁移到Customer Journey Analytics。 |

{style="table-layout:auto"}

+++

在决定迁移到Customer Journey Analytics后，您需要确定适合您组织的最佳迁移方法。

您选择的从Adobe Analytics迁移到Customer Journey Analytics的方法取决于以下因素：

* 您现有的Adobe Analytics实施

* 您的未来目标

请阅读以下章节，以确定哪种Customer Journey Analytics迁移方法最符合贵组织的当前实施和未来目标：

## 了解迁移方法

从Adobe Analytics迁移到Customer Journey Analytics时存在多种迁移方法。

通常，每种迁移方法在执行迁移所需的工作量级别以及迁移完成后实现的长期可行性方面有所不同。

下表列出了每种迁移方法、其工作量及其长期可行性：

| 迁移方法 | 工作量 | 长期生存能力 |
|---------|----------|---------|
| **Web SDK的新实施**</br>&#x200B;您可以执行新的Adobe Experience Platform Web SDK实施，以开始将数据发送到Adobe Experience PlatformEdge Network <!-- what is the correct branding -->. <p>对于尚未使用Web SDK的组织，此迁移方法可能是将数据导入Edge Network最直接的方法（所需的步骤最少），但所有工作都是预先完成的，例如创建XDM架构。</p><p>基本步骤为：</p><ol><li>为您的组织创建XDM架构</li><li>实施Web SDK</li><li>将数据发送到Platform</li></ol> | 高 | 高 |
| **迁移Adobe Analytics实施以使用Web SDK**</br>&#x200B;如果您的Adobe Analytics实施AppMeasurement或Analytics扩展，则可以将其迁移以使用Adobe Experience Platform Web SDK在将数据发送到Customer Journey Analytics之前开始向Edge Network发送数据。 <!-- what else? --><p>这是将数据导入Edge Network的最简单、最顺畅的方法；它需要更多的步骤，但提供了更有条理的过渡，具有更具体的里程碑。</p><p>基本步骤为：</p><ol><li>将您现有的Adobe Analytics实施移动到Web SDK中，并验证在那里的所有组件是否都正常工作。</li><li>根据需要为您的组织创建XDM架构。</li><li>使用数据流映射将数据对象中的所有字段映射到您的XDM架构。</li><li>将数据发送到Platform</li></ol> | 审核 | 高 |
| **配置现有的Adobe Analytics Web SDK实施以将数据发送到Customer Journey Analytics**</br>&#x200B;如果您的Adobe Analytics实施已经在使用Web SDK，则可以开始向Customer Journey Analytics发送数据。<p>在将数据发送到Customer Journey Analytics之前，请考虑更新您的Adobe Analytics架构，以满足贵组织的特定需求以及您将使用的任何其他平台应用程序。</p><p>基本步骤为：</p><ol><li>开始向Customer Journey Analytics发送数据。<!-- What's involved here? Just point it at CJA? --></li><li>（可选）根据需要为您的组织创建XDM架构。</li><li>使用数据流映射将数据对象中的所有字段映射到您的XDM架构。</li></ol> | 低 | 高 |
| **Analytics源连接器**</br>&#x200B;如果您的Adobe Analytics实施AppMeasurement或Analytics扩展，则可以开始以Customer Journey Analytics将数据发送到数据视图。<p>这是将数据导入Customer Journey Analytics的最简单方法，但长期而言是最不可行的方法。</p> | 低 | 低 |

{style="table-layout:auto"}

使用下图帮助可视化每种迁移方法在工作量方面所处的阶段，以及每种迁移方法实现的长期可行性：

![cja迁移方法](assets/cja-migration-methods.png)

## 根据您当前的Adobe Analytics实施评估可用的迁移方法

并非所有迁移方法都适用于每种类型的Adobe Analytics实施。

请按照以下信息作为一般准则来帮助您了解哪种迁移方法最适合您的组织。

如果您需要更具体的建议、指导或支持，请联系您的Adobe代表。

| Adobe Analytics实施 | 可用的迁移方法 |
|---------|----------|
| AppMeasurement | <ul><li>Web SDK的新实施</li><li>将Adobe Analytics迁移到Web SDK</li><li>Analytics源连接器</li></ul> |
| Adobe Analytics 扩展 | <ul><li>Web SDK的新实施</li><li>将Adobe Analytics迁移到Web SDK</li><li>Analytics源连接器</li></ul> |
| Web SDK | <ul><li>配置Adobe Analytics Web SDK实施以将数据发送到Customer Journey Analytics</li></ul> |

{style="table-layout:auto"}

## 权衡可供您使用的迁移方法的优缺点

给定迁移方法的优缺点因您现有的Adobe Analytics实施而异。

在使用以下信息确定适合您的迁移方法之前，请查看中的信息 [了解迁移方法](#understand-migration-methods) 如果你还没有的话。

### AppMeasurement和Adobe Analytics扩展

下表显示了适用于已使用AppMeasurement或Adobe Analytics扩展实施Adobe Analytics的组织可用的迁移方法：

| 迁移方法 | 优势 | 缺点 |
|---------|----------|---------|
| **Web SDK的新实施** | <ul><li>使用XDM架构，这是一种灵活的架构，可定义您需要的任何字段</li><li>不依赖于 Adobe Analytics 命名法（属性、eVar、事件等）</li><li>没有字符限制问题（属性有 100 个字符）</li><li>高性能报表和数据可用性，因为Adobe Experience Platform是专为提供强大功能而构建的 [实时个性化用例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>经得起未来考验（将获得所有最新特性和功能）</li><li>在其他Experience Cloud产品（AJO、RTCDP等）之间合并Adobe Experience Cloud数据收集的标记</li><li>[第一方设备 ID](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html) 可提高访客识别的准确性</li></ul> | <ul><li>最耗时、最苛刻的迁移方法<p>必须先在XDM中重新创建完整架构，然后才能开始实施Web SDK</p></li></ul> |
| **将Adobe Analytics迁移到Web SDK** | <ul><li>保留您的Adobe Analytics实施中已配置的规则和数据元素。</li><li>使您能够迁移至Web SDK而不影响您现有的Adobe Analytics报表。</li><li>提供了灵活性，以便稍后为您的组织创建XDM架构。</br>不需要Customer Journey Analytics中的Adobe Analytics Experience Event Field组。 <!-- With the new implementation, you're double-counting with 2 implementation; with the migration, you're double-counting, but both of them are through Edge Network. --></li><li>不依赖于 Adobe Analytics 命名法（属性、eVar、事件等）</li><li>没有字符限制问题（属性有 100 个字符）</li><li>高性能报表和数据可用性，因为Adobe Experience Platform是专为提供强大功能而构建的 [实时个性化用例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>经得起未来考验（将获得所有最新特性和功能）</li><li>在其他Experience Cloud产品（AJO、RTCDP等）之间合并Adobe Experience Cloud数据收集的标记</li><li>[第一方设备 ID](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html) 可提高访客识别的准确性</li></ul> | <ul><li>在将来的某个时刻必须符合XDM架构，使用数据流映射。</li><li>会产生一些技术债务。 例如，可以保留旧版AppMeasurement或Analytics扩展代码。 </li></ul> |
| **Analytics源连接器** | <ul><li>最省时和最苛刻的迁移方法。 <p>以最少的投资将数据快速迁移到Customer Journey Analytics</p></li></ul> | <ul><li>数据不会发送到Edge Network，并且无法与其他Adobe Experience Platform应用程序共享；它仅受Customer Journey Analytics限制<li>未来难以迁移到Web SDK</li><li>在架构中使用Analytics Experience Event字段组。</br>此字段组添加了许多Customer Journey Analytics架构中不需要的Adobe Analytics事件。  这可能会导致Customer Journey Analytics所需的架构更加杂乱、复杂。</li><li>最高级别的 [延迟](/help/admin/guardrails.md#latencies) 跨所有实施方法</li></ul> |

{style="table-layout:auto"}

### Web SDK

下表显示了适用于已使用Web SDK实施Adobe Analytics的组织可用的迁移方法：

| 迁移方法 | 优势 | 缺点 |
|---------|----------|---------|
| **配置Adobe Analytics Web SDK实施以将数据发送到Customer Journey Analytics** | 如果您的Adobe Analytics实施已经在使用Web SDK，则这是首选的迁移方法。 <p>使用此实施方法时，您可以选择是否使用现有Adobe Analytics架构，也可以更新到XDM架构以在开始使用其他Platform应用程序时更好地符合组织的需求。</p><p>**使用Adobe Analytics架构**</p><p>使用Adobe Analytics架构的优势包括：</p><ul><li>轻松迁移<p>如果您已使用Adobe Experience Platform Web SDK将数据发送到Adobe Analytics，则可以将其他服务添加到您的数据流以将数据发送到Adobe Experience Platform(然后可以在您的Customer Journey Analytics配置中使用)。</p></li></ul><p>使用Adobe Analytics架构的缺点包括：</p><ul><li>虽然使用Adobe Analytics架构不会限制您如何将其与其他Platform应用程序一起使用，但它的确会导致架构比不使用该架构时复杂得多。 这是因为Adobe Analytics架构包含许多特定于Adobe Analytics的对象，您的组织可能不会使用这些对象。<p>当需要对架构进行更改时，您必须筛选成千上万个未使用的字段以查找需要更新的字段。</p></li></ul><p>**使用XDM架构**</p><p>更新XDM架构的优点包括：</p><ul><li>简化架构，根据贵组织的需求以及您使用的特定平台应用程序量身定制。</li><p>当需要对架构进行更改时，您不必在数千个未使用的字段中进行筛选，即可找到需要更新的字段。</p></ul><p>更新XDM架构的缺点包括：</p><ul><li>在开始向Customer Journey Analytics发送数据之前，需要更新架构是一个耗时的过程。</li></ul> | 无 |

{style="table-layout:auto"}

## 接下来，将数据发送到Adobe Experience Platform

使用上述信息选择迁移方法后，了解如何 [将数据发送到Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) 具体取决于您选择的迁移方法。
