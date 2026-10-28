---
title: 在Customer Journey Analytics中将付费媒体数据与Web数据连接起来
description: 将付费媒体摘要数据与Adobe Customer Journey Analytics中的网站活动结合使用，比较广告支出、点击次数、订单、收入和广告支出回报率。
solution: Customer Journey Analytics
feature: Use Cases
hide: true
role: Admin
source-git-commit: 3fc129c2eeb5fd86e8ef4d885a4682dd819fc481
workflow-type: tm+mt
source-wordcount: '3907'
ht-degree: 3%
---
# 将付费媒体数据与Web数据连接起来

此用例指南说明了如何将付费媒体摘要数据与[!DNL Adobe Customer Journey Analytics]中的网站行为事件数据连接起来。


将您的广告帐户（Meta、Google广告等）连接到Experience Platform可在Customer Journey Analytics中提供付费媒体摘要数据：每个帐户、营销活动、广告组、广告、体验和资产的每日展示次数、点击次数、支出和广告网络报告的转化。 使用Customer Journey Analytics，您可以使用Web SDK收集您自己的网站行为事件数据：页面查看次数、订单数、收入。

将这两种类型的数据加入一个Workspace自由格式表中后，您可以将广告效果与网站上的活动进行比较。 在[!DNL Analysis Workspace]中，使用共享营销活动、广告组和广告ID报告展示次数、点击次数，以及付费登陆次数、订单和收入的情况。

| 数据源 | 量度示例 |
|---|---|
| 付费媒体摘要数据 | 广告网络报告的展示次数、点击次数、支出、转化和转化值。 |
| 网站行为事件 | 在您的网站上衡量的付费登陆页面、页面查看次数、订单和收入 |
| 计算量度 | 登陆页面访问率、Web转化率、Web广告支出回报率、每次Web订单的成本以及网络与Web转化之间的差距 |

结合使用这两种类型的数据，您可以比较点击前数据（来自广告）和点击后数据（来自网站）。

本指南介绍基于由[!DNL Adobe Content Analytics]配置管理的连接以及您自己配置的连接的情况。

## 工作原理

下图说明了如何通过Customer Journey Analytics连接摄取付费媒体摘要数据和网站行为事件数据。

数据视图负责解析和统一数据，因此您可以使用Workspace正确报告数据。

![付费媒体加入](./assets/paid-media-web-join.png){zoomable="yes"}

付费媒体摘要数据集包含不带个人ID的每日量度。 网站事件数据集包含带有时间戳的行为事件和人员标识符。 摘要数据组与这些数据集中的维度相关联，以便相同的维度值显示在同一报表行中。

>[!IMPORTANT]
>
>此连接使聚合的摘要数据和Web事件保持一致，以便进行报告。 它不会将广告展示或点击链接到个人。 广告网络转化仍保留网络的报告方法。 网站订单和收入会使用您在本指南中配置的归因设置。

## 了解报表加入

您只能在ID显示在登陆页面URL或现有事件字段中的级别进行连接。 例如，仅营销活动标记支持营销活动报告，但不支持广告级别的报告。 体验级和资产级连接需要其他URL参数，并且不在本指南的范围之内。

请参阅[摘要数据](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/summary-data)和[摘要数据组组件设置](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/summary-data-group)以供参考。

### 选择连接键

付费媒体数据集提供原始网络ID和Adobe生成的全局唯一标识符(GUID)。

| 标识符 | 示例 | 用途 |
|---|---|---|
| 网络ID | 营销活动ID `123456789` | 将从登陆页面URL捕获的ID匹配到付费媒体摘要维度 |
| GUID | `meta_111111111_123456789` | 使用网络、帐户和实体层次结构标识付费媒体实体 |

GUID结构为`{adNetwork}_{accountID}[_{campaignID}[_{adGroupID}[_{adID}]]]`。 由[!DNL Adobe Content Analytics]管理的付费媒体组件使用这些GUID。

本指南使用网络ID进行Web连接，因为营销活动、广告组和广告URL宏并不提供重构GUID所需的所有信息。 请使用以下摘要字段：

| 报告级别 | 网络ID字段 | GUID字段 |
|---|---|---|
| 促销活动 | `paidMedia.campaignID` | `paidMedia.campaignGUID` |
| 广告组 | `paidMedia.adGroupID` | `paidMedia.adGroupGUID` |
| 广告 | `paidMedia.adID` | `paidMedia.adGUID` |

网络字段为`paidMedia.adNetwork`。 示例值包括`meta`和`google_ads`。 派生字段输出必须与数据集中的值完全匹配。

>[!NOTE]
>
>摘要数据组匹配维度值，而不是表中所有维度的组合。 确认您选择的ID在您报告的帐户和网络间明确标识实体。 基于名称的组可以组合共享名称的不同实体。

## 先决条件

确认您拥有：

* [!DNL Customer Journey Analytics]选择或更高，可访问此处使用的派生字段函数：[URL Parse](/help/data-views/derived-fields/derived-fields.md#url-parse)、[Case When](/help/data-views/derived-fields/derived-fields.md#case-when)、[Regex Replace](/help/data-views/derived-fields/derived-fields.md#regex-replace)，对于名称扩充，[Lookup](/help/data-views/derived-fields/derived-fields.md#lookup)。
* [!DNL Adobe Experience Platform]权限用于管理目标沙盒中的架构、数据集和数据流，以及访问数据集和查询服务以进行验证。
* [!DNL Customer Journey Analytics]编辑目标连接和数据视图的权限。
* 付费媒体源连接器在同一沙盒中配置，并摄取摘要和查找数据集。 有关示例连接器，请参阅[Meta广告源](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/advertising/meta-ads)。
* 捕获完整登陆页面URL（包括其查询字符串）或包含网络ID的等效字段的网站事件。


### 广告标记

识别包含营销活动、广告组和广告ID的查询参数。 可以使用现有的基于ID的标记，而无需更改广告平台。

| 标记模式 | Campaign参数 | 广告组参数 | 广告参数 |
|---|---|---|---|
| 网站URL中的Meta ID | <code>campaign_id={{campaign.id}}</code> | <code>adset_id={{adset.id}}</code> | <code>ad_id={{ad.id}}</code> |
| UTM参数中的Meta ID | <code>utm_campaign={{campaign.id}}</code> | <code>utm_term={{adset.id}}</code> | <code>utm_content={{ad.id}}</code> |
| UTM参数中的Google广告ID | <code>utm_campaign={campaignid}</code> | <code>utm_term={adgroupid}</code> | <code>utm_content={creative}</code> |

对于Meta UTM标记，源值（如`utm_source=fb`）可以识别网络。 对于Google广告UTM标记，请使用源值，例如`utm_source=google`。

某些[!DNL Adobe Advertising]集成将`s_kwcid`值与此布局一起使用：

```text
AL!<id>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}!{campaignid}!{adgroupid}
```

本指南后面部分中的解析规则仅适用于此布局。 在使用实际登陆URL之前，请对其进行检查。

如果您无权访问广告平台，请检查Web数据集中的登陆URL。 您还可以检查以下付费媒体查找字段：

* Google Ads帐户查找：名为`google_ads_tracking_url_template`和`google_ads_final_url_suffix`的`additionalDetails`条目。
* Meta广告查找： `paidMedia.adDetails.creative.paidMediaCreative.destinationURL`。

存储的目标URL中的宏可以采用百分比编码。 验证实际网站事件中扩展的ID，而不是假设存储的URL代表最终登录URL。

>[!IMPORTANT]
>
>促销活动名称（如`utm_campaign=fall_sale`）与促销活动ID不匹配。 仅在包含实际ID的级别连接。 如果ID缺失，请与广告运营团队合作，为将来的流量更新标记；此设置无法重新构建历史访问中缺失的ID。

### 起点

打开您计划使用的数据视图，并检查组件以确定起点。

| | 起点 | 现有的配置 | 遵循的步骤 |
|---|---|---|---|
| A | 带有Web或移动和付费媒体的Content Analytics | 付费媒体数据集和组件，以及Content Analytics事件和查找数据集 | 如果需要，添加您的网站事件数据集，然后配置Web派生字段和报告组 |
| B | 仅带付费媒体的Content Analytics | 付费媒体数据集和组件；也可以存在共享内容查找数据集 | 添加您的网站事件数据集，然后配置Web派生字段和报告组 |
| C | 无Content Analytics配置的付费媒体 | Experience Platform中存在付费媒体数据集，但连接和数据视图不包含付费媒体配置 | 添加网站和付费媒体数据集，然后创建付费媒体和Web组件 |
| D | 不带付费媒体的Content Analytics | 仅限Content Analytics组件 | 在Content Analytics配置中启用付费媒体渠道，然后遵循现有配置路径 |

在扩展Content Analytics管理的连接时，请勿删除或修改系统配置的数据集或只读组件。

## 收集网站行为事件

如果您的网站已将所需事件发送到Customer Journey Analytics中使用的数据集，请跳过架构、数据集和数据流创建。 确认`web.webPageDetails.URL`包含登陆页面查询字符串。

### 创建架构和数据集

1. 在Experience Platform中，选择target沙盒。
1. 转到&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 架构]**，然后选择&#x200B;**[!UICONTROL 创建架构]**。
1. 选择&#x200B;**[!UICONTROL 手动]**&#x200B;和`XDM ExperienceEvent`类。
1. 命名架构，例如`Web Behavioral Events`。
1. 添加实施所需的字段组。

   | 字段组 | 所需数据 |
   |---|---|
   | AEP Web SDK体验事件 | 页面URL、页面查看次数、反向链接和其他Web上下文 |
   | Commerce详细信息 | 采购计数、订单值、货币、购买ID和产品详细信息 |
   | 营销活动详细信息，可选 | 跟踪代码（如果您的实施单独捕获它们） |
   | IdentityMap （如果尚不存在） | 人员标识符，如ECID |

1. 保存架构。 此报告用例不需要启用配置文件。
1. 转到&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 数据集]** > **[!UICONTROL 创建数据集]** > **[!UICONTROL 从架构创建数据集]**。
1. 选择架构并创建一个名为的数据集，例如`Web Behavioral Events`。 将&#x200B;**[!UICONTROL 配置文件]**&#x200B;保留为禁用状态，除非其他用例需要它。

### 配置数据流和Web SDK

1. 转到&#x200B;**[!UICONTROL 数据收集]** > **[!UICONTROL 数据流]** > **[!UICONTROL 新建数据流]**。
1. 命名数据流并选择您的事件架构作为映射架构。
1. 保存，然后选择&#x200B;**[!UICONTROL 添加服务]** > **[!UICONTROL Adobe Experience Platform]**。
1. 选择沙盒和事件数据集，然后&#x200B;**[!UICONTROL 保存]**。
1. 使用数据流ID配置[Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/js-overview)。

捕获以下内容：

* 在将`web.webPageDetails.URL`和`web.webPageDetails.pageViews.value`中的完整URL设置为`1`的情况下，捕获每个页面上的页面查看次数。
* 将`commerce.purchases.value`设置为`1`以及`commerce.order.priceTotal`、`commerce.order.currencyCode`和`commerce.order.purchaseID`的购买事件。
* 适用于您的Customer Journey Analytics连接的人员标识符。

您不需要解析网站代码中的UTM参数。 本指南中的派生字段在报告时解析URL。 如果您的实施已经捕获专用字段中的ID，请改用这些字段。

### 验证引入

检查数据集活动是否已成功引入。 在查询服务中，运行以下查询，将`web_behavioral_events`替换为您数据集的SQL表名称：

```sql
SELECT timestamp, eventType, web.webPageDetails.URL
FROM web_behavioral_events
WHERE web.webPageDetails.URL RLIKE '[?&](campaign_id|utm_campaign|s_kwcid)='
ORDER BY timestamp DESC
LIMIT 20;
```

确认返回的URL包含扩展的网络ID。 如果存在付费流量但查询未返回任何行，请检查最近的登陆URL并根据您的标记调整参数模式。

## 配置连接

要将Web事件数据集摄取到Customer Journey Analytics，您需要将该数据集添加到相关连接。 这可确保Web行为事件与付费媒体数据集一起可用于分析。

### 添加网站事件数据集

1. 在Customer Journey Analytics中，转到&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 连接]**。
1. 编辑包含付费媒体数据集的连接。
1. 选择&#x200B;**[!UICONTROL 添加数据集]**&#x200B;并选择网站事件数据集。
1. 配置数据集：

   | 设置 | 数值 |
   |---|---|
   | 人员 ID | 具有ECID命名空间的`identityMap`或您实施的人员ID字段 |
   | 时间戳 | `timestamp` |
   | 数据源类型 | Web数据 |
   | 导入所有新数据 | 启用 |
   | 回填所有现有数据 | 为您需要的历史时段启用 |

1. 添加数据集并保存连接。

### 添加付费媒体数据集（如果尚未配置）

>[!IMPORTANT]
>
>跳过此部分以了解Content Analytics管理付费媒体数据集的连接。


至少添加付费媒体广告摘要和付费媒体帐户、付费媒体营销活动、付费媒体广告组和付费媒体广告查找数据集。

| 数据集 | 类型 | 关键配置 |
|---|---|---|
| 付费媒体广告摘要 | 摘要 | 使用架构的每日时间戳配置；启用新数据导入和所需的回填。 |
| 付费媒体帐户查找 | 查找 | 键： `paidMedia.accountGUID`；广告摘要中的匹配字段： `paidMedia.accountGUID`。 |
| 付费媒体营销活动查找 | 查询 | 键： `paidMedia.campaignGUID`；广告摘要中的匹配字段： `paidMedia.campaignGUID`。 |
| 付费媒体广告组查找 | 查询 | 键： `paidMedia.adGroupGUID`；广告摘要中的匹配字段： `paidMedia.adGroupGUID`。 |
| 付费媒体广告查找 | 查询 | 键： `paidMedia.adGUID`；广告摘要中的匹配字段： `paidMedia.adGUID`。 |

在保存之前，请确认连接编辑器公开所需的匹配字段。 本指南后面的名称扩充明确使用派生字段查找规则。

仅在需要划分其他可用摘要数据集时添加这些数据集，例如地理位置、人口统计、位置或性能。

## 配置数据视图

打开&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 数据视图]**&#x200B;并选择您的数据视图。 如果需要，请使用您配置的连接创建数据视图。

对于新数据视图，使用GMT将网站事件与UTC付费媒体天数保持一致，并保持默认的30分钟会话超时，除非您的报告要求不同。 更改现有数据视图的时区会影响其其他报表；请在更改时区之前评估该影响。

### 添加付费媒体量度（如果尚未配置）

如果这些量度或维度已存在，请跳过此步骤。 从&#x200B;**[!UICONTROL 付费媒体广告摘要]**&#x200B;添加以下字段：

| 组件名称 | 架构字段 | 格式 |
|---|---|---|
| **量度** | | |
| 展示次数\|广告摘要 | `paidMedia.metrics.impressions` | 小数 |
| 点击次数\|广告摘要 | `paidMedia.metrics.clicks` | 小数 |
| 支出\|广告摘要 | `paidMedia.metrics.spend` | 货币 |
| 转化\|广告摘要 | `paidMedia.metrics.conversions` | 小数 |
| 转化值\|广告摘要 | `paidMedia.metrics.conversionValue` | 货币 |
| **维度** | | |
| 广告网络 | `paidMedia.adNetwork` | 字符串 |
| 帐户 GUID | `paidMedia.accountGUID` | 字符串 |
| 营销活动 GUID | `paidMedia.campaignGUID` | 字符串 |
| 广告组 GUID | `paidMedia.adGroupGUID` | 字符串 |
| 广告 GUID | `paidMedia.adGUID` | 字符串 |

货币格式本身不会协调不同的源货币。 在比较支出和收入之前确认货币基准。

使用派生字段创建GUID维度的描述性名称。 使用[查找](/help/data-views/derived-fields/derived-fields.md#lookup)规则为GUID维度应用描述性名称。  例如：使用查询数据集&#x200B;**[!UICONTROL 付费媒体帐户查询]**&#x200B;查找&#x200B;**[!UICONTROL paidMedia.accountGUID （付费媒体广告摘要）]**，该数据集具有要返回的匹配键`paidMedia.accountGUID`和值： `paidMedia.accountDetails.accountName`。


### 创建Web网络派生字段

选择&#x200B;**[!UICONTROL 创建派生字段]**&#x200B;并命名字段`PM Network (Web)`。 以下所有[URL分析](/help/data-views/derived-fields/derived-fields.md#url-parse)规则都读取网站数据集的`web.webPageDetails.URL`字段，此处称为页面URL。

按以下顺序添加规则：

| 规则 | 功能 | 配置 |
|---|---|---|
| 1 | [URL分析](/help/data-views/derived-fields/derived-fields.md#url-parse) | 页面URL。 获取`utm_source`的查询字符串值。 |
| 2 | [URL分析](/help/data-views/derived-fields/derived-fields.md#url-parse) | 页面URL。 获取`s_kwcid`的查询字符串值。 |
| 3 | [URL分析](/help/data-views/derived-fields/derived-fields.md#url-parse) | 页面URL。 获取`gclid`的查询字符串值。 |
| 4 | [URL分析](/help/data-views/derived-fields/derived-fields.md#url-parse) | 页面URL。 获取`fbclid`的查询字符串值。 |
| 5 | [案例时间](/help/data-views/derived-fields/derived-fields.md#case-when) | 应用以下条件。 |

配置最终[Case When](/help/data-views/derived-fields/derived-fields.md#case-when)规则：

1. 如果设置了规则2或规则3，则返回`google_ads`。
1. 否则，如果设置了规则4或规则1等于`fb`、`facebook`、`ig`、`instagram`或`meta`，则返回`meta`。
1. 否则，如果规则1等于`google`，则返回`google_ads`。
1. 仅在`paidMedia.adNetwork`中确认其他网络的值后为其添加映射。
1. 否则，不返回任何值。

若要输入固定输出，请打开值选取器，选择&#x200B;**[!UICONTROL 自定义字符串值]**，然后输入字符串。

这些分类规则基于标记，不能证明访问来自付费广告。 例如，源参数本身也可能出现在非付费链接上。 在将字段用作付费流量分类器之前，请根据标记惯例调整条件。

### 创建Web ID派生字段

为每个报告级别创建一个派生字段。 以下结构处理前面所述的三种标记模式：

| 规则 | 功能 | 配置 |
|---|---|---|
| 1 | [URL分析](/help/data-views/derived-fields/derived-fields.md#url-parse) | 从页面URL中读取特定于级别的Meta参数 |
| 2 | [URL分析](/help/data-views/derived-fields/derived-fields.md#url-parse) | 从页面URL中读取特定于级别的UTM参数 |
| 3 | [URL分析](/help/data-views/derived-fields/derived-fields.md#url-parse) | 从页面URL读取`s_kwcid` |
| 4 | [正则表达式替换](/help/data-views/derived-fields/derived-fields.md#regex-replace) | 将特定于级别的表达式应用于规则3；输出`$1` |
| 5 | [案例时间](/help/data-views/derived-fields/derived-fields.md#case-when) | 如果设置了规则3，则返回规则4；如果设置了规则1，则返回规则1；否则，返回规则2 |

使用以下值：

| 派生字段 | Meta参数 | UTM参数 | 正则表达式 |
|---|---|---|---|
| **PM促销活动ID (Web)** | `campaign_id` | `utm_campaign` | `^.*!([^!]*)![^!]*$` |
| **PM广告组ID (Web)** | `adset_id` | `utm_term` | `^.*!([^!]*)$` |
| **PM广告ID (Web)** | `ad_id` | `utm_content` | `^[^!]*![^!]*![^!]*!([^!]*)!.*$` |

在最终的[Case When](/help/data-views/derived-fields/derived-fields.md#case-when)规则中，从值选取器中选择较早的规则输出，而不是将其输入为文本字符串。

促销活动表达式提取从第二个到最后一个`s_kwcid`值，广告组表达式提取最后一个值，广告表达式提取第四个值。 这些位置取决于前面显示的确切布局。

使用&#x200B;**[!UICONTROL 最终输出]**&#x200B;确认结果与付费媒体广告摘要中的ID匹配。 如果您的URL使用不同的布局，则不要保留`s_kwcid`分析分支。 如果URL只使用UTM参数，请忽略未使用的规则并相应地更新后续规则引用。

每个派生字段最多支持五个[URL解析规则](/help/data-views/derived-fields/derived-fields.md#url-parse)和一个[正则表达式替换规则](/help/data-views/derived-fields/derived-fields.md#regex-replace)。 每个派生字段保留一个ID。

### 创建付费登陆量度

使用`PM Campaign ID (Web)`作为输入创建名为`Paid Media Landings (Web)`的派生字段。

生成器将输入字段的规则扩展到新字段。 在这些规则之后，添加一个[Case When](/help/data-views/derived-fields/derived-fields.md#case-when)规则，该规则在设置了促销活动ID输出时返回自定义数值`1`，否则不返回任何值。 将结果作为指标添加。

此量度计算带有营销活动ID的事件。 此量度仅表示您的实施在登陆事件上发送该ID承载URL时的登陆，而不是在重复或不相关的事件上发送。

>[!NOTE]
>
>扩展的派生字段规则是副本。 如果更改ID字段，则还要检查并更新对应的登录和名称字段。 如果省略了解析规则，请引用实际的最终ID规则，而不是假设它是规则5。

### 添加可选的Web名称字段

要按名称报告，请在展开的Web ID规则之后创建以下派生字段，其中包含[查找规则](/help/data-views/derived-fields/derived-fields.md#lookup)：

| 派生字段 | 输入 | 查找数据集 | 匹配字段 | 返回字段 |
|---|---|---|---|---|
| PM促销活动名称(Web) | PM Campaign ID (Web)的最终输出 | 付费媒体营销活动查找 | `paidMedia.campaignID` | `paidMedia.metadata.name` |
| PM广告组名称(Web) | PM广告组ID (Web)的最终输出 | 付费媒体广告组查找 | `paidMedia.adGroupID` | `paidMedia.metadata.name` |
| PM广告名称(Web) | PM Ad ID (Web)的最终输出 | 付费媒体广告查找 | `paidMedia.adID` | `paidMedia.metadata.name` |

选择最终ID规则作为要应用查找的字段。 在将字段添加为维度之前，验证最终输出预览中的名称。 如果必填匹配字段不可用，请改用基于ID的报表。

名称作为文本进行匹配。 当不同的实体共享一个名称时，请使用ID维度。

### 添加Web组件并配置归因

将Web ID和网络派生的字段作为维度添加。 如果创建了可选名称字段，请添加这些字段。 将组件设置保留为其默认值，以便它们与您添加到其组中的摘要维度相匹配。

确认数据视图包含所需的Web组件：

| 组件 | 类型 | 架构字段 |
|---|---|---|
| 页面 URL | 维度 | `web.webPageDetails.URL` |
| 页面名称 | 维度 | `web.webPageDetails.name` |
| 反向链接URL | 维度 | `web.webReferrer.URL` |
| 事件类型 | 维度 | `eventType` |
| 产品 SKU | 维度 | `productListItems.SKU` |
| 产品名称 | 维度 | `productListItems.name` |
| Page Views | 量度 | `web.webPageDetails.pageViews.value` |
| 添加到购物车 | 量度 | `commerce.productListAdds.value` |
| 订单数 | 量度 | `commerce.purchases.value` |
| 收入 | 量度 | `commerce.order.priceTotal` |

将付费登陆次数派生字段添加为量度，然后配置单独的订单和收入量度：

1. 复制&#x200B;**[!UICONTROL 订单]**&#x200B;并命名副本`Orders (Web)`。 如果&#x200B;**[!UICONTROL 订单]**&#x200B;不存在，请直接添加`commerce.purchases.value`。
1. 复制&#x200B;**[!UICONTROL 收入]**&#x200B;并命名副本`Revenue (Web)`。 如果&#x200B;**[!UICONTROL 收入]**&#x200B;不存在，请直接添加`commerce.order.priceTotal`。
1. 将&#x200B;**[!UICONTROL 订单(Web)]**&#x200B;格式化为小数，小数位数为零，并将&#x200B;**[!UICONTROL 收入(Web)]**&#x200B;格式化为货币。
1. 对于这两个量度，请打开&#x200B;**[!UICONTROL 归因]**&#x200B;并启用&#x200B;**[!UICONTROL 覆盖默认归因]**。
1. 选择&#x200B;**[!UICONTROL 最近联系]**&#x200B;模型和&#x200B;**[!UICONTROL 会话]**&#x200B;容器。

保持原始&#x200B;**[!UICONTROL 订单]**&#x200B;和&#x200B;**[!UICONTROL 收入]**&#x200B;量度不变，以保留现有报表。 此设置需要明确启用覆盖，即使显示的默认值似乎匹配。

对于回访中的转化点数，请考虑&#x200B;**[!UICONTROL 人员]**&#x200B;容器和相应的回顾时间范围。 查看[摘要数据用例](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/data-views/summary-data)。

使用量度归因，而不是向Web ID维度添加持久性。 为避免夸大解释为登陆的计数，请勿将ID保留到以后的事件，因为这会更改哪些事件显示在促销活动行下。

### 创建摘要端连接维度

从Web联接的付费媒体广告摘要中添加单独的维度：

| 组件名称 | 架构字段 |
|---|---|
| 广告网络（已加入） | `paidMedia.adNetwork` |
| Campaign ID（网络） | `paidMedia.campaignID` |
| 广告组ID（网络） | `paidMedia.adGroupID` |
| 广告ID（网络） | `paidMedia.adID` |

请勿编辑或复制只读、模板管理的付费媒体组件。 根据架构字段创建上述单独的组件。

如果您创建了可选的Web名称字段，则还应创建以下摘要端查找派生字段：

| 组件名称 | 从广告摘要输入 | 查找数据集 | 匹配字段 | 返回字段 |
|---|---|---|---|---|
| 营销活动名称（已加入） | `paidMedia.campaignGUID` | 付费媒体营销活动查找 | `paidMedia.campaignGUID` | `paidMedia.metadata.name` |
| 广告组名称（已加入） | `paidMedia.adGroupGUID` | 付费媒体广告组查找 | `paidMedia.adGroupGUID` | `paidMedia.metadata.name` |
| 广告名称（已加入） | `paidMedia.adGUID` | 付费媒体广告查找 | `paidMedia.adGUID` | `paidMedia.metadata.name` |

使用摘要数据集中的GUID作为每个查询的输入。 直接从查找数据集获取的维度不满足摘要数据组中摘要维度的要求。

### 创建摘要数据组

在计划用于报表的Web维度上创建每个组。 添加相应的摘要维并在报告中隐藏添加的成员。

| Web维度：在此处创建组 | 摘要维：添加为隐藏成员 |
|---|---|
| PM网络(Web) | 广告网络（已加入） |
| PM Campaign ID (Web) | Campaign ID（网络） |
| PM广告组ID (Web) | 广告组ID（网络） |
| PM Ad ID (Web) | 广告ID（网络） |
| PM Campaign名称(Web)，可选 | 营销活动名称（已加入） |
| PM广告组名称(Web)，可选 | 广告组名称（已加入） |
| PM广告名称(Web)，可选 | 广告名称（已加入） |

对于每一行：

1. 选择Web维度。
1. 打开&#x200B;**[!UICONTROL 摘要数据组]**&#x200B;并启用&#x200B;**[!UICONTROL 创建分组]**。
1. 添加摘要维度。
1. 为添加的摘要成员启用&#x200B;**[!UICONTROL 隐藏报表]**。 保持Web维度可见。
1. 确认组件设置（包括小写、子字符串和包含/排除规则）在成员之间匹配。

每个组最多支持10个维度。 要包含另一个摘要数据集的量度，请将该数据集的等效摘要维度作为隐藏成员添加到同一组。

>[!IMPORTANT]
>
>使用Web维度作为报表维度，并在此维度上创建组。 反向排列可显示不带相应Web量度的摘要量度。

保存数据视图。

## 创建计算量度

在Workspace中，转到&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 计算量度]**，然后使用配置的数据视图创建以下量度：

| 名称 | 定义 | 格式 |
|---|---|---|
| 着陆率 | 付费媒体登陆(Web) /点击量\|广告摘要 | 百分比 |
| Web转化率 | 订单(Web)/付费媒体登陆(Web) | 百分比 |
| Web ROAS | 收入(Web)/支出\|广告摘要 | 小数，两位 |
| 每个Web订单的成本 | 支出\|广告摘要/订单(Web) | 货币 |
| 网络与Web转化差距 | 转化\|广告摘要 — 订单(Web) | 小数，零位 |

在解释比率量度之前，请查看零分母的行。 网络与Web的转化差距本身并不指示错误：这两种来源在归因、衡量和报告窗口方面可能有所不同。

## 构建并验证报告

1. 使用配置的数据视图创建Workspace项目。
1. 选择包含两个源数据的日期范围。 允许付费媒体摄取延迟；摘要数据可能会使网站事件滞后一天。
1. 添加包含&#x200B;**[!UICONTROL PM Campaign ID (Web)]**&#x200B;作为行维度的自由格式表，如果已配置名称组，则添加&#x200B;**[!UICONTROL PM Campaign Name (Web)]**。
1. 添加&#x200B;**[!UICONTROL 展示次数 |广告摘要]**，**[!UICONTROL 点击次数 |广告摘要]**，**[!UICONTROL 支出 |广告摘要]**，**[!UICONTROL 转化 |广告摘要]**，**[!UICONTROL 付费媒体登陆 |广告摘要]**、**[!UICONTROL 订单(Web)]**、**[!UICONTROL 收入(Web)]**&#x200B;和计算量度。
1. 按Web广告组和广告维度划分促销活动行。 确认摘要量度和Web量度均填充在每个配置的级别。
1. 使用&#x200B;**[!UICONTROL PM Network (Web)]**&#x200B;添加第二个表以查看网络级总计和无值行。

   ![付费媒体和Web数据工作区项目](./assets/paid-media-and-web-data-workspace.png)

   ![无数据的付费媒体和Web数据工作区项目](./assets/paid-media-and-web-data-workspace-no-value.png)

在共享报告之前，请检查以下各项：

* 登陆事件ID与付费媒体广告摘要ID相匹配。
* 付费媒体量度和Web量度会填充到相同的行中。
* 订单和收入会收到预期会话或人员归因。
* 理解无值行。 它们可以包含不匹配的摘要数据或没有付费媒体标识符的Web活动。
* 登陆至点击的差异与您的收藏集设置、同意处理和报告窗口相一致。 没有通用预期匹配率。

### 不匹配故障诊断

| 症状 | 检查并纠正操作 |
|---|---|
| 摘要量度会填充，但所有Web量度均为零 | 确认行使用Web维度，并且组是在这些维度上创建的。 然后，检查登陆URL以了解实际ID而不是名称。 |
| Web量度会填充，但摘要级别为空 | 确认级别的摘要维度位于相应的组中，并且所选日期存在匹配的付费媒体数据。 |
| Web行中缺少名称 | 检查最终输出预览中的查找输入和匹配字段。 如果名称扩充不可用，则使用ID组。 |
| Web ID包含文本或编码的宏 | 要求广告运营团队检查目标URL，并确认网络在登录之前扩展了宏。 |
| Google Ads ID不匹配 | 检查实际`s_kwcid`布局或UTM参数并更新分析规则。 |
| 网络值被拆分，如`facebook`和`meta` | 使网络派生字段输出与`paidMedia.adNetwork`完全匹配。 |
| ID会显示在单独的行中 | 确认设置是否在分组维度间匹配，并检查基础字符串值。 |
| 网站活动似乎发生了天变化 | 将数据视图时区与UTC摘要日期边界进行比较。 |
| 促销活动中的订单或收入为零或低于预期 | 明确启用量度归因覆盖，并确认其模型、容器和回顾设置。 |
| 付费登陆次数出乎意料地高 | 确认只有登陆事件包含计数营销活动参数。 重复的ID承载事件也有助于此量度。 |
| 不同的营销活动共享一个名称行 | 使用基于ID的报表来区分具有相同名称的实体。 |
