---
title: 了解升级到 Customer Journey Analytics 时对 Adobe Analytics 功能的支持
description: 了解升级到 Customer Journey Analytics 时对 Adobe Analytics 功能的支持
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 92053109-f80d-47ab-b011-c28a5411149c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '464'
ht-degree: 100%

---

# 了解升级到 Customer Journey Analytics 时对 Adobe Analytics 功能的支持 {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-migrate-projects"
>title="组件和项目"
>abstract="Adobe Analytics 的组件包括：项目（及其相关的自由格式表和可视化图表）、区段和计算量度。"

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
>title="尚不支持 Activity Map 叠加"
>abstract="Customer Journey Analytics 尚不支持 Activity Map 叠加。预计将在未来推出。"

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
>title="数据源"
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
>abstract="Adobe Analytics 和 Customer Journey Analytics 的附加组件，专门用于音频、视频或流式处理内容等媒体数据收集。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-component-migration"
>title="迁移项目和组件"
>abstract="将 Adobe Analytics 项目及其相关组件引入 Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

以下列表仅显示在升级到 Customer Journey Analytics 过程中需要考虑的 Adobe Analytics 功能。有关显示哪些 Adobe Analytics 功能在 Customer Journey Analytics 中完全受支持、部分受支持或不受支持的完整列表，请参阅 [Customer Journey Analytics 功能支持](/help/getting-started/aa-vs-cja/cja-aa.md)。

请考虑在升级到 Customer Journey Analytics 时要继续使用以下哪些 Adobe Analytics 功能：

| Adobe Analytics 功能 |  Customer Journey Analytics 中的相应功能 |
|---------|----------|
| [Adobe Analytics 中的组件和项目](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [将项目及其相关组件迁移至 Customer Journey Analytics ](https://experienceleague.adobe.com/zh-hans/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)。 |
| [Activity Map 叠加和链接跟踪](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/activity-map/overview) | 尚不可用 |
| [分类数据](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/classifications/c-classifications) | 查找数据集是 Customer Journey Analytics 中对数据进行分类的方法。<p>[为包含分类数据的每个维度创建一个查找数据集。](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)</p> |
| [营销渠道](https://experienceleague.adobe.com/zh-hans/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | 派生字段在数据视图中创建。 <p>[创建营销渠道派生字段。](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)</p> |
| [数据源](https://experienceleague.adobe.com/zh-hans/docs/analytics/export/analytics-data-feed/data-feed-overview) | Experience Platform 和 Customer Journey Analytics 提供了许多功能，这些功能可以独立地或以组合方式解决各种导出需求。这些功能包括 [Experience Platform 数据访问 API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html)、[Experience Platform 目标](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html)、[Customer Journey Analytics 全表导出](/help/analysis-workspace/export/export-cloud.md)和 [BI 工具集成](/help/data-views/bi-extension.md)。<p>有关导出选项的更多信息，请参阅[数据导出用例](/help/use-cases/data-export/overview.md)。</p> |
| [Data Warehouse](https://experienceleague.adobe.com/zh-hans/docs/analytics/export/data-warehouse/data-warehouse) | [Customer Journey Analytics 完整表格导出](/help/analysis-workspace/export/export-cloud.md)从 Adobe Analytics 中的 Data Warehouse 报告演化而来，具有许多当今在 Data Warehouse 中不提供但经常有人要求提供的新功能。 |
| [流媒体数据](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-overview) | 使用作为工作区中的“同时观看媒体的人数”面板和“媒体播放耗时”面板一部分的 Analytics Source Connector 即可获取流媒体数据。 |
