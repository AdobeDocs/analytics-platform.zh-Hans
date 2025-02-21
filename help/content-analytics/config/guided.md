---
title: Content Analytics指导配置
description: 如何使用载入引导式配置配置内容分析
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: 82dacd2581450303b1b87d2a72f6f6ede987d367
workflow-type: tm+mt
source-wordcount: '2036'
ht-degree: 18%

---

# Content Analytics指导配置

>[!WARNING]
>
>本文是即将发布的最终版本的初步非官方草稿版本，是内容分析文档的一部分。 所有内容可能会发生更改，并且本条当前版本不承担任何法律义务。
>

{{release-limited-testing}}

引导式配置可帮助您快速轻松地配置Content Analytics。 引导式配置使用向导来设置自动为组织配置Content Analytics的要求。 在&#x200B;**[!UICONTROL 配置]**&#x200B;屏幕中，您可以创建新配置或编辑现有配置。

>[!IMPORTANT]
>
>您组织中的每个沙盒只能有一个内容分析配置。


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
>abstract="提供该连接的名称。在&#x200B;**[!UICONTROL 数据视图]**、**[!UICONTROL 体验捕捉和定义]**&#x200B;以及&#x200B;**[!UICONTROL 数据收集]**&#x200B;部分中，您可以提供更多详细信息，以确保正确配置内容分析。"

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
>id="aca_onboarding_dataview_change_content"
>title="新建数据视图"
>abstract="选择新数据视图将导致该数据视图更新为包括Content Analytics量度和维度。 如有必要，关联的连接也会更新以包括Content Analytics数据集。 当前为Content Analytics配置的连接和数据视图不会进行修改。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_change_title"
>title="新建数据视图"
>abstract="新建数据视图"

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

数据视图已绑定到Customer Journey Analytics [连接](/help/connections/overview.md)。 并且连接基于您组织内的沙盒。 保存配置后，**[!UICONTROL 沙盒]**&#x200B;会根据选定的数据视图，自动填充为沙盒的正确名称。


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
>abstract="指定用于确定内容在您的网站上呈现方式的参数。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="体验捕捉和定义"
>abstract="您可以在 Adobe 内容分析扩展中的标签属性中编辑与所选配置关联的设置。"

<!-- markdownlint-enable MD034 -->

在此部分中，您可以选择在通过Content Analytics收集的数据中包含体验。  体验是网页上的所有文本，可以使用访问某个网页的初始用户使用的URL重现这些文本。

默认情况下，**[!UICONTROL 包含体验]**&#x200B;处于关闭状态。 在选中时，您必须定义要包含体验的URL。

只有在满足以下条件时，才应考虑包含体验：

* 网站上的内容仅由URL驱动。
* 必须使用页面URL重现网站上的页面。

要在新的或未实施的配置中包含体验，请执行以下操作：

![Content Analytics配置体验捕获和定义](../assets/aca-configuration-experience.png)

1. 启用&#x200B;**[!UICONTROL 包含体验]**。
1. 指定用于确定如何在您的网站上呈现内容的参数。 参数是&#x200B;**[!UICONTROL 域正则表达式]**&#x200B;和&#x200B;**[!UICONTROL 查询参数]**&#x200B;的零个或多个组合。
   1. 输入&#x200B;**[!UICONTROL 域正则表达式]**，例如`(?!.*\b(store|help|admin)\b)`。
   1. 指定&#x200B;**[!UICONTROL 查询参数]**&#x200B;的逗号分隔列表，例如`outdoors, patio, kitchen`。
1. 如果要删除域正则表达式和查询参数的组合，请选择&#x200B;**[!UICONTROL 删除]**。
1. 如果要添加其他正则表达式和查询参数组合，请选择&#x200B;**[!UICONTROL 添加其他]**。

要在已实施的配置中编辑现有体验或包含新体验，请执行以下操作：

![Content Analytics配置体验捕获和定义](../assets/aca-configuration-experience-edit.png)

* 选择![编辑](/help/assets/icons/Edit.svg)编辑以编辑与所选配置关联的Tag属性中Adobe Content Analytics扩展中的参数。


### 数据收集 {#onboarding-data-collection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="数据收集"
>abstract="定义您想要使用的标签属性，或者创建一个新的属性。并使用正则表达式定义那些您想要包含或排除的页面和资产。"

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
>abstract="您可以在 Adobe 内容分析扩展中的标签属性中编辑与所选配置关联的页面设置。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="数据收集"
>abstract="您可以在 Adobe 内容分析扩展中的标签属性中编辑与所选配置关联的资产设置。"

<!-- markdownlint-enable MD034 -->

#### 新配置 {#new-configuration}

在新配置中，您需要定义要使用哪个Tag属性，或创建一个新的Tag属性。 此外，您需要使用正则表达式定义要包含或排除的页面和资产。

* 要使用现有的标记属性，请执行以下操作：

  ![Content Analytics数据收集现有标记](../assets/aca-configuration-datacollection-existingtag.png)

   * 选择&#x200B;**[!UICONTROL 现有]**。
   * 从&#x200B;**[!UICONTROL 标记属性]**&#x200B;下拉菜单中选择现有属性。

* 要创建新的标记属性，请执行以下操作：

  ![Content Analytics数据收集新标记](../assets/aca-configuration-datacollection-newtag.png)

   1. 选择&#x200B;**[!UICONTROL 新建]**。
   2. 指定&#x200B;**[!UICONTROL 标记名称]**，例如`ACA Test`。
   3. 指定&#x200B;**[!UICONTROL 域]**，例如`example.com`。

* 如果已选择包含体验，请指示在为Content Analytics收集数据时应包含或排除哪些页面。

   * 为&#x200B;**[!UICONTROL Experience]**&#x200B;指定正则表达式。 例如：`(?!.*\b(store|help|admin)\b)`。

* 指示在为Content Analytics收集数据时应包含或排除哪些资产。

   * 为&#x200B;**[!UICONTROL 资源]**&#x200B;指定正则表达式。 例如：`(?!.*\b(store|help|admin)\b)`。


#### 现有配置 {#existing-configuration}

对于现有配置，无法编辑Tag属性。 但是，您可以编辑要包含或排除的页面和资产。

* 要编辑在为Content Analytics收集数据时应包含或排除哪些页面，请在&#x200B;**[!UICONTROL 体验]**&#x200B;下选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**。

* 要编辑在收集内容分析的数据时应包含或排除哪些资产，请在&#x200B;**[!UICONTROL 资产]**&#x200B;下选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**。

### 概要 {#summary}

提供所有必要的详细信息后，摘要将提供已创建或已修改工件的详细信息。

* 当您实施新配置时，您会看到&#x200B;**[!UICONTROL 您几乎可以为Content Analytics]**&#x200B;摘要实施&#x200B;_配置名称_。

* 对于现有的已实施配置，您会看到&#x200B;**[!UICONTROL 您已为内容分析]**&#x200B;摘要实施了&#x200B;_配置名称_。

![Content Analytics配置摘要](../assets/aca-configuration-summary.png)

### 操作 {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_content"
>title="加入实施警告"
>abstract="如果选择&#x200B;**[!UICONTROL 实施]**，则将基于在此工作流中提供的输入配置内容分析。 默认情况下，系统会根据对内容分析通常有用的内容来选择多个设置，但您（作为数据控制者）必须查看每个工件的设置，以确认这些设置是否根据您的隐私政策、合同权利和义务以及适用法律下的同意要求实施。<br/><br/>请注意，在手动发布与此配置关联的标签库之前，不会收集任何数据。<br/><br/>为了获取图像和文本的属性，Adobe将使用以下方式检索属性：<ol><li>在用户网站访问时捕获的URL，根据您配置的数据收集设置以及</li><li>托管图像的URL。</li></ol>您不得标记托管在第三方网站上的图像。"

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_title"
>title="确认实施"
>abstract="确认实施"

<!-- markdownlint-enable MD034 -->


<!-- markdownlint-enable MD034 -->


创建或编辑配置后，以下操作可用。

* **[!UICONTROL 放弃]**：在创建新配置或编辑现有配置时所做的所有更改都将被放弃。
* **[!UICONTROL 保存供以后使用]**：保存对新配置或现有尚未实施的配置所做的更改。 您可以在稍后阶段重新访问配置以进行进一步更改，或实施配置。
* **[!UICONTROL 实施]**：保存和实施新配置或现有尚未实施的配置的设置或更改。 实施包括：
   * **[!UICONTROL Adobe Experience Platform]**&#x200B;配置：
      * 创建架构以对Content Analytics事件、资产属性和（如果已配置）体验属性进行建模。
      * 创建数据集以收集Content Analytics事件、资产属性和（如果已配置）体验属性。
      * 创建数据流，该数据流使用功能化服务从Content Analytics事件生成和更新内容属性。
   * **[!UICONTROL 数据收集]**&#x200B;配置：
      * 新的或现有的标记属性配置为支持Content Analytics数据收集。 此配置意味着包含适用于标记的Adobe Content Analytics扩展。
      * 为Content Analytics事件创建数据流。
      * Adobe Content Analytics扩展已配置为确保将Content Analytics事件发送到Content Analytics的数据流。
      * 如果没有为Tags属性配置Web SDK，则会创建新的Web SDK配置，以仅发送Content Analytics事件。
      * 如果为此Tag属性配置了Web SDK，则不会对现有Web SDK配置进行任何更改。
   * **[!UICONTROL Customer Journey Analytics]**&#x200B;配置：
      * 选定的数据视图已更新，将包含Content Analytics维度和量度。
      * 已修改与选定数据视图关联的连接，以包含Content Analytics事件和属性数据集。
      * 向Workspace中添加了Content Analytics报表模板。
* **[!UICONTROL 保存]**：保存对已实施配置所做的更改并更新实施。
* **[!UICONTROL 退出]**。 退出引导式配置。 将会丢弃对已实施配置所做的所有更改。


## 发布 {#publish}

要激活您的内容分析配置，您需要[手动](manual.md)发布在您选择&#x200B;**[!UICONTROL 实施]**&#x200B;后创建的标记属性，作为引导式配置向导的一部分。

>[!MORELIKETHIS]
>
>[手动配置](manual.md)
>
