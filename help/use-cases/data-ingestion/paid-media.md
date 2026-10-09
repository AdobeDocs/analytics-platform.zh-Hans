---
title: 在Customer Journey Analytics中摄取付费媒体数据
description: 了解如何通过Adobe Experience Platform源连接器摄取付费媒体数据，并在Customer Journey Analytics中准备连接、数据视图和量度。
solution: Customer Journey Analytics
feature: Use Cases
hold: true
role: Admin
source-git-commit: 29a21d57b6b50d873a4464d1a705c1b4855dd3ea
workflow-type: tm+mt
source-wordcount: '1198'
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
* 选定要在其中工作的沙盒。 选择沙盒，然后再继续设置步骤。

如果您使用[!DNL Meta Ads]作为源，请确保您还具有以下先决条件：

* [!DNL Meta Business Manager]帐户，至少具有一个包含营销活动、广告集、广告和资源的活动广告帐户。
* 在[!DNL Meta]开发人员控制台中配置并链接到[!DNL Business Manager]的[!DNL Graph API]和[!DNL Marketing API]授权的[!DNL Meta]应用程序。
* 已批准应用程序的`ads_read`和`ads_management`范围。
* 授权连接的用户的广告商级别或更高的访问权限。
* 已验证对[!DNL Meta]用户界面中目标广告帐户的访问权限。

对连接器的身份验证使用[!DNL OAuth 2.0]。 在安装过程中，您可以登录并授予对连接器的访问权限。 由于访问令牌已过期，因此，如果授权被撤销，请准备好重新授权连接。

## 数据模型

[Content Analytics付费媒体自动配置](/help/content-analytics/config/paid-media.md)详细说明了付费媒体数据模型。 该自动配置通常会创建和配置所需的数据集和组件，并专门用于分析内容。

要了解付费媒体数据模型，请参阅此文档。 使用它可决定要在Customer Journey Analytics中使用哪些数据集。 配置的源连接器会生成这些数据集。

## 摄取付费媒体数据

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
* 确认关键报表字段，例如维度（例如： `channel`， `adNetwork`）和量度（例如： `impressions`， `clicks`， `spend`）包含值。 请注意，并非所有源平台都会填充某些字段，如`region`。
* 确认相关帐户中的货币和时区值一致。

## 使用付费媒体数据

Customer Journey Analytics不会直接报告Experience Platform数据集。 实际上，您需要通过连接公开数据集，然后构建一个数据视图，该视图定义报告中使用的维度、量度和逻辑。

### 创建或更新连接

请使用以下流程创建或更新连接：

1. 在Customer Journey Analytics中，[创建或编辑现有连接](/help/connections/create-connection.md)。
1. 确保选择包含付费媒体数据集的沙盒作为连接配置的一部分。
1. 将摘要量度数据集添加为摘要数据。 如果有多个摘要度量数据集可用，请使用[搜索](/help/connections/create-connection.md#add-datasets)按`Paid Media`类进行筛选，以识别正确的数据集。
1. 将每个查询数据集添加为查询数据集。 使用帐户、促销活动、广告组、广告、资源和体验的相应实体GUID标识符（Adobe生成的全局键），将查找数据集与摘要数据联接。 某些源平台还支持对本机ID值进行连接。
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

### 创建项目

要报告和分析付费媒体数据，请在Analysis Workspace中创建项目。

## 验证

使用以下核对清单验证实施。

### Adobe Experience Platform检查

* 确认源权限和ad-platform访问权限已设置。
* 确认连接器已通过身份验证，并且数据流按计划运行。
* 确认所有付费媒体数据集都存在且已填充。
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
>[Meta Ads源连接器](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/connectors/advertising/meta-ads)
>[Content Analytics付费媒体自动配置](/help/content-analytics/config/paid-media.md)
