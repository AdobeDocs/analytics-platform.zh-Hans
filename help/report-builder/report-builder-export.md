---
title: 从Report Builder导出报表
description: 介绍如何将数据从Report Builder导出到安全目标
role: User, Admin
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 1d5d87d8-1920-406b-8cce-41b89b7ae70b
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 38%

---

# 通过导出到云目标来计划工作簿

您可以将Customer Journey Analytics工作簿从Report Builder导出到Google、Azure和Amazon等云提供商。

[将报告从Report Builder导出到云的优势](#advantages-of-exporting-to-the-cloud)包括能够在第三方工具中使用报告，或者将其与外部数据相结合。

在将工作簿从Report Builder导出到Cloud目标之前，请确保您的数据块、环境和权限符合[导出要求](#export-requirements)。

## 了解导出过程

将工作簿从Report Builder导出到云时，请按照以下流程操作：

1. [配置云帐户](/help/components/exports/cloud-export-accounts.md)

1. [在帐户上配置一个位置](/help/components/exports/cloud-export-locations.md)

1. [从Report Builder导出报告](#export-a-report-from-report-builder)

1. 访问云帐户中的数据并[在Adobe中管理导出](/help/components/exports/manage-exports.md)

![步骤1至4中描述的导出过程。](assets/report-builder-export-process.png)

## 从Report Builder导出报告

>[!NOTE]
>
>在按本节所述导出数据之前，请先在上一节中了解有关[导出过程](#understand-the-export-process)的更多信息。

要从Report Builder导出报表，请执行以下操作：

1. 如果尚未配置，请配置一个导出帐户和位置，如[配置云导出帐户](/help/components/exports/cloud-export-accounts.md)中所述。

1. 在包含要导出数据的Excel电子表格中，打开&#x200B;**[!UICONTROL Adobe Report Builder]**&#x200B;右侧面板。

1. 选择&#x200B;[!UICONTROL **计划**]。

<!-- add screenshot -->

1. 在&#x200B;**[!UICONTROL 工作簿]**&#x200B;选项卡上，选择加号图标以创建新计划

   ![Report Builder计划选项卡](assets/report-builder-schedule-cloud.png)

   或

   若要按已创建的计划导出工作簿，请从计划列表中选择该计划，然后选择&#x200B;**[!UICONTROL 按计划发送]**。

1. 在&#x200B;[!UICONTROL **Adobe Report Builder**]&#x200B;右侧面板中，指定以下信息以继续创建新计划：

   | 字段名称 | 函数 |
   |---------|----------|
   | **[!UICONTROL 文件]** | 显示当前选定要导出的工作簿文件。 选择文件名旁边的工作簿图标![表选择](/help/assets/icons/TableSelect.svg)以选择当前工作簿（如果尚未选择）。 |
   | **[!UICONTROL 文件名]** <!--should be File name --> | 允许您在导出工作簿之前更改文件名。<p>工作簿文件名默认为工作簿的名称</p> |
   | **[!UICONTROL 文件类型]** | 选择导出文件的文件类型。 您可以选择Excel、PDF或CSV。 <p>当您选择&#x200B;**[!UICONTROL CSV]**&#x200B;时，请注意，计划工作簿已作为ZIP附件发送。 某些公司电子邮件管理部门可能会阻止包含ZIP附件的电子邮件。 您会看到相应的警告。</p> |
   | **[!UICONTROL 将时间戳附加到文件名]** | 选择此选项可以在文件名后附加一个时间戳，以标识工作簿的更新日期。 时间戳有助于查看在特定日期发送的工作簿版本。 选中后，您可以选择以下选项： |
   | **[!UICONTROL 文件名预览]** <!--should be File name preview --> | 显示导出后文件名的显示方式预览。 |
   | **[!UICONTROL 密码保护工作簿]** | 指定密码以保护导出的文件，以便只有拥有密码的人才能访问它。 <p>密码长度必须至少为8个字符，并且至少包含1个数字和1个特殊字符（如`!`、`@`、`#`和`$`）。</p> |
   | **[!UICONTROL 电子邮件]** | 选择此选项将文件发送到特定电子邮件地址。 有关详细信息，请参阅[通过电子邮件共享计划工作簿](/help/report-builder/schedule-reportbuilder.md)。 |
   | **[!UICONTROL 其他投放]** | 选择此选项将文件发送到云帐户，然后使用如下所述的&#x200B;**[!UICONTROL 帐户]**&#x200B;和&#x200B;**[!UICONTROL 位置]**&#x200B;下拉菜单选择帐户和位置。 |
   | **[!UICONTROL 帐户]** | 选择您想要发送数据的云导出账户。 <p>或者，如果您尚未配置要使用的云帐户，则可以配置一个新帐户：<ol><li>选择&#x200B;[!UICONTROL **添加帐户**]，然后指定以下信息：<ul><li>[!UICONTROL **位置帐户名称**]：指定位置账户的名称。此名称会在创建位置时出现 </li><li>[!UICONTROL **位置账户描述**]：提供帐户的简短描述，以帮助将它与同一帐户类型的其他帐户区分开来。</li><li>**[!UICONTROL 使帐户对贵组织的所有用户都可用]**：选择此选项可允许贵组织中的其他用户使用该帐户。 共享帐户时，请考虑以下事项：<ul><li>无法取消共享您共享的帐户。</li><li>共享帐户只能由帐户的所有者编辑。</li><li>任何人都可以为共享帐户创建位置。</li></ul></li><li>[!UICONTROL **帐户类型**]：选择您要导出到的云帐户类型。 可用的帐户类型为Amazon S3角色ARN、Google Cloud Platform、Azure SAS和Azure RBAC。</li></ul><li>要完成帐户配置，请继续访问下面与您选择的&#x200B;[!UICONTROL **帐户类型**]&#x200B;相对应的链接：<ul><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li></ul></ol> |
   | **[!UICONTROL 位置]** | 在帐户上选择要发送导出数据的位置。<p>或者，如果您尚未配置要在所选帐户上使用的位置，则可以配置一个新位置：<ol><li>选择&#x200B;[!UICONTROL **添加位置**]，然后指定以下信息： <ul><li>[!UICONTROL **名称：**]&#x200B;位置的名称。</li><li>[!UICONTROL **描述**]：提供位置的简短描述，以帮助将它与帐户上的其他位置区分开来。</li><li>**[!UICONTROL 使位置对贵组织的所有用户都可用]**：选择此选项可允许贵组织中的其他用户使用该位置。 共享帐户时，请考虑以下事项：<ul><li>无法取消共享您共享的位置。</li><li>共享位置只能由帐户的所有者编辑。</li><li>仅当与位置关联的帐户也共享时，才能共享位置。</li></ul></li><li>[!UICONTROL **位置帐户**]：选择要在其中创建位置的帐户。</li></ul><li>要完成位置配置，请继续使用下面与您在&#x200B;[!UICONTROL **位置帐户**]&#x200B;字段中选择的帐户类型相对应的链接：<ul><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li></ul> |
   | **[!UICONTROL 显示计划选项]** | 选择此选项可查看用于计划导出的其他选项。 如果只想发送导出一次，请将此选项保留为未选中状态。 取消选择此选项后，将立即启动导出。 |
   | **[!UICONTROL 开始于]** | 计划导出开始的日期和时间。 <p>仅当选择计划导出频率时此选项才可用。</p> |
   | **[!UICONTROL 结束日期]** | 计划导出的到期日期和时间。计划导出在您设置的日期和时间过后不再运行。 <p>仅当选择计划导出频率时此选项才可用。</p> |
   | **[!UICONTROL 频率]** | 您可以将频率设置为每小时、每天、每周、每月或每年的特定日期。例如，您可以设置一个计划，在该月的第一个星期日晚上发送工作簿，这样收件人就会在星期一早上第一时间在收件箱中收到电子邮件。 |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **按计划发送**]&#x200B;以导出工作簿。

   数据会按照您指定的频率发送到您指定的云帐户。

1. （可选）创建导出后，无论您选择立即发送还是按照定义的计划发送，您都可以在[导出页面](/help/components/exports/manage-exports.md)上查看和管理它，并在[导出日志](/help/components/exports/manage-export-logs.md)中查看它。</p>

## 管理导出

在从 Analysis Workspace 导出数据后，您可以编辑、重新导出、复制、标记或删除现有的导出内容，如[管理导出内容](/help/components/exports/manage-exports.md)中所述。

## 导出到云的优势

通过将 Customer Journey Analytics 数据导出到云，您可以：

* 导出到共享位置，如Google Cloud Platform、Microsoft Azure和Amazon S3。

* 存储大量历史数据。

  此类数据可用于检测长期趋势，以获取商业智能，并最终做出更好的商业决策。

* 在导出的 Customer Journey Analytics 数据中加入计算量度。

* 将数据输出组织为连接值。

* 导出一次或按计划。

* 以Excel、PDF或CSV格式导出文件。

* 导出包含多个维的数据块。

## 导出要求 {#export-requirements}

### 最低要求

确保您的数据块、环境和权限满足以下要求：

* **数据块：**&#x200B;所有数据块必须至少包含一个列、行或值的组件。

* **环境：**&#x200B;确保 Customer Journey Analytics 使用的 [IP 地址](/help/technotes/ip-addresses.md)和[域](/help/technotes/domains.md)可以通过其组织的防火墙。
