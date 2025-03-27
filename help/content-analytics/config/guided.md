---
title: Content Analytics指导配置
description: 如何使用载入引导式配置配置内容分析
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: 20767a4672319602d35435aeedb76749a245e691
workflow-type: tm+mt
source-wordcount: '2428'
ht-degree: 25%

---

# Content Analytics指导配置

{{draft-aca}}

{{release-limited-testing}}

引导式配置可帮助您快速轻松地配置Content Analytics。 引导式配置使用向导来设置自动为组织配置Content Analytics的要求。 在&#x200B;**[!UICONTROL 配置]**&#x200B;屏幕中，您可以创建新配置或编辑现有配置。

>[!IMPORTANT]
>
>您组织中的每个沙盒只能有一个内容分析配置。

访问Content Analytics配置

* 从Customer Journey Analytics的主菜单中选择&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL Content Analytics配置]**。

在&#x200B;**[!UICONTROL Content Analytics配置]**&#x200B;屏幕中，您会看到一个现有Content Analytics配置的表。

![Content Analytics配置](../assets/aca-configuration-table.png)
对于每个配置，提供了以下详细信息：

| 列 | 描述 |
|---|---|
| **[!UICONTROL 名称]** | 配置的名称。 |
| **[!UICONTROL 创建者]** | 创建配置的技术帐户。 |
| **[!UICONTROL 创建于]** | 创建配置时的时间戳。 |
| **[!UICONTROL 修改于]** | 上次修改配置时的时间戳。 |
| **[!UICONTROL 沙盒]** | （计划要）配置和实施Content Analytics的组织内的沙盒。 |
| **[!UICONTROL 状态]** | 配置的状态。 状态可以是：<br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 草稿]**：配置已保存以供稍后使用，未部署。<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL 失败]**：配置失败。 您可以选择&#x200B;**[!UICONTROL 编辑]**&#x200B;以获取有关失败的信息。 Adobe可主动处理任何失败的实施。 您可以联系客户关怀部门了解详细信息。<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 完成]**：配置已成功完成并实施。 |

您可以使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)自定义表。 选择要在&#x200B;**[!UICONTROL 自定义表]**&#x200B;对话框中显示哪些列，然后选择&#x200B;**[!UICONTROL 应用]**&#x200B;以应用更改。

在Content Analytics **[!UICONTROL 配置]**&#x200B;屏幕中，您可以创建新配置或编辑现有配置。

要创建新配置，请执行以下操作：

* 选择&#x200B;**[!UICONTROL 创建配置]**。 此操作打开[引导式配置向导](#guided-configuration-wizard)。

要编辑现有配置，请执行以下操作：

* 为现有Content Analytics配置选择![更多](/help/assets/icons/More.svg)，然后选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**。 此操作打开[引导式配置向导](#guided-configuration-wizard)。

## 引导式配置向导

引导式配置向导包含四个部分（[详细信息](#details)、[数据视图](#data-view)、[体验捕获和定义](#experience-capture-and-definition)以及[数据收集](#data-collection)），每个部分都会提示您提供正确设置和配置Content Analytics所需的详细信息。 请先完成每个部分，然后再转到下一部分，因为部分中的某些设置可能取决于前面部分中的配置值。

### 详细信息 {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="详细信息"
>abstract="提供该连接的名称。在&#x200B;**[!UICONTROL 数据视图]**、**[!UICONTROL 体验捕捉和定义]**&#x200B;以及&#x200B;**[!UICONTROL 数据收集]**&#x200B;部分中，您可以提供更多详细信息，以确保正确配置内容分析。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="详细信息"
>abstract="本指南设置了配置内容分析所需的要求。请为此配置提供名称"

<!-- markdownlint-enable MD034 -->

每个配置都需要一个唯一的名称。 例如：`Example Content Analytics configuration`。保存或实施配置需要此名称。

![内容分析配置详细信息](../assets/aca-configuration-details.png)


### 数据视图 {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="数据视图"
>abstract="要配置内容分析，您需要选择一个现有的数据视图。因此，您可以将内容分析数据与其他数据合并。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="数据视图"
>abstract="从 Customer Journey Analytics 中选择一个您希望将内容分析数据与之合并的现有数据视图。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="数据视图"
>abstract="从 Customer Journey Analytics 中选择一个您希望将内容分析数据与之合并的现有数据视图。<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_change_dialog"
>title="新的数据视图"
>abstract="选择新的数据视图导致了该数据视图被更新，使其包含内容分析量度和维度。需要时相关联的连接也会被更新，使其包含内容分析数据集。当前为内容分析配置的连接和数据视图不会更改。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="清理选定的数据视图"
>abstract="您选择的数据视图已为内容分析进行设置。现有的内容分析配置已被移除，数据视图将使用新配置进行设置。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="清理以前的数据视图"
>abstract="您已选择新的数据视图。以前选定的数据视图的内容分析配置已被移除。"

<!-- markdownlint-enable MD034 -->

您的配置要求选择[数据视图](/help/data-views/data-views.md)。

1. 选择数据视图

   * 要为配置选择新的数据视图，请使用![数据](/help/assets/icons/Data.svg) **[!UICONTROL 选择数据视图]**。

     数据视图的![Content Analytics配置](../assets/aca-configuration-dataview.png)

   * 要修改配置的数据视图，请选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**。

     数据视图的![Content Analytics配置](../assets/aca-configuration-dataview-edit.png)


   在这两种情况下，您都会看到&#x200B;**[!UICONTROL 数据视图]**&#x200B;对话框，您可以在其中为您的配置选择数据视图。

   数据视图的![Content Analytics配置 — 数据视图表](../assets/aca-configuration-dataview-dialog.png)

   对于新配置，列表仅显示与没有活动配置的沙盒关联的数据视图。 此外，您只会看到与您有权访问的沙盒关联的数据视图，以及您有权修改的连接。

   如果您编辑现有配置，则列表仅显示沙盒中可用的、已与现有配置关联的数据视图。

   您可以执行以下操作：

   * 要搜索特定的数据视图，请使用![搜索](/help/assets/icons/Search.svg)字段。
   * 要筛选可用数据视图的列表，请选择![显示筛选器](/help/assets/icons/Filter.svg)。 您可以在[!UICONTROL 连接]、[!UICONTROL 所有者]和[!UICONTROL 沙盒]上筛选列表。<br/>使用![隐藏](/help/assets/icons/Filter.svg) **[!UICONTROL 隐藏筛选器]**&#x200B;以隐藏筛选器窗格。
   * 要定义要在表中显示的列，请选择![列设置](/help/assets/icons/ColumnSetting.svg)。 选择要在&#x200B;**[!UICONTROL 自定义表]**&#x200B;对话框中显示哪些列，然后选择&#x200B;**[!UICONTROL 应用]**&#x200B;以应用更改。

1. 选择![SelectBox](/help/assets/icons/SelectBox.svg)您要使用的数据视图。
1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以确认所选的数据视图。 选择&#x200B;**[!UICONTROL 取消]**&#x200B;以取消。


在Customer Journey Analytics中，数据视图绑定到Customer Journey Analytics [连接](/help/connections/overview.md)。 并且连接基于您组织内的沙盒。 保存配置后，**[!UICONTROL 沙盒]**&#x200B;会根据选定的数据视图，自动填充沙盒的名称。


### 体验捕捉和定义 {#onboarding-experiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="体验捕捉和定义"
>abstract="您可以选择将体验包含在使用内容分析收集的数据中。选中后，您必须定义正则表达式和查询参数的一个或多个组合，以定义要包含体验的 URL。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="体验捕捉和定义"
>abstract="收集内容分析中的体验"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="体验捕捉和定义"
>abstract="指定用于决定内容如何在网站上呈现的参数。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="体验捕捉和定义"
>abstract="您可以在与当前配置关联的标记属性中编辑 Adobe 内容分析扩展中的设置。"

<!-- markdownlint-enable MD034 -->

在此部分中，您可以选择在通过Content Analytics收集的数据中包含体验。  体验是网页上的所有文本，可以使用访问某个网页的初始用户使用的URL重现这些文本。

默认情况下，**[!UICONTROL 包含体验]**&#x200B;处于关闭状态。 在选中时，您必须定义要包含体验的URL。

仅在满足以下条件时，才考虑包含体验：

* 您只能使用面向公众的URL访问网站内容。 访问网站不需要个性化令牌、Cookie或无法通过URL获得的其他机制。
* 必须使用页面URL重现网站上的页面。

要在新的或未实施的配置中包含体验，请执行以下操作：

![Content Analytics配置体验捕获和定义](../assets/aca-configuration-experience.png)

1. 启用&#x200B;**[!UICONTROL 包含体验]**。
1. （可选）指定用于在您的网站上呈现内容的参数。 参数是&#x200B;**[!UICONTROL 域正则表达式]**&#x200B;和&#x200B;**[!UICONTROL 查询参数]**&#x200B;的零个或多个组合。 查询参数指示哪些参数会影响页面上的内容。 此输入允许Content Analytics在定义独特体验时，忽略任何不会影响页面内容的参数。
   1. 输入&#x200B;**[!UICONTROL 域正则表达式]**，例如`/^(?!.*\b(store|help|admin)\b)/`。 确保使用`/`转义正则表达式。 域正则表达式指示这些参数应用于哪些URL。 例如，您可能具有多个站点，并且每个站点的不同参数会驱动内容。 如果查询参数应用于您的所有页面，则可以使用`.*`来指示所有页面。
   1. 指定&#x200B;**[!UICONTROL 查询参数]**&#x200B;的逗号分隔列表，例如`outdoors, patio, kitchen`。
1. 如果要删除域正则表达式和查询参数的组合，请选择&#x200B;**[!UICONTROL 删除]**。
1. 如果要添加其他正则表达式和查询参数组合，请选择&#x200B;**[!UICONTROL 添加正则表达式]**。

要在已实施的配置中编辑现有体验或包含新体验，请执行以下操作：

![Content Analytics配置体验捕获和定义](../assets/aca-configuration-experience-edit.png)

* 切换&#x200B;**[!UICONTROL 包含体验]**&#x200B;以启用或禁用Analysis Workspace中的体验组件、可视化图表和面板的可用性。
* 选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**&#x200B;以编辑Content Analytics中体验的数据收集配置。 您被重定向到与当前配置关联的Tags属性中的[Adobe Content Analytics扩展](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering)。




### 数据收集 {#onboarding-data-collection}

在此部分中，您可以配置如何收集内容分析数据。

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="数据收集"
>abstract="定义您想要使用的标记属性，或者创建一个新的标记属性。并使用正则表达式定义那些您想要包含或排除的页面和资产。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="数据收集"
>abstract="**提供标记属性**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_boldheader"
>title="数据收集"
>abstract="**要包含/排除的页面**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_header"
>title="数据收集"
>abstract="指明在为内容分析收集数据时应&#x200B;**包括**&#x200B;或&#x200B;**排除**&#x200B;哪些页面"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_boldheader"
>title="数据收集"
>abstract="**要包含/排除的资产**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_header"
>title="数据收集"
>abstract="指明在为内容分析收集数据时应&#x200B;**包括**&#x200B;或&#x200B;**排除**&#x200B;哪些资产"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_experiences_edit_button"
>title="数据收集"
>abstract="您可以在与当前配置关联的标记属性中编辑 Adobe 内容分析扩展中的页面设置。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="数据收集"
>abstract="您可以在与当前配置关联的标记属性中编辑 Adobe 内容分析扩展中的资产设置。"

<!-- markdownlint-enable MD034 -->

#### 新配置 {#new-configuration}

在新配置中，您需要定义是使用现有Tags属性还是创建新的Tags属性。 此外，您需要使用正则表达式定义要包含或排除的页面和资产。

* 要使用现有的Tags属性，请执行以下操作：

  ![Content Analytics数据收集现有标记](../assets/aca-configuration-datacollection-existingtag.png)

   1. 选择&#x200B;**[!UICONTROL 选择现有]**。
   2. 从&#x200B;**[!UICONTROL 标记属性]**&#x200B;下拉菜单中选择现有属性。 您可以开始键入以搜索并限制可用选项。

* 要创建新的Tags属性：

  ![Content Analytics数据收集新标记](../assets/aca-configuration-datacollection-newtag.png)

   1. 选择&#x200B;**[!UICONTROL 新建]**。
   1. 指定&#x200B;**[!UICONTROL 标记名称]**，例如`ACA Test for Documentation`。
   1. 指定&#x200B;**[!UICONTROL 域]**，例如`example.com`。

* 如果已选择包含体验，请指示在为Content Analytics收集数据时应包含或排除哪些页面。

   * 为&#x200B;**[!UICONTROL 要包含/排除]**&#x200B;的页面指定正则表达式字符串。 例如：`/^(?!.*documentation).*/`从Content Analytics中排除所有文档页面。 确保使用`/`转义正则表达式。

* 指示在为Content Analytics收集数据时应包含或排除哪些资产。

   * 为&#x200B;**[!UICONTROL Assets指定要包含/排除]**&#x200B;的正则表达式字符串。 例如： `/^(?!.*(logo\.jpg|\.svg)).*$/`从Content Analytics中排除所有徽标JPEG和SVG图像。 确保使用`/`转义正则表达式。


#### 现有配置 {#existing-configuration}

对于现有配置，无法编辑Tags属性。 但是，您可以编辑要包含或排除的页面和资产。

* 要编辑在为Content Analytics收集数据时应包含或排除哪些页面，请在&#x200B;**[!UICONTROL 体验]**&#x200B;下选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**。 您将被重定向到与当前Adobe Content Analytics配置的Tags属性关联的[Content Analytics扩展](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering)。 您可以编辑正则表达式以包含或排除页面。 请确保您[发布](#publish)更改。

* 要编辑在收集内容分析的数据时应包含或排除哪些资产，请在&#x200B;**[!UICONTROL 资产]**&#x200B;下选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**。 您将被重定向到与当前Adobe Content Analytics配置的Tags属性关联的[Content Analytics扩展](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering)。 您可以编辑正则表达式以包含或排除资产。 请确保您[发布](#publish)更改。

### 概要 {#summary}

提供所有必要的详细信息后，摘要将提供已创建或已修改工件的详细信息。

* 当您实施新配置时，您会看到&#x200B;**[!UICONTROL 您几乎可以为Content Analytics]**&#x200B;摘要实施&#x200B;_配置名称_。

* 对于现有的已实施配置，您会看到&#x200B;**[!UICONTROL 您已为内容分析]**&#x200B;摘要实施了&#x200B;_配置名称_。

![Content Analytics配置摘要](../assets/aca-configuration-summary.png)

### 操作 {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="实施确认"
>abstract="如果选择&#x200B;**[!UICONTROL 实施]**，将根据您在此工作流程中提供的输入来配置内容分析。默认情况下，会根据内容分析的一般用途选择几种设置，但您（作为数据控制者）必须检查每个工件的设置，以确认这些设置是根据您的隐私政策、合同权利和义务以及符合适用法律的同意声明要求实施的。<br/><br/>请注意，在手动发布与此配置关联的标记库之前，不会收集任何数据。<br/><br/>为了获取图像和文本的属性，Adobe 使用了以下方式检索属性：<ol><li>根据您配置的数据收集设置，在用户访问网站时捕获的 URL，以及</li><li>托管图像的 URL。</li></ol>您不得对第三方网站上托管的图像进行标记。"

<!-- markdownlint-enable MD034 -->

创建或编辑配置后，以下操作可用。

* **[!UICONTROL 放弃]**：在创建新配置或编辑现有配置时所做的所有更改都将被放弃。
* **[!UICONTROL 保存供以后使用]**：保存对新配置或现有尚未实施的配置所做的更改。 您可以在稍后阶段重新访问配置以进行进一步更改，或实施配置。
* **[!UICONTROL 实施]**：保存和实施新配置或现有尚未实施的配置的设置或更改。 实施包括：

   * **[!UICONTROL Customer Journey Analytics]**&#x200B;配置：
      * 选定的数据视图已更新，将包含Content Analytics维度和量度。
      * 已修改与选定数据视图关联的连接，以包含Content Analytics事件和属性数据集。
      * 向Workspace中添加了Content Analytics报表模板。


   * **[!UICONTROL Adobe Experience Platform]**&#x200B;配置：
      * 创建架构以对Content Analytics事件、资产属性和（如果已配置）体验属性进行建模。
      * 创建数据集以收集Content Analytics事件、资产属性和（如果已配置）体验属性。
      * 创建数据流，该数据流使用功能化服务从Content Analytics事件生成和更新内容属性。


   * **[!UICONTROL 数据收集]**&#x200B;配置：
      * 新的或现有的标记属性配置为支持Content Analytics数据收集。 此配置意味着包含适用于标记的Adobe Content Analytics扩展。
      * 为Content Analytics事件创建数据流。
      * Adobe Content Analytics扩展已配置为确保将Content Analytics事件发送到Content Analytics的数据流。
      * 如果没有为Tags属性配置Web SDK，则会创建新的Web SDK配置，以仅发送Content Analytics事件。
      * 如果为此Tags属性配置了Web SDK，则不会对现有Web SDK配置进行任何更改。


* **[!UICONTROL 保存]**：保存对已实施配置所做的更改并更新实施。
* **[!UICONTROL 退出]**。 退出引导式配置。 将会丢弃对已实施配置所做的所有更改。


## 发布 {#publish}

要开始收集Content Analytics配置的数据，您需要[手动](manual.md)发布在您选择&#x200B;**[!UICONTROL 实施]**&#x200B;后创建的Tags属性。


>[!MORELIKETHIS]
>
>[手动配置](manual.md)
>
