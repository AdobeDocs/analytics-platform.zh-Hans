---
git-repo: https://github.com/AdobeDocs/analytics-platform.zh-Hans
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Customer Journey Analytics 指南
user-guide-description: 了解 Adobe Customer Journey Analytics 以及如何将 Analysis Workspace 与来自 Experience Platform 的数据配合使用。
breadcrumb-title: Customer Journey Analytics 指南
source-git-commit: aaf23560b69c90fdbaee3fa401b5fe58e6a4e5d1
workflow-type: ht
source-wordcount: '938'
ht-degree: 100%

---

# Adobe Customer Journey Analytics 指南 {#using}

+ [Adobe Customer Journey Analytics 指南](../getting-started/cja-landing.md)
+ [Adobe Customer Journey Analytics 的 AI 助手](../ai-assistant.md)

+ 发行说明 {#releases}
   + [最新版本](../release-notes/latest.md)
   + [2024 版](../release-notes/2024.md)
   + [2023 版](../release-notes/2023.md)
   + [2022 版](../release-notes/2022.md)
   + [2021 版](../release-notes/2021.md)
   + [2020 版](../release-notes/2020.md)
   + [功能发布策略](../release-notes/releases.md)
   + [文档更新](../release-notes/doc-changes.md)

+ 快速入门 {#cja-overview}
   + [Customer Journey Analytics 概述](../getting-started/cja-overview.md)
   + [快速入门指南](../getting-started/cja-getting-started.md)
   + [登陆页面](../getting-started/landing.md)
   + [登陆页面（旧的）](../getting-started/cja-landing-old.md)
   + [常见问题解答](../getting-started/cja-faq.md)
   + [比较 Customer Journey Analytics 和 BI 解决方案](../getting-started/cja-vs-bi.md)

+ Customer Journey Analytics 和 Adobe Analytics {#compare-aa-cja}
   + 升级到 Customer Journey Analytics {#upgrade-to-cja}
      + [快速入门](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)
      + [选择您的升级路径](/help/getting-started/cja-upgrade/cja-upgrade-path.md)
      + [向平台发送数据](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)
      + [保留历史数据](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)
   + 与 Adobe Analytics 进行比较 {#cja-aa-comparison}
      + [概述](../getting-started/aa-vs-cja/overview.md)
      + [实用 Adobe Analytics 数据 ](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [功能支持](../getting-started/aa-vs-cja/cja-aa.md)
      + [比较术语](../getting-started/aa-vs-cja/terminology.md)
      + [比较数据处理](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [环境](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [分析处理与数据准备](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [Analytics 标识](../getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [Adobe Analytics 的演变](../getting-started/aa-to-cja.md)
   + [适用于 Adobe Analytics 用户的用户指南](../getting-started/aa-to-cja-user.md)

+ 数据引入 {#cja-data-ingestion}
   + [数据摄取概述](../data-ingestion/data-ingestion.md)
   + 摄取并使用快速入门指南{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Experience Platform Edge Network {#edge-network}
         + [Web SDK](../data-ingestion/aepwebsdk.md)
         + [Mobile SDK](../data-ingestion/aepmobilesdk.md)
         + [服务器 API](../data-ingestion/serverapi.md)
      + [批次数据](../data-ingestion/batch.md)
      + [流式数据](../data-ingestion/streaming.md)
      + [源连接器](../data-ingestion/sources.md)

+ 连接 {#cja-connections}
   + [连接概述](../connections/overview.md)
   + [创建或编辑连接](../connections/create-connection.md)
   + [管理连接](../connections/manage-connections.md)
   + [合并事件数据集](../connections/combined-dataset.md)
   + [标准查找](../connections/standard-lookups.md)
   + [查找 B2B](../connections/transform-datasets-b2b-lookups.md)

+ 数据视图 {#cja-dataviews}
   + [数据视图概述](../data-views/data-views.md)
   + [创建或编辑数据视图](../data-views/create-dataview.md)
   + [会话设置](../data-views/session-settings.md)
   + 组件设置 {#component-settings}
      + [组件设置概述](../data-views/component-settings/overview.md)
      + [归因](../data-views/component-settings/attribution.md)
      + [行为](../data-views/component-settings/behavior.md)
      + [格式](../data-views/component-settings/format.md)
      + [包括/排除值](../data-views/component-settings/include-exclude-values.md)
      + [量度去重](../data-views/component-settings/metric-deduplication.md)
      + [无值选项](../data-views/component-settings/no-value-options.md)
      + [持久性](../data-views/component-settings/persistence.md)
      + [子字符串](../data-views/component-settings/substring.md)
      + [摘要数据组](../data-views/component-settings/summary-data-group.md)
      + [值分段](../data-views/component-settings/value-bucketing.md)
   + [标准组件参考](../data-views/component-reference.md)
   + [BI 扩展](../data-views/bi-extension.md)
   + [派生字段](../data-views/derived-fields/derived-fields.md)
   + [摘要数据](../data-views/summary-data.md)
   + [标签和政策](../data-views/data-governance.md)

+ 工具 {#tools}
   + 资产转移 {#asset-transfer}
      + [转移资产](../tools/asset-transfer/transfer-assets.md)
   + 产品使用情况 {#product-usage}
      + [概述](../tools/product-usage/usage-overview.md)
      + [数据设置](../tools/product-usage/data-settings.md)
      + [“选择禁用”设置](../tools/product-usage/opt-out-settings.md)

+ Workspace 项目 {#cja-workspace}
   + [Analysis Workspace 概述](../analysis-workspace/home.md)
   + [执行基本分析](../analysis-workspace/perform-basic-analysis.md)
   + [执行高级分析](../analysis-workspace/perform-adv-analysis.md)
   + 项目 {#build-workspace-project}
      + [概述](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [创建项目](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [打开项目](/help/analysis-workspace/build-workspace-project/open-projects.md)
      + [保存项目](../analysis-workspace/build-workspace-project/save-projects.md)
      + Workspace 中的文件夹 {#workspace-folders}
         + [关于文件夹](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [创建文件夹和子文件夹](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [管理文件夹](../analysis-workspace/build-workspace-project/workspace-folders/manage-folders.md)
         + [将项目添加或移动到文件夹](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
      + [热键（快捷方式）](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [调色板](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [视图密度](../analysis-workspace/build-workspace-project/view-density.md)
   + 可视化内容 {#visualizations}
      + [概述](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [管理数据源](../analysis-workspace/visualizations/t-sync-visualization.md)
      + [智能题注](../analysis-workspace/visualizations/intelligent-captions.md)
      + 自由格式表 {#freeform-table}
         + [概述](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + [创建超链接](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)
         + 列和行设置 {#column-row-settings}
            + [列设置](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [行设置](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [动态项和静态项](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [排序和过滤表格](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [Workspace 总计](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + 同类群组表 {#cohort-table}
         + [概述](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [配置](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [用例](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + 流失 {#fallout}
         + [概述](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [配置](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [维度间流失](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [应用过滤器](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + 流量 {#flow}
         + [概述](../analysis-workspace/visualizations/c-flow/flow.md)
         + [配置](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [维度间流量](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + 历程画布 {#journey-canvas}
         + [概述](../analysis-workspace/visualizations/journey-canvas/journey-canvas.md)
         + [配置](../analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)
         + [疑难解答 ](../analysis-workspace/visualizations/journey-canvas/journey-canvas-troubleshooting.md)
      + [面积（堆叠）](../analysis-workspace/visualizations/area.md)
      + [条形图（堆叠）](../analysis-workspace/visualizations/bar.md)
      + [项目符号](../analysis-workspace/visualizations/bullet-graph.md)
      + [组合](../analysis-workspace/visualizations/combo-charts.md)
      + [圆环图](../analysis-workspace/visualizations/donut.md)
      + [直方图](../analysis-workspace/visualizations/histogram.md)
      + [水平条形图（堆叠）](../analysis-workspace/visualizations/horizontal-bar.md)
      + [关键量度摘要](../analysis-workspace/visualizations/key-metric.md)
      + [线形图](../analysis-workspace/visualizations/line.md)
      + [散点图](../analysis-workspace/visualizations/scatterplot.md)
      + [摘要数字和变化](../analysis-workspace/visualizations/summary-number-change.md)
      + [节头](/help/analysis-workspace/visualizations/section-header.md)
      + [文本](../analysis-workspace/visualizations/text.md)
      + [树形图](../analysis-workspace/visualizations/treemap.md)
      + [维恩图](../analysis-workspace/visualizations/venn.md)
   + 面板 {#panels}
      + [概述](../analysis-workspace/c-panels/panels.md)
      + [空白面板](../analysis-workspace/c-panels/blank-panel.md)
      + [归因](../analysis-workspace/c-panels/attribution.md)
      + [试验](../analysis-workspace/c-panels/experimentation.md)
      + [自由格式表](../analysis-workspace/c-panels/freeform-panel.md)
      + [媒体受众平均逗留分钟数](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)
      + [媒体并行查看者](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [媒体播放耗时](../analysis-workspace/c-panels/media-playback-time-spent.md)
      + [下一项或上一项](../analysis-workspace/c-panels/next-previous.md)
      + [快速洞察](../analysis-workspace/c-panels/quickinsight.md)
   + 策划、共享和计划项目 {#curate-share}
      + [概述](../analysis-workspace/curate-share/send-schedule-files.md)
      + [策划项目](../analysis-workspace/curate-share/curate.md)
      + [共享项目](../analysis-workspace/curate-share/share-projects.md)
      + [创建可共享链接](../analysis-workspace/curate-share/shareable-links.md)
      + [仅供查看的项目](../analysis-workspace/curate-share/view-only-projects.md)
   + 导出 {#export}
      + [概述](../analysis-workspace/export/export-project-overview.md)
      + [下载](../analysis-workspace/export/download-send.md)
      + [发送给其他人](../analysis-workspace/export/t-schedule-report.md)
      + [导出到云](../analysis-workspace/export/export-cloud.md)
   + 异常检测 {#anomaly-detection}
      + [概述](../analysis-workspace/c-anomaly-detection/anomaly-detection.md)
      + [查看异常](../analysis-workspace/c-anomaly-detection/view-anomalies.md)
      + [统计技术](../analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)
   + 预测 {#forecasting}
      + [概述](../analysis-workspace/c-forecast/forecasting.md)
      + [查看预测](../analysis-workspace/c-forecast/view-forecasts.md)
      + [统计技术](../analysis-workspace/c-forecast/statistics-forecasting.md)
   + [目录](../analysis-workspace/build-workspace-project/project-table-of-contents.md)
   + [用户偏好设置](../analysis-workspace/user-preferences.md)
   + Workspace 常见问题解答及更多信息 {#workspace-faq}
      + [常见问题解答](../analysis-workspace/workspace-faq/faq.md)
      + [错误消息](../analysis-workspace/workspace-faq/error-messages.md)
      + [限制](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [管理要求](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [辅助功能](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ Analytics 功能板 {#cja-dashboards}
   + [概述](../mobile-app/home.md)
   + [策划人任务](../mobile-app/curator.md)
   + [创建移动记分卡](../mobile-app/create-scorecard.md)
   + [管理移动记分卡](../mobile-app/manage-scorecard.md)
   + [设置执行用户以使用功能板](../mobile-app/set-up-execs.md)
   + [执行用户快速入门指南](../mobile-app/executive.md)

+ 引导式分析 {#guided-analysis}
   + [概述](../guided-analysis/overview.md)
   + [积极增长](../guided-analysis/types/active-growth.md)
   + [转化趋势](../guided-analysis/types/conversion-trends.md)
   + [参与](../guided-analysis/types/engagement.md)
   + [首次使用影响](../guided-analysis/types/first-use-impact.md)
   + [频率](../guided-analysis/types/frequency.md)
   + [漏斗](../guided-analysis/types/funnel.md)
   + [净增长](../guided-analysis/types/net-growth.md)
   + [发布影响](../guided-analysis/types/release-impact.md)
   + [维系](../guided-analysis/types/retention.md)
   + [时间表](../guided-analysis/types/timeline.md)
   + [趋势](../guided-analysis/types/trends.md)
   + [行业用例](../guided-analysis/industry-use-cases.md)
   + [常见问题解答](../guided-analysis/faq.md)

+ 组件 {#cja-components}
   + [概述](../components/overview.md)
   + [使用 Analysis Workspace 中的组件](../components/use-components-in-workspace.md)
   + [添加组件描述](../components/add-component-descriptions.md)
   + 注释 {#annotations}
      + [注释概述](../components/annotations/overview.md)
      + [创建注释](../components/annotations/create-annotations.md)
      + [管理注释](../components/annotations/manage-annotations.md)
      + [查看注释](../components/annotations/view-annotations.md)
      + [移动注释](../components/annotations/mobile-annotations.md)
   + [计划的项目](../components/scheduled-projects-manager.md)
   + 受众{#audiences}
      + [受众概述](../components/audiences/audiences-overview.md)
      + [创建并发布受众](../components/audiences/publish.md)
      + [管理受众](../components/audiences/manage.md)
   + 维度 {#dimensions}
      + [维度概述](../components/dimensions/overview.md)
      + [预览维度](../components/dimensions/view-dimensions.md)
      + [划分维度](../components/dimensions/t-breakdown-fa.md)
      + [时间划分维度](../components/dimensions/time-parting-dimensions.md)
      + [高基数维度](../components/dimensions/high-cardinality.md)
   + [量度](../components/apply-create-metrics.md)
   + 过滤器 {#cja-filters}
      + [概述](../components/filters/filters-overview.md)
      + [创建过滤器](../components/filters/create-filters.md)
      + [构建过滤器](../components/filters/filter-builder.md)
      + [快速过滤器](../components/filters/quick-filters.md)
      + [顺序过滤器](../components/filters/seg-sequential-build.md)
      + [共享过滤器](../components/filters/filters-share.md)
      + [标记过滤器](../components/filters/filters-tag.md)
      + [过滤过滤器列表](../components/filters/filters-filter.md)
      + [将过滤器标记为收藏](../components/filters/filters-favorite.md)
      + [批准过滤器](../components/filters/filters-approve.md)
      + [复制过滤器](../components/filters/filters-copy.md)
      + [管理过滤器](../components/filters/manage-filters.md)
      + [运算符](../components/filters/operators.md)
   + 计算量度 {#cja-calcmetrics}
      + [概述](../components/calc-metrics/calc-metr-overview.md)
      + 计算量度工作流 {#cm-workflow}
         + [创建计算量度](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [生成计算量度](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [查找量度](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [量度类型和归因](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [生成参与率量度](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [过滤量度](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [堆叠和替换过滤器](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [筛选计算量度](../components/calc-metrics/cm-workflow/cm-filter.md)
         + [将计算量度标记为收藏内容](../components/calc-metrics/cm-workflow/cm-favorite.md)
         + [复制计算量度](../components/calc-metrics/cm-workflow/cm-copy.md)
         + [使用函数](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [标记计算量度](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [批准计算量度](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [共享计算量度](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [管理计算量度](../components/calc-metrics/cm-workflow/cm-manager.md)
         + [示例](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
      + [计算量度模板](../components/calc-metrics/default-calcmetrics.md)
      + [基本功能](../components/calc-metrics/cm-functions.md)
      + [高级功能](../components/calc-metrics/cm-adv-functions.md)
   + 日期范围 {#cja-date-ranges}
      + [概述](../components/date-ranges/overview.md)
      + [创建日期范围](../components/date-ranges/create.md)
      + [管理日期范围](../components/date-ranges/manage.md)
      + [日期比较](../components/date-ranges/time-comparison.md)
      + [示例](../components/date-ranges/custom-date-ranges.md)
   + 警报 {#alerts}
      + [概述](/help/components/c-intelligent-alerts/intelligent-alerts.md)
      + [创建警报](/help/components/c-intelligent-alerts/alert-builder.md)
      + [管理警报](/help/components/c-intelligent-alerts/alert-manager.md)
      + [功能比较 ](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)
      + [用例](/help/components/c-intelligent-alerts/alerts-use-cases.md)
   + 导出 {#exports}
      + [配置云导出帐户](/help/components/exports/cloud-export-accounts.md)
      + [配置云导出位置](/help/components/exports/cloud-export-locations.md)
      + [管理云导出位置](/help/components/exports/manage-export-locations.md)
      + [管理导出](/help/components/exports/manage-exports.md)
      + [管理导出日志](/help/components/exports/manage-export-logs.md)
      + [导出故障诊断](/help/components/exports/troubleshoot-exports.md)
   + 数据词典 {#data-dictionary}
      + [概述](../components/data-dictionary/data-dictionary-overview.md)
      + [查看数据词典中的组件信息](../components/data-dictionary/view-data-dictionary.md)
      + [编辑数据词典中的组件条目](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [监测数据词典健康状况](../components/data-dictionary/monitor-data-dictionary-health.md)

+ Report Builder {#cja-reportbuilder}
   + [概述](../report-builder/report-buider-overview.md)
   + [Report Builder 设置](../report-builder/report-builder-setup.md)
   + [创建数据块](../report-builder/create-a-data-block.md)
   + [Report Builder 中心](../report-builder/report-builder-hub.md)
   + [选择数据视图](../report-builder/select-data-view.md)
   + [选择日期范围](../report-builder/select-date-range.md)
   + [使用过滤器](../report-builder/work-with-filters.md)
   + [筛选维度](../report-builder/filter-dimensions.md)
   + [管理数据块](../report-builder/manage-reportbuilder.md)
   + [计划工作簿](../report-builder/schedule-reportbuilder.md)
   + [限制标签](../report-builder/restricted-labels.md)
   + [Report Builder 设置](../report-builder/report-builder-settings.md)

+ 报告活动管理器 {#reporting-activity-manager}
   + [概述](../reporting-activity-manager/reporting-activity-overview.md)
   + [查看报告活动](../reporting-activity-manager/reporting-activity.md)
   + [取消报告请求](../reporting-activity-manager/reporting-activity-cancel-requests.md)

+ 拼合 {#stitching}
   + [概述](../stitching/overview.md)
   + [创建和管理拼合数据集](../stitching/stitching-ui.md)
   + [常见问题解答](../stitching/faq.md)

+ Adobe 集成 {#integrations}
   + [概述](/help/integrations/overview.md)
   + [集成 Adobe Analytics](/help/integrations/aa.md)
   + [集成 Target](/help/integrations/at.md)
   + [集成 Journey Optimizer 数据](/help/integrations/ajo.md)
   + [集成决策管理数据](/help/integrations/ajo-od.md)
   + [集成 Customer AI](/help/integrations/customer-ai.md)

+ 数据管理 {#cja-privacy}
   + [数据管理](../privacy/privacy-overview.md)
   + [审核日志](../privacy/audit-log.md)
   + [客户管理的密钥](../privacy/cmk.md)

+ 用例 {#cja-usecases}
   + [Customer Journey Analytics 用例](../use-cases/cja-usecases.md)
   + Google Analytics 数据{#ga}
      + [从 Google Analytics 迁移数据](../use-cases/ga/overview.md)
      + [引入 Google Analytics 历史数据](../use-cases/ga/backfill.md)
      + [配置流式处理 Google Analytics 数据](../use-cases/ga/streaming.md)
      + [报告 Google Analytics 数据](../use-cases/ga/report.md)
   + 数据摄取 {#data-ingestion}
      + [收錄并使用 Marketo Engage 数据](../use-cases/data-ingestion/marketo.md)
      + [收錄和使用 Experience Platform 受众](../use-cases/data-ingestion/ingest-aep-segments.md)
   + 数据视图 {#data-views}
      + [数据视图用例](../use-cases/data-views/data-views-usecases.md)
      + [使用绑定维度和量度](../use-cases/data-views/binding-dimensions-metrics.md)
      + [使用摘要数据](../use-cases/data-views/summary-data.md)
   + 数据导出 {#data-export}
      + [概述](../use-cases/data-export/overview.md)
      + [BI 扩展](../use-cases/data-export/bi-extension.md)
      + [导出数据集](../use-cases/data-export/export-datasets.md)
      + [导出整个表](../use-cases/data-export/export-full-table.md)
      + [查询服务和导出数据集](../use-cases/data-export/queryservice-export-datasets.md)
   + B2B {#b2b}
      + [B2B 项目示例](../use-cases/b2b/example.md)
   + 跨渠道数据 {#cross-channel}
      + [跨渠道分析数据](../use-cases/cross-channel/cross-channel.md)
      + [导入呼叫中心数据和网站数据](../use-cases/cross-channel/call-center.md)
   + Adobe Analytics 数据 {#aa-data}
      + [使用“营销渠道”维度](../use-cases/aa-data/marketing-channels.md)
      + [将报告包与不同的架构相结合](../use-cases/aa-data/combine-report-suites.md)
   + 复杂的数据 {#complex-data}
      + [使用对象数组](../use-cases/object-arrays.md)
   + 拼合 {#stitching}
      + [共享设备](/help/use-cases/stitching/shared-devices.md)
   + 派生字段 {#derived-fields}
      + [报告目标](../use-cases/goals-using-derived-fields.md)

+ Labs {#labs}
   + [Labs 用户指南](../labs/labs.md)

+ 故障排除 {#troubleshooting}
   + [比较数据](../troubleshooting/compare.md)
   + [指标和受众的一致性](../troubleshooting/consistency-rcdp-cja.md)
   + [缺乏权限](../troubleshooting/lack-of-permissions.md)

+ 技术说明 {#technotes}
   + [访问控制](../technotes/access-control.md)
   + [数据中心](../technotes/data-centers.md)
   + [删除后果](../technotes/deletion.md)
   + [域名](../technotes/domains.md)
   + [术语表](../technotes/glossary.md)
   + [护栏](../technotes/guardrails.md)
   + [IP 地址](../technotes/ip-addresses.md)
   + [优化性能](../technotes/optimizing-performance.md)
   + [查看和管理使用情况](../technotes/estimate-usage.md)

+ [Customer Journey Analytics API](https://developer.adobe.com/cja-apis/docs/)
