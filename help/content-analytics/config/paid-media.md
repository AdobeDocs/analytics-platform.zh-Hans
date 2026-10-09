---
title: Content Analytics付费媒体自动配置
description: 了解数据集、连接、数据视图等的自动配置。
solution: Customer Journey Analytics
feature: Content Analytics
hold: true
role: Admin
source-git-commit: e9274ad7899537837723e2eb9cd842c5449530ff
workflow-type: tm+mt
source-wordcount: '2309'
ht-degree: 2%
---
# 付费媒体自动配置

当您在Content Analytics中启用付费媒体渠道并保存配置时，Adobe会使用付费媒体数据集的报表配置更新选定的连接和数据视图。 您无需自己重新创建默认维度、量度、查找逻辑或摘要数据组。

将创建三个对象层：

| 对象 | 包含 | 用途 |
| --- | --- | --- |
| 摘要数据集 | 广告、体验投放或资产级别的Advertising网络性能数据，如果支持，则单独进行人口统计/地理划分。 | 允许您衡量投放情况、点击次数、支出以及广告网络报告的结果 |
| 元数据和属性查找数据集 | 帐户、营销活动、广告组、广告、体验和资源详细信息；Content Analytics创意属性。 | 允许您使用可识别的名称、创意详细信息、缩略图和内容属性而不是使用标识符进行报告。 |
| 数据视图组件和配置 | 维度、量度、计算量度、派生字段和摘要数据组。 | 允许您构建Workspace分析，而无需手动重建这些数据集之间的关系。 |

启用付费媒体不会自动将付费媒体数据连接到您网站的订单、预订或收入。 体验事件数据与付费媒体数据之间的关联需要客户特定的跟踪密钥映射和报表配置。

## 摘要数据集

下图显示了在Content Analytics中为一个或多个广告网络启用付费媒体渠道时如何生成摘要数据集。 可使用来自可用广告网络的相关API下载体验、资产和广告数据，并将这些数据转换为潜在的六个摘要数据集。

![付费媒体生成摘要数据集](/help/content-analytics/assets/paid-media-generation-of-datasets.png)

特定的广告网络可确定创建哪些摘要数据集。 并非每个您为其配置了源连接器的广告网络都会生成所有六个可能的摘要数据集。 有关概要数据集的概述，请参阅下表，其中包含以下信息：

* 摘要数据集名称、事件类型和组件后缀
* 实体
* 细分
* 为以下网络填充了![复选标记](/help/assets/icons2/Checkmark.svg)的数据集：
  * ![MetaSolid](/help/assets/icons2/MetaSolid.svg) Meta
  * ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) Google
  * ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) Pinterest
  * ![Snapchat](/help/assets/icons2/Snapchat.svg) Snapchat
  * ![TikTok](/help/assets/icons2/TikTok.svg) TikTok

    >[!AVAILABILITY]
    >
    >Pinterest、Snapchat和TikTok处于版本的有限测试阶段，可能尚未在您的环境中提供。 当该功能正式可用时，将删除此说明。 有关Customer Journey Analytics发布过程的信息，请参阅[Customer Journey Analytics功能发布](/help/release-notes/releases.md)
    >


* 摘要数据集中的每一行所表示的内容。

| 摘要数据集<br/>事件类型<br/>组件后缀 | 实体<br/>划分 | ![MetaMulti](/help/assets/icons2/MetaSolid.svg) | ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) | ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) | ![Snapchat](/help/assets/icons2/Snapchat.svg) | ![TikTok](/help/assets/icons2/TikTok.svg) | 每一行表示 |
|---|---|:---:|:---:|:---:|:---:|:---:|---|
| `paidmedia_ad_summary` <br/> `ad.summary`<br/>`\| Ad Summary` | 广告<br/>无 | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | 广告的每日效果，无需考虑人口统计或地理因素。 |
| `paidmedia_ad_demographics` <br/> `ad.demographics`<br/>`\| Ad Demo` | 广告<br/>年龄，性别 | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | 按年龄和性别细分的广告每日效果<br/>。 |
| `paidmedia_ad_geography` <br/> `ad.geography`<br/>`\| Ad Geo` | 广告<br/>国家/地区 | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | 按国家和地区细分的广告每日效果<br/>。 |
| `paidmedia_experience_placement` <br/> `ad.experience.placement`<br>`\| Experience Placement` | Experience<br>平台，位置 | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | 每日表现与<br/>广告的创意体验相关，<br/>按平台和位置细分。 |
| `paidmedia_asset_summary` <br/>`ad.asset.summary`<br/>`\| Asset Summary` | 资源<br/>无 | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | | ![Checkmark](/help/assets/icons2/Checkmark.svg) | 在其广告/营销活动上下文<br/>中的每日资产级别性能<br/>没有人口统计或地理细分。 |
| `paidmedia_assets_demographics` <br/> `ad.asset.demographics`<br/>`\| Asset Demo` | 资产<br/>年龄，性别 | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | | | | 按年龄和性别细分的广告/营销活动上下文中的每日资产级绩效<br/><br/>。 |


此表描述了数据集覆盖范围，并不能保证特定网络会填充每个量度或元数据字段。 检查分析所需的字段。 不可用字段或不受支持的划分与测量出的字段零值不同。

单独的查找数据集描述了帐户、促销活动、广告组、广告、体验和资产。 它们使用实体GUID提供名称和元数据。 摘要数据集和六个查找数据集之间不存在一对一的配对。

摘要数据分组将等效维度汇总在一起；分组不会汇总六个性能量度总计。

## 组件

Content Analytics付费媒体渠道在启用后，还会生成多个数据视图组件。 这些组件具有组件后缀，用于区分名称相似的组件。

### 量度

不同的广告网络会返回不同的性能细分。 Content Analytics会保留这些区别，而不是将量度的每个版本都视为可互换的。

例如：

| 组件 | 含义 | 适当的开始分析 |
| --- | --- | --- |
| 点击次数\|广告摘要 | 在广告的无细分级别报告的点击数 | 营销活动或广告效果 |
| 单击\|资源摘要 | 资产级别报告的点击次数 | Creative-asset性能 |
| 点击次数\|广告地域 | 广告地理位置报表的点击量 | 按国家或地区列出的绩效 |
| 点击次数\|体验位置 | 体验投放位置报表中的点击量 | Creative按投放位置列出的性能 |

每个点击量度组件提供不同的报表上下文。 您不能将这些量度组件合计为一个总计。 同一基础广告活动可以在多个摘要数据集中表示。

### 维度

每个摘要数据集都包含ID和GUID。 ID是由广告网络提供的身份（帐户、促销活动、广告组、广告、体验和资产），在&#x200B;**广告网络数据内是唯一的**。 GUID是Adobe提供的身份（用于帐户、营销活动、广告组、广告、体验和资产），在&#x200B;**广告网络中是唯一的**。 ID和GUID用于查找相应的名称和元数据。

### 派生字段

派生字段是自动报告配置的一部分。 派生字段将标识符转换为名称和元数据，显示创意属性，并支持在报表源间使用的等效维度。 它们不会创建其他广告活动或自动归因网站转化。

对分析中的量度和该划分支持的维度使用相同的划分。 请注意，人口统计和地理总数不一定等于广告网络的无细分总数，也不意味着摄取失败。

## 报告和分析

完成Content Analytics付费媒体的设置和引入后，您可以开始报告和分析。 有关一些示例，请参阅下表。 使用可用的规范分组维度，并从匹配报表级别选择量度。

| 业务问题 | 开始级别 | 行和划分 | 开始量度 | 重要边界 |
| --- | --- | --- | --- | --- |
| 我的营销活动和广告表现如何？ | 广告摘要 | 营销活动名称、广告组名称、广告名称；（可选）广告网络和帐户名称 | 展示次数\|广告摘要、点击次数\|广告摘要、支出\|广告摘要、匹配CTR和CPC | 使用一个级别计算投放/支出总计；在合并帐户之前验证货币 |
| 哪些创意资产获得的响应最强？ | 资产摘要 | 资产名称（付费媒体）、资产标识；（可选）广告网络 | 展示次数\|资源摘要、点击次数\|资源摘要、点进率\|资源摘要 | 这是网络报告的资产性能，不是稍后现场转换的证据 |
| 哪些图像特征与性能相关？ | 资产摘要 | 资产标记、资产对象、资产人员类别、资产场景或其他可用的资产属性 | 资产摘要展示次数、点击次数和CTR | 属性提取必须可用；多值属性类别可以重叠 |
| 哪些消息传送特征与付费性能相关？ | 体验投放位置 | 体验关键字、体验色调、体验说服策略或其他可用的体验属性；（可选）平台和投放位置 | 展示次数\|体验投放位置，点击次数\|体验投放位置，匹配CTR | 需要填充体验属性；结果特定于投放位置并描述关联，而不是因果影响 |
| 哪些投放位置表现最佳？ | 体验投放位置 | 体验名称、平台、投放位置 | 展示次数\|体验投放位置，点击次数\|体验投放位置，匹配CTR | 投放位置和可用值因广告网络而异 |
| Meta与Google的广告/资源/体验有何异同？ | 为问题选择的广告摘要、资产摘要或体验投放位置 | 具有相应促销活动、资产或体验维度的广告网络 | 两个网络的相同级别和量度定义 | 仅比较两个网络填充的字段；Google不会填充此模型中的三个人口统计/地理摘要 |

这些报告可以揭示创意属性和性能之间的关联，但不能证明属性导致了结果。

避免出现不兼容的组合：资产名称（付费媒体）与广告摘要量度不能替代资产报表。 使用资产汇总量度进行资产分析，使用广告地理位置量度进行区域分析。 来自不兼容配对的空单元格或零单元格不应解释为没有活动的证据。

### 示例

以下示例介绍了如何报告和分析付费媒体效果，以及如何将Content Analytics体验和资产数据与付费媒体数据相结合。

#### 广告营销活动效果

您想要报告广告级别的促销活动效果。 在Analysis Workspace中，使用促销活动名称作为维度（行），并使用下表所述的指标。 每个量度具有相同的组件后缀。

| 量度 | 报告级别 |
| --- | --- |
| 展示次数 | 广告摘要 |
| 点击量 | 广告摘要 |
| 支出 | 广告摘要 |
| 点进率 | 广告摘要 |
| 每次点击成本 | 广告摘要 |

（可选）按广告名称划分促销活动名称，但将所有五列保留在“广告摘要”级别。

要调查单个资产，请使用单独的表，其中具有资产名称（付费媒体）和匹配的资产摘要列。 不要将两个表的总数相加。

#### 确定表现最佳的广告

您想了解Meta广告在哪些方面的表现最佳？

要进行调查，请使用地理和人口结构的其他细分。 使用促销活动名称或广告名称作为维度，并使用下表所述的量度。 每个量度具有相同的组件后缀。

| 量度 | 报告级别 |
| --- | --- |
| 展示次数 | 广告地域 |
| 点击量 | 广告地域 |
| 支出 | 广告摘要 |
| 点进率 | 广告地域 |
| 每次点击成本 | 广告摘要 |


#### 将付费媒体数据与体验事件数据连接起来

将付费媒体表现与网站行为数据相结合，了解促销活动和广告如何与网站参与度、转化和收入相关联。 例如，将广告网络点击次数和支出与归因于同一营销活动访问的订单进行比较。

要配置此报表，请将付费媒体摘要数据集和您的现场事件数据集包含在同一Customer Journey Analytics连接中。 从登陆页面URL参数或现有事件字段中捕获稳定的促销活动、广告或支持的资产标识符。 根据需要使用派生字段解析这些值，并将其映射到相应的付费媒体标识符，从而保留所需的网络和帐户上下文。 将标识符保留为字符串。 要关联匹配的事件和摘要维度，请在数据视图中配置摘要数据组。 启用付费媒体渠道不会自动配置此特定于实施的URL跟踪和映射。


| 跟踪选项 | 注意事项 |
|---|---|
| Meta Ads | 使用动态标识符（例如`campaign.id`、`adset.id`和`ad.id`，如果支持）配置目标URL参数。 捕获您网站上的已解析值。 启用连接器不会自动将这些参数添加到广告URL。 |
| Google Ads | |
| 单个资产 | 下游结果的资产级报表需要一个捕获的标识符，该标识符映射到与点击关联的特定资产。 如果广告格式允许进行特定于资产的跟踪，则自定义URL参数可以支持此功能。 仅广告标识符无法区分广告中的多个资产，并且应用于整个多资产广告的一个静态资产参数无法识别与点击关联的资产。 |

在Analysis Workspace中，使用&#x200B;**[!UICONTROL 广告摘要]**&#x200B;指标进行促销活动或广告比较，使用&#x200B;**[!UICONTROL 资源摘要]**&#x200B;指标进行支持的资源比较。 将归因模型和回顾窗口应用于反映您的报表问题的网站转化量度。

请注意以下各项：

* 付费媒体数据是无人员ID的汇总摘要数据。 现场行为是事件数据。
* 分组匹配维度支持跨这些源的报告，但不将单个广告网络转化与网站转化或执行人员级别拼接匹配。
* 此比较会显示关联，而不是因果提升。
* 结果可能会因转化定义、归因窗口、浏览转化或模型化转化、同意以及报表日期或时区而有所不同。
* 跨渠道重用跟踪参数时，验证营销活动标记访问的来源。


#### 比较促销活动效果与现场订单

登陆页面URL可以包含多个跟踪参数。 在此示例中，`utm_id`中的促销活动ID用于将促销活动支出与网站订单进行比较。

https://www.example.com/offer?utm_source=facebook&utm_medium=paid_social&utm_campaign=autumn_offer&utm_id=120218706543980215

用于此比较的参数： `utm_id=120218706543980215`。 其他参数描述源、媒体和促销活动标签，但不用作本示例中使用的匹配字段。

如果在网站事件数据中捕获了URL，并且网站事件数据集和付费媒体数据集都是同一Customer Journey Analytics连接的一部分，则：

1. 识别营销活动。 使用派生字段从URL读取`utm_id`并将其值映射到付费媒体数据中的相应促销活动标识符。
1. 对匹配的维度进行分组。 在数据视图中，将网站营销活动维度添加到付费营销活动维度的`Summary Data Group`，并保留任何现有成员。
1. 比较支出和订单。 在Analysis Workspace中，使用分组的促销活动维度作为自由格式表的行。 将`Ad Summary`支出和网站`Orders`添加为列。 设置`Orders`的归因模型和回顾时间范围。


自由格式表显示广告网络支出以及归因于每个营销活动的网站订单。 两个广告支出相似的营销活动的归因下游网站操作数不同。 使用此比较可识别促销活动和登陆页面体验以进行进一步调查或测试，而不是仅根据广告量度来评估性能。

此示例使用促销活动ID，但在可捕获匹配值时，相同的方法可以使用广告组、广告或资产标识符。 Content Analytics属性，如&#x200B;**[!UICONTROL 资源前景色]**，可让您比较创意特征与付费媒体效果。 通过跨两个源配置特定于资产的跟踪和匹配属性维度，您可以将该比较扩展到已归因的网站订单，并使用结果指导创意测试。

#### 将资源性能与Web数据相结合

如果要报告和分析与付费媒体投资相关的资产性能，请考虑在广告网络付费媒体配置中添加特定资产UTM参数。 例如，除了标准动态参数（如s`ite_source_name`、`campaign.id`、`adset.id`或`placement`）之外，还添加静态自定义参数（如`aca_asset_id=999999`）。

此自定义参数将会添加到您的登陆页面URL。 例如： https://www.example.com/home.html?utm_content=120241705099850539%2Caca_asset_id%3D9999999%2Caca_placement%3DFacebook_Desktop_Feed&amp;aca_id_2=8888888&amp;utm_medium=paid&amp;utm_source=fb&amp;utm_id=120241705099830539&amp;utm_term=120241705099840539&amp;utm_campaign=120241705099830539

现在，页面上的资产与您的付费媒体数据之间存在关联。 在Analysis Workspace中使用该关系查看Content Analytics资源元数据（例如&#x200B;**[!UICONTROL 资源前景色]**）如何有助于付费媒体促销活动取得成功。


<!--

Do we need to include the tables from the Wiki?

## Reference

The following table lists paid media fields, their XDM paths, provisioned components, and reporting visibility.

+++ Paid media fields

| Field name | XDM path | ACA Paid Media component | Provisioning status | Reporting visibility |
| --- | --- | --- | --- | --- |
| Ad Network | `paidMedia.adNetwork` | Ad Network (dimension) | existing | visible through shared grouping: Ad Network |
| Channel | `paidMedia.channel` | Content Channel (dimension)<br/>Content Channel (shared dimension) | existing | visible through shared grouping: Content Channel |
| Account GUID | `paidMedia.accountGUID` | Account GUID (dimension) | existing | visible through shared grouping: Account GUID |
| Campaign GUID | `paidMedia.campaignGUID` | Campaign GUID (dimension) | existing | visible through shared grouping: Campaign GUID |
| Ad Group GUID | `paidMedia.adGroupGUID` | AdGroup GUID (dimension) | existing | visible through shared grouping: AdGroup GUID |
| Ad GUID | `paidMedia.adGUID` | Ad GUID (dimension) | existing | visible through shared grouping: Ad GUID |
| Experience GUID | `paidMedia.experienceGUID` | Experience GUID \| Ad Summary (dimension)<br/>Experience Id (shared dimension) | existing | visible through shared grouping: Experience Id |
| Asset GUID | `paidMedia.assetGUID` | Asset GUID \| Ad Summary (dimension)<br/>Asset Id (shared dimension) | existing | visible through shared grouping: Asset Id |
| Name | `paidMedia.metadata.name` | Ad Name (derived field)<br/>Ad Name (shared dimension)<br/>AdGroup Name (derived field)<br/>AdGroup Name (shared dimension)<br/>Asset Name (Paid Media) (derived field)<br/>Asset Name (Paid Media) (shared dimension)<br/>Campaign Name (derived field)<br/>Campaign Name (shared dimension)<br/>Experience Name (derived field)<br/>Experience Name (shared dimension) | existing | visible through shared grouping: Ad Name, AdGroup Name, Asset Name (Paid Media), Campaign Name, Experience Name |
| Status | `paidMedia.metadata.status` | Ad Status (derived field)<br/>Ad Status (shared dimension)<br/>Ad Group Status (derived field)<br/>Ad Group Status (shared dimension)<br/>Campaign Status (derived field)<br/>Campaign Status (shared dimension) | curated net-new | visible through shared grouping: Ad Status, Ad Group Status, Campaign Status |
| Serving Status | `paidMedia.metadata.servingStatus` | | excluded | missing provisioned component |
| Updated Time | `paidMedia.metadata.updatedTime` | | excluded | missing provisioned component |
| Account Name | `paidMedia.accountDetails.accountName` | Account Name (derived field)<br/>Account Name (shared dimension) | existing | visible through shared grouping: Account Name |
| Currency | `paidMedia.accountDetails.currency` | Account Currency (derived field)<br/>Account Currency (shared dimension) | curated net-new | visible through shared grouping: Account Currency |
| Timezone | `paidMedia.accountDetails.timezone` | Account Timezone (derived field)<br/>Account Timezone (shared dimension) | curated net-new | visible through shared grouping: Account Timezone |
| Account Type | `paidMedia.accountDetails.accountType` | Account Type (derived field)<br/>Account Type (shared dimension) | curated net-new | visible through shared grouping: Account Type |
| Business Name | `paidMedia.accountDetails.businessName` | Account Business Name (derived field)<br/>Account Business Name (shared dimension) | curated net-new | visible through shared grouping: Account Business Name |
| Campaign Type | `paidMedia.campaignDetails.campaignType` | Campaign Type (derived field)<br/>Campaign Type (shared dimension) | curated net-new | visible through shared grouping: Campaign Type |
| Objective | `paidMedia.campaignDetails.objective` | Campaign Objective (derived field)<br/>Campaign Objective (shared dimension) | curated net-new | visible through shared grouping: Campaign Objective |
| Is Automated Campaign | `paidMedia.campaignDetails.isAutomatedCampaign` | Campaign Is Automated \| Ad Summary (derived field) | curated net-new | hidden |
| Bid Strategy | `paidMedia.campaignDetails.budgetSettings.bidStrategy` | Campaign Bid Strategy (derived field)<br/>Campaign Bid Strategy (shared dimension) | curated net-new | visible through shared grouping: Campaign Bid Strategy |
| Budget Type | `paidMedia.campaignDetails.budgetSettings.budgetType` | Campaign Budget Type (derived field)<br/>Campaign Budget Type (shared dimension) | curated net-new | visible through shared grouping: Campaign Budget Type |
| Daily Budget | `paidMedia.campaignDetails.budgetSettings.dailyBudget` | Campaign Daily Budget (derived field)<br/>Campaign Daily Budget (shared dimension) | curated net-new | visible through shared grouping: Campaign Daily Budget |
| Lifetime Budget | `paidMedia.campaignDetails.budgetSettings.lifetimeBudget` | Campaign Lifetime Budget (derived field)<br/>Campaign Lifetime Budget (shared dimension) | curated net-new | visible through shared grouping: Campaign Lifetime Budget |
| Campaign Budget Optimization | `paidMedia.campaignDetails.budgetSettings.isCampaignBudgetOptimization` | Campaign Budget Optimization \| Ad Summary (derived field) | curated net-new | hidden |
| Catalog ID | `paidMedia.campaignDetails.catalogId` | Campaign Catalog ID \| Ad Summary (derived field) | curated net-new | hidden |
| Start Time | `paidMedia.campaignDetails.startTime` | Campaign Start Time (derived field)<br/>Campaign Start Time (shared dimension) | curated net-new | visible through shared grouping: Campaign Start Time |
| End Time | `paidMedia.campaignDetails.endTime` | Campaign End Time (derived field)<br/>Campaign End Time (shared dimension) | curated net-new | visible through shared grouping: Campaign End Time |
| Ad Group Type | `paidMedia.adGroupDetails.adGroupType` | Ad Group Type (derived field)<br/>Ad Group Type (shared dimension) | curated net-new | visible through shared grouping: Ad Group Type |
| Bid Strategy Type | `paidMedia.adGroupDetails.budgetSettings.bidStrategyType` | Ad Group Bid Strategy Type (derived field)<br/>Ad Group Bid Strategy Type (shared dimension) | curated net-new | visible through shared grouping: Ad Group Bid Strategy Type |
| Optimization Goal | `paidMedia.adGroupDetails.optimizationSettings.optimizationGoal` | Ad Group Optimization Goal (derived field)<br/>Ad Group Optimization Goal (shared dimension) | curated net-new | visible through shared grouping: Ad Group Optimization Goal |
| Delivery Status | `paidMedia.adGroupDetails.deliverySettings.deliveryStatus` | Ad Group Delivery Status \| Ad Summary (derived field) | curated net-new | hidden |
| Start Time | `paidMedia.adGroupDetails.startTime` | Ad Group Start Time (derived field)<br/>Ad Group Start Time (shared dimension) | curated net-new | visible through shared grouping: Ad Group Start Time |
| End Time | `paidMedia.adGroupDetails.endTime` | Ad Group End Time (derived field)<br/>Ad Group End Time (shared dimension) | curated net-new | visible through shared grouping: Ad Group End Time |
| Ad Type | `paidMedia.adDetails.adType` | Ad Type (derived field)<br/>Ad Type (shared dimension) | curated net-new | visible through shared grouping: Ad Type |
| Delivery Status | `paidMedia.adDetails.deliveryStatus` | Ad Delivery Status (derived field)<br/>Ad Delivery Status (shared dimension) | curated net-new | visible through shared grouping: Ad Delivery Status |
| Review Status | `paidMedia.adDetails.reviewStatus` | Ad Review Status (derived field)<br/>Ad Review Status (shared dimension) | curated net-new | visible through shared grouping: Ad Review Status |
| Creative Type | `paidMedia.adDetails.creative.paidMediaCreative.creativeType` | Ad Creative Type (derived field)<br/>Ad Creative Type (shared dimension) | curated net-new | visible through shared grouping: Ad Creative Type |
| Title | `paidMedia.adDetails.creative.paidMediaCreative.title` | Ad Title (derived field)<br/>Ad Title (shared dimension) | curated net-new | visible through shared grouping: Ad Title |
| Call to Action | `paidMedia.adDetails.creative.paidMediaCreative.callToAction` | Ad Call to Action (derived field)<br/>Ad Call to Action (shared dimension) | curated net-new | visible through shared grouping: Ad Call to Action |
| Destination URL | `paidMedia.adDetails.creative.paidMediaCreative.destinationURL` | Ad Destination URL (derived field)<br/>Ad Destination URL (shared dimension) | curated net-new | visible through shared grouping: Ad Destination URL |
| Display URL | `paidMedia.adDetails.creative.paidMediaCreative.displayURL` | Ad Display URL (derived field)<br/>Ad Display URL (shared dimension) | curated net-new | visible through shared grouping: Ad Display URL |
| Experience Type | `paidMedia.experienceDetails.experienceType` | Experience Type (derived field)<br/>Experience Type (shared dimension) | curated net-new | visible through shared grouping: Experience Type |
| Landing Page URL | `paidMedia.experienceDetails.landingPageURL` | Experience Landing Page URL (derived field)<br/>Experience Landing Page URL (shared dimension) | curated net-new | visible through shared grouping: Experience Landing Page URL |
| Call To Action | `paidMedia.experienceDetails.callToAction` | Experience Call to Action (derived field)<br/>Experience Call to Action (shared dimension) | curated net-new | visible through shared grouping: Experience Call to Action |
| Card Count | `paidMedia.experienceDetails.carouselProperties.cardCount` | Experience Card Count \| Ad Summary (derived field) | curated net-new | hidden |
| Asset Type | `paidMedia.assetDetails.assetType` | Asset Type (derived field)<br/>Asset Type (shared dimension) | curated net-new | visible through shared grouping: Asset Type |
| Permalink URL | `paidMedia.assetDetails.mediaProperties.permalinkURL` | Asset Permalink URL \| Ad Summary (derived field) | curated net-new | hidden |
| Width | `paidMedia.assetDetails.dimensions.width` | Asset Width (derived field)<br/>Asset Width (shared dimension) | curated net-new | visible through shared grouping: Asset Width |
| Height | `paidMedia.assetDetails.dimensions.height` | Asset Height (derived field)<br/>Asset Height (shared dimension) | curated net-new | visible through shared grouping: Asset Height |
| Aspect Ratio | `paidMedia.assetDetails.dimensions.aspectRatio` | Asset Aspect Ratio (derived field)<br/>Asset Aspect Ratio (shared dimension) | curated net-new | visible through shared grouping: Asset Aspect Ratio |
| Orientation | `paidMedia.assetDetails.dimensions.orientation` | Asset Orientation \| Ad Summary (derived field)<br/>Asset Orientation (shared dimension) | curated net-new | visible through shared grouping: Asset Orientation |
| MIME Type | `paidMedia.assetDetails.fileProperties.mimeType` | Asset MIME Type \| Ad Summary (derived field) | curated net-new | hidden |
| Impressions | `paidMedia.metrics.impressions` | Impressions \| Ad Summary (metric) | existing | visible |
| Clicks | `paidMedia.metrics.clicks` | Clicks \| Ad Summary (metric) | existing | visible |
| Spend | `paidMedia.metrics.spend` | Spend \| Ad Summary (metric) | existing | visible |
| Reach | `paidMedia.metrics.reach` | Reach \| Ad Summary (metric) | curated net-new | visible |
| Conversions | `paidMedia.metrics.conversions` | Conversions \| Ad Summary (metric) | curated net-new | visible |
| Conversion Value | `paidMedia.metrics.conversionValue` | Conversion Value \| Ad Summary (metric) | curated net-new | visible |
| Video Views | `paidMedia.metrics.videoViews` | Video Views \| Ad Summary (metric) | curated net-new | visible |
| Engagements | `paidMedia.metrics.engagements` | Engagements \| Ad Summary (metric) | curated net-new | visible |
| Post-Click Conversions | `paidMedia.conversionMetrics.postClickConversions` | Post-Click Conversions \| Ad Summary (metric) | curated net-new | visible |
| Post-View Conversions | `paidMedia.conversionMetrics.postViewConversions` | Post-View Conversions \| Ad Summary (metric) | curated net-new | visible |
| Purchases | `paidMedia.conversionMetrics.conversionsByType.purchases` | Purchases \| Ad Summary (metric) | curated net-new | visible |
| Add to Cart | `paidMedia.conversionMetrics.conversionsByType.addToCart` | Add to Cart \| Ad Summary (metric) | curated net-new | visible |
| Leads | `paidMedia.conversionMetrics.conversionsByType.leads` | Leads \| Ad Summary (metric) | curated net-new | visible |
| Registrations | `paidMedia.conversionMetrics.conversionsByType.registrations` | Registrations \| Ad Summary (metric) | curated net-new | visible |
| Downloads | `paidMedia.conversionMetrics.conversionsByType.downloads` | Downloads \| Ad Summary (metric) | curated net-new | visible |
| Subscriptions | `paidMedia.conversionMetrics.conversionsByType.subscriptions` | Subscriptions \| Ad Summary (metric) | curated net-new | visible |
| Landing Page View | `paidMedia.conversionMetrics.conversionsByType.landingPageView` | Landing Page Views \| Ad Summary (metric) | curated net-new | visible |
| Total Order Value | `paidMedia.conversionMetrics.totalOrderValue` | Total Order Value \| Ad Summary (metric) | curated net-new | visible |
| Video Plays | `paidMedia.videoMetrics.videoPlays` | Video Plays \| Ad Summary (metric) | curated net-new | visible |
| Video Completions | `paidMedia.videoMetrics.videoCompletions` | Video Completions \| Ad Summary (metric) | curated net-new | visible |
| Link Clicks | `paidMedia.extendedMetrics.linkClicks` | Link Clicks \| Ad Summary (metric) | curated net-new | visible |
| Outbound Clicks | `paidMedia.extendedMetrics.outboundClicks` | Outbound Clicks \| Ad Summary (metric) | curated net-new | visible |
| App Installs | `paidMedia.extendedMetrics.appInstalls` | App Installs \| Ad Summary (metric) | curated net-new | visible |
| Lead Submissions | `paidMedia.extendedMetrics.leadSubmissions` | Lead Submissions \| Ad Summary (metric) | curated net-new | visible |
| Device Type | `paidMedia.dimensionalBreakdowns.deviceType` | | excluded | removed in source range |
| Placement | `paidMedia.dimensionalBreakdowns.placement` | Placement (dimension) | curated net-new | visible through shared grouping: Placement |
| Platform | `paidMedia.dimensionalBreakdowns.platform` | Platform (dimension) | curated net-new | visible through shared grouping: Platform |
| Country | `paidMedia.dimensionalBreakdowns.country` | Country (dimension) | curated net-new | visible through shared grouping: Country |
| Region | `paidMedia.dimensionalBreakdowns.region` | Region (dimension) | curated net-new | visible through shared grouping: Region |
| Other connector-populated fields | See field tables | No named component | excluded | not surfaced |

+++

### Identifiers

| Field name | Description | XDM path | ACA Paid Media component | ACA context label | Meta | Google Ads | Pinterest | Snapchat | TikTok |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Record ID | *Unique record URI, inherited from data/record.* | `@id` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta:{entity}:{ids}`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads:{entity}:{ids}`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (pinterest:&lt;entity&gt;: source-derived composite record ID; GUIDs use pinterest_; writer later emits this as _id.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (snapchat:&lt;entity&gt;: source-derived composite record ID; GUIDs use snapchat_; writer later emits this as _id.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (tiktok:&lt;entity&gt;: source-derived composite record ID; GUIDs use tiktok_; summary IDs omit dimension values; writer emits _id.) |
| Entity Type | The type of paid media entity | `entityType` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) |
| Ad Network | The advertising platform/network | `paidMedia.adNetwork` | Ad Network (dimension) | Ad Network | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads`) | ⚪ (Fixed routing discriminator (pinterest); not a source attribute.) | ⚪ (Fixed routing discriminator (snapchat); not a source attribute.) | ⚪ (Fixed routing discriminator (tiktok); not a source attribute.) |
| Network | Alias of adNetwork for migration from GenStudio templates | `paidMedia.network` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ⚪ (Fixed routing discriminator (pinterest); not a source attribute.) | ⚪ (Fixed routing discriminator (snapchat); not a source attribute.) | ⚪ (Fixed routing discriminator (tiktok); not a source attribute.) |
| Channel | Content channel indicating the source of the data (e.g., Web, Mobile, PaidMedia). Used as a reporting dimension for cross-channel breakdowns. | `paidMedia.channel` | Content Channel (dimension)<br/>Content Channel (shared dimension) | Content Channel (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`PaidMedia`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`PaidMedia`) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) |
| Hierarchy Path | Full hierarchical path showing parent-child relationships (e.g., account_id/campaign_id/adgroup_id/ad_id) | `paidMedia.hierarchyPath` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account ID | Unique identifier for the ad account within the network | `paidMedia.accountID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account GUID | Unique identifier for the ad account across all networks | `paidMedia.accountGUID` | Account GUID (dimension) | Account Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta_` prefix) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads_` prefix) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Campaign ID | Unique identifier for the campaign within the network | `paidMedia.campaignID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Campaign GUID | Unique identifier for the campaign across all networks | `paidMedia.campaignGUID` | Campaign GUID (dimension) | Campaign Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad Group ID | Unique identifier for the ad group/ad set/ad squad within the network | `paidMedia.adGroupID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad Group GUID | Unique identifier for the ad group/ad set/ad squad across all networks | `paidMedia.adGroupGUID` | AdGroup GUID (dimension) | AdGroup Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad ID | Unique identifier for the individual ad within the network | `paidMedia.adID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad GUID | Unique identifier for the individual ad across all networks | `paidMedia.adGUID` | Ad GUID (dimension) | Ad Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Experience ID | Unique identifier for creative experience (multi-asset compositions) within the network | `paidMedia.experienceID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Ad ID on Experience lookup and summaries; null on Ad lookup; asset reverse join recovers ad ID when metadata matches.) |
| Experience GUID | Unique identifier for creative experience (multi-asset compositions) across all networks | `paidMedia.experienceGUID` | Experience GUID \| Ad Summary (dimension)<br/>Experience Id (shared dimension) | Experience Id (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Asset ID | Unique identifier for creative assets (images, videos, etc.) within the network | `paidMedia.assetID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Asset GUID | Unique identifier for creative assets (images, videos, etc.) across all networks | `paidMedia.assetGUID` | Asset GUID \| Ad Summary (dimension)<br/>Asset Id (shared dimension) | Asset Id (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account GUID | Account GUID (class entityIDs hierarchy) | `entityIDs.account.accountGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Account ID | Account ID (class entityIDs hierarchy) | `entityIDs.account.accountID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Campaign GUID | Campaign GUID (class entityIDs hierarchy) | `entityIDs.campaign.campaignGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Campaign ID | Campaign ID (class entityIDs hierarchy) | `entityIDs.campaign.campaignID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group GUID | Ad Group GUID (class entityIDs hierarchy) | `entityIDs.adGroup.adGroupGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group ID | Ad Group ID (class entityIDs hierarchy) | `entityIDs.adGroup.adGroupID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad GUID | Ad GUID (class entityIDs hierarchy) | `entityIDs.ad.adGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad ID | Ad ID (class entityIDs hierarchy) | `entityIDs.ad.adID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Experience GUID | Experience GUID (class entityIDs hierarchy) | `entityIDs.experience.experienceGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Experience ID | Experience ID (class entityIDs hierarchy) | `entityIDs.experience.experienceID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Asset GUID | Asset GUID (class entityIDs hierarchy) | `entityIDs.asset.assetGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Asset ID | Asset ID (class entityIDs hierarchy) | `entityIDs.asset.assetID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group Name | Display name of the ad group/ad set/ad squad. Mirrors metadata.name from the ad group lookup. | `paidMedia.denormalizedNames.adGroupName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Ad group name"))`) | | |
| Ad Name | Display name of the individual ad. Mirrors metadata.name from the ad lookup. | `paidMedia.denormalizedNames.adName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Ad name"))`) | | |
| Campaign Name | Display name of the campaign. Mirrors metadata.name from the campaign lookup. | `paidMedia.denormalizedNames.campaignName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Campaign name"))`) | | |

-->
