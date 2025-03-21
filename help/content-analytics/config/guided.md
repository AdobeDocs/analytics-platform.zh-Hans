---
title: Content Analytics指导配置
description: 如何使用载入引导式配置配置内容分析
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: 01459765d84a46d170c1619ffeae184957bbf839
workflow-type: tm+mt
source-wordcount: '3324'
ht-degree: 13%

---

# Content Analytics指导配置

{{draft-aca}}

{{release-limited-testing}}

引导式配置可帮助您快速轻松地配置Content Analytics。 引导式配置使用向导来设置自动为组织配置Content Analytics的要求。 在&#x200B;**[!UICONTROL 配置]**&#x200B;屏幕中，您可以创建新配置或编辑现有配置。

>[!IMPORTANT]
>
>您组织中的每个沙盒只能有一个内容分析配置。

访问Content Analytics配置

* 从Customer Journey Analytics的主菜单中选择&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL Content Analytics]**。

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
| **[!UICONTROL 状态]** | 配置的状态。 状态可以是：<br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 草稿]**：配置已保存以供稍后使用，未部署。<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL 失败]**：配置失败。 您需要编辑配置并进行必要的更改。<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 完成]**：配置已成功完成并实施。 |

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
>abstract="本指南设置了配置Content Analytics所需的要求。 请为此配置提供名称"

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
>abstract="选择新数据视图会更新该数据视图，使其包含Content Analytics量度和维度。 需要时相关联的连接也会被更新，使其包含内容分析数据集。当前为内容分析配置的连接和数据视图不会更改。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="清理所选数据视图"
>abstract="您选择了已为Content Analytics配置的数据视图。 现有Content Analytics配置将被删除，并且数据视图将配置您的新配置。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="清理以前的数据视图"
>abstract="您已选择新的数据视图。 已删除上一个选定数据视图的Content Analytics配置。"

<!-- markdownlint-enable MD034 -->

您的配置要求选择[数据视图](/help/data-views/data-views.md)。

1. 选择数据视图

   * 要为配置选择新的数据视图，请使用![数据](/help/assets/icons/Data.svg) **[!UICONTROL 选择数据视图]**。

     数据视图的![Content Analytics配置](../assets/aca-configuration-dataview.png)

   * 要修改配置的数据视图，请选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**。

     数据视图的![Content Analytics配置](../assets/aca-configuration-dataview-edit.png)


   在这两种情况下，您都会看到&#x200B;**[!UICONTROL 数据视图]**&#x200B;对话框，您可以在其中为您的配置选择数据视图。

   数据视图的![Content Analytics配置 — 数据视图表](../assets/aca-configuration-dataview-dialog.png)

   对于新配置，列表仅显示与没有活动配置的沙盒关联的数据视图。

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
>abstract="指定用于确定如何在您的网站上呈现内容的参数。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="体验捕捉和定义"
>abstract="您可以在与当前配置关联的Tags属性中编辑Adobe Content Analytics扩展中的设置。"

<!-- markdownlint-enable MD034 -->

在此部分中，您可以选择在通过Content Analytics收集的数据中包含体验。  体验是网页上的所有文本，可以使用访问某个网页的初始用户使用的URL重现这些文本。

默认情况下，**[!UICONTROL 包含体验]**&#x200B;处于关闭状态。 在选中时，您必须定义要包含体验的URL。

仅在满足以下条件时，才考虑包含体验：

* 您只能使用面向公众的URL访问网站内容。 访问网站不需要个性化令牌、Cookie或无法通过URL获得的其他机制。
* 必须使用页面URL重现网站上的页面。

要在新的或未实施的配置中包含体验，请执行以下操作：

![Content Analytics配置体验捕获和定义](../assets/aca-configuration-experience.png)

1. 启用&#x200B;**[!UICONTROL 包含体验]**。
1. （可选） 指定用于在您的网站上呈现内容的参数。 参数是&#x200B;**[!UICONTROL 域正则表达式]**&#x200B;和&#x200B;**[!UICONTROL 查询参数]**&#x200B;的零个或多个组合。
   1. 输入&#x200B;**[!UICONTROL 域正则表达式]**，例如`/^(?!.*\b(store|help|admin)\b)/`。 确保使用`/`转义正则表达式。
   1. 指定&#x200B;**[!UICONTROL 查询参数]**&#x200B;的逗号分隔列表，例如`outdoors, patio, kitchen`。
1. 如果要删除域正则表达式和查询参数的组合，请选择&#x200B;**[!UICONTROL 删除]**。
1. 如果要添加其他正则表达式和查询参数组合，请选择&#x200B;**[!UICONTROL 添加正则表达式]**。

要在已实施的配置中编辑现有体验或包含新体验，请执行以下操作：

![Content Analytics配置体验捕获和定义](../assets/aca-configuration-experience-edit.png)

* 选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**&#x200B;以编辑Content Analytics中收集体验的配置。 您被重定向到与当前配置关联的Tags属性中的[Adobe Content Analytics扩展](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering)。




### 数据收集 {#onboarding-data-collection}

在此部分中，您可以配置如何收集内容分析数据。

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="数据收集"
>abstract="定义要使用哪个Tags属性，或创建一个新属性。 并使用正则表达式定义那些您想要包含或排除的页面和资产。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="数据收集"
>abstract="**提供Tags属性**"

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
>abstract="在与当前配置关联的Tags属性中，您可以编辑Adobe Content Analytics扩展中的页面设置。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="数据收集"
>abstract="您可以在与当前配置关联的Tags属性中，编辑Adobe Content Analytics扩展中的资源设置。"

<!-- markdownlint-enable MD034 -->

#### 新配置 {#new-configuration}

在新配置中，您需要定义是使用现有Tags属性还是创建新的Tags属性。 此外，您需要使用正则表达式定义要包含或排除的页面和资产。

* 要使用现有的Tags属性，请执行以下操作：

  ![Content Analytics数据收集现有标记](../assets/aca-configuration-datacollection-existingtag.png)

   1. 选择&#x200B;**[!UICONTROL 现有]**。
   2. 从&#x200B;**[!UICONTROL 标记属性]**&#x200B;下拉菜单中选择现有属性。 您可以开始键入以搜索并限制可用选项。

* 要创建新的Tags属性：

  ![Content Analytics数据收集新标记](../assets/aca-configuration-datacollection-newtag.png)

   1. 选择&#x200B;**[!UICONTROL 新建]**。
   1. 指定&#x200B;**[!UICONTROL 标记名称]**，例如`ACA Test for Documentation`。
  <!--1. Specify **[!UICONTROL Domains]**, for example, `example.com`. -->
   1. 选择&#x200B;**[!UICONTROL 添加]**。

* 如果已选择包含体验，请指示在为Content Analytics收集数据时应包含或排除哪些页面。

   * 为&#x200B;**[!UICONTROL Experience]**&#x200B;指定正则表达式。 例如：`/^(?!.*documentation).*/`从Content Analytics中排除所有文档页面。 确保使用`/`转义正则表达式。

* 指示在为Content Analytics收集数据时应包含或排除哪些资产。

   * 为&#x200B;**[!UICONTROL 资源]**&#x200B;指定正则表达式。 例如： `/^(?!.*(logo\.jpg|\.svg)).*$/`从Content Analytics中排除所有徽标JPEG和SVG图像。 确保使用`/`转义正则表达式。


#### 现有配置 {#existing-configuration}

对于现有配置，无法编辑Tags属性。 但是，您可以编辑要包含或排除的页面和资产。

* 要编辑在为Content Analytics收集数据时应包含或排除哪些页面，请在&#x200B;**[!UICONTROL 体验]**&#x200B;下选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**。 您将被重定向到与当前Adobe Content Analytics配置的Tags属性关联的[Content Analytics扩展](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering)。 您可以编辑正则表达式以包含或排除页面。 确保您[发布](manual.md#publish)您所做的更改。

* 要编辑在收集内容分析的数据时应包含或排除哪些资产，请在&#x200B;**[!UICONTROL 资产]**&#x200B;下选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**。 您将被重定向到与当前Adobe Content Analytics配置的Tags属性关联的[Content Analytics扩展](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering)。 您可以编辑正则表达式以包含或排除资产。 请确保您[发布](manual.md#publish)更改。

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
>abstract="如果选择&#x200B;**[!UICONTROL 实施]**，将根据您在此工作流程中提供的输入来配置内容分析。默认情况下，系统会根据对Content Analytics通常有用的内容选择多个设置，但您（作为数据控制者）必须查看每个工件的设置，以确认这些设置是根据您的隐私政策、合同权利和义务以及适用法律下的同意要求实施的。<br/><br/>请注意，在手动发布与此配置关联的标记库之前，不会收集任何数据。<br/><br/>为了派生图像和文本的属性，Adobe使用以下方式检索属性：<ol><li>根据您配置的数据收集设置，在用户访问网站时捕获的URL，以及</li><li>托管图像的 URL。</li></ol>您不得对第三方网站上托管的图像进行标记。"

<!-- markdownlint-enable MD034 -->

创建或编辑配置后，以下操作可用。

* **[!UICONTROL 放弃]**：在创建新配置或编辑现有配置时所做的所有更改都将被放弃。
* **[!UICONTROL 保存供以后使用]**：保存对新配置或现有尚未实施的配置所做的更改。 您可以在稍后阶段重新访问配置以进行进一步更改，或实施配置。
* **[!UICONTROL 实施]**：保存和实施新配置或现有尚未实施的配置的设置或更改。 实施包括：

   * **[!UICONTROL Customer Journey Analytics]**&#x200B;配置：
      * 选定的数据视图已更新，将包含Content Analytics维度和量度。
      * 已修改与选定数据视图关联的连接，以包含Content Analytics事件和属性数据集。
      * 向Workspace中添加了Content Analytics报表模板。

+++ 详细信息

     详情见以下情景：

      * **标记**&#x200B;属性存在&#x200B;**✓**&#x200B;或不存在&#x200B;**✕**。
      * Tags属性的&#x200B;**Web SDK**&#x200B;扩展存在&#x200B;**✓**&#x200B;或不存在&#x200B;**✕**。
      * Tag属性的Adobe **Content Analytics**&#x200B;扩展存在&#x200B;**✓**&#x200B;或不存在&#x200B;**✕**。

     <table style="table-layout:fixed">
      <tr>
        <th></th>
        <th colspan="4">方案：</th>
      </tr>
      <tr>
        <th>
          <strong>设置</strong>
        </th>
        <th>
          <strong>✓标记<br>✓ Web SDK<br/>✓ Content Analytics</strong>
        </th>
        <th>
          <strong>✓标记<br>✓ Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          <strong>✓标记<br>✕ Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          <strong>✕标记<br>✕ Web SDK<br/>✕ Content Analytics</strong>
        </th>
      </tr>
      <tbody>
        <tr>
          <td>报表模板</td>
          <td colspan="4">报告模板可用</td>
        </tr>
        <tr>
          <td>数据视图</td>
          <td colspan="4">已修改/创建以具有ACA维度和量度</td>
        </tr>
        <tr>
          <td>连接</td>
          <td colspan="4">修改为包括ACA数据集(ACA事件、资产属性、体验属性)</td>
        </tr>
      </tbody>
    </table>

+++

   * **[!UICONTROL Adobe Experience Platform]**&#x200B;配置：
      * 创建架构以对Content Analytics事件、资产属性和（如果已配置）体验属性进行建模。
      * 创建数据集以收集Content Analytics事件、资产属性和（如果已配置）体验属性。
      * 创建数据流，该数据流使用功能化服务从Content Analytics事件生成和更新内容属性。

+++ 详细信息

     详情见以下情景：

      * **标记**&#x200B;属性存在&#x200B;**✓**&#x200B;或不存在&#x200B;**✕**。
      * Tags属性的&#x200B;**Web SDK**&#x200B;扩展存在&#x200B;**✓**&#x200B;或不存在&#x200B;**✕**。
      * Tag属性的Adobe **Content Analytics**&#x200B;扩展存在&#x200B;**✓**&#x200B;或不存在&#x200B;**✕**。

     <table style="table-layout:fixed">
      <tr>
        <th></th>
        <th colspan="4">方案：</th>
      </tr>
      <tr>
        <th>
          <strong>设置</strong>
        </th>
        <th>
          <strong>✓标记<br>✓ Web SDK<br/>✓ Content Analytics</strong>
        </th>
        <th>
          <strong>✓标记<br>✓ Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          <strong>✓标记<br>✕ Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          <strong>✕标记<br>✕ Web SDK<br/>✕ Content Analytics</strong>
        </th>
      </tr>
      <tbody>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics事件架构</strong></td>
        </tr>
        <tr>
          <td style="margin-left: 160.0px;">名称</td>
          <td>Content Analytics事件</td>
          <td>Content Analytics事件</td>
          <td>Content Analytics事件</td>
          <td>Content Analytics事件</td>
        </tr>
        <tr>
          <td>描述</td>
          <td><i>预定tbd</i></td>
          <td><i>预定tbd</i></td>
          <td><i>预定tbd</i></td>
          <td><i>预定tbd</i></td>
        </tr>
        <tr>
          <td>配置文件已启用</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics事件数据集</strong></td>
        </tr>
        <tr>
          <td>名称</td>
          <td>Content Analytics事件</td>
          <td>Content Analytics事件</td>
          <td>Content Analytics事件</td>
          <td>Content Analytics事件</td>
        </tr>
        <tr>
          <td>架构</td>
          <td>Content Analytics事件</td>
          <td>Content Analytics事件</td>
          <td>Content Analytics事件</td>
          <td>Content Analytics事件</td>
        </tr>
        <tr>
          <td>描述</td>
          <td><i>预定tbd</i></td>
          <td><i>预定tbd</i></td>
          <td><i>预定tbd</i></td>
          <td><i>预定tbd</i></td>
        </tr>
        <tr>
          <td>标记</td>
          <td><i>空的？</i></td>
          <td><i>空的？</i></td>
          <td><i>空的？</i></td>
          <td><i>空的？</i></td>
        </tr>
        <tr>
          <td>系统数据集</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td>配置文件已启用</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
        </tr>
        <tr>
          <td>数据管理（DULE标签）</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics资产属性架构</strong></td>
        </tr>
        <tr>
          <td>名称</td>
          <td>Content Analytics资产属性</td>
          <td>Content Analytics资产属性</td>
          <td>Content Analytics资产属性</td>
          <td>Content Analytics资产属性</td>
        </tr>
        <tr>
          <td>描述</td>
          <td><i>预定tbd</i></td>
          <td><i>预定tbd</i></td>
          <td><i>预定tbd</i></td>
          <td><i>预定tbd</i></td>
        </tr>
        <tr>
          <td>配置文件已启用</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics Assets属性数据集</strong></td>
        </tr>
        <tr>
          <td>名称</td>
          <td>Content Analytics资产属性</td>
          <td>Content Analytics资产属性</td>
          <td>Content Analytics资产属性</td>
          <td>Content Analytics资产属性</td>
        </tr>
        <tr>
          <td>架构</td>
          <td>Content Analytics资产属性</td>
          <td>Content Analytics资产属性</td>
          <td>Content Analytics资产属性</td>
          <td>Content Analytics资产属性</td>
        </tr>
        <tr>
          <td>描述</td>
          <td><i>预定tbd</i></td>
          <td><i>预定tbd</i></td>
          <td><i>预定tbd</i></td>
          <td><i>预定tbd</i></td>
        </tr>
        <tr>
          <td>标记</td>
          <td><i>空的？</i></td>
          <td><i>空的？</i></td>
          <td><i>空的？</i></td>
          <td><i>空的？</i></td>
        </tr>
        <tr>
          <td>系统数据集</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td>配置文件已启用</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
        </tr>
        <tr>
          <td>数据管理（DULE标签）</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics体验属性架构</strong></td>
        </tr>
        <tr>
          <td>名称</td>
          <td>Content Analytics体验属性</td>
          <td>Content Analytics体验属性</td>
          <td>Content Analytics体验属性</td>
          <td>Content Analytics体验属性</td>
        </tr>
        <tr>
          <td>描述</td>
          <td><i>预定tbd</i></td>
          <td><i>预定tbd</i></td>
          <td><i>预定tbd</i></td>
          <td><i>预定tbd</i></td>
        </tr>
        <tr>
          <td>配置文件已启用</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics体验属性数据集</strong></td>
        </tr>
        <tr>
          <td>名称</td>
          <td>Content Analytics体验属性</td>
          <td>Content Analytics体验属性</td>
          <td>Content Analytics体验属性</td>
          <td>Content Analytics体验属性</td>
        </tr>
        <tr>
          <td>架构</td>
          <td>Content Analytics体验属性</td>
          <td>Content Analytics体验属性</td>
          <td>Content Analytics体验属性</td>
          <td>Content Analytics体验属性</td>
        </tr>
        <tr>
          <td>描述</td>
          <td><i>预定tbd</i></td>
          <td><i>预定tbd</i></td>
          <td><i>预定tbd</i></td>
          <td><i>预定tbd</i></td>
        </tr>
        <tr>
          <td>标记</td>
          <td><i>空的？</i></td>
          <td><i>空的？</i></td>
          <td><i>空的？</i></td>
          <td><i>空的？</i></td>
        </tr>
        <tr>
          <td>系统数据集</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td>配置文件已启用</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
        </tr>
        <tr>
          <td>数据管理（DULE标签）</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
      </tbody>
    </table>

+++

   * **[!UICONTROL 数据收集]**&#x200B;配置：
      * 新的或现有的标记属性配置为支持Content Analytics数据收集。 此配置意味着包含适用于标记的Adobe Content Analytics扩展。
      * 为Content Analytics事件创建数据流。
      * Adobe Content Analytics扩展已配置为确保将Content Analytics事件发送到Content Analytics的数据流。
      * 如果没有为Tags属性配置Web SDK，则会创建新的Web SDK配置，以仅发送Content Analytics事件。
      * 如果为此Tags属性配置了Web SDK，则不会对现有Web SDK配置进行任何更改。

+++ 详细信息

     详情见以下情景：

      * **标记**&#x200B;属性存在&#x200B;**✓**&#x200B;或不存在&#x200B;**✕**。
      * Tags属性的&#x200B;**Web SDK**&#x200B;扩展存在&#x200B;**✓**&#x200B;或不存在&#x200B;**✕**。
      * Tag属性的Adobe **Content Analytics**&#x200B;扩展存在&#x200B;**✓**&#x200B;或不存在&#x200B;**✕**。

     <table style="table-layout:fixed">
      <tr>
        <th></th>
        <th colspan="4">方案：</th>
      </tr>
      <tr>
        <th>
          <strong>设置</strong>
        </th>
        <th>
          <strong>✓标记<br>✓ Web SDK<br/>✓ Content Analytics</strong>
        </th>
        <th>
          <strong>✓标记<br>✓ Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          <strong>✓标记<br>✕ Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          <strong>✕标记<br>✕ Web SDK<br/>✕ Content Analytics</strong>
        </th>
      </tr>
      <tbody>
        <tr>
          <td colspan="5"><strong><br/>数据流</strong></td>
        </tr>
        <tr>
          <td>名称</td>
          <td><i>现有值</i></td>
          <td>内容分析</td>
          <td>内容分析</td>
          <td>内容分析</td>
        </tr>
        <tr>
          <td>描述</td>
          <td><i>现有值</i></td>
          <td><i>预定</i></td>
          <td><i>预定</i></td>
          <td><i>预定</i></td>
        </tr>
        <tr>
          <td>映射架构</td>
          <td><i>现有值</i></td>
          <td><i>预定</i></td>
          <td><i>预定</i></td>
          <td><i>预定</i></td>
        </tr>
        <tr>
          <td>地理位置和网络查找</td>
          <td><i>现有值</i></td>
          <td>关闭所有选项</td>
          <td>关闭所有选项</td>
          <td>关闭所有选项</td>
        </tr>
        <tr>
          <td>设备查找</td>
          <td><i>现有值</i></td>
          <td>不收集任何设备信息</td>
          <td>不收集任何设备信息</td>
          <td>不收集任何设备信息</td>
        </tr>
        <tr>
          <td>IP 模糊处理</td>
          <td><i>现有值</i></td>
          <td>无</td>
          <td>无</td>
          <td>无</td>
        </tr>
        <tr>
          <td>第一方ID Cookie</td>
          <td><i>现有值</i></td>
          <td>关</td>
          <td>关</td>
          <td>关</td>
        </tr>
        <tr>
          <td>第三方ID同步</td>
          <td><i>现有值</i></td>
          <td>关</td>
          <td>关</td>
          <td>关</td>
        </tr>
        <tr>
          <td>访问类型</td>
          <td><i>现有值</i></td>
          <td>混合身份验证</td>
          <td>混合身份验证</td>
          <td>混合身份验证</td>
        </tr>
        <tr>
          <td>媒体分析</td>
          <td><i>现有值</i></td>
          <td>关</td>
          <td>关</td>
          <td>关</td>
        </tr>
            <tr>
          <td>机器人检测</td>
          <td><i>现有值</i></td>
          <td>关</td>
          <td>关</td>
          <td>关</td>
        </tr>
        <tr>
          <td>映射</td>
          <td><i>现有值</i></td>
          <td><i>用户提供</i></td>
          <td><i>用户提供</i></td>
          <td><i>用户提供</i></td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>标记属性</strong><br/>现有属性或新属性。 名称和域由用户提供。</td>
        </tr>
        <tr>
          <td>名称</td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td><i>用户已提供</i> (默认为“Content Analytics”)</td>
        </tr>
        <tr>
          <td>域</td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td ><i>预定</i></td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>标记库</strong></td>
        </tr>
        <tr>
          <td>名称</td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td>
            <br/>
          </td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Web SDK扩展</strong></td>
        </tr>
        <tr>
          <td>名称</td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td>Content Analytics - Web SDK</td>
          <td>Content Analytics - Web SDK</td>
        </tr>
        <tr>
          <td>IMS组织</td>
          <td><i>自动填充</i></td>
          <td><i>自动填充</i></td>
          <td><i>自动填充</i></td>
          <td><i>自动填充</i></td>
        </tr>
        <tr>
          <td>边缘域</td>
          <td><i>现有值<br/>可能需要更新以匹配AppMeasurement实施</i></td>
          <td><i>现有值<br/>可能需要更新以匹配AppMeasurement实施</i></td>
          <td>
            <a href="http://edge.adobedc.net">edge.adobedc.net</a>
          </td>
          <td>
            <a href="http://edge.adobedc.net">edge.adobedc.net</a>
          </td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>数据流</strong></td>
        </tr>
        <tr>
          <td>生产</td>
          <td><i>现有值<br/>用于发送到其他数据流的数据流覆盖</i></td>
          <td><i>现有值<br/>用于发送到其他数据流的数据流覆盖</i></td>
          <td><i>用户已提供</i>？</td>
          <td><i>用户已提供</i>？</td>
        </tr>
        <tr>
          <td>暂存</td>
          <td><i>现有值<br/>用于发送到其他数据流的数据流覆盖</i></td>
          <td><i>现有值<br/>用于发送到其他数据流的数据流覆盖</i></td>
          <td><i>用户已提供</i>？</td>
          <td><i>用户已提供</i>？</td>
        </tr>
        <tr>
          <td>开发</td>
          <td><i>现有值<br/>用于发送到其他数据流的数据流覆盖</i></td>
          <td><i>现有值<br/>用于发送到其他数据流的数据流覆盖</i></td>
          <td><i>用户已提供</i>？</td>
          <td><i>用户已提供</i>？</td>
        </tr>
        <tr>
          <td>隐私</td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td>在？</td>
          <td>在？</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>身份标识</strong></td>
        </tr>
        <tr>
          <td>迁移ECID</td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td>已选中</td>
          <td>已选中</td>
        </tr>
        <tr>
          <td>使用第三方Cookie</td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td>已选中</td>
          <td>已选中</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>个性化</strong></td>
        </tr>
        <tr>
          <td>将Target从at.js迁移到Web SDK</td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td>未选中</td>
          <td>未选中</td>
        </tr>
        <tr>
          <td>启用个性化存储</td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td>未选中</td>
          <td>未选中</td>
        </tr>
        <tr>
          <td>Adobe Journey Optimizer的自动点击收藏集</td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td>始终</td>
          <td>始终</td>
        </tr>
        <tr>
          <td>Adobe Target的自动点击收藏集</td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td>从不</td>
          <td>从不</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>数据收集</strong></td>
        </tr>
        <tr>
          <td>收集内部链接点击次数</td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td>未选中</td>
          <td>未选中</td>
        </tr>
        <tr>
          <td>收集外部链接点击次数</td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td>未选中</td>
          <td>未选中</td>
        </tr>
        <tr>
          <td>收集下载链接点击次数</td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td>未选中</td>
          <td>未选中</td>
        </tr>
        <tr>
          <td>发送事件数据时，自动包含</td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td>所有默认上下文信息</td>
          <td>所有默认上下文信息</td>
        </tr>
        <tr>
          <td>流媒体</td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td>空值</td>
          <td>空值</td>
        </tr>
        <tr>
          <td>数据流配置覆盖</td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td>匹配数据流配置</td>
          <td>匹配数据流配置</td>
        </tr>
        <tr>
          <td>高级设置 — Edge基本路径</td>
          <td><i>现有值</i></td>
          <td><i>现有值</i></td>
          <td>ee</td>
          <td>ee</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics扩展</strong></td>
        </tr>
        <tr>
          <td>数据流</td>
          <td><i>现有值</i></td>
          <td><i>预定</i></td>
          <td><i>预定</i></td>
          <td><i>预定</i></td>
        </tr>
        <tr>
          <td>体验捕获和定义</td>
          <td><i>现有值</i></td>
          <td><i>用户提供</i></td>
          <td><i>用户提供</i></td>
          <td><i>用户提供</i></td>
        </tr>
        <tr>
          <td>事件过滤</td>
          <td><i>现有值</i></td>
          <td><i>用户提供</i></td>
          <td><i>用户提供</i></td>
          <td><i>用户提供</i></td>
        </tr>
      </tbody>
    </table>

+++

* **[!UICONTROL 保存]**：保存对已实施配置所做的更改并更新实施。
* **[!UICONTROL 退出]**。 退出引导式配置。 将会丢弃对已实施配置所做的所有更改。


## 发布 {#publish}

要激活Content Analytics配置，您需要发布在您选择&#x200B;**[!UICONTROL 实施]** [手动](manual.md)后创建的Tags属性。



<!--
## Onboarding settings and configurations

The following sections outline the settings and configurations applied to [Customer Journey Analytics](#customer-journey-analytics-cja), [Experience Platform](#experience-platform-aep) and [Data Collection](#data-collection-dc) as part of the implementation of a Content Analytics configuration.

Details are provided for the following scenarios:

* **Tags** property exists **✓** or does not exist **✕**.
* **Web SDK** extension for the Tags property exists **✓** or does not exist **✕**.
* Adobe **Content Analytics** extension for the Tag property exists **✓** or does not exist **✕**.

### Customer Journey Analytics {#cja}

<table style="table-layout:fixed">
  <tr>
    <th></th>
    <th colspan="4">Scenarios:</th>
  </tr>
  <tr>
    <th>
      <strong>Setting</strong>
    </th>
    <th>
      <strong>✓ Tags<br>✓ Web SDK<br/>✓ Content Analytics</strong>
    </th>
    <th>
      <strong>✓ Tags<br>✓ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✓Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✕ Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
  </tr>
  <tbody>
    <tr>
      <td>Report Template</td>
      <td colspan="4">A report template is available</td>
    </tr>
    <tr>
      <td>Data view</td>
      <td colspan="4">Modified/Created to have ACA dimensions and metrics</td>
    </tr>
    <tr>
      <td>Connection</td>
      <td colspan="4">Modified to include ACA datasets (ACA events, Asset attributes, Experience Attribute)</td>
    </tr>
  </tbody>
</table>

### Experience Platform {#aep}

<table style="table-layout:fixed">
  <tr>
    <th></th>
    <th colspan="4">Scenarios:</th>
  </tr>
  <tr>
    <th>
      <strong>Setting</strong>
    </th>
    <th>
      <strong>✓ Tags<br>✓ Web SDK<br/>✓ Content Analytics</strong>
    </th>
    <th>
      <strong>✓ Tags<br>✓ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✓Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✕ Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
  </tr>
  <tbody>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics Events schema</strong></td>
    </tr>
    <tr>
      <td style="margin-left: 160.0px;">Name</td>
      <td>Content Analytics Events</td>
      <td>Content Analytics Events</td>
      <td>Content Analytics Events</td>
      <td>Content Analytics Events</td>
    </tr>
    <tr>
      <td>Description</td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
    </tr>
    <tr>
      <td>Profile enabled</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics Events dataset</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td>Content Analytics Events</td>
      <td>Content Analytics Events</td>
      <td>Content Analytics Events</td>
      <td>Content Analytics Events</td>
    </tr>
    <tr>
      <td>Schema</td>
      <td>Content Analytics Event</td>
      <td>Content Analytics Event</td>
      <td>Content Analytics Event</td>
      <td>Content Analytics Event</td>
    </tr>
    <tr>
      <td>Description</td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
    </tr>
    <tr>
      <td>Tags</td>
      <td><i>empty?</i></td>
      <td><i>empty?</i></td>
      <td><i>empty?</i></td>
      <td><i>empty?</i></td>
    </tr>
    <tr>
      <td>System dataset</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td>Profile enabled</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Data governance (DULE labels)</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics Asset Attributes schema</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td>Content Analytics Asset Attributes</td>
      <td>Content Analytics Asset Attributes</td>
      <td>Content Analytics Asset Attributes</td>
      <td>Content Analytics Asset Attributes</td>
    </tr>
    <tr>
      <td>Description</td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
    </tr>
    <tr>
      <td>Profile enabled</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics Assets Attributes dataset</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td>Content Analytics Asset Attributes</td>
      <td>Content Analytics Asset Attributes</td>
      <td>Content Analytics Asset Attributes</td>
      <td>Content Analytics Asset Attributes</td>
    </tr>
    <tr>
      <td>Schema</td>
      <td>Content Analytics Asset Attributes</td>
      <td>Content Analytics Asset Attributes</td>
      <td>Content Analytics Asset Attributes</td>
      <td>Content Analytics Asset Attributes</td>
    </tr>
    <tr>
      <td>Description</td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
    </tr>
    <tr>
      <td>Tags</td>
      <td><i>empty?</i></td>
      <td><i>empty?</i></td>
      <td><i>empty?</i></td>
      <td><i>empty?</i></td>
    </tr>
    <tr>
      <td>System dataset</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td>Profile enabled</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Data governance (DULE labels)</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics Experience Attributes schema</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td>Content Analytics Experience Attributes</td>
      <td>Content Analytics Experience Attributes</td>
      <td>Content Analytics Experience Attributes</td>
      <td>Content Analytics Experience Attributes</td>
    </tr>
    <tr>
      <td>Description</td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
    </tr>
    <tr>
      <td>Profile enabled</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics Experience Attributes dataset</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td>Content Analytics Experience Attributes</td>
      <td>Content Analytics Experience Attributes</td>
      <td>Content Analytics Experience Attributes</td>
      <td>Content Analytics Experience Attributes</td>
    </tr>
    <tr>
      <td>Schema</td>
      <td>Content Analytics Experience Attributes</td>
      <td>Content Analytics Experience Attributes</td>
      <td>Content Analytics Experience Attributes</td>
      <td>Content Analytics Experience Attributes</td>
    </tr>
    <tr>
      <td>Description</td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
      <td><i>predetermined tbd</i></td>
    </tr>
    <tr>
      <td>Tags</td>
      <td><i>empty?</i></td>
      <td><i>empty?</i></td>
      <td><i>empty?</i></td>
      <td><i>empty?</i></td>
    </tr>
    <tr>
      <td>System dataset</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
    <tr>
      <td>Profile enabled</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Data governance (DULE labels)</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
      <td>?</td>
    </tr>
  </tbody>
</table>


### Data Collection {#dc}

<table style="table-layout:fixed">
  <tr>
    <th></th>
    <th colspan="4">Scenarios:</th>
  </tr>
  <tr>
    <th>
      <strong>Setting</strong>
    </th>
    <th>
      <strong>✓ Tags<br>✓ Web SDK<br/>✓ Content Analytics</strong>
    </th>
    <th>
      <strong>✓ Tags<br>✓ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✓Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
    <th>
      <strong>✕ Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
    </th>
  </tr>
  <tbody>
    <tr>
      <td colspan="5"><strong><br/>Datastream</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td><i>existing value</i></td>
      <td>Content Analytics</td>
      <td>Content Analytics</td>
      <td>Content Analytics</td>
    </tr>
    <tr>
      <td>Description</td>
      <td><i>existing value</i></td>
      <td><i>predetermined</i></td>
      <td><i>predetermined</i></td>
      <td><i>predetermined</i></td>
    </tr>
    <tr>
      <td>Mapping schema</td>
      <td><i>existing value</i></td>
      <td><i>predetermined</i></td>
      <td><i>predetermined</i></td>
      <td><i>predetermined</i></td>
    </tr>
    <tr>
      <td>Geolocation and Network Lookup</td>
      <td><i>existing values</i></td>
      <td>All options off</td>
      <td>All options off</td>
      <td>All options off</td>
    </tr>
    <tr>
      <td>Device Lookup</td>
      <td><i>existing value</i></td>
      <td>Do not collect any device information</td>
      <td>Do not collect any device information</td>
      <td>Do not collect any device information</td>
    </tr>
    <tr>
      <td>IP Obfuscation</td>
      <td><i>existing value</i></td>
      <td>None</td>
      <td>None</td>
      <td>None</td>
    </tr>
    <tr>
      <td>First Party ID Cookie</td>
      <td><i>existing value</i></td>
      <td>Off</td>
      <td>Off</td>
      <td>Off</td>
    </tr>
    <tr>
      <td>Third Party ID Synch</td>
      <td><i>existing value</i></td>
      <td>Off</td>
      <td>Off</td>
      <td>Off</td>
    </tr>
    <tr>
      <td>Access Type</td>
      <td><i>existing value</i></td>
      <td>Mixed Authentication</td>
      <td>Mixed Authentication</td>
      <td>Mixed Authentication</td>
    </tr>
    <tr>
      <td>Media Analytics</td>
      <td><i>existing value</i></td>
      <td>Off</td>
      <td>Off</td>
      <td>Off</td>
    </tr>
        <tr>
      <td>Bot Detection</td>
      <td><i>existing value</i></td>
      <td>Off</td>
      <td>Off</td>
      <td>Off</td>
    </tr>
    <tr>
      <td>Mapping</td>
      <td><i>existing value</i></td>
      <td><i>user provided</i></td>
      <td><i>user provided</i></td>
      <td><i>user provided</i></td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Tags property</strong><br/>An existing property or new property. The name and domain are provided by the user.</td>
    </tr>
    <tr>
      <td>Name</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td><i>user provided</i> (default "Content Analytics")</td>
    </tr>
    <tr>
      <td>Domain</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td ><i>predetermined</i></td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Tags library</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>
        <br/>
      </td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Web SDK Extension</strong></td>
    </tr>
    <tr>
      <td>Name</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Content Analytics - Web SDK</td>
      <td>Content Analytics - Web SDK</td>
    </tr>
    <tr>
      <td>IMS Org</td>
      <td><i>automatically populated</i></td>
      <td><i>automatically populated</i></td>
      <td><i>automatically populated</i></td>
      <td><i>automatically populated</i></td>
    </tr>
    <tr>
      <td>Edge Domain</td>
      <td><i>existing value<br/>Might require an update to match the AppMeasurement implementation</i></td>
      <td><i>existing value<br/>Might require an update to match the AppMeasurement implementation</i></td>
      <td>
        <a href="http://edge.adobedc.net">edge.adobedc.net</a>
      </td>
      <td>
        <a href="http://edge.adobedc.net">edge.adobedc.net</a>
      </td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Datastreams</strong></td>
    </tr>
    <tr>
      <td>Production</td>
      <td><i>existing value<br/>Datastream override used to send to a different datastream</i></td>
      <td><i>existing value<br/>Datastream override used to send to a different datastream</i></td>
      <td><i>user provided</i>?</td>
      <td><i>user provided</i>?</td>
    </tr>
    <tr>
      <td>Staging</td>
      <td><i>existing value<br/>Datastream override used to send to a different datastream</i></td>
      <td><i>existing value<br/>Datastream override used to send to a different datastream</i></td>
      <td><i>user provided</i>?</td>
      <td><i>user provided</i>?</td>
    </tr>
    <tr>
      <td>Development</td>
      <td><i>existing value<br/>Datastream override used to send to a different datastream</i></td>
      <td><i>existing value<br/>Datastream override used to send to a different datastream</i></td>
      <td><i>user provided</i>?</td>
      <td><i>user provided</i>?</td>
    </tr>
    <tr>
      <td>Privacy</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>In?</td>
      <td>In?</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Identity</strong></td>
    </tr>
    <tr>
      <td>Migrate ECID</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Checked</td>
      <td>Checked</td>
    </tr>
    <tr>
      <td>Use third-party cookies</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Checked</td>
      <td>Checked</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Personalization</strong></td>
    </tr>
    <tr>
      <td>Migrate Target from at.js to Web SDK</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Unchecked</td>
      <td>Unchecked</td>
    </tr>
    <tr>
      <td>Enable personalization storage</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Unchecked</td>
      <td>Unchecked</td>
    </tr>
    <tr>
      <td>Auto click collection for Adobe Journey Optimizer</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Always</td>
      <td>Always</td>
    </tr>
    <tr>
      <td>Auto click collection for Adobe Target</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Never</td>
      <td>Never</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Data Collection</strong></td>
    </tr>
    <tr>
      <td>Collect internal links clicks</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Unchecked</td>
      <td>Unchecked</td>
    </tr>
    <tr>
      <td>Collect external link clicks</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Unchecked</td>
      <td>Unchecked</td>
    </tr>
    <tr>
      <td>Collect download links clicks</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Unchecked</td>
      <td>Unchecked</td>
    </tr>
    <tr>
      <td>When sending event data, automatically include</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>All default context information</td>
      <td>All default context information</td>
    </tr>
    <tr>
      <td>Streaming Media</td>
      <td><i>existing values</i></td>
      <td><i>existing values</i></td>
      <td>Blank values</td>
      <td>Blank values</td>
    </tr>
    <tr>
      <td>Datastream Configuration Overrides</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>Match datastream configuration</td>
      <td>Match datastream configuration</td>
    </tr>
    <tr>
      <td>Advanced Settings - Edge base path</td>
      <td><i>existing value</i></td>
      <td><i>existing value</i></td>
      <td>ee</td>
      <td>ee</td>
    </tr>
    <tr>
      <td colspan="5"><strong><br/>Content Analytics Extension</strong></td>
    </tr>
    <tr>
      <td>Datastreams</td>
      <td><i>existing value</i></td>
      <td><i>predetermined</i></td>
      <td><i>predetermined</i></td>
      <td><i>predetermined</i></td>
    </tr>
    <tr>
      <td>Experience Capturing & Definition</td>
      <td><i>existing value</i></td>
      <td><i>user provided</i></td>
      <td><i>user provided</i></td>
      <td><i>user provided</i></td>
    </tr>
    <tr>
      <td>Event Filtering</td>
      <td><i>existing value</i></td>
      <td><i>user provided</i></td>
      <td><i>user provided</i></td>
      <td><i>user provided</i></td>
    </tr>
  </tbody>
</table>

-->

>[!MORELIKETHIS]
>
>[手动配置](manual.md)
>
