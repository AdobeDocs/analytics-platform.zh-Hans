---
title: 选择Customer Journey Analytics迁移路径
description: 了解迁移到Customer Journey Analytics时可能的迁移路径的优点和缺点
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 7bc4425f11980780ab64a201029cd63e4bd7849c
workflow-type: tm+mt
source-wordcount: '2080'
ht-degree: 2%

---

# 第2步：选择迁移路径

+++展开此部分可查看此页面上的信息在较大的迁移过程中所处的位置。 确保所有先前的迁移步骤均已完成。

在继续此部分之前，请先确保已完成所有以前的迁移任务。

此页面上的信息介绍了迁移的步骤2，如下表所示：

| 迁移任务 | 详细信息 |
|---------|----------|
| **第1步： [迁移入门](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 了解迁移到Adobe Analytics的好处以及基本迁移过程。 |
| <span class="preview">**第2步：选择迁移路径**</span> | <span class="preview">可以使用各种方法迁移到Customer Journey Analytics。 根据贵组织当前的Adobe Analytics环境和长期目标，选择最适合贵组织的方法。</span> |
| **步骤3： [将数据发送到Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 将数据发送到Adobe Experience Platform的过程因您在步骤2中选择的迁移路径而异。 |
| **第4步： [保留历史数据](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多数组织都需要将其历史Adobe Analytics数据保留一定时间。 可以使用各种选项来完成此操作。 |
| **步骤5： [执行其他实施任务](/help/getting-started/cja-getting-started.md)** | 在迁移过程的这一阶段，您需要在Customer Journey Analytics环境准备就绪之前执行各种任务。<p>这些附加任务适用于从Adobe Analytics进行的迁移以及新的Customer Journey Analytics实施。</p><p>这些任务包括：</p><ul><li>将其他数据引入Experience Platform</li><li>在Platform数据集与Customer Journey Analytics之间创建连接</li><li>创建数据视图</li><li>移植报表API使用情况</li><li>考虑数据馈送和Data Warehouse</li><li>迁移项目和组件</li><li>Planning用户载入</li></ul> <p>有关更多信息，请参阅 [Customer Journey Analytics快速入门](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

在决定迁移到Customer Journey Analytics后，您需要确定组织的最佳迁移路径。

您选择的从Adobe Analytics迁移到Customer Journey Analytics的路径取决于以下因素：

* 您现有的Adobe Analytics实施

* 您的未来目标

使用本页上的信息可确定哪种Customer Journey Analytics迁移路径最符合贵组织的当前实施和未来目标。

要确定组织的最佳迁移路径，应按顺序阅读以下部分：

1. 首先， [了解可用的迁移路径](#understand-migration-methods).

1. 然后， [评估您可用的迁移路径](#assess-the-migration-methods-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. 最后， [权衡每个迁移路径的优缺点](#weigh-the-advantages-and-disadvantages-of-the-migration-methods-available-to-you).

## 了解迁移路径

从Adobe Analytics迁移到Customer Journey Analytics存在各种迁移路径。

通常，每个迁移路径在执行迁移所需的工作量级别以及迁移完成后实现的长期可行性方面有所不同。

下表列出了每种迁移路径、其工作量及其长期可行性：

| 迁移路径 | 工作量 | 长期生存能力 |
|---------|----------|---------|
| **Experience PlatformWeb SDK的新实施**</br>&#x200B;虽然从技术上讲这并非迁移，但您可以通过重新实施Experience PlatformWeb SDK来开始使用Customer Journey Analytics，从而开始将数据发送到Adobe Experience PlatformEdge Network。 <p>对于尚未使用Web SDK的组织，此迁移路径可能是将数据导入Edge Network的最直接方法，因为它所需的步骤最少；但是，由于所有工作都是预先完成的（例如创建XDM架构），因此它需要更大的初始工作。</p><p>基本步骤为：</p><ol><li>为您的组织创建XDM架构。</li><li>实施Web SDK。</li><li>将数据发送到Platform。</li></ol> | 高 | 高 |
| **迁移Adobe Analytics实施以使用Web SDK**</br>&#x200B;如果您的Adobe Analytics实施AppMeasurement或Analytics扩展，则可以对其进行迁移，以使用Adobe Experience Platform Web SDK在将数据发送到Customer Journey Analytics之前开始向Edge Network和Adobe Analytics发送数据。<p>这是将数据导入Edge Network的最简单、最顺畅的方法；它需要更多的步骤，但提供了从Adobe Analytics到Customer Journey Analytics的更系统化的过渡，并带有更具体的里程碑。</p><p>基本步骤为：</p><ol><li>将您现有的Adobe Analytics实施移动到Web SDK中，并验证所有内容在Adobe Analytics中均可正常工作。</li><li>根据需要为您的组织创建XDM架构。</li><li>使用数据流映射将数据对象中的所有字段映射到您的XDM架构。</li><li>将数据发送到Platform。</li></ol> | 审核 | 高 |
| **配置现有的Adobe Analytics Web SDK实施**</br>&#x200B;如果您的Adobe Analytics实施已经在使用Adobe Experience Platform Web SDK，则您可以开始轻而易举地将数据发送到Customer Journey Analytics。<p>在将数据发送到Customer Journey Analytics之前，请考虑更新您的Adobe Analytics架构，以满足贵组织的特定需求以及您将使用的任何其他平台应用程序。</p><p>基本步骤为：</p><ol><li>开始向Customer Journey Analytics发送数据。<!-- What's involved here? Just point it at CJA? --></li><li>（可选）根据需要为您的组织创建XDM架构。</li><li>（视情况而定）如果您创建了XDM架构，请使用数据流映射将数据对象中的所有字段映射到XDM架构。</li></ol> | 低 | 高 |
| **使用Analytics源连接器**</br>&#x200B;如果您的Adobe Analytics实施AppMeasurement或Analytics扩展，则可以开始以Customer Journey Analytics将数据发送到数据视图。<p>这是将数据导入Customer Journey Analytics的最简单方法，但长期而言是最不可行的方法。</p> | 低 | 低 |

{style="table-layout:auto"}

使用下图有助于直观显示每个迁移路径在工作量级别和长期可行性方面所处的范围：

![cja迁移路径](assets/cja-migration-methods.png)

## 根据您当前的Adobe Analytics实施评估可用的迁移路径

并非所有迁移路径都适用于每种类型的Adobe Analytics实施。

请通过以下信息帮助您了解哪种迁移路径最适合您的组织。

如果您需要更具体的建议、指导或支持，请联系您的Adobe代表。

| 现有Adobe Analytics实施 | 可用的迁移路径 |
|---------|----------|
| AppMeasurement | <ul><li>Experience PlatformWeb SDK的新实施</li><li>将Adobe Analytics迁移到Web SDK</li><li>Analytics源连接器</li></ul> |
| Adobe Analytics 扩展 | <ul><li>Experience PlatformWeb SDK的新实施</li><li>将Adobe Analytics迁移到Web SDK</li><li>Analytics源连接器</li></ul> |
| Web SDK | <ul><li>配置Adobe Analytics Web SDK实施以将数据发送到Customer Journey Analytics</li></ul> |

{style="table-layout:auto"}

## 权衡可供您使用的迁移路径的优缺点

根据您现有的Adobe Analytics实施，给定迁移路径的优缺点会有所不同。

在使用以下信息确定适合您的迁移路径之前，请查看中的信息 [了解迁移路径](#understand-migration-methods) 如果你还没有的话。

### 对于使用的Adobe Analytics实施：AppMeasurement和Adobe Analytics扩展

以下是适用于已使用AppMeasurement或Adobe Analytics扩展实施了Adobe Analytics的组织可用的迁移路径。 展开每个部分可查看每个迁移路径的优缺点。

**迁移路径：**

+++Experience PlatformWeb SDK的新实现

| 优势 | 缺点 |
|----------|---------|
| <ul><li>使用XDM架构和灵活的架构来定义所需的任何字段，并且只定义相关的字段(让您从Adobe Analytics体验事件字段组中移开)</li><li>不依赖于Adobe Analytics命名法(属性、eVar、事件等)</li><li>没有字符限制问题（属性有 100 个字符）</li><li>高性能报表和数据可用性，因为Adobe Experience Platform是专为提供强大功能而构建的 [实时个性化用例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>经得起未来考验（将获得所有最新特性和功能）</li><li>在其他Experience Cloud产品（AJO、RTCDP等）之间合并Adobe Experience Cloud数据收集的标记</li><li>[第一方设备 ID](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html) 可提高访客识别的准确性</li></ul> | <ul><li>最耗时、最苛刻的迁移路径<p>必须先在XDM中重新创建完整架构，然后才能开始实施Web SDK</p></li></ul> |

{style="table-layout:auto"}

+++

+++将Adobe Analytics迁移到Web SDK | 优点 | 缺点 | ------------------- | <ul><li>使您能够迁移至Web SDK而不影响您现有的Adobe Analytics报表。</li><li>保留已在Adobe Analytics实施中配置的规则和数据元素（适用于使用Analytics扩展的组织）。</li><li>提供灵活性，以便以后为您的组织创建XDM架构：灵活的架构用于定义所需的任何字段，并且只定义相关的字段。</br>不需要Adobe Experience Platform中的“Adobe Analytics体验事件字段”组。 <!-- With the new implementation, you're double-counting with 2 implementation; with the migration, you're double-counting, but both of them are through Edge Network. --></li><li>不依赖于Adobe Analytics命名法(属性、eVar、事件等)</li><li>没有字符限制问题（属性有 100 个字符）</li><li>高性能报表和数据可用性，因为Adobe Experience Platform是专为提供强大功能而构建的 [实时个性化用例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>经得起未来考验（将获得所有最新特性和功能）</li><li>在其他Experience Cloud产品（AJO、RTCDP等）之间合并Adobe Experience Cloud数据收集的标记</li><li>[第一方设备 ID](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html) 可提高访客识别的准确性</li></ul> | <ul><li>在将来的某个时刻必须符合XDM架构，使用数据流映射。</li><li>会产生一些技术债务。 例如，可以保留旧版AppMeasurement或Analytics扩展代码。 </li></ul> |

{style="table-layout:auto"}

+++

+++使用Analytics源连接器 | 优点 | 缺点 | ------------------- | <ul><li>最省时和最苛刻的迁移路径。 <p>以最少的投资将数据快速迁移到Customer Journey Analytics</p></li></ul> | <ul><li>数据不会发送到Edge Network，并且无法与其他Adobe Experience Platform应用程序共享；它仅受Customer Journey Analytics限制<li>未来难以迁移到Web SDK</li><li>在架构中使用Analytics Experience Event字段组。</br>此字段组添加了许多Customer Journey Analytics架构中不需要的Adobe Analytics事件。  这可能会导致Customer Journey Analytics所需的架构更加杂乱、复杂。</li><li>最高级别的 [延迟](/help/admin/guardrails.md#latencies) 跨所有实施方法</li></ul> |

{style="table-layout:auto"}

+++

### 对于使用的Adobe Analytics实施： Web SDK

以下迁移路径适用于已使用Experience PlatformWeb SDK实施Adobe Analytics的组织：

**迁移路径：**

+++配置Adobe Analytics Web SDK实施以将数据发送到Customer Journey Analytics

| 优势 | 缺点 |
|----------|---------|
| 如果您的Adobe Analytics实施已经在使用Web SDK，则这是首选的迁移路径。 <p>使用此实施方法时，您可以选择是否使用现有Adobe Analytics架构，也可以更新到XDM架构以在开始使用其他Platform应用程序时更好地符合组织的需求。</p><p>**使用Adobe Analytics架构**</p><p>使用Adobe Analytics架构的优势包括：</p><ul><li>轻松迁移<p>如果您已使用Adobe Experience Platform Web SDK将数据发送到Adobe Analytics，则可以将其他服务添加到您的数据流以将数据发送到Adobe Experience Platform(然后可以在您的Customer Journey Analytics配置中使用)。</p></li></ul><p>使用Adobe Analytics架构的缺点包括：</p><ul><li>虽然使用Adobe Analytics架构不会限制您如何将其与其他Platform应用程序一起使用，但它的确会导致架构比不使用该架构时复杂得多。 这是因为Adobe Analytics架构包含许多特定于Adobe Analytics的对象，您的组织可能不会使用这些对象。<p>当需要对架构进行更改时，您必须筛选成千上万个未使用的字段以查找需要更新的字段。</p></li></ul><p>**使用XDM架构**</p><p>更新XDM架构的优点包括：</p><ul><li>简化架构，根据贵组织的需求以及您使用的特定平台应用程序量身定制。</li><p>当需要对架构进行更改时，您不必在数千个未使用的字段中进行筛选，即可找到需要更新的字段。</p></ul><p>更新XDM架构的缺点包括：</p><ul><li>在开始向Customer Journey Analytics发送数据之前，需要更新架构是一个耗时的过程。</li></ul> | 无 |

{style="table-layout:auto"}

+++

## 接下来，将数据映射到XDM架构

按照上表中的链接向Experience Platform发送数据后，您可能需要 [将数据映射到XDM架构](/help/getting-started/cja-migration/cja-migration-xdm.md)，具体取决于您选择的实施方法。

以下实施方法要求您将数据映射到XDM架构：

* 从Adobe Analytics标记扩展迁移到Web SDK标记扩展

* 配置现有的Adobe Analytics Web SDK实施以将数据发送到Customer Journey Analytics

或者，如果您选择重新实施Experience PlatformWeb SDK，则无需映射，因为您已经 [设置新的XDM架构](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) 作为新实施的一部分。

如果您选择使用Analytics Source Connector进行迁移，则不需要映射，因为Analytics Source Connector使用您现有的Adobe Analytics架构，而不是XDM架构。
