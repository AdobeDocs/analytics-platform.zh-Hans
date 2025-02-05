---
title: Content Analytics指导配置
description: 如何使用载入引导式配置配置内容分析
solution: Customer Journey Analytics
feature: Data Views
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 69e2f358398fd8d2646e5a3c1cb6dfd1b5b5efbb
workflow-type: tm+mt
source-wordcount: '1651'
ht-degree: 11%

---

# Content Analytics指导配置

>[!WARNING]
>
>本文是即将发布的最终版本的初步非官方草稿版本，是内容分析文档的一部分。 所有内容可能会发生更改，并且本条当前版本不承担任何法律义务。
>

{#release-limited-testing}

引导式配置可帮助您快速轻松地配置Content Analytics。 引导式配置使用向导来设置自动为组织配置Content Analytics的要求。 在&#x200B;**[!UICONTROL 配置]**&#x200B;屏幕中，您可以创建新配置或编辑现有配置。

访问Content Analytics配置

* 从Customer Journey Analytics的主菜单中选择&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL Content Analytics]**。

在Content Analytics配置屏幕中，您将看到一个现有Content Analytics配置的表。

![Content Analytics配置](../assets/aca-configuration-table.png)
对于每个配置，提供了以下详细信息：

| 列 | 描述 |
|---|---|
| **[!UICONTROL 名称]** | 配置的名称。 |
| **[!UICONTROL 创建者]** | 创建配置的技术帐户。 |
| **[!UICONTROL 创建于]** | 创建配置时的时间戳。 |
| **[!UICONTROL 修改于]** | 上次修改配置时的时间戳。 |
| **[!UICONTROL 沙盒]** | （计划要）配置和实施Content Analytics的组织内的沙盒。 |
| **[!UICONTROL 状态]** | 配置的状态。 状态可以是：<br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 草稿]**：配置已保存以供稍后使用，未部署。<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL 失败]**：配置失败。 您需要编辑配置并进行必要的更改。<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 完成]**：配置已成功完成并实施。 |

您可以使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)自定义表。 选择要在&#x200B;**[!UICONTROL 自定义表]**&#x200B;对话框中显示哪些列，然后选择&#x200B;**[!UICONTROL 应用]**&#x200B;以应用更改。

在Content Analytics **[!UICONTROL 配置]**&#x200B;屏幕中，您可以创建新配置或编辑现有配置。

要创建新配置，请执行以下操作：

* 选择&#x200B;**[!UICONTROL 创建配置]**。 此操作将打开引导式配置向导。

要编辑现有配置，请执行以下操作：

* 为现有Content Analytics配置选择![更多](/help/assets/icons/More.svg)，然后选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**。 此操作将打开引导式配置向导。

## 引导式配置向导

引导式配置向导包含四个部分（[详细信息](#details)、[数据视图](#data-view)、[体验捕获和定义](#experience-capture-and-definition)以及[数据收集](#data-collection)），每个部分都会提示您提供正确设置和配置内容分析所需的详细信息。 请先完成每个部分，然后再转到下一部分，因为部分中的某些设置可能取决于前面部分中的配置值。

### 详细信息 {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="详细信息"
>abstract="提供该连接的名称。在&#x200B;**[!UICONTROL 数据视图]**、**[!UICONTROL 体验捕获和定义]**&#x200B;以及&#x200B;**[!UICONTROL 数据收集]**&#x200B;部分中，您提供了更多详细信息，以确保可以正确配置Content Analytics。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="详细信息"
>abstract="本指南将会设置配置内容分析所需的要求。请为此配置提供名称"

<!-- markdownlint-enable MD034 -->

每个配置都需要一个唯一的名称。 例如，`Example Content Analytics configuration`。

![内容分析配置详细信息](../assets/aca-configuration-details.png)


### 数据视图 {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="数据视图"
>abstract="在配置Content Analytics时，您需要选择现有数据视图。 因此，您可以将内容分析数据与其他数据合并。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="数据视图"
>abstract="从Customer Journey Analytics中选择要与内容分析数据合并的现有数据视图。<br/>[了解详情](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views){target=\"_blank\"}"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="数据视图"
>abstract="从Customer Journey Analytics中选择要与您的内容分析数据合并的现有数据视图。<br/>"

<!-- markdownlint-enable MD034 -->

您的配置要求选择[数据视图](/help/data-views/data-views.md)。

数据视图的![Content Analytics配置](../assets/aca-configuration-dataview.png)

要选择数据视图，请执行以下操作：

1. 使用![数据](/help/assets/icons/Data.svg) **[!UICONTROL 选择数据视图]**。 您会看到&#x200B;**[!UICONTROL 数据视图]**&#x200B;对话框，您可以在其中为您的配置选择数据视图。

   如果创建新配置，则列表仅显示与没有活动配置的沙盒关联的数据视图。
如果您编辑现有配置，则列表仅显示沙盒中可用的、已与现有配置关联的数据视图。

   * 要筛选可用数据视图的列表，请选择![显示筛选器](/help/assets/icons/Filter.svg)。 您可以对“连接”、“所有者”和“沙盒”列表进行过滤。<br/>使用![隐藏](/help/assets/icons/Filter.svg) **[!UICONTROL 隐藏筛选器]**&#x200B;以隐藏筛选器窗格。
   * 要定义要在表中显示的列，请选择![列设置](/help/assets/icons/ColumnSetting.svg)。 选择要在&#x200B;**[!UICONTROL 自定义表]**&#x200B;对话框中显示哪些列，然后选择&#x200B;**[!UICONTROL 应用]**&#x200B;以应用更改。
1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以确认所选的数据视图。 选择&#x200B;**[!UICONTROL 取消]**&#x200B;以取消。

数据视图绑定到Customer Journey Analytics[连接](/help/connections/overview.md)。 并且连接基于您组织内的沙盒。 保存配置后，**[!UICONTROL 沙盒]**&#x200B;会根据选定的数据视图，自动填充为沙盒的正确名称。


### 体验捕捉和定义

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
>id="aca_onboarding_experiences_url_header"
>title="体验捕捉和定义"
>abstract="指定以下参数适用的 URL"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_edit_button"
>title="体验捕捉和定义"
>abstract="您可以在Tag属性中编辑与所选配置关联的AdobeContent Analytics扩展中的设置。"



<!-- markdownlint-enable MD034 -->

在此部分中，您可以选择在通过Content Analytics收集的数据中包含体验。 体验是网页上的所有文本，可以使用访问某个网页的初始用户使用的URL重现这些文本。 在选中时，您必须定义要包含体验的URL。

要在新的或未实施的配置中包含体验，请执行以下操作：

![Content Analytics配置体验捕获和定义](../assets/aca-configuration-experience.png)

1. 启用&#x200B;**[!UICONTROL 包含体验]**。
1. 指定用于确定如何在您的网站上呈现内容的参数。 参数是&#x200B;**[!UICONTROL 域正则表达式]**&#x200B;和&#x200B;**[!UICONTROL 查询参数]**&#x200B;的零个或多个组合。
   1. 输入&#x200B;**[!UICONTROL 域正则表达式]**，例如`(?!.*\b(store|help|admin)\b)`。
   1. 指定&#x200B;**[!UICONTROL 查询参数]**&#x200B;的逗号分隔列表，例如`outdoors, patio, kitchen`。
   1. 如果要删除组合，请选择&#x200B;**[!UICONTROL 删除]**。
   1. 如果要添加其他组合，请选择&#x200B;**[!UICONTROL 添加其他]**。

要在已实施的配置中编辑现有体验或包含新体验，请执行以下操作：

![Content Analytics配置体验捕获和定义](../assets/aca-configuration-experience-edit.png)

* 选择![编辑](/help/assets/icons/Edit.svg)编辑以在Tag属性中编辑与所选配置关联的AdobeContent Analytics扩展中的参数。


### 数据收集 {#onboarding-data-collection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="数据收集"
>abstract="定义您想要使用的标签属性，或者创建一个新的属性。并使用正则表达式定义要包含或排除的页面和资产。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="数据收集"
>abstract="提供标签属性"

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

<!-- markdownlint-enable MD034 -->

#### 新配置

在新配置中，您需要定义要使用哪个Tag属性，或创建一个新的Tag属性。 此外，您需要使用正则表达式定义要包含或排除的页面和资产。

* 要使用现有的标记属性，请执行以下操作：

  ![Content Analytics数据收集现有标记](../assets/aca-configuration-datacollection-existingtag.png)

   * 选择&#x200B;**[!UICONTROL 现有]**。
   * 从&#x200B;**[!UICONTROL 标记属性]**&#x200B;下拉菜单中选择现有属性。

* 要创建新的标记属性，请执行以下操作：

  ![Content Analytics数据收集新标记](../assets/aca-configuration-datacollection-newtag.png)

   1. 选择&#x200B;**[!UICONTROL 新建]**。
   2. 指定&#x200B;**[!UICONTROL 标记名称]**，例如`ACA Test`。
   3. 指定一个或多个&#x200B;**[!UICONTROL 域]**，例如`example.com`。

   * 要添加更多域，请选择&#x200B;**[!UICONTROL 添加其他]**。
   * 要删除域，请选择![CrossSize75](/help/assets/icons/CrossSize75.svg)。

* 如果已选择包含体验，请指示在为Content Analytics收集数据时应包含或排除哪些页面。

   * 为&#x200B;**[!UICONTROL Experience]**&#x200B;指定正则表达式。 例如：`(?!.*\b(store|help|admin)\b)`。

* 指示在为Content Analytics收集数据时应包含或排除哪些资产。

   * 为&#x200B;**[!UICONTROL 资源]**&#x200B;指定正则表达式。 例如：`(?!.*\b(store|help|admin)\b)`。


#### 现有配置

对于现有配置，无法编辑Tag属性。 但是，您可以编辑要包含或排除的页面和资产。

* 要编辑在为Content Analytics收集数据时应包含或排除哪些页面，请在&#x200B;**[!UICONTROL 体验]**&#x200B;下选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**。

* 要编辑在收集内容分析的数据时应包含或排除哪些资产，请在&#x200B;**[!UICONTROL 资产]**&#x200B;下选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**。

### 概要

提供所有必要的详细信息后，您会看到&#x200B;**[!UICONTROL 您几乎可以为Content Analytics]**&#x200B;摘要实施&#x200B;_配置名称_。

对于现有的已实施配置，您会看到&#x200B;**[!UICONTROL 您已为内容分析]**&#x200B;摘要实施了&#x200B;_配置名称_。

![Content Analytics配置摘要](../assets/aca-configuration-summary.png)

### 操作

创建或编辑配置后，以下操作可用。

* **[!UICONTROL 放弃]**：在创建新配置或编辑现有配置时所做的所有更改都将被放弃。
* **[!UICONTROL 保存供以后使用]**：保存对新配置或现有尚未实施的配置所做的更改。 您可以在稍后阶段重新访问配置以进行进一步更改，或实施配置。
* **[!UICONTROL 实施]**：保存和实施对新配置或现有尚未实施的配置所做的更改。 实施包括：
   * **[!UICONTROL Adobe Experience Platform]**&#x200B;配置：
      1. 创建架构以对Content Analytics事件、资产属性和（如果已配置）体验属性进行建模。
      1. 创建数据集以收集Content Analytics事件、资产属性和（如果已配置）体验属性。
   * **[!UICONTROL Content Analytics]**&#x200B;配置：
      * 基于配置设置特征化汇编程序进程。
   * **[!UICONTROL Customer Journey Analytics]**&#x200B;配置：
      1. 选定的数据视图已更新，将包含Content Analytics维度和量度。
      1. 已修改与选定数据视图关联的连接，以包含Content Analytics事件和属性数据集。
      1. Content Analytics报表模板已添加到Workspace。
   * **[!UICONTROL 数据收集]**&#x200B;配置：
      1. 新的或现有的标记属性配置为支持Content Analytics数据收集。 此配置意味着包含适用于标记的AdobeContent Analytics扩展。
      1. 为Content Analytics事件创建数据流。
      1. AdobeContent Analytics扩展已配置为确保Content Analytics事件发送到Content Analytics的数据流。
      1. 如果没有为Tags属性配置Web SDK，则会创建新的Web SDK配置，以仅发送Content Analytics事件。
      1. 如果为此Tag属性配置了Web SDK，则不会对现有Web SDK配置进行任何更改。
* **[!UICONTROL 保存]**：保存对已实施配置所做的更改并更新实施。


