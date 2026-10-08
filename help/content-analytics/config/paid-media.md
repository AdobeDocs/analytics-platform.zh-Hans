---
title: Content Analytics付费媒体自动配置
description: 了解数据集、连接、数据视图等的自动配置。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
source-git-commit: 2727dce145b996192ac873dd43d5106b011ff736
workflow-type: tm+mt
source-wordcount: '1493'
ht-degree: 4%
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

下图显示当您在Content Analytics中为一个或多个广告网络启用付费媒体渠道时，如何生成汇总数据集。 可使用来自可用广告网络的相关API下载体验、资产和广告数据，并将这些数据转换为潜在的六个摘要数据集。

![付费媒体生成摘要数据集](/help/content-analytics/assets/paid-media-generation-of-datasets.svg)

创建哪些摘要数据集取决于特定的广告网络。 并非每个您为其配置了源连接器的广告网络都会生成所有六个可能的摘要数据集。 有关概要数据集的概述，请参阅下表，其中包含以下信息：

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

| 摘要数据集<br/>事件类型<br/>组件后缀 | 实体 | 划分 | ![MetaMulti](/help/assets/icons2/MetaSolid.svg) | ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) | ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) | ![Snapchat](/help/assets/icons2/Snapchat.svg) | ![TikTok](/help/assets/icons2/TikTok.svg) | 每一行表示 |
|---|---|---|:---:|:---:|:---:|:---:|:---:|---|
| `paidmedia_ad_summary` <br/> `ad.summary`<br/>`\| Ad Summary` | 广告 | 无 | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | 广告的每日效果，无需考虑人口统计或地理因素。 |
| `paidmedia_ad_demographics` <br/> `ad.demographics`<br/>`\| Ad Demo` | 广告 | 年龄、性别 | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | 按年龄和性别细分的广告日常表现。 |
| `paidmedia_ad_geography` <br/> `ad.geography`<br/>`\| Ad Geo` | 广告 | 国家/地区 | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | 按国家和地区细分的广告每日效果。 |
| `paidmedia_experience_placement` <br/> `ad.experience.placement`<br>`\| Experience Placement` | 体验 | 平台，位置 | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | 与广告的创意体验关联的每日表现，按平台和位置划分。 |
| `paidmedia_asset_summary` <br/>`ad.asset.summary`<br/>`\| Asset Summary` | 资产 | 无 | ![Checkmark](/help/assets/icons2/Checkmark.svg) | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | | ![Checkmark](/help/assets/icons2/Checkmark.svg) | 在其广告/营销活动上下文中提供每日资产级别的绩效，无人口统计或地理细分。 |
| `paidmedia_assets_demographics` <br/> `ad.asset.demographics`<br/>`\| Asset Demo` | 资产 | 年龄、性别 | ![Checkmark](/help/assets/icons2/Checkmark.svg) | | | | | 在其广告/营销活动上下文中按年龄和性别细分的每日资产级绩效。 |


此表描述了数据集覆盖范围，并不能保证每个量度或元数据字段都由特定网络填充。 检查分析所需的字段。 不可用字段或不受支持的划分与测量出的字段零值不同。

单独的查找数据集描述了帐户、促销活动、广告组、广告、体验和资产。 它们使用实体GUID提供名称和元数据。 摘要数据集和六个查找数据集之间不存在一对一的配对。

摘要数据分组将等效维度汇总在一起；分组不会汇总六个性能量度总计。

## 组件

Content Analytics付费媒体渠道在启用后，还会生成多个数据视图组件。 这些组件具有组件后缀，用于区分彼此的相似命名组件。

### 量度

不同的广告网络会返回不同的性能细分。 Content Analytics会保留这些区别，而不是将量度的每个版本都视为可互换的。

例如：

| 组件 | 含义 | 适当的开始分析 |
| --- | --- | --- |
| 点击次数\|广告摘要 | 在广告的无细分级别报告的点击数 | 营销活动或广告效果 |
| 单击\|资源摘要 | 资产级别报告的点击次数 | Creative-asset性能 |
| 点击次数\|广告地域 | 广告地理位置报表的点击量 | 按国家或地区列出的绩效 |
| 点击次数\|体验位置 | 体验投放位置报表中的点击量 | Creative按投放位置列出的性能 |

每个点击量度组件提供不同的报表上下文。 您不能简单地将这些量度组件合计为一个总计。 同一基础广告活动可以在多个摘要数据集中表示。

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

### 广告营销活动效果示例

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

### 联网表现最佳的广告示例

您想了解Meta广告在哪些方面的表现最佳？

要进行调查，请使用地理和人口结构的其他细分。 使用促销活动名称或广告名称作为维度，并使用下表所述的量度。 每个量度具有相同的组件后缀。

| 量度 | 报告级别 |
| --- | --- |
| 展示次数 | 广告地域 |
| 点击量 | 广告地域 |
| 支出 | 广告摘要 |
| 点进率 | 广告地域 |
| 每次点击成本 | 广告摘要 |


