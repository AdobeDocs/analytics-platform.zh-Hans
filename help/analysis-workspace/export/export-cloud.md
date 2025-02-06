---
description: 了解如何将Analysis Workspace项目导出到云位置。
keywords: Analysis Workspace
title: 将Customer Journey Analytics报表导出到云端
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: 668f17531b4b8a01acffdbb0edef07092859d100
workflow-type: tm+mt
source-wordcount: '2281'
ht-degree: 3%

---

# 将Customer Journey Analytics报表导出到云端 {#full-table-export}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-full-table-export"
>title="创建与Data Warehouse类似的完整表导出"
>abstract="在Analysis Workspace中看到数据后，即可使用完整的表导出。 您可以根据需要创建或计划完整表导出。<br><br>如果您已经知道要包括在导出中的数据，则创建完整表导出只需几分钟即可完成。"

<!-- markdownlint-enable MD034 -->

您可以从Customer Journey Analytics中导出Workspace的完整表，并将导出发送到指定的云目标。

也可以使用其他导出Customer Journey Analytics报表的方法，如[导出概述](/help/analysis-workspace/export/export-project-overview.md)中所述。

## 了解完整的表导出

您可以将完整的表从Analysis Workspace导出到Google、Azure、Amazon和Adobe等云提供商。

[将完整表导出到云的优势](#advantages-of-exporting-to-the-cloud)包括能够导出数百万行、包括计算量度、以串联值输出结构数据等等。

导出完整表时，请考虑以下事项：

* 在导出到云之前，请确保您的表、环境和权限符合[导出要求](#export-requirements)。

* 将完整表导出到云时不支持某些[功能](#unsupported-features)和[组件](#unsupported-components)。

将完整的表导出到云时，请使用以下流程：

1. [配置云帐户](/help/components/exports/cloud-export-accounts.md)

1. [在帐户上配置位置](/help/components/exports/cloud-export-locations.md)

1. [从Workspace导出整个表](#export-full-tables-from-analysis-workspace)

1. [访问云中的数据](#view-exported-data-and-manifest-file)和[管理Adobe中的导出](/help/components/exports/manage-exports.md)

![步骤1至4中描述的完整表导出过程。](assets/export-full-table-process.png)

## 从Analysis Workspace导出完整表

>[!NOTE]
>
>在按本节所述导出数据之前，请参阅上面[了解完整表导出](#understand-full-table-export)部分以了解有关完整表导出的更多信息。

要从Analysis Workspace导出完整表，请执行以下操作：

1. 如果尚未配置，请按照[配置云导出帐户](/help/components/exports/cloud-export-accounts.md)中的说明配置导出帐户和位置。

1. 在Analysis Workspace中，右键单击包含要导出数据的自由格式表。

1. 选择&#x200B;[!UICONTROL **导出完整表**]。

   ![突出显示了“导出完整表”的“自由格式表”下拉菜单。](assets/export-full-table.png)

1. 在&#x200B;[!UICONTROL **新建完整表导出**]&#x200B;对话框中，指定以下信息：

   | 字段名称 | 功能 |
   |---------|----------|
   | 名称 | 指定导出的名称。 此名称将显示在导出列表中。 |
   | 标记 | 您可以将现有标记应用于导出，也可以创建新标记并应用它。 <p>要将现有标记应用于导出，请从下拉菜单中选择任意标记。 您公司的任何标记都可以应用<!-- double-check this -->。</p> <p>要创建新标记，请键入新标记的名称，然后按Enter。</p><p>将标记应用于导出时，请考虑以下事项： <ul><li>您可以在导出表中过滤或搜索您应用的标记。</li> <li>导出完整表时，不会自动应用应用于项目的标记，如[管理导出](/help/components/exports/manage-exports.md)中的“在导出页面上配置列”中所述。 （或者，当[计划导出完整项目](/help/analysis-workspace/export/t-schedule-report.md)时，应用于该项目的所有标记将自动应用于导出。） <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | 描述 | 为导出添加描述。 查看导出时，可以选择在[导出页面](/help/components/exports/manage-exports.md)中将说明作为列查看。 |
   | 数据视图 | 选择包含要包含在导出中的组件的数据视图。 数据视图下拉菜单位于对话框的左上角，可以通过数据视图图标![数据视图图标](assets/data-view-icon.png)来标识。  <p>**注意：**&#x200B;如果选择的数据视图缺少已包含在数据表中的组件，则系统会提示您清除数据表并使用选定数据视图中包含的组件重新创建数据表。 </p> |
   | 回顾时间范围 | 选择要包含在每个导出文件中的报表时间范围。 选项包括&#x200B;[!UICONTROL **今天**]、[!UICONTROL **昨天**]、[!UICONTROL **最近7天**]、[!UICONTROL **最近30天**]、[!UICONTROL **本周**]&#x200B;和&#x200B;[!UICONTROL **本月**]。 <p>当&#x200B;[!UICONTROL **导出频率**]&#x200B;设置为&#x200B;[!UICONTROL **立即发送（一次性）**]&#x200B;时，不显示此选项。 |
   | 数据表 | 显示要导出的自由格式表。 可以通过将组件从左侧面板拖到表中来修改数据表。 在将组件添加到画布时，表格会动态更新。  <p>应用于项目中整个表的任何区段都会显示在表中每个单独列的顶部。</p> |
   | 清除 | 清除数据表的内容。 这样，您就可以直接在新增完整表格导出对话框中开始构建新表格。 |
   | 导出频率 | 设置导出的频率计划。 <p>您可以选择&#x200B;[!UICONTROL **立即发送（一次性）**]&#x200B;以仅发送导出一次。 选择此选项后，将立即启动导出。<p>或者，您可以选择按定义的计划发送导出。 按计划发送时，选项包括&#x200B;[!UICONTROL **每日**]、[!UICONTROL **每周**]、[!UICONTROL **按一周的某一天每月发送**]、[!UICONTROL **按月份的某一天每月发送**]、[!UICONTROL **按月份的某一天每月发送**]&#x200B;以及&#x200B;[!UICONTROL **按特定日期每年发送**]。 </p><p>选择导出频率时，请考虑以下事项：</p><ul><li>[!UICONTROL **回顾窗口**]&#x200B;字段中的选项会根据您在此选择的内容而更改。<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>根据您选择的选项，还会显示其他配置字段。</li></ul> |
   | 开始日期 | 计划导出应开始的日期和时间。 <p>仅当选择计划的导出频率时，此选项才可用。</p> |
   | 结束日期 | 计划导出过期的日期和时间。 计划导出在设置的日期和时间后不再运行。 <p>仅当选择计划的导出频率时，此选项才可用。</p> |
   | 文件格式 | 选择导出的数据应采用.csv还是.json格式。 |
   | 帐户 | 选择要将数据发送到的云导出帐户。 <p>或者，如果您尚未配置要使用的云帐户，则可以配置新帐户：<ol><li>选择&#x200B;[!UICONTROL **添加帐户**]，然后指定以下信息：<ul><li>[!UICONTROL **位置帐户名称**]：指定位置帐户的名称。 创建位置时将显示此名称 </li><li>[!UICONTROL **位置帐户说明**]：提供帐户的简短说明，以帮助将其与相同帐户类型的其他帐户区分开来。</li><li>[!UICONTROL **帐户类型**]：选择您要导出到的云帐户类型。 可用的帐户类型包括Amazon S3 Role ARN、Google Cloud Platform、Azure SAS、Azure RBAC、Snowflake和AEP Data Landing Zone。</li></ul><li>若要完成帐户配置，请使用下面的链接继续操作，该链接与您选择的&#x200B;[!UICONTROL **帐户类型**]&#x200B;相对应：<ul><li>[AEP数据登陆区](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3角色ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google云平台](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | 位置名称 | 选择您希望发送导出数据的帐户位置。<p>或者，如果您尚未在选定的帐户上配置要使用的位置，则可以配置一个新位置：<ol><li>选择&#x200B;[!UICONTROL **添加位置**]，然后指定以下信息： <ul><li>[!UICONTROL **名称**]：位置的名称。</li><li>[!UICONTROL **描述**]：提供位置的简短描述，以帮助将该位置与帐户上的其他位置区分开来。</li><li>[!UICONTROL **位置帐户**]：选择要创建位置的帐户。</li></ul><li>要完成位置配置，请使用下面的链接继续操作，该链接与您在&#x200B;[!UICONTROL **位置帐户**]&#x200B;字段中选择的帐户类型相对应：<ul><li>[AEP数据登陆区](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone)。</li><li>[Amazon S3角色ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google云平台](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]&#x200B;以保存导出。

   数据会以您指定的频率发送到您指定的云帐户。

1. （可选）创建导出后，无论您是选择立即发送导出还是按定义的计划发送，都可以在[导出页面](/help/components/exports/manage-exports.md)上查看和管理导出，并在[导出日志](/help/components/exports/manage-export-logs.md)中查看。</p>

## 管理导出

从Analysis Workspace导出数据后，您可以编辑、重新导出、复制、标记或删除现有导出，如[管理导出](/help/components/exports/manage-exports.md)中所述。

## 查看导出的数据和清单文件

### 导出的数据

导出的数据可在您配置的云目标中作为压缩文件使用，如[配置云导出帐户](/help/components/exports/cloud-export-accounts.md)和[配置云导出位置](/help/components/exports/cloud-export-locations.md)中所述。

压缩文件的文件名如下所示，具体取决于您选择CSV还是JSON作为文件格式：

* `cja-export-{reportInstanceId}-{idx}.csv.gz`

* `cja-export-{reportInstanceId}-{idx}.json.gz`

>[!NOTE]
>
>在导出表时，您选择采用&#x200B;[!UICONTROL **文件格式**]&#x200B;字段的文件格式，如[从Analysis Workspace导出完整表](#export-full-tables-from-analysis-workspace)中所述。

### 清单文件

文件名为`cja-export-{reportInstanceId}-{idx}.json.gz`的清单文件包含在任何至少包含一个文件的成功导出投放中。 利用清单文件，可确认是否已成功提交所有文件。 它包括以下信息：

* 已传送的所有文件的列表

* 每个文件的MD5校验和

<!-- add in  what the file name, structure, and file format will be -->

## 导出到云的优势

将Customer Journey Analytics数据导出到云允许您：

* 导出到共享位置，如Adobe Experience Platform Data Landing Zone、Google Cloud Platform、Microsoft Azure、Amazon S3或Snowflake。

* 存储大量历史数据。

  此类数据可用于检测长期趋势，以获取业务情报，最终做出更好的业务决策。

* 导出包含数千行或数百万行的完整表（300万、3000万、1.5亿或3亿行，具体取决于许可证类型）。 其他导出方法最多允许50,000行。

* 在导出的Customer Journey Analytics数据中包含计算量度。

* 将数据输出构造为连接值。

* 导出一次或按计划。 （也适用于[其他导出选项](/help/analysis-workspace/export/export-project-overview.md)。）

* 以CSV或JSON格式导出文件。 （也适用于[其他导出选项](/help/analysis-workspace/export/export-project-overview.md)。）

* 导出包含多个维的表。

## 导出要求 {#export-requirements}

### 最低要求

确保您的表、环境和权限满足以下要求：

* **表：**&#x200B;所有表必须在该行至少包含一个维度，并在每列至少包含一个量度，才能支持完整表导出。

* **环境：**&#x200B;确保Customer Journey Analytics使用的[IP地址](/help/technotes/ip-addresses.md)和[域](/help/technotes/domains.md)允许通过其组织的防火墙。

* **权限：**&#x200B;在Adobe Admin Console中，必须为用户分配一个产品配置文件，该配置文件具有分配给用户的&#x200B;[!UICONTROL **完全表导出**]&#x200B;权限，才能导出完全表。 有关为Admin Console中的产品配置文件分配权限的信息，请参阅Admin Console](/help/technotes/access-control.md)中的[Customer Journey Analytics权限。

  >[!NOTE]
  >
  >  分配了[产品管理员角色](/help/technotes/access-control.md#product-admin-role)的用户始终具有导出完整表的权限；无需为这些用户分配&#x200B;[!UICONTROL **完整表导出**]&#x200B;权限。


### 不支持的功能

以下功能不受支持，并且会自动从完整表导出中删除：

* 百分比
* 总计
* 搜索筛选
* 静态行
* 日期调整
* 动态维度

  有关详细信息，请参阅自由格式表中的[动态与静态维度项](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)。
* 第一个划分中的Dimension经过转换，作为辅助维度添加到导出表的行中；任何其他划分都不会包含在该表中
* 大多数数据集不支持排序；对于小型数据集，可能会对数据排序

### 不支持的组件

以下组件不受支持，Analysis Workspace在执行完整表导出时会提示您从表中删除它们：

* 在指标定义中使用基本或高级函数的计算指标（有关详细信息，请参阅[基本函数](/help/components/calc-metrics/cm-functions.md)和[高级函数](/help/components/calc-metrics/cm-adv-functions.md)）
* 管理员已限制导出组件（有关详细信息，请参阅[标签和策略](/help/data-views/data-governance.md)中的数据视图中的&#x200B;*数据治理策略筛选器*&#x200B;部分）
* 满足以下所有条件的任何维度：
   * 是从属于[对象数组](/help/use-cases/object-arrays.md)一部分的字段创建的(类似于Adobe Analytics中的多值变量)
   * 已启用[持久性](/help/data-views/component-settings/persistence.md)
   * 未使用[绑定维度](/help/use-cases/data-views/binding-dimensions-metrics.md)
* 来自引用不同[对象数组](/help/use-cases/object-arrays.md)的字段的多个维度。 （允许引用同一对象数组的多个维度。）
* 每个报表有超过5个维度和5个量度（最多支持5个维度和5个量度）
* 在表列中：
   * 日期范围
   * 维度
* 在表行中：
   * 计算量度
   * 量度
   * 日期范围
   * 过滤器

### 归因行为

完全表导出支持使用非默认归因模型的计算量度（如[列设置](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)中的&#x200B;*使用非默认归因模型*&#x200B;部分中所述）。

如果在报表中使用非默认归因模型，则忽略或保留报表中使用的分配模型，具体取决于报表是具有一个维度还是多个维度：

* **对于在单个维度中包含量度归因的报表：** [量度归因](/help/data-views/component-settings/attribution.md)将覆盖[分配模型](/help/data-views/component-settings/persistence.md)，通常在使用量度归因时会这样做。

  例如，“首次接触”量度归因会覆盖“最近”维度分配。

* **对于同时包含多个维度的量度归因的报表：** [除了维度[分配模型](/help/data-views/component-settings/persistence.md)之外，还应用了量度归因](/help/data-views/component-settings/attribution.md)。

  例如，除了“最近”维度分配之外，还应用了“首次联系”量度归因。 此外，量度归因将应用于后分配的维度项目对，就像它们是单个维度项目一样，而不是像通常在自由格式表中那样单独应用于每个维度项目。

  >[!NOTE]
  >
  >仅当将数据导出到云中时，才支持多维报表，如本文所述。

## 完整表格导出(在Customer Journey Analytics中)与Data Warehouse(在Adobe Analytics中)的比较

如果您之前使用Data Warehouse导出Adobe Analytics数据，则下表可以帮助您了解在Customer Journey Analytics中导出完整表与在Adobe Analytics中导出带有Data Warehouse的数据之间的区别。


| 功能 | Customer Journey Analytics中的完整表导出 | Adobe Analytics中的Data Warehouse |
|---------|----------|---------|
| 构建自定义报表 | 是 | 是 |
| 计算量度 | 是 | 否 |
| 区段 | 是 | 有限制 |
| 维度 | 限制为5 | 无限制 |
| 量度 | 限制为5 | 无限制 |
| 报告行 | 限制为300万、3000万、1.5亿或3亿，具体取决于层级 | 无限制 |
| 报告数量 | 无限制 | 无限制 |
| 临时（一次性）投放 | 是 | 是 |
| 计划定期投放 | 是 | 是 |
| 电子邮件投放 | 否 | 是 |
| FTP/SFTP | 否 | 旧版支持 |
| Azure | 是 | 是 |
| Amazon S3 | 是 | 是 |
| Google Cloud Platform | 是 | 是 |
| Snowflake | 是 | 否 |
| 投放频率 | 每日 | 每小时 |
