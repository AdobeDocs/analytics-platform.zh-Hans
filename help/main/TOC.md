---
git-repo: https://github.com/AdobeDocs/analytics-platform.zh-Hans
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Customer Journey Analytics 指南
user-guide-description: 了解 Customer Journey Analytics (CJA) 以及如何将 Analysis Workspace 用于来自 Experience Platform 的数据。
breadcrumb-title: Customer Journey Analytics 指南
source-git-commit: d11a1cf98999c5797ab456bd547c065a5103b068
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 97%

---


# Customer Journey Analytics 指南 {#using}

+ [Customer Journey Analytics 指南](../getting-started/cja-landing.md)
+ 发行说明 {#releases}
   + [最新版本](../release-notes/latest.md)
   + [2022 版](../release-notes/2022.md)
   + [2021 版](../release-notes/2021.md)
   + [2020 版](../release-notes/2020.md)
   + [CJA 版本](../release-notes/releases.md)
   + [CJA 文档更新](../release-notes/doc-changes.md)
+ Customer Journey Analytics 概述{#cja-overview}
   + [Customer Journey Analytics 概述](../getting-started/cja-overview.md)
   + [快速入门](../getting-started/cja-getting-started.md)
   + [Real-Time CDP 和 CJA 之间量度和受众会员计数的一致性](../getting-started/consistency-rcdp-cja.md)
   + [CJA 访问控制](../getting-started/cja-access-control.md)
   + [Customer Journey Analytics 登陆页面](../getting-started/landing.md)
   + [常见问题解答](../getting-started/cja-faq.md)
   + [从 Adobe Analytics 演变到 Customer Journey Analytics](../getting-started/aa-to-cja.md)
   + [Customer Journey Analytics 新用户的用户指南](../getting-started/aa-to-cja-user.md)
   + 比较 Adobe Analytics 和 Customer Journey Analytics{#compare-aa-cja}
      + [Customer Journey Analytics 功能支持](../getting-started/aa-vs-cja/cja-aa.md)
      + [比较通过 Analytics Source Connector 传递的 Analytics 数据的术语](../getting-started/aa-vs-cja/terminology.md)
      + [跨 Adobe Analytics 和 CJA 比较数据处理](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [虚拟报告环境和沙盒环境](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [处理规则、VISTA 和分类与数据准备](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [AAID、ECID、AACUSTOMID 和 Analytics Source Connector](../getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [删除后果](../getting-started/cja-deletion.md)
   + [CJA 术语表](../getting-started/cja-glossary.md)
+ 连接 {#cja-connections}
   + [连接概述](../connections/overview.md)
   + [创建连接](../connections/create-connection.md)
   + [管理连接](../connections/manage-connections.md)
   + [合并事件数据集](../connections/combined-dataset.md)
   + [标准查找](../connections/standard-lookups.md)
   + 跨渠道分析 {#cca}
      + [跨渠道分析概述](../connections/cca/overview.md)
      + [重播的工作原理](../connections/cca/replay.md)
      + [跨渠道分析常见问题解答](../connections/cca/faq.md)
+ 数据视图 {#cja-dataviews}
   + [数据视图概述](../data-views/data-views.md)
   + [创建或编辑数据视图](../data-views/create-dataview.md)
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
      + [值分段](../data-views/component-settings/value-bucketing.md)
   + [标准组件参考](../data-views/component-reference.md)
   + [数据视图用例](../data-views/data-views-usecases.md)
   + [标签和策略](../data-views/data-governance.md)
+ 工作区项目 {#cja-workspace}
   + [Analysis Workspace 概述](../analysis-workspace/home.md)
   + [执行基本分析](../analysis-workspace/perform-basic-analysis.md)
   + [执行高级分析](../analysis-workspace/perform-adv-analysis.md)
   + 项目 {#build-workspace-project}
      + [项目概述](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [保存项目](../analysis-workspace/build-workspace-project/save-projects.md)
      + 工作区中的文件夹 {#workspace-folders}
         + [关于工作区中的文件夹](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [创建文件夹和子文件夹](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [添加项目](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
         + [删除项目](../analysis-workspace/build-workspace-project/workspace-folders/remove-projects.md)
         + [保存新项目](../analysis-workspace/build-workspace-project/workspace-folders/save-new-project-folder.md)
      + [热键（快捷方式）](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [调色板](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [视图密度](../analysis-workspace/build-workspace-project/view-density.md)
   + 可视化图表 {#visualizations}
      + [可视化图表概述](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [管理数据源](../analysis-workspace/visualizations/t-sync-visualization.md)
      + 自由格式表 {#freeform-table}
         + [自由格式表](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + 列和行设置 {#column-row-settings}
            + [列设置](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [行设置](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [动态项和静态项](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [对表格进行分页、过滤和排序](../analysis-workspace/visualizations/freeform-table/pagination-filtering-sorting.md)
         + [工作区总计](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + 同类群组表 {#cohort-table}
         + [什么是同类群组分析？](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [配置同类群组分析报告](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [同类群组分析用例](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + 流失 {#fallout}
         + [流失概述](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [配置流失可视化图表](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [维度间流失](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [在流失分析中应用过滤器](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + 流量 {#flow}
         + [流量概述](../analysis-workspace/visualizations/c-flow/flow.md)
         + [配置流量可视化图表](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [维度间流量](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + [面积图和堆叠的面积图](../analysis-workspace/visualizations/area.md)
      + [条形图和堆叠的条形图](../analysis-workspace/visualizations/bar.md)
      + [项目符号图表](../analysis-workspace/visualizations/bullet-graph.md)
      + [组合图表](../analysis-workspace/visualizations/combo-charts.md)
      + [圆环图](../analysis-workspace/visualizations/donut.md)
      + [直方图](../analysis-workspace/visualizations/histogram.md)
      + [水平条形图和堆叠的水平条形图](../analysis-workspace/visualizations/horizontal-bar.md)
      + [关键量度摘要](../analysis-workspace/visualizations/key-metric.md)
      + [线形图](../analysis-workspace/visualizations/line.md)
      + [散点图](../analysis-workspace/visualizations/scatterplot.md)
      + [摘要数字和摘要变化](../analysis-workspace/visualizations/summary-number-change.md)
      + [文本](../analysis-workspace/visualizations/text.md)
      + [树形图](../analysis-workspace/visualizations/treemap.md)
      + [维恩图](../analysis-workspace/visualizations/venn.md)
   + 面板 {#panels}
      + [面板概述](../analysis-workspace/c-panels/panels.md)
      + [归因面板](../analysis-workspace/c-panels/attribution.md)
      + [空白面板](../analysis-workspace/c-panels/blank-panel.md)
      + [“试验”面板](../analysis-workspace/c-panels/experimentation.md)
      + [“自由格式”面板](../analysis-workspace/c-panels/freeform-panel.md)
      + [“快速分析”面板](../analysis-workspace/c-panels/quickinsight.md)
      + [“媒体并行查看者”面板](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + 媒体播放耗时 {#media-playback-timespent}
         + [概述](../analysis-workspace/c-panels/media-playback-timespent/media-playback-time-spent.md)
         + [输入和输出设置](../analysis-workspace/c-panels/media-playback-timespent/panel-inputs-outputs.md)
         + [常见问题解答](../analysis-workspace/c-panels/media-playback-timespent/faqs.md)
   + 策划、共享和计划项目 {#curate-share}
      + [“共享”菜单](../analysis-workspace/curate-share/send-schedule-files.md)
      + [策划项目](../analysis-workspace/curate-share/curate.md)
      + [共享项目](../analysis-workspace/curate-share/share-projects.md)
      + [创建可共享链接](../analysis-workspace/curate-share/shareable-links.md)
      + [仅供查看的项目](../analysis-workspace/curate-share/view-only-projects.md)
      + [下载 PDF 或 CSV 文件](../analysis-workspace/curate-share/download-send.md)
      + [计划项目](../analysis-workspace/curate-share/t-schedule-report.md)
   + Attribution IQ{#attribution}
      + [归因概述](../analysis-workspace/attribution/overview.md)
      + [归因模型和回顾时间范围](../analysis-workspace/attribution/models.md)
      + [算法归因](../analysis-workspace/attribution/algorithmic.md)
      + [归因最佳实践](../analysis-workspace/attribution/best-practices.md)
      + [常见问题解答](../analysis-workspace/attribution/faq.md)
   + Virtual Analyst {#virtual-analyst}
      + [Virtual Analyst 概述](../analysis-workspace/virtual-analyst/overview.md)
      + 异常检测 {#anomaly-detection}
         + [异常检测概述](../analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)
         + [在 Analysis Workspace 中查看异常](../analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md)
         + [异常检测中使用的统计技术](../analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)
   + [用户首选项](../analysis-workspace/user-preferences.md)
   + 工作区常见问题解答 {#workspace-faq}
      + [常见问题解答](../analysis-workspace/workspace-faq/faq.md)
      + [优化 Analysis Workspace 性能](../analysis-workspace/workspace-faq/optimizing-performance.md)
      + [错误消息](../analysis-workspace/workspace-faq/error-messages.md)
      + [Analysis Workspace 限制](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [管理要求](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Analysis Workspace 中的辅助功能](../analysis-workspace/workspace-faq/aw-accessibility.md)
      + [Analysis Workspace 中的长尾](../analysis-workspace/workspace-faq/long-tail.md)
+ Report Builder {#cja-reportbuilder}
   + [Report Builder 概述](../report-builder/report-buider-overview.md)
   + [Report Builder 设置](../report-builder/report-builder-setup.md)
   + [创建数据块](../report-builder/create-a-data-block.md)
   + [Report Builder 中心](../report-builder/report-builder-hub.md)
   + [选择日期范围](../report-builder/select-date-range.md)
   + [使用过滤器](../report-builder/work-with-filters.md)
   + [筛选维度](../report-builder/filter-dimensions.md)
   + [管理数据块](../report-builder/manage-reportbuilder.md)
   + [限制标签](../report-builder/restricted-labels.md)
   + [Report Builder 设置](../report-builder/report-builder-settings.md)
+ 组件 {#cja-components}
   + [组件概述](../components/overview.md)
   + 批注 {#annotations}
      + [批注概述](../components/annotations/overview.md)
      + [创建批注](../components/annotations/create-annotations.md)
      + [管理批注](../components/annotations/manage-annotations.md)
      + [查看批注](../components/annotations/view-annotations.md)
      + [移动批注](../components/annotations/mobile-annotations.md)
   + 受众{#audiences}
      + [受众概述](../components/audiences/audiences-overview.md)
      + [创建并发布受众](../components/audiences/publish.md)
      + [管理受众](../components/audiences/manage.md)
   + 维度{#dimensions}
      + [预览维度](../components/dimensions/view-dimensions.md)
      + [划分维度](../components/dimensions/t-breakdown-fa.md)
      + [时间划分维度](../components/dimensions/time-parting-dimensions.md)
      + [具有很高基数的维度](../components/dimensions/high-cardinality.md)
   + [量度](../components/apply-create-metrics.md)
   + 过滤器 {#cja-filters}
      + [过滤器概述](../components/filters/filters-overview.md)
      + [创建过滤器](../components/filters/create-filters.md)
      + [管理过滤器](../components/filters/manage-filters.md)
      + [快速过滤器](../components/filters/quick-filters.md)
      + [临时过滤器](../components/filters/ad-hoc-filters.md)
      + [运算符](../components/filters/operators.md)
   + 计算量度 {#cja-calcmetrics}
      + [计算量度概述](../components/calc-metrics/calc-metr-overview.md)
      + 计算量度工作流程 {#cm-workflow}
         + [计算指标工作流程](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [查找指标](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [生成指标](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [指标类型和归因](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [构建简单的“每次访问的页面查看次数”指标](../components/calc-metrics/cm-workflow/cm-pvv.md)
         + [筛选量度](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [堆叠和替换区段](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [过滤和加权指标](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [使用函数](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [参与率指标](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [标记计算指标](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [批准计算指标](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [共享计算指标](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [计算量度管理器](../components/calc-metrics/cm-workflow/cm-manager.md)
      + [基本功能](../components/calc-metrics/cm-functions.md)
      + [高级功能](../components/calc-metrics/cm-adv-functions.md)
   + 日期范围 {#cja-date-ranges}
      + [日期范围概述](../components/date-ranges/overview.md)
      + [创建日期范围](../components/date-ranges/create.md)
      + [管理日期范围](../components/date-ranges/manage.md)
      + [日历概述](../components/date-ranges/calendar.md)
      + [创建自定义日期范围](../components/date-ranges/custom-date-ranges.md)
      + [日期比较](../components/date-ranges/time-comparison.md)
+ Analytics 功能板{#cja-dashboards}
   + [Analytics 功能板 — 概述](../mobile-app/home.md)
   + [策划人任务](../mobile-app/curator.md)
   + [创建移动记分卡](../mobile-app/create-scorecard.md)
   + [设置执行用户以使用功能板](../mobile-app/set-up-execs.md)
   + [执行用户快速入门指南](../mobile-app/executive.md)
+ Adobe 集成 {#integrations}
   + [关于将 Adobe 解决方案与 CJA 集成的概述](/help/integrations/overview.md)
   + [将 Journey Optimizer 数据与 CJA 集成](/help/integrations/ajo.md)
   + [将 Customer AI 数据与 CJA 集成](/help/integrations/customer-ai.md)
+ 用例 {#cja-usecases}
   + [Customer Journey Analytics 用例](../use-cases/cja-usecases.md)
   + Google Analytics 数据{#ga}
      + [将数据从 Google Analytics 迁移到 CJA 概览](../use-cases/ga/overview.md)
      + [将 Google Analytics 历史数据提取到平台](../use-cases/ga/backfill.md)
      + [将流式 Google Analytics 数据配置到 Platform](../use-cases/ga/streaming.md)
      + [在 CJA 中给出 Google Analytics 数据报告](../use-cases/ga/report.md)
   + [将报告包与不同的架构相结合](../use-cases/combine-report-suites.md)
   + [使用对象数组](../use-cases/object-arrays.md)
   + [使用绑定维度和量度](../use-cases/binding-dimensions-metrics.md)
   + [(B2B) 将帐户级别的数据作为查询数据集进行添加](../use-cases/b2b.md)
   + [将 Marketo Engage 数据摄取到 AEP 并在 CJA 中报告](../use-cases/marketo.md)
   + [将 AEP 受众引入 CJA](../use-cases/ingest-aep-segments.md)
   + [跨渠道分析数据](../use-cases/cross-channel.md)
   + [导入呼叫中心数据和网站数据](../use-cases/call-center.md)
   + [摄取数据用例](../use-cases/data-ingestion.md)
   + [使用“营销渠道”维度](../use-cases/marketing-channels.md)
+ Labs {#labs}
   + [Labs 用户指南](../labs/labs.md)
+ 故障排除 {#troubleshooting}
   + [将 Adobe Analytics 数据与 CJA 数据进行比较](../troubleshooting/compare.md)
+ 数据管理 {#cja-privacy}
   + [审核日志](../privacy/audit-log.md)
   + [数据管理](../privacy/privacy-overview.md)
+ [CJA API](https://developer.adobe.com/cja-apis/docs/)
