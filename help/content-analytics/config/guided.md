---
title: Content Analytics 引导式配置
description: 如何使用引导式配置流程来配置 Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: 8531c372607f39a3e39de8eda4f624057e56d9a4
workflow-type: tm+mt
source-wordcount: '2694'
ht-degree: 97%

---

# Content Analytics 引导式配置

引导式配置可帮助您快速轻松地配置 Content Analytics。引导式配置会使用向导来设置相关要求，以便为您的组织自动配置 Content Analytics。在&#x200B;**[!UICONTROL 配置]**&#x200B;屏幕中，您可以创建新的配置或编辑现有配置。

>[!IMPORTANT]
>
>您的组织中每个沙盒内只能有一个 Content Analytics 配置。

要访问 Content Analytics 配置

* 从 Customer Journey Analytics 的主菜单中选择&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL Content Analytics 配置]**。

在 **[!UICONTROL Content Analytics 配置]**&#x200B;屏幕中，您会看到包含现有 Content Analytics 配置的表格。

![Content Analytics 配置](../assets/aca-configuration-table.png)
对于每个配置，会提供以下详细信息：

| 列 | 描述 |
|---|---|
| **[!UICONTROL 名称]** | 配置的名称。 |
| **[!UICONTROL 创建者]** | 创建配置的技术帐户。 |
| **[!UICONTROL 创建日期]** | 创建配置的时间戳。 |
| **[!UICONTROL 修改日期]** | 配置最后修改的时间戳。 |
| **[!UICONTROL 沙盒]** | 组织内（计划）配置并实施 Content Analytics 的沙盒。 |
| **[!UICONTROL 状态]** | 配置的状态。状态可以是：<br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 草稿]**：配置已保存，以供稍后使用，但尚未部署。<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL 失败]**：配置失败。您可以选择&#x200B;**[!UICONTROL 编辑]**，获取有关失败的信息。Adobe 会主动解决任何实施失败的问题。您可以联系客户关怀部门了解详情。<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 完成]**：配置已完成，并已成功实施。 |

您可以使用 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) 来自定义该表格。选择要在&#x200B;**[!UICONTROL 自定义表格]**&#x200B;对话框中显示哪些列，然后选择&#x200B;**[!UICONTROL 应用]**，以应用更改。

在 Content Analytics **[!UICONTROL 配置]**&#x200B;屏幕中，您可以创建新配置，或编辑现有配置。

要创建新的配置：

* 选择&#x200B;**[!UICONTROL 创建配置]**。此操作会打开[引导式配置向导](#guided-configuration-wizard)。

编辑现有配置：

* 选择![更多](/help/assets/icons/More.svg) ，然后选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**&#x200B;现有 Content Analytics 配置。此操作会打开[引导式配置向导](#guided-configuration-wizard)。

## 引导式配置向导

引导式配置向导由四个部分组成（[详细信息](#details)、[数据视图](#data-view)、[体验捕获和定义](#experience-capture-and-definition)以及[数据收集](#data-collection)），每个部分都会提示您输入必要的资料，以正确设置及配置 Content Analytics。请先完成每个部分，然后再进入下一个部分，因为某一部分中的某些设置可能取决于前面部分中的配置值。

### 详细信息 {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="详细信息"
>abstract="提供该连接的名称。在&#x200B;**[!UICONTROL 数据视图]**、**[!UICONTROL 体验捕捉和定义]**&#x200B;以及&#x200B;**[!UICONTROL 数据收集]**&#x200B;部分中，您可以提供更多资料，以确保可以正确配置 Content Analytics。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="详细信息"
>abstract="本指南列出了配置 Content Analytics 所需的必要条件。请为此配置提供名称"

<!-- markdownlint-enable MD034 -->

每个配置都需要一个唯一的名称。例如：`Example Content Analytics configuration`。需要名称进行保存或实施配置。

![Content Analytics 配置详情](../assets/aca-configuration-details.png)


### 数据视图 {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="数据视图"
>abstract="要配置 Content Analytics，您需要选择一个现有的数据视图。然后，您可以将 Content Analytics 数据与其他数据合并。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="数据视图"
>abstract="从 Customer Journey Analytics 中选择一个您希望将 Content Analytics 数据与之合并的现有数据视图。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="数据视图"
>abstract="从 Customer Journey Analytics 中选择一个您希望将 Content Analytics 数据与之合并的现有数据视图。<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_change_dialog"
>title="新建数据视图"
>abstract="您已为此配置选择了新的数据视图。新的数据视图将进行更新，以包含 Content Analytics 量度和维度。这些量度和维度将会从原先选择的数据视图中移除。<br/><br/>如果不同的连接与新的数据视图相关联，则该连接将会更新，以包含 Content Analytics 数据集。Content Analytics 数据集不会从原先选择的连接中删除。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="清理选定的数据视图"
>abstract="您选择了已为 Content Analytics 配置的数据视图。现有的 Content Analytics 配置已移除，数据视图将使用新配置。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="清理以前的数据视图"
>abstract="您已选择新的数据视图。之前选定数据视图的 Content Analytics 配置已移除。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_new_dialog"
>title="新建数据视图"
>abstract="您已为此配置选择了新的数据视图。新的数据视图将进行更新，以包含 Content Analytics 量度和维度。类似的量度和维度将会从现有的数据视图中移除。<br/>如果不同的连接与新的数据视图相关联，则该连接将会更新，以包含 Content Analytics 数据集。请注意，Content Analytics 数据集不会从现有配置中移除。"

<!-- markdownlint-enable MD034 -->

您的配置需要选择一个[数据视图](/help/data-views/data-views.md)。

1. 选择数据视图

   * 要为某个配置选择新的数据视图，请使用![数据](/help/assets/icons/Data.svg) **[!UICONTROL 选择数据视图]**。

     ![数据视图的 Content Analytics 配置](../assets/aca-configuration-dataview.png)

   * 要为某个配置更改数据视图，请选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**。

     ![数据视图的 Content Analytics 配置](../assets/aca-configuration-dataview-edit.png)


   在两种场景中，您都会看到一个&#x200B;**[!UICONTROL 数据视图]**&#x200B;对话框，您可以在其中为您的配置选择一个数据视图。

   ![数据视图的 Content Analytics 配置 - 数据视图表](../assets/aca-configuration-dataview-dialog.png)

   对于新的配置，该列表仅显示那些与没有有效配置的沙盒相关联的数据视图。
此外，您只能看到那些与您有权访问的沙盒以及您有权更改的连接相关联的数据视图。

   如果您编辑一共现有配置，则该列表仅显示与现有配置相关联的沙盒中可用的数据视图。

   您可以执行以下操作：

   * 要搜索特定的数据视图，请使用![搜索](/help/assets/icons/Search.svg)字段。
   * 要筛选可用数据视图的列表，请选择![显示筛选器](/help/assets/icons/Filter.svg)。 您可以在[!UICONTROL 连接]、[!UICONTROL 所有者]和[!UICONTROL 沙盒]上筛选列表。<br/>使用![隐藏](/help/assets/icons/Filter.svg) **[!UICONTROL 隐藏区段]**&#x200B;来隐藏区段窗格。
   * 要定义在表格中显示哪些列，请选择![列设置](/help/assets/icons/ColumnSetting.svg)。选择要在&#x200B;**[!UICONTROL 自定义表格]**&#x200B;对话框中显示哪些列，然后选择&#x200B;**[!UICONTROL 应用]**，以应用更改。

1. 选择 ![SelectBox](/help/assets/icons/SelectBox.svg) 您想要使用的数据视图。
1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以确认所选的数据视图。选择&#x200B;**[!UICONTROL 取消]**&#x200B;即可取消。


在 Customer Journey Analytics 中，[数据视图](/help/data-views/data-views.md)与 Customer Journey Analytics [连接](/help/connections/overview.md)相关联。连接基于您组织内的沙盒。保存配置后，**[!UICONTROL 沙盒]**&#x200B;字段中将会根据所选的数据视图自动填充沙盒的名称。


### 体验捕捉和定义 {#onboarding-experiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="体验捕捉和定义"
>abstract="您可以选择将体验包含在使用 Content Analytics 收集的数据中。选中后，您必须定义正则表达式和查询参数的一个或多个组合，以定义要包含体验的 URL。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="体验捕捉和定义"
>abstract="收集 Content Analytics 中的体验"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="体验捕捉和定义"
>abstract="指定用于决定内容如何在网站上呈现的参数。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_new_include_experiences"
>title="体验捕捉和定义"
>abstract="启用后，将收集体验数据，生成体验属性，并提供体验报告。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_include_experiences"
>title="体验捕捉和定义"
>abstract="启用后，将收集体验数据，生成体验属性，并提供体验报告。<br><br/>使用 ![编辑](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 编辑]**&#x200B;功能，可修改与当前配置相关联的“标记”属性中体验的数据收集配置。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="体验捕捉和定义"
>abstract="您必须在 Adobe Content Analytics 扩展中编辑体验数据收集的设置。"

<!-- markdownlint-enable MD034 -->

在这个部分，您可以选择将体验包含在使用 Content Analytics 收集的数据中。体验是网页上的所有文本，并且可以使用初始用户访问该网页时使用的 URL 进行重现。

默认情况下，**[!UICONTROL 包含体验]**&#x200B;处于关闭状态。选中后，您必须定义要包含体验的 URL。

仅在以下情况适用时才考虑包含体验：

* 网站上的页面必须能够通过页面 URL 重复出现。
* 任何给定用户看到的文本内容都可以使用页面 URL 重复出现，并且不取决于 cookie 或其他个性化机制。

>[!IMPORTANT]
>
>实施 [Content Analytics 版本控制](manual.md#versioning)，收集您因 Content Analytics 而对体验（页面）所做的更改。



#### 新的配置 {#new-experiences-configuration}

要将体验包含到新的或未实施的配置中：

![Content Analytics 配置，体验捕获和定义](../assets/aca-configuration-experience.png)

1. 启用&#x200B;**[!UICONTROL 包括体验]**。切换启用体验的操作会影响以下方面：

   * Content Analytics 扩展中的数据收集
   * 从 Content Analytics 事件数据生成体验属性的过程
   * Customer Journey Analytics 中的报告模板。

1. 指定内容如何在网站上呈现的参数。这些参数是&#x200B;**[!UICONTROL 域正则表达式]**&#x200B;和&#x200B;**[!UICONTROL 查询参数]**&#x200B;的零个或多个组合。查询参数表示哪些参数会影响页面上的内容。此输入允许 Content Analytics 在定义了独特体验的情况下忽略任何不影响页面内容的参数。
   1. 输入&#x200B;**[!UICONTROL 域正则表达式]**，例如 `/^(?!.*\b(store|help|admin)\b)/`。确保使用以下方法将正则表达式转义 `/`。域正则表达式表示这些参数适用于哪些 URL。例如，您可能有多个站点，并且每个站点都用不同的参数驱动内容。如果查询参数适用于所有页面，那么您可以使用 `.*` 表示所有页面。
   1. 指定以逗号分隔的&#x200B;**[!UICONTROL 查询参数]**&#x200B;列表，例如 `outdoors, patio, kitchen`。
1. 如果您想移除域正则表达式和查询参数的组合，请选择&#x200B;**[!UICONTROL 移除]**。
1. 如果您想添加正则表达式和查询参数的另一个组合，请选择&#x200B;**[!UICONTROL 添加正则表达式]**。


#### 已实施的配置 {#implemented-experiences-configuration}

要在已实施的配置中编辑现有体验或包含新体验，请执行以下操作：

![Content Analytics 配置体验捕获和定义](../assets/aca-configuration-experience-edit.png)

* 切换启用或禁用&#x200B;**[!UICONTROL 包含体验]**：

   * 从 Content Analytics 事件数据生成体验属性的过程
   * Customer Journey Analytics 中的报告模板。

* 选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**&#x200B;可进一步编辑 Content Analytics 中体验数据收集的配置。您在与当前配置相关联的标记属性中被重定向到 [Adobe Content Analytics 扩展](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting)。


### 数据收集 {#onboarding-data-collection}

在此部分，您可配置如何收集 Content Analytics 数据。

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
>abstract="指明在为 Content Analytics 收集数据时应&#x200B;**包括**&#x200B;或&#x200B;**排除**&#x200B;哪些页面"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_boldheader"
>title="数据收集"
>abstract="**要包含/排除的资产**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_header"
>title="数据收集"
>abstract="指明在为 Content Analytics 收集数据时应&#x200B;**包括**&#x200B;或&#x200B;**排除**&#x200B;哪些资产"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_experiences_edit_button"
>title="数据收集"
>abstract="您可以在与当前配置关联的标记属性中编辑 Adobe Content Analytics 扩展中的页面设置。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="数据收集"
>abstract="您可以在与当前配置关联的标记属性中编辑 Adobe Content Analytics 扩展中的资产设置。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tags_disabled_description "
>title="标记属性已禁用"
>abstract="Content Analytics 扩展已激活。"

<!-- markdownlint-enable MD034 -->

#### 新的配置 {#new-configuration}

在新的配置中，您需要定义是否要使用某个现有的“标记”属性，还是要创建一个新的“标记”属性。并且您需要使用正则表达式定义那些您想要包含或排除的页面和资产。

* 要使用一个现有的“标记”属性：

  ![Content Analytics 数据收集现有标记](../assets/aca-configuration-datacollection-existingtag.png)

   1. 选择&#x200B;**[!UICONTROL 选择现有的]**。
   2. 从&#x200B;**[!UICONTROL 标记属性]**&#x200B;下拉菜单中选择现有属性。 您可以开始输入进行搜索，并限制可用的选项。您不能选择正在被另一个已实施的 Content Analytics 配置使用的标记属性。


* 要创建一个新的“标记”属性：

  ![Content Analytics 数据收集：新标记](../assets/aca-configuration-datacollection-newtag.png)

   1. 选择&#x200B;**[!UICONTROL 新建]**。
   1. 指定一个&#x200B;**[!UICONTROL 标记名称]**，例如 `ACA Test for Documentation`。
   1. 指定&#x200B;**[!UICONTROL 域]**，例如，`example.com`。

* 表示在为 Content Analytics 收集数据时应包含或排除哪些页面。

  为&#x200B;**[!UICONTROL 要包含/排除的页面]**&#x200B;指定一个正则表达式字符串。<br/>例如：`^(?!.*documentation).*`，以从 Content Analytics 中排除所有文档页面。

* 指明在为 Content Analytics 收集数据时应包括或排除哪些资产。

  为&#x200B;**[!UICONTROL 要包含/排除的资产]**&#x200B;指定一个正则表达式字符串。<br/>例如： `^(?!.*(logo\.jpg)).*$`从Content Analytics中排除所有徽标JPEG图像。

>[!IMPORTANT]
>
>如果您现有的 Web SDK 实施使用了 [JavaScript 库](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/web-sdk/install/library)，而不是[标签扩展](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)，则从新创建的标记属性中手动移除自动包含的 Web SDK 扩展。
>



#### 现有的配置 {#existing-configuration}

对于现有配置，您无法编辑“标记”属性。要更新与现有配置关联的标记属性，请使用[Content Analytics标记扩展配置](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/content-analytics/overview)。

但是，您可以编辑要包含或排除的页面和资产。

* 要编辑在收集 Content Analytics 数据时应包含或排除哪些页面，请选择&#x200B;**[!UICONTROL 体验]**&#x200B;下的 ![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**。您被重定向到为当前 Content Analytics 配置与标记属性相关联的 [Adobe Content Analytics 扩展](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting)。但是，您可以编辑要包含或排除页面的正则表达式。确保您[发布](#publish)更改内容。

* 要编辑在收集 Content Analytics 数据时应包含或排除哪些资产，请选择&#x200B;**[!UICONTROL 资产]**&#x200B;下的 ![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**。您被重定向到为当前 Content Analytics 配置与标记属性相关联的 [Adobe Content Analytics 扩展](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting)。但是，您可以编辑要包含或排除资产的正则表达式。确保您[发布](#publish)更改内容。

### 摘要 {#summary}

在提供了所有必要的详细信息后，摘要中会提供有关创建或修改的构件的详细信息。

* 在实施新配置时，您会看到&#x200B;**[!UICONTROL “您即将准备好为 Content Analytics 实施&#x200B;_配置名称_”]**&#x200B;的摘要。

* 对于已实施的配置，您会看到&#x200B;**[!UICONTROL 您已为 Content Analytics 实施&#x200B;_实施名称_]**&#x200B;的摘要。

![Content Analytics 配置摘要](../assets/aca-configuration-summary.png)

### 操作 {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="实施确认"
>abstract="如果选择&#x200B;**[!UICONTROL 实施]**，则会根据您在此工作流程中提供的输入来配置 Content Analytics。默认情况下，会根据 Content Analytics 的一般用途选择几种设置，但您（作为数据控制者）必须检查每个工件的设置，以确保这些设置是根据您的隐私政策、合同权利和义务以及符合适用法律的同意声明要求实施的。<br/><br/>请注意，在手动发布与此配置关联的标记库之前，不会收集任何数据。<br/><br/>为了获取图像和文本的属性，Adobe 使用了以下方式检索属性：<ol><li>根据您配置的数据收集设置，在用户访问网站时捕获的页面 URL，以及</li><li>托管图像的 URL。</li></ol>您不得对第三方网站上托管的图像进行标记。"

<!-- markdownlint-enable MD034 -->

创建或编辑配置时，您有以下选项：

* **[!UICONTROL 丢弃]**：作为配置一部分的所有更改都将被丢弃。
* **[!UICONTROL 保存以供未来使用]**：对配置所做的更改已保存。您可以在稍后阶段重新访问该配置，以进行进一步的更改，或实施该配置。保存配置时只需要一个[!UICONTROL 名称]的值。
* **[!UICONTROL 实施]**：为配置所做的设置或更改已保存并实施。所有被标记为![必需的](/help/assets/icons/Required.svg)字段必须有正确的值。实施包括：

   * **[!UICONTROL Customer Journey Analytics]** 配置：
      * 选定的数据视图已更新，以包含 Content Analytics 维度和量度。
      * 与所选数据视图相关联的连接已更改，以包含 Content Analytics 事件和属性数据集。
      * Content Analytics 报告模板已添加到工作区。


   * **[!UICONTROL Adobe Experience Platform]** 配置：
      * 通过创建架构来模拟 Content Analytics 事件、资产属性和（如果已配置）体验属性。
      * 通过创建数据集来收集 Content Analytics 事件、资产属性和（如果已配置）体验属性。
      * 创建一个数据流，用于通过特征化服务从 Content Analytics 事件生成和更新内容属性。


   * **[!UICONTROL 数据收集]**&#x200B;配置：
      * 新的或现有的”标记“属性被配置为支持 Content Analytics 数据收集。此配置意味着需包含用于”标记“的 Adobe Content Analytics 扩展。
      * 为 Content Analytics 事件创建数据流。
      * Adobe Content Analytics 扩展已配置，以确保将 Content Analytics 事件发送到 Content Analytics 的数据流。
      * 如果未为”标记“属性配置 Web SDK，则会创建一个新的 Web SDK 配置，以仅发送 Content Analytics 事件。
      * 如果为此”标记“属性配置了 Web SDK，则现有的 Web SDK 配置不会进行任何更改。


* **[!UICONTROL 保存]**：对已实施的配置所做的更改会被保存，并且实施会被更新。
* **[!UICONTROL 退出]**。退出引导式配置。对已实施的配置所做的所有更改都会被丢弃。


## 发布 {#publish}

要开始为 Content Analytics 配置收集数据，您需要[手动](manual.md)发布在您选择&#x200B;**[!UICONTROL 实施]**&#x200B;后所创建的标记属性。


>[!MORELIKETHIS]
>
>[手动配置](manual.md)
>
