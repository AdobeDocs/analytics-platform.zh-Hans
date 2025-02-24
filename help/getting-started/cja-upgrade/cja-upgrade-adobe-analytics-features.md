---
title: 了解升级到 Customer Journey Analytics 时对 Adobe Analytics 功能的支持
description: 了解升级到Customer Journey Analytics时支持的Adobe Analytics功能
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 92053109-f80d-47ab-b011-c28a5411149c
source-git-commit: 5e80e68c6b5d3dca19dae21c6719b040b28afaf9
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 55%

---

# 了解升级到 Customer Journey Analytics 时对 Adobe Analytics 功能的支持 {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-migrate-projects"
>title="组件和项目"
>abstract="Adobe Analytics 的组件包括：项目（及其相关的自由格式表和可视化）、区段和计算量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map"
>title="Activity Map 叠加和链接跟踪"
>abstract="浏览器扩展，可让您在网站上以叠加方式查看链接跟踪数据。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map-support"
>title="尚不支持活动图叠加"
>abstract="Customer Journey Analytics中尚不支持Activity Map叠加。 计划将来提供。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-classification"
>title="分类数据"
>abstract="以单独维度对数据进行分组或分类。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channels"
>title="营销渠道"
>abstract="创建规则，对客户到达网站的方式进行分类。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds"
>title="数据馈送"
>abstract="从 Adobe Analytics 导出原始数据，供外部工具和流程使用。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-warehouse"
>title="Data Warehouse"
>abstract="以电子表格格式从 Adobe Analytics 导出经过处理的数据。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-streaming-media"
>title="流媒体数据"
>abstract="Adobe Analytics 的附加组件，专门用于音频、视频或流式处理内容等媒体数据收集。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-component-migration"
>title="迁移项目和组件"
>abstract="将Adobe Analytics项目及其关联的组件引入Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>在回答[Customer Journey Analytics升级核对清单](https://gigazelle.github.io/cja-ttv/)中的问题时，使用此页上的信息。

以下列表仅显示升级到Customer Journey Analytics的过程中需要考虑的Adobe Analytics功能。 有关显示Customer Journey Analytics完全支持、部分支持或不支持哪些Adobe Analytics功能的完整列表，请参阅[Customer Journey Analytics功能支持](/help/getting-started/aa-vs-cja/cja-aa.md)。

在升级到Customer Journey Analytics时，请考虑要继续使用的以下Adobe Analytics功能中的哪项：

| Adobe Analytics功能 | Customer Journey Analytics中的相应功能 |
|---------|----------|
| 来自Adobe Analytics的[组件和项目](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [将项目及其相关组件迁移到Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)。 |
| [Activity Map叠加图和链接跟踪](https://experienceleague.adobe.com/en/docs/analytics/analyze/activity-map/overview) | 尚不可用 |
| [分类数据](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/c-classifications) | 查找数据集是在Customer Journey Analytics中对数据进行分类的方法。<p>[为每个包含分类数据的维度创建一个查找数据集。](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)</p> |
| [营销渠道](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | 派生字段在数据视图中创建。 <p>[创建营销渠道派生的字段。](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)</p> |
| [数据馈送](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) | 数据集的第一代数据导出可通过[ Experience Platform 数据访问 API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html)以及[ Experience Platform 目标](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html)实现。这些选项提供了事件/行级别的导出，可将收集或摄入的所有数据导出到 Experience Platform 数据湖中。后处理数据列不可用，因为后处理列是在查询时计算的。可通过报告导出帖子列。 |
| [Data Warehouse](https://experienceleague.adobe.com/en/docs/analytics/export/data-warehouse/data-warehouse) | [Customer Journey Analytics 全表导出](/help/analysis-workspace/export/export-cloud.md)从 Adobe Analytics 中的 Data Warehouse 报告演化而来，具有许多当今在 Data Warehouse 中不提供但经常有人要求提供的新功能。 |
| [流媒体数据](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-overview) | 使用作为 Workspace 中的“同时观看媒体的人数”面板和“媒体播放耗时”面板一部分的 Analytics Source Connector 即可获取流媒体数据。 |
