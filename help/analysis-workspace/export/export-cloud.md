---
description: 了解如何将完整的表导出到云位置。
keywords: Analysis Workspace
title: 将完整表导出到云
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '2482'
ht-degree: 79%

---

# 将全表导出到云 {#full-table-export}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-full-table-export"
>title="创建类似于数据仓库的完整表格导出"
>abstract="只要您在分析工作区中看到数据，就可以完整表格导出。您可以根据需要创建或计划完整表格导出。<br><br>如果您已经知道导出中要包含哪些数据，那么创建完整表格导出只需几分钟即可完成。"

<!-- markdownlint-enable MD034 -->

您可以从Customer Journey Analytics导出Analysis Workspace的完整表，并将导出内容发送到指定的云目标。

如[导出概述](/help/analysis-workspace/export/export-project-overview.md)中所述，还有其他导出 Customer Journey Analytics 报告的方法。

## 了解完整表格导出

您可以从 Analysis Workspace 将完整表格导出到云提供商，例如 Google、Azure、Amazon 和 Adobe。

[将完整表格导出到云的优点](#advantages-of-exporting-to-the-cloud)包括：能够导出数百万行数据，包含计算量度，以连接值的形式输出结构化数据等。

导出完整表格时，请考虑以下事项：

* 在导出到云之前，请确保您的表、环境和权限满足[导出要求](#export-requirements)。

* 将完整表格导出至云时，某些[功能](#unsupported-features)和[组件](#unsupported-components)不受支持。

将完整表格导出到云时，请使用以下流程：

1. [配置云帐户](/help/components/exports/cloud-export-accounts.md)

1. [在帐户上配置一个位置](/help/components/exports/cloud-export-locations.md)

1. [从工作区导出完整表格](#export-full-tables-from-analysis-workspace)

1. [访问云中的数据](#view-exported-data-and-manifest-file)并[管理 Adobe 中的导出内容](/help/components/exports/manage-exports.md)

![步骤 1 至 4 中所描述的完整表格导出流程。](assets/export-full-table-process.png)

## 导出整个表  {#export-from-workspace}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-details"
>title="详细信息"
>abstract="指定导出内容的名称。您还可以添加描述和标签。此信息有助于您在导出表格和电子邮件通知中识别该导出任务。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-data-structure"
>title="数据结构"
>abstract="这是您正在导出的自由格式表。您可以通过将组件从左侧面板拖动到表格中来调整数据结构。您可以将组件拖动到筛选区域以应用筛选条件。当您向画布添加组件时，该表会动态更新。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="export-manifest"
>title="清单文件"
>abstract="选中后，每次成功导出都会附带一个清单文件。您可以使用清单文件确认所有文件均已成功传递。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-schedule"
>title="计划"
>abstract="选择导出的执行频率。选择“立即发送（单次）”以立即启动导出。计划导出在指定的日期和时间启动。 "

<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-destination"
>title="目的地"
>abstract="选择要发送数据的云帐户及目标位置。您可以选择现有帐户和位置，或选择“新增”进行创建。指定在导出失败或即将过期时接收通知的用户和用户组。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-file-format"
>title="文件格式"
>abstract="选择 Parquet 文件格式时，组件名称中的部分特殊字符将被替换为下划线 (_)。有关替换字符的完整列表，请参阅下方链接。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>在按照本节说明导出数据之前，请先通过上述[了解完整表格导出](#understand-full-table-export)部分来了解有关完整表格导出的更多信息。

若要从 Analysis Workspace 导出完整表格：

1. 如果尚未配置，请配置一个导出帐户和位置，如[配置云导出帐户](/help/components/exports/cloud-export-accounts.md)中所述。

1. 在Analysis Workspace中，从自由格式表的上下文菜单中选择&#x200B;[!UICONTROL **导出完整表**]。

   ![自由格式表下拉菜单，其中突出显示了“导出完整表格”。](assets/export-full-table.png)

1. 在&#x200B;[!UICONTROL **新建完整表格导出**]&#x200B;对话框中，指定以下信息：

   | 字段名称 | 功能 |
   |---------|----------|
   | 名称 | 指定导出内容的名称。此名称会在导出列表中显示。 |
   | 标记 | 您可以将现有标记应用于导出内容，也可以创建新标记并应用它。 <p>要将现有标记应用于导出内容，请从下拉菜单中选择任意标记。您公司的任何标记均可应用<!-- double-check this -->。</p> <p>要创建新标记，请键入新标记的名称，然后按 Enter。</p><p>在导出内容中应用标记时，请考虑以下事项： <ul><li>您应用的标记可以在导出表中进行过滤或搜索。</li> <li>导出完整表格时，应用于项目的标记不会自动应用，如[管理导出内容](/help/components/exports/manage-exports.md)中的“在导出页面上配置列”中所述。（或者，当[计划导出整个项目](/help/analysis-workspace/export/t-schedule-report.md)，任何应用于项目的标记都会自动应用于导出内容。）<!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | 描述 | 为导出内容添加描述。在查看导出内容时，您可以选择在[导出页面](/help/components/exports/manage-exports.md)中将描述内容视为一列进行查看。 |
   | 数据视图 | 选择包含您想要在导出内容中加入的组件的数据视图。![数据](/help/assets/icons/Data.svg)数据视图下拉菜单位于对话框的左上角。  <p>**注意：**&#x200B;如果选择的数据视图缺少已包含在数据表中的组件，则系统会提示您清除并使用选定数据视图中包含的组件重新创建面板。 </p> |
   | 回溯时间范围 | 选择要包含在每个导出文件中的报告时间范围。相关选项包括&#x200B;[!UICONTROL **今天**]、**[!UICONTROL 昨天、]****[!UICONTROL 过去 7 天]**、**[!UICONTROL 过去 30 天]**、**[!UICONTROL 本星期]**&#x200B;和&#x200B;**[!UICONTROL 本月]**。 <p>当&#x200B;**[!UICONTROL 导出频率]**&#x200B;设置为&#x200B;**[!UICONTROL 立即发送（一次性）]**&#x200B;时，不显示此选项。 |
   | 数据表 | 显示您正在导出的自由格式表。您可以通过将组件从左侧面板拖到表中来修改数据表。当您向画布添加组件时，该表会动态更新。  <p>任何应用于项目中完整表格的区段都会出现在表格中每个单独列的顶部。</p> |
   | 清除 | 清除数据表的内容。这样您就可以直接在新的完整表格导出对话框中开始构建新表。 |
   | 导出频率 | 设置导出的频率。 <p>您可以选择&#x200B;[!UICONTROL **立即发送（一次性）**]&#x200B;只发送一次导出内容。当您选择此选项时，会立即启动导出。<p>或者，您可以选择按定义的计划发送导出内容。当按计划发送时，相关选项包括&#x200B;**[!UICONTROL 每天]**、**[!UICONTROL 每周]**、**[!UICONTROL 每月按星期几]**、**[!UICONTROL 每月按一个月中的某一天]**、**[!UICONTROL 每年按一个月中的某一天]**&#x200B;和&#x200B;**[!UICONTROL 每年按特定日期]**。 </p><p>选择导出频率时，请考虑以下因素：</p><ul><li>**[!UICONTROL 回顾时间范围]**&#x200B;字段中的选项根据您在此处选择的内容而变化。<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>根据您选择的选项，将显示其他配置字段。</li></ul> |
   | 开始日期  | 计划导出开始的日期和时间。 <p>仅当选择计划导出频率时此选项才可用。</p> |
   | 结束时间 | 计划导出的到期日期和时间。计划导出在您设置的日期和时间过后不再运行。 <p>仅当选择计划导出频率时此选项才可用。</p> |
   | 文件格式 | 选择导出的数据是否应为 .csv 或 .json 格式。 |
   | 包含清单文件 | 启用后，任何成功的导出传递都会包含一份清单文件。您可以使用清单文件确认所有文件均已成功传送。它包含以下信息：<ul><li>已传递的所有文件的列表</li><li>每个文件的 MD5 校验和</li></ul><p>导出的数据以压缩文件的形式存储在您配置的云目标中，如[配置云导出账户](/help/components/exports/cloud-export-accounts.md)和[配置云导出位置](/help/components/exports/cloud-export-locations.md)中所述。</p><p>压缩文件的文件名如下所示，具体取决于您选择的文件格式是 CSV 还是 JSON：</p><ul><li>`cja-export-{reportInstanceId}-{idx}.csv.gz`</li><li>`cja-export-{reportInstanceId}-{idx}.json.gz`</li></ul><p>您在上面的**[!UICONTROL *文件格式**]字段中选择文件格式。</p> |
   | 帐户 | 选择您想要发送数据的云导出账户。 <p>或者，如果您尚未配置要使用的云帐户，则可以配置一个新帐户：<ol><li>选择&#x200B;**[!UICONTROL 添加帐户]**，然后指定以下信息：<ul><li>**[!UICONTROL 位置帐户名称]**：指定位置账户的名称。此名称会在创建位置时出现 </li><li>**[!UICONTROL *位置帐户描述]**：提供帐户的简短描述，以帮助将其与相同帐户类型的其他帐户区分开来。</li><li>**[!UICONTROL 帐户类型]**：选择您要导出到的云帐户类型。可用的帐户类型包括 Amazon S3 Role ARN、Google Cloud Platform、Azure SAS、Azure RBAC、Snowflake 和 AEP Data Landing Zone。</li></ul><li>要完成帐户配置，请继续访问下面与您选择的&#x200B;**[!UICONTROL 帐户类型]**&#x200B;相对应的链接：<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | 位置 | 在帐户上选择要发送导出数据的位置。<p>或者，如果您尚未配置要在所选帐户上使用的位置，则可以配置一个新位置：<ol><li>选择&#x200B;**[!UICONTROL *dd位置]**，然后指定以下信息： <ul><li>**[!UICONTROL 名称：]**&#x200B;位置的名称。</li><li>**[!UICONTROL 描述]**：提供位置的简短描述，以帮助将它与帐户上的其他位置区分开来。</li><li>**[!UICONTROL 位置帐户]**：选择要在其中创建位置的帐户。</li></ul><li>若要完成位置配置，请使用下面的链接继续操作，该链接与您在**[!UICONTROL 位置帐户]**字段中选择的帐户类型相对应：<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone)。</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]&#x200B;来保存导出内容。

   数据会按照您指定的频率发送到您指定的云帐户。

1. （可选）创建导出后，无论您选择立即发送还是按照定义的计划发送，您都可以在[导出页面](/help/components/exports/manage-exports.md)上查看和管理它，并在[导出日志](/help/components/exports/manage-export-logs.md)中查看它。</p>

## 管理导出

在从 Analysis Workspace 导出数据后，您可以编辑、重新导出、复制、标记或删除现有的导出内容，如[管理导出内容](/help/components/exports/manage-exports.md)中所述。

## 全表导出的优点 {#advantages}

通过将 Customer Journey Analytics 数据导出到云，您可以：

* 导出到共享位置，例如 Adobe Experience Platform Data Landing Zone、Google Cloud Platform、Microsoft Azure、Amazon S3 或 Snowflake。

* 存储大量历史数据。

  此类数据可用于检测长期趋势，以获得业务情报，并最终带来更好的业务决策。

* 导出包含数千或数百万行（300 万、3000 万、1.5 亿或 3 亿行，具体取决于许可证类型）的完整表格。其他导出方法最多允许 50,000 行。

* 在导出的 Customer Journey Analytics 数据中加入计算量度。

* 将数据输出组织为连接值。

* 一次性或按计划导出。（[其他导出选项](/help/analysis-workspace/export/export-project-overview.md)也提供该功能。）

* 以 CSV 或 JSON 格式导出文件。（[其他导出选项](/help/analysis-workspace/export/export-project-overview.md)也提供该功能。）

* 导出包含多个维度的表。

## 最低要求

确保您的表、环境和权限满足以下要求：

* **表：**&#x200B;所有表都必须至少包含行中的一个维度，每个列中包含一个量度，才能支持完整表导出。

* **环境：**&#x200B;确保 Customer Journey Analytics 使用的 [IP 地址](/help/technotes/ip-addresses.md)和[域](/help/technotes/domains.md)可以通过其组织的防火墙。

* **权限：**&#x200B;在Adobe Admin Console中，必须为用户分配一个产品配置文件，该配置文件具有分配给用户的&#x200B;**[!UICONTROL 完全表导出]**&#x200B;权限，以便导出完全表。 有关在 Admin Console 中为产品轮廓分配权限的信息，请参阅 [Admin Console 中的 Customer Journey Analytics 权限](/help/technotes/access-control.md)。

  >[!NOTE]
  >
  >  分配有[产品管理员角色](/help/technotes/access-control.md#product-admin-role)的用户始终有权导出完整表格；因此无需为这些用户分配&#x200B;**[!UICONTROL 完整表格导出]**&#x200B;权限。


## 不支持的功能

以下功能不受支持，并且会自动从完整表格导出中移除：

* 百分比
* 总计
* 搜索过滤
* 静态行
* 日期对齐
* 来自摘要数据集的量度
* 动态维度项

  将维度拖放到自由格式表的列标题上时，会创建动态维度项，从而导致列被排名前5的维度项动态筛选。 在Analysis Workspace中，每次加载项目时，排名前5的维度项都会更新。 在完整表格导出中，这些维度项目会变为静态。 如需了解更多信息，请参阅[自由格式表中的动态与静态维度项](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)。
* 转换第一个划分中的维度，并将其添加为导出表行中的次要维度。 表格中不包含任何其他细分。
* 大多数数据集不支持排序；对于小型数据集，可能会对数据排序。

## 不支持的组件

以下组件不受支持，并且 Analysis Workspace 会在执行完整表格导出时提示您将其从表中移除：

* 在量度定义中使用基本函数或高级函数的计算量度（有关详细信息，请参阅[基本函数](/help/components/calc-metrics/cm-functions.md)和[高级函数](/help/components/calc-metrics/cm-adv-functions.md)）
* 管理员已限制导出组件（有关详细信息，请参阅&#x200B;*标签和策略*&#x200B;中数据视图[中数据管理策略的](/help/data-views/data-governance.md)区段）
* 满足以下所有条件的任何维度：
   * 从属于[对象数组](/help/use-cases/object-arrays.md)的字段创建(类似于Adobe Analytics中的多值变量)。
   * 已启用[持久性](/help/data-views/component-settings/persistence.md)。
   * 未使用[绑定维度](/help/use-cases/data-views/binding-dimensions-metrics.md)。
* 来自引用不同[对象数组](/help/use-cases/object-arrays.md)的字段的多个维度。（允许多个维度引用同一对象数组。）
* 每个报告包含超过 10 个维度和 10 个量度（最多支持 10 个维度和 10 个量度）
* 在表列中：
   * 日期范围
   * 维度
* 在表行中：
   * 计算量度
   * 量度
   * 日期范围
   * 区段

## 归因行为

完整表格导出支持使用非默认归因模型的计算量度（如[列设置](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)中的&#x200B;*使用非默认归因模型*&#x200B;部分中所述）。

如果在报表中使用非默认归因模型，则忽略或保留报表中使用的分配模型，具体取决于报表是具有一个维度还是多个维度：

* **对于在单个维度中包含量度归因的报告：**[量度归因](/help/data-views/component-settings/attribution.md)会覆盖[分配模型](/help/data-views/component-settings/persistence.md)，就像使用量度归因时通常进行的操作一样。

  例如，“首次接触”量度归因会覆盖“最近”维度分配。

* **对于同时包含多个维度的量度归因的报告：除了维度[分配模型](/help/data-views/component-settings/persistence.md)外，还应用了**[量度归因](/help/data-views/component-settings/attribution.md)。

  例如，除了“最近”维度分配之外，还会应用“首次接触”量度归因。此外，量度归因会像对单个维度项目一样，应用于后分配的维度项目对，而不是像通常在自由格式表中那样单独应用于每个维度项目。

  >[!NOTE]
  >
  >如本文所述，仅当将数据导出到云端时，才支持多维报告。

## 与Data Warehouse比较

如果您之前使用 Data Warehouse 导出过 Adobe Analytics 数据，则下表可以帮助您了解在 Customer Journey Analytics 中导出完整表格与使用 Adobe Analytics 中的 Data Warehouse 导出数据之间的区别。


| 功能 | Customer Journey Analytics 中的完整表格导出 | Adobe Analytics 中的 Data Warehouse |
|---------|----------|---------|
| 生成自定义报告 | 是 | 是 |
| 计算量度 | 是 | 否 |
| 区段 | 是 | 有限制 |
| 维度 | 限 10 个 | 无限制 |
| 量度 | 限 10 个 | 无限制 |
| 报告行 | 限额为 300 万、3000 万、1.5 亿或 3 亿，具体取决于等级 | 无限制 |
| 报告数量 | 无限制 | 无限制 |
| 临时（一次性）传递 | 是 | 是 |
| 计划定期传递 | 是 | 是 |
| 电子邮件传递 | 否 | 是 |
| FTP / SFTP | 否 | 旧版支持 |
| Azure | 是 | 是 |
| Amazon S3 | 是 | 是 |
| Google Cloud Platform | 是 | 是 |
| Snowflake | 是 | 否 |
| 传递频率 | 每日 | 每小时 |
