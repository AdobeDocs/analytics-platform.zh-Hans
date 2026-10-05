---
title: 在Customer Journey Analytics中摄取付费媒体数据
description: 了解如何通过Adobe Experience Platform源连接器摄取付费媒体数据，并在Customer Journey Analytics中准备连接、数据视图和量度。
solution: Customer Journey Analytics
feature: Use Cases
hold: true
role: Admin
source-git-commit: 4bb99471d256fe29dc54980a5da37cf2385b679f
workflow-type: tm+mt
source-wordcount: '1704'
ht-degree: 0%
---

# 摄取和使用付费媒体数据

付费媒体数据包括来自[!DNL Meta Ads]、[!DNL Google Ads]、[!DNL TikTok]和[!DNL LinkedIn]等平台的广告效果和元数据。 本指南介绍如何将该数据摄取到Adobe Experience Platform并在Customer Journey Analytics中将其用于报表和分析。

付费媒体数据通常经过三个阶段：

1. Advertising平台提供促销活动、广告、资源和性能数据。
1. Adobe Experience Platform通过源连接器摄取该数据，并将其存储在标准付费媒体数据集中。
1. Customer Journey Analytics通过连接和数据视图公开数据集，以便您可以在Workspace中分析数据。

付费媒体数据通过Experience Platform源连接器摄取。 例如，您可以在Advertising类别中使用[!DNL Meta Ads]连接器。 当您连接受支持的源时，Adobe会根据全局付费媒体架构和字段组设置标准付费媒体数据集。

## 先决条件

确保您在Experience Platform中具有以下访问权限：

* 查看和管理源的权限。
* 创建架构、数据集和数据流的权限。
* 选定要在其中工作的沙盒。 在继续设置步骤之前，您必须选择沙盒。

如果您使用[!DNL Meta Ads]作为源，请确保您还具有以下先决条件：

* [!DNL Meta Business Manager]帐户，至少具有一个包含营销活动、广告集、广告和资源的活动广告帐户。
* 在[!DNL Meta]开发人员控制台中配置并链接到[!DNL Business Manager]的[!DNL Graph API]和[!DNL Marketing API]授权的[!DNL Meta]应用程序。
* 已批准应用程序的`ads_read`和`ads_management`范围。
* 授权连接的用户的广告商级别或更高的访问权限。
* 已验证对[!DNL Meta]用户界面中目标广告帐户的访问权限。

对连接器的身份验证使用[!DNL OAuth 2.0]。 在安装过程中，您可以登录并授予对连接器的访问权限。 由于访问令牌已过期，因此，如果授权被撤销，请准备好重新授权连接。

## 付费媒体数据模型

[摘要度量数据集](#summary-metrics-datasets)充当事实表，查找数据集提供相关维度。 查找数据集按实体`GUID`和帐户、促销活动、广告组、广告、资源和体验的本机ID值联接到摘要指标数据集。

查找数据集共享两个常见的构建块：

* **实体ID对象**：存储帐户、广告、广告组、资产、营销活动和体验对象。 每个对象都包含Adobe生成的全局密钥和平台原生ID。
* **付费媒体核心元数据**：存储常用描述性字段，例如名称、状态、目标、优化目标、竞价策略、预算类型、预算值、货币、时区、服务状态、日期、广告网络、渠道、层次结构路径、网络和项目组合标识符。

下表总结了六个查找数据集。

| 查找数据集 | 关键内容 |
|---|---|
| 帐户查找 | 帐户级别的元数据，例如名称、货币、时区、状态、支出限制和创建日期 |
| 营销活动查找 | 预算、计划、定位、转化跟踪、归因、投放位置、提升的对象、目标和目录或存储ID的促销活动设置 |
| 广告组查找 | 广告组元数据，例如营销活动链接、状态、预算、优化目标和定位 |
| 广告查找 | 广告创意详细信息，例如资源、变体、维度、跟踪URL、call to action、正文文本、标题、目标URL、投放状态和审核状态 |
| 资产查找 | 资源属性，例如维度、文件详细信息、图像属性、媒体URL、使用情况元数据、视频元数据、描述、子类型、标题和类型 |
| 体验查找 | 体验级别的创意分组，例如体验ID、资源、标题、描述和call to action |

### 摘要量度数据集

付费媒体摘要量度数据集是中心摘要数据集。 摘要数据集中的每一行通常表示一天的一个实体，并包括用于报表的时间戳、标识符、事件类型、实体ID和非正规化名称。

每个摘要量度数据集可以包含以下量度组：

* **核心性能**：展示次数、点击次数、点进率、参与次数、参与率、转化率、转化率、转化值、潜在客户、链接点击次数、下载次数，以及应用程序安装或打开次数。
* **成本和预算**：每日支出、分配和剩余预算、步调、超支或缺支、平均成本指标和竞价金额。
* **视频**：视频查看次数、查看率里程碑和平均观看时间。
* **展示份额**：展示份额、最高展示份额和损失的展示份额量度。
* **转化详细信息**：转化类型、添加到购物车的操作、结账、致电、指示请求、潜在客户表单活动和其他与转化相关的事件。
* **社交参与**：赞、评论和关注。
* **归因和路径**：归因模型详细信息、置信度、权重、路径量度和渠道贡献。
* **质量和欺诈**：质量分数、欺诈指标、无效流量率和品牌安全量度。
* **维度细分**：数据可以按渠道、广告网络、设备类型、年龄组、性别、国家/地区、城市、语言、每周时间、受众类别、创意格式和其他维度进行细分，具体取决于源平台。

### 标准数据集

当您连接付费媒体源时，Adobe会根据全局付费媒体架构类和字段组设置12个标准付费媒体数据集。 这些数据集包括6个摘要指标数据集、6个查找数据集和支持数据集。 必须存在所有12个摘要和查找数据集，才能正确解析下游付费媒体数据。

#### 必需的数据集

* 付费媒体帐户摘要
* 付费媒体营销活动摘要
* 付费媒体广告组摘要
* 付费媒体广告摘要
* 付费媒体体验摘要
* 付费媒体资产摘要
* 付费媒体帐户查找
* 付费媒体营销活动查找
* 付费媒体广告组查找
* 付费媒体广告查找
* 付费媒体体验查找
* 付费媒体资产查找

#### 支持的数据集

例如

* 付费媒体广告人口统计查找
* 付费媒体体验置入摘要
* 付费媒体广告地理摘要
* 付费媒体广告摘要（摘要量度）
* 付费媒体资产人口统计摘要

## 在Adobe Experience Platform中摄取付费媒体数据

使用以下流程连接源并将付费媒体数据摄取到Experience Platform：

1. 确认您具有所需的Experience Platform源权限和ad-platform访问权限。
1. 在Experience Platform中，转到&#x200B;**[!UICONTROL 源]** > **[!UICONTROL 目录]** > **[!UICONTROL Advertising]**。
1. 确保您位于包含付费媒体数据集的沙盒中。
1. 选择要使用的连接器，如&#x200B;**[!DNL Meta Ads]**。 选择&#x200B;**[!UICONTROL 设置]**&#x200B;以创建新连接，或选择&#x200B;**[!UICONTROL 添加数据]**&#x200B;以将更多数据添加到现有连接。
1. 通过登录具有所需广告商级别访问权限的用户，向[!DNL OAuth 2.0]进行身份验证。
1. 选择要提取的广告帐户、实体和insight数据。
1. 验证查找数据集和摘要量度数据集是否已正确配置。
1. 输入数据流设置，确认目标数据集，并配置摄取计划。
1. 保存数据流并监视&#x200B;**[!UICONTROL 源]** > **[!UICONTROL 数据流]**&#x200B;中的运行。
1. 验证标准付费媒体数据集是否存在并包含数据。

在迁移到Customer Journey Analytics之前，请验证摄取的数据：

* 确认实体`GUID`和本机ID值在摘要量度和查找数据集中填充一致。
* 确认每个概要量度行都包含一个时间戳。
* 确认关键报表字段，例如维度（例如： `channel`， `adNetwork`）和量度（例如： `impressions`， `clicks`， `spend`）包含值。 请注意，某些字段（如`region`）可能并非由所有源平台填充。
* 确认相关帐户中的货币和时区值一致。

## 将付费媒体数据引入Customer Journey Analytics

Customer Journey Analytics不会直接报告Experience Platform数据集。 实际上，您需要通过连接公开数据集，然后构建一个数据视图，该视图定义报告中使用的维度、量度和逻辑。

### 创建或更新连接

请使用以下流程创建或更新连接：

1. 在Customer Journey Analytics中，[创建或编辑现有连接](/help/connections/create-connection.md)。
1. 确保选择包含付费媒体数据集的沙盒作为连接配置的一部分。
1. 将摘要量度数据集添加为摘要数据。 如果有多个摘要度量数据集可用，请使用[搜索](/help/connections/create-connection.md#add-datasets)按`Paid Media`类进行筛选，以识别正确的数据集。
1. 将每个查询数据集添加为查询数据集。 使用帐户、促销活动、广告组、广告、资源和体验的相应实体GUID标识符（Adobe生成的全局键），将查找数据集与摘要数据联接。 某些源平台可能还支持对本机ID值进行联接。
1. 如果要将聚合的付费媒体数据与共享元数据（如ID、跟踪代码或`UTM`参数）相关联，则可以选择添加点击流事件数据。
1. 查看每个数据集的[数据集特定的设置](/help/connections/create-connection.md#dataset-settings)。
1. 保存连接并确认连接开始回填数据。

付费媒体数据是聚合数据，不依赖于人员级别的身份拼接。 摘要表中的实体标识符用于连接查找表中的类似标识。

### 创建数据视图

连接就绪后，您需要为连接创建或编辑一个或多个数据视图：


1. 在Customer Journey Analytics中，[创建或编辑一个或多个数据视图](/help/data-views/create-dataview.md)：
1. 定义时区和货币等默认设置。
1. 添加付费媒体分析所需的组件。

包括以下组件：

* **维度**：营销活动、渠道、广告网络、广告组、广告、资产、帐户、区域和设备类型。
* **量度**：展示次数、点击次数、点进率、支出、转化、转化值、参与次数以及相关的视频或展示共享量度。
* **派生字段**：使用[解析](/help/data-views/derived-fields/derived-fields.md#url-parse)、[正则表达式](/help/data-views/derived-fields/derived-fields.md#regex-replace)或[查找](/help/data-views/derived-fields/derived-fields.md#lookup)逻辑对维度进行标准化或分类，以便在广告网络中生成一致的渠道和促销活动值。
* **摘要分组**：[将来自多个数据集的相关值合并到一个报告维度中](/help/data-views/component-settings/summary-data-group.md)，如统一的付费渠道维度。
* **计算指标**：定义可重用的效率指标，如CPC、CPM、CPA、CTR和转化率。

## 验证

使用以下核对清单验证实施。

### Adobe Experience Platform检查

* 确认源权限和ad-platform访问权限已设置。
* 确认连接器已通过身份验证，并且数据流按计划运行。
* 确认存在并填充所有12个标准数据集。
* 确认架构使用全局付费媒体类和字段组。
* 确认已填充联接键、时间戳和关键报表字段。

### Customer Journey Analytics检查

* 确认连接中包含摘要量度数据集和六个查找数据集。
* 确认数据视图包含所需的广告维度和付费媒体量度。
* 确认派生字段会按预期标准化渠道和营销活动值。
* 确认摘要分组可根据需要合并多网络数据。
* 确认为您的组织使用的比率定义了计算指标。
* 确认Workspace报表与源广告平台报表一致。


>[!MORELIKETHIS]
>
>[Meta Ads源连接器](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/advertising/meta-ads)
>
