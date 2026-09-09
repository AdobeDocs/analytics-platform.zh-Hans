---
title: 从AppMeasurement或标记迁移到XDM
description: 了解如何从AppMeasurement或标记迁移到XDM
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
source-git-commit: db34e721f156b3eb0aab20b2dca57e194c83d6fb
workflow-type: tm+mt
source-wordcount: '2379'
ht-degree: 5%

---

# 从标记迁移到XDM {#upgrade-migration-planner}

{{upgrade-note-step}}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_intro"
>title="迁移概述"
>abstract="升级到Adobe Experience Platform时，将标记实施迁移到Customer Journey Analytics Web SDK。<br/>继续现有的迁移或开始新的迁移。"

<!-- markdownlint-enable MD034 -->

Migration Planner提供了一个迁移向导，可自动执行从标记到XDM的迁移，包括架构创建。 这些是与从Adobe Analytics升级到Customer Journey Analytics相关的最复杂和最耗时的任务之一。

## 支持的Adobe Analytics实施

Migration Planner支持使用Analytics扩展（标记）的Adobe Analytics实施。

迁移规划程序不可用于使用AppMeasurement或Experience Platform Web SDK的Adobe Analytics实施。

## 迁移规划者中包含的升级任务

Migration Planner提供了一个迁移向导，可自动完成以下复杂且耗时的升级任务：

* **XDM架构创建**：自动创建基于Adobe Analytics报表包变量的新XDM架构。 Migration Planner智能扫描您的Adobe Analytics报表包变量，然后使用该信息在XDM中创建必要字段。 生成的XDM架构仅包含Customer Journey Analytics架构中所需的那些字段。

  或者，您可以指向现有的XDM架构，也可以从头开始创建XDM架构。

  +++ 如果选择从头开始创建XDM架构，可以展开此部分以了解有关有用资源的信息。

  * [规划您的 XDM 模式架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md){target="_blank"}。

  * [在 Adobe Experience Platform 中创建所需的自定义架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}。

    创建架构时请考虑以下选项：

    * 如果要将 Customer Journey Analytics 与 RTCDP 集成，则必须在架构上启用&#x200B;**[!UICONTROL 轮廓]**&#x200B;选项，如[创建用于 Customer Journey Analytics 的 XDM 架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md){target="_blank"}中所述。 在启用该选项后，当数据被引入基于此架构的数据集中时，该数据将合并到实时客户轮廓。

    * 如果您想要包含流式处理媒体数据，则必须[将您的架构配置为可以摄取和使用流式传输数据](/help/data-ingestion/streaming.md){target="_blank"}。

    +++

  * **将Adobe Analytics实施迁移到Web SDK**：无论您的Adobe Analytics实施是使用标记还是JavaScript，迁移规划者都会引导您完成迁移到Experience Platform Web SDK的操作。

    * **将标记属性从AppMeasurement迁移到Web SDK**：

    * **将JavaScript实施从AppMeasurement迁移到Web SDK JavaScript库**

  * **在Customer Journey Analytics中创建数据视图**：根据创建的XDM架构字段，自动创建数据视图并使用组件填充它们。


## 开始之前

在创建迁移之前，请确保您具备以下条件：

* 受支持的Adobe Analytics实施（标记的Analytics扩展）。 请参阅[支持的Adobe Analytics实施](#supported-adobe-analytics-implementations)。

* 在您登录的Adobe组织中访问要迁移的Experience Cloud Tags属性。

* 访问要将其变量映射到XDM的Adobe Analytics报表包。

* 在Adobe Experience Platform中创建架构的权限。

<!-- Confirm the exact roles and permissions required to use the Migration Planner and to create schemas and Data Views. -->

## 将Analytics实施迁移到Web SDK

迁移将经历三个阶段：[!UICONTROL **审核**]、[!UICONTROL **映射**]&#x200B;和&#x200B;[!UICONTROL **实现**]。 使用以下步骤创建迁移，然后继续[验证并部署迁移](#validate-and-deploy-a-migration)以完成每个阶段。

1. 在Customer Journey Analytics中，打开&#x200B;[!UICONTROL **迁移规划者**]。

   <!-- Confirm the exact navigation path to open the Migration Planner in Customer Journey Analytics. -->

1. 在迁移规划者的&#x200B;[!UICONTROL **迁移**]&#x200B;选项卡上，选择&#x200B;[!UICONTROL **新建**]。

   ![新建迁移对话框，您可以在其中选择迁移类型并输入迁移名称。](assets/migration-planner-new-migration.png)

1. 指定以下信息：

   | 字段名称 | 功能 |
   | --------- | ---------- |
   | [!UICONTROL **名称**] | 为此迁移指定一个名称。 |
   | [!UICONTROL **描述**] | 为此迁移指定可选描述。 |
   | [!UICONTROL **标记属性**] | 选择要迁移的Adobe Tags属性。 有关详细信息，请参阅Experience Platform文档中的[属性](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/admin/companies-and-properties){target="_blank"}。 |
   | [!UICONTROL **标记库**] | 选择迁移所基于的标记库快照。 快照可确定使用的标记库版本。 有关详细信息，请参阅Experience Platform文档中的[发布概述](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/publish/overview){target="_blank"}。 |

1. 在&#x200B;[!UICONTROL **迁移名称**]&#x200B;字段中，为此迁移指定一个名称，然后选择&#x200B;[!UICONTROL **下一步**]。

1. 选择要迁移的标记属性，然后选择&#x200B;[!UICONTROL **下一步**]。

   只显示已登录Experience Cloud组织可用的标记属性。

1. 选择要迁移的标记库快照，然后选择&#x200B;[!UICONTROL **下一步**]。

   快照将确定迁移所基于的标记库版本。 每个快照都会显示其环境（如&#x200B;[!UICONTROL **开发**]、[!UICONTROL **暂存**]&#x200B;或&#x200B;[!UICONTROL **生产**]）。

1. 选择映射集以确定Analytics变量将如何映射到XDM架构字段。

   执行以下其中一项操作：

   * 选择&#x200B;[!UICONTROL **创建新映射集**]。

   * 选择现有映射集。

     可以选择在上次迁移期间创建的映射集或作为独立映射集创建的映射集。

     跨多个迁移重用映射集会将相同的映射应用于每个迁移。

1. 选择&#x200B;[!UICONTROL **创建迁移**]。

1. 继续下面的部分[验证并部署迁移](#validate-and-deploy-a-migration)。

## 验证和部署迁移

创建迁移后，打开它以完成其三个阶段：[!UICONTROL **审核**]、[!UICONTROL **映射**]&#x200B;和&#x200B;[!UICONTROL **实施**]。

1. 在Migration Planner中，选择&#x200B;[!UICONTROL **迁移**]&#x200B;选项卡。

1. 在要验证的迁移旁边，选择&#x200B;[!UICONTROL **打开**]。

   迁移概述页面显示了要完成的三个阶段，以及迁移及其工件的摘要。

   ![包含“审核”、“映射”和“实施”阶段卡的迁移概述页面。](assets/migration-planner-overview.png)

1. 完成&#x200B;[!UICONTROL **审核**]&#x200B;阶段：

   1. 在审核卡片（[!UICONTROL **标记扩展审核**]&#x200B;或&#x200B;[!UICONTROL **JavaScript审核**]，具体取决于您的迁移类型）中，选择&#x200B;[!UICONTROL **开始审核**]&#x200B;以查看迁移中包含的规则和数据元素。

      ![审核页面，您可以在其中选择规则和数据元素并解决任何调查结果。](assets/migration-planner-audit.png)

   1. 在&#x200B;[!UICONTROL **规则**]&#x200B;和&#x200B;[!UICONTROL **数据元素**]&#x200B;选项卡上，选择要包含在迁移中的项。

      库&#x200B;**]中标记为[!UICONTROL **&#x200B;的规则已发布。 标记为&#x200B;[!UICONTROL **属性**]&#x200B;的规则仅存在于属性中，但不是所选库的一部分。

   1. 复查所选规则的任何调查结果。 对于每个发现结果，选择&#x200B;[!UICONTROL **查看**]&#x200B;以解决该问题，或选择&#x200B;[!UICONTROL **忽略**]&#x200B;以保持未寻址。

      例如，当两个规则具有相同的事件和条件时，[!UICONTROL **重复规则事件**]&#x200B;发现结果允许您保留一个规则并删除另一个规则，或者选择&#x200B;[!UICONTROL **不执行任何操作**]&#x200B;认可该发现结果而不做更改。

      在继续之前，解决调查结果是可选的。 有关发现结果类型的完整列表以及如何解析每个类型，请参阅[查看和解析审核发现结果](#review-and-resolve-audit-findings)。

   1. 选择&#x200B;[!UICONTROL **保存并继续**]。

1. 完成&#x200B;[!UICONTROL **映射**]&#x200B;阶段：

   1. 在&#x200B;[!UICONTROL **Analytics → XDM映射**]&#x200B;卡中，选择&#x200B;[!UICONTROL **创建新映射**]。

   1. 选择是基于Analytics变量创建新架构，还是针对现有Experience Platform架构进行映射，然后按照提示选择报表包、映射字段并查看架构。

      有关详细步骤，请参阅[将Analytics变量映射到XDM字段](#map-analytics-variables-to-xdm-fields)。 若要跨迁移重用一组映射，请参阅[创建和管理映射集](#create-and-manage-mapping-sets)。

1. 完成&#x200B;[!UICONTROL **实施**]&#x200B;阶段：

   1. 在&#x200B;[!UICONTROL **生成Web SDK实现**]&#x200B;卡中，使用审核和映射结果生成Web SDK实现包，然后将其部署到您的站点。

      有关详细步骤，请参阅[生成和部署Web SDK实施](#generate-and-deploy-the-web-sdk-implementation)。


## 审核并解决审核发现

在&#x200B;[!UICONTROL **审核**]&#x200B;阶段，迁移规划程序将标记所选规则上的调查结果。 在继续之前解决调查结果是可选的，但解决这些调查结果有助于确保干净迁移。

对于每个发现结果，选择&#x200B;[!UICONTROL **查看**]&#x200B;以打开该发现结果并选择如何解析它，或选择&#x200B;[!UICONTROL **忽略**]&#x200B;以保持未寻址。

Migration Planner可以标记以下类型的调查结果：

* [!UICONTROL **重复的规则事件**]：两个或更多规则的事件和条件相同。 当您查看发现结果时，比较主要规则和重复规则，然后保留一个规则并删除另一个规则，或者选择&#x200B;[!UICONTROL **不执行任何操作**]&#x200B;以认可该发现结果而不做更改。

* [!UICONTROL **重复的规则逻辑**]：规则共享相同的逻辑。<!-- Confirm the exact remediation options for this finding type. -->

* [!UICONTROL **规则操作顺序错误**]：规则的操作按顺序运行，可能会在迁移期间导致问题。<!-- Confirm the exact remediation options for this finding type. -->

如果发现结果没有引导式修正，则迁移规划者显示&#x200B;[!UICONTROL **无可用的修正详细信息**]。 手动查看调查结果，并在解决该调查结果时将其关闭。

[!UICONTROL **个调查结果**]&#x200B;面板显示您已处理的调查结果数量以及仍打开的调查结果数量。 完成后，选择&#x200B;[!UICONTROL **保存并继续**]。

## 将Analytics变量映射到XDM字段

在&#x200B;[!UICONTROL **映射**]&#x200B;阶段，您可以将Analytics变量映射到XDM字段，并生成或选择目标架构。 在&#x200B;[!UICONTROL **Analytics → XDM映射**]&#x200B;卡中，选择&#x200B;[!UICONTROL **新建映射**]，然后完成以下步骤：

1. **架构选择**：选择是基于Analytics变量创建新架构，还是基于现有Experience Platform架构进行映射。

1. **报表包**：选择要映射其变量的Analytics报表包。

1. **Experience Platform架构**：创建目标XDM架构，或选择要映射的现有架构。

1. **手动映射**：查看自动映射并调整单个Analytics变量映射到XDM字段的方式。

1. **查看架构**：查看生成的映射和架构，然后确认。

<!-- The XDM mapping editor was not captured in the walkthrough. Confirm the exact steps, controls, and options on each step (Schema choice, Report suite, Experience Platform schema, Manual mapping, Review schema). -->

若要跨迁移重用一组映射，请参阅[创建和管理映射集](#create-and-manage-mapping-sets)。

## 比较迁移输出

在部署迁移概述页面之前，使用&#x200B;[!UICONTROL **比较输出**]&#x200B;验证迁移。

<!-- The Compare outputs screen was not captured in the walkthrough. Confirm what the comparison shows (for example, AppMeasurement output compared with the Web SDK / XDM output) and how to interpret the results. -->

## 生成和部署Web SDK实施

在&#x200B;[!UICONTROL **实施**]&#x200B;阶段，迁移规划者使用您的审核和映射结果来构建Web SDK实施包。

1. 在迁移概述页面的&#x200B;[!UICONTROL **生成Web SDK实现**]&#x200B;卡中，生成实现包。

1. 通过选择&#x200B;[!UICONTROL **生成标记库**]&#x200B;生成迁移的标记库。

1. 配置双重部署，然后将Web SDK实施部署到您的站点。

<!-- This stage was not captured in the walkthrough. Confirm the exact steps for generating the package, configuring the dual deployment, building the tag library, and deploying to the site. -->

有关此阶段生成的项目，请参阅[导出迁移项目](#export-migration-artifacts)。

## 导出迁移对象

迁移概述页面提供迁移规划者生成的对象。 您可以从&#x200B;[!UICONTROL **项目项目**]&#x200B;面板中下载单个项目，也可以选择&#x200B;[!UICONTROL **全部导出**]&#x200B;以一次导出所有项目。

可以使用以下工件：

* [!UICONTROL **映射JSON**]： Analytics变量与XDM字段之间的映射。

* [!UICONTROL **XDM架构(JSON)**]：为迁移创建的目标XDM架构。

* [!UICONTROL **标记开发库**]：为Web SDK实现生成的标记库。

每个项目都显示其状态，如&#x200B;[!UICONTROL **就绪**]&#x200B;或&#x200B;[!UICONTROL **未生成**]。 在相应阶段生成工件后，即可下载工件。

## 创建和管理映射集 {#mapping-sets}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_sets"
>title="映射集"
>abstract="映射集确定Analytics变量如何映射到XDM字段。<br/>创建新映射集或选择现有映射集以跨多个迁移应用相同的映射。 您还可以在其他迁移任务中引用映射集。"

<!-- markdownlint-enable MD034 -->

映射集确定Analytics变量如何映射到XDM架构字段。

您可以在迁移过程](#migrate-an-analytics-implementation-to-the-web-sdk)中创建新映射集[。 或者，您也可以创建一个独立的映射集，以便用于未来的迁移或其他迁移任务。

### 创建独立映射集 {#xdm-mapping}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_schema"
>title="选择架构"
>abstract="映射集确定Analytics变量如何映射到XDM字段。<br/>创建新映射集或选择现有映射集以跨多个迁移应用相同的映射。 您还可以在其他迁移任务中引用映射集。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_field_group"
>title="字段组首选项"
>abstract="选择标准字段组以尽可能使用已发布的Adobe字段组。 这样可提高最大一致性，并在没有标准字段可用时回退到自定义租户字段。<br/>选择自定义字段组以尽可能使用租户 — 命名空间自定义字段。 这有助于实现最大的灵活性。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="migration_mapping_lookback"
>title="回顾时段"
>abstract="控制在确定哪些变量正在主动接收数据时回溯多远。 架构中包含的变量包含回溯时段内的数据。"

<!-- markdownlint-enable MD034 -->

1. 在Migration Planner中，选择&#x200B;[!UICONTROL **映射集**]&#x200B;选项卡。

1. 选择&#x200B;[!UICONTROL **新映射集**]。

1. 在&#x200B;[!UICONTROL **名称**]&#x200B;字段中，输入描述性名称以便稍后识别此映射集，然后选择&#x200B;[!UICONTROL **下一步**]。

1. 从&#x200B;[!UICONTROL **报表包**]&#x200B;菜单中，选择要将其变量映射到XDM字段的报表包，然后选择&#x200B;[!UICONTROL **下一步**]。

1. 在&#x200B;[!UICONTROL **为XDM映射选择架构部分**]&#x200B;中，选择是基于Analytics变量创建新架构，还是基于现有Experience Platform架构进行映射。

   选择创建新架构将指导您完成将Analytics变量映射到XDM字段的过程。 选择使用现有架构时，您可以手动将变量映射到Experience Platform架构注册表中的预注册架构。

   <!-- Screenshot pending: the XDM mapping editor (Create new mapping) was not available for capture in the walkthrough. -->

   * [!UICONTROL **创建新架构**]：运行基本和高级扫描以自动为Analytics变量建议XDM字段映射，然后查看生成的架构。

   * [!UICONTROL **使用现有架构**]：搜索并选择已在Experience Platform架构注册表中注册的架构，然后手动将Analytics变量拖动到XDM字段。

1. 在&#x200B;[!UICONTROL **字段组偏好设置**]&#x200B;下拉菜单中，选择要如何将自定义变量组织到字段组中：

   * [!UICONTROL **标准优先**]：尽可能使用已发布的Adobe字段组。 这样可提高最大一致性，并在没有标准字段可用时回退到自定义租户字段。

   * [!UICONTROL **自定义优先**]：尽可能使用租户命名空间自定义字段。 这有助于实现最大的灵活性。

   <!-- * [!UICONTROL **Ask each time**]: Prompt for each signal so you can decide individually. -->

1. 在&#x200B;[!UICONTROL **回顾期间**]&#x200B;字段中，选择在确定哪些变量正在主动接收数据时要回顾多远。 架构中包含的变量包含回溯时段内的数据。

1. 选择&#x200B;[!UICONTROL **创建映射集**]。

新的映射集显示在&#x200B;[!UICONTROL **映射集**]&#x200B;选项卡上，您可以在其中打开该映射集以查看其详细信息。

### 导出映射集

您可以导出映射集以将其用于其他迁移任务或其他工具。

<!-- Confirm where the export control lives (the Mapping sets list exposes only an Open action) and the export format (for example, JSON). -->

### 发布和版本映射集

每个映射集都有一个状态和版本。 在&#x200B;[!UICONTROL **映射集**]&#x200B;选项卡上，映射集可以显示为：

* [!UICONTROL **草稿**]：映射集仍在编辑中。

* [!UICONTROL **已发布**]：映射集已最终完成。

* 迁移&#x200B;**]中的[!UICONTROL **：映射集绑定到一个或多个迁移。

<!-- Confirm how to publish a mapping set, how versions are created (v1, v2, v3), and what "bindings" represent. -->

### 编辑映射集<!-- can you? -->

<!-- Steps pending: confirm whether a mapping set can be edited after creation and where the edit control lives (the Mapping sets list exposes only an Open action). -->

### 删除映射集<!-- can you? -->

<!-- Steps pending: confirm whether a mapping set can be deleted, and whether deletion is blocked while the set is in use by a migration. -->

## 管理现有迁移

### 查找并跟踪您的迁移

[!UICONTROL **迁移**]&#x200B;选项卡列出了您的迁移及其进度。 使用它查找要继续的迁移，或检查正在进行的迁移的状态。

* **搜索**：使用搜索字段按名称或属性查找迁移。

* **筛选器**：按迁移类型或状态筛选列表。

* **跟踪进度**：每个迁移都会显示其在三个阶段中的进度（例如，1/3）以及整体状态：

  * [!UICONTROL **未启动**]：迁移已创建，但没有完成任何阶段。

  * [!UICONTROL **进行中**]：至少完成了一个阶段。

  * [!UICONTROL **已完成**]：所有三个阶段都已完成。

要继续迁移，请选择迁移旁边的&#x200B;[!UICONTROL **打开**]。

<!-- The row actions ("...") menu was not captured in the walkthrough. Confirm which actions it contains (for example, rename, duplicate, or delete a migration). -->

